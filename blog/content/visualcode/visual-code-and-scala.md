---
title: "Visual Code and Scala"
date: 2020-04-29T08:01:37+02:00
draft: false
---

This week I am setting up my new laptop - moving off Mac finally and back onto Linux - YAY.

So one of the things I'm getting working is Visual Code Studio and Scala. Sounds easy doesn't it?

### Step 2
Of course you went for Step 1 which was "aaah, this is easy, just download the extension and you're done. How hard is that Hamish?", so we're starting at Step 2: for when step 1 was a fail.

[Scalameta](https://scalameta.org/metals/) is the extension for Scala on vscode. Install it; but wait, that's not all - there's more.

l. Have you got the correct verion of Java installed?
I installed Java from the Ubuntu repo and while it was 11.0.7-10, it seemed it was giving issues. Despite futsing around with various Metal options, it seemed to not be loading Bloop.

l. Bloop. To the layman (yup, that's me), this is another thing that flummoxed me. It seems it's job is to automagically download the libraries from Maven.

## Step 3
Uninstall java from the Ubuntu repo's and install it via [SdkMan](https://sdkman.io/). That's what the sbt recommends. Do this:

* install sdkman
 * curl -s "https://get.sdkman.io" | bash

* Install Java
 * What I didn't understand was that this installs as your user, not system-wide; which I can see is going to bite me later!
 * sdk list java
 * sdk install java 11.0.7.hs-adpt (no, I don't know what these (_adpt_ and _hs_) things mean yet)
 * Test java: java -version
 * Add JAVA_HOME to your .bashrc
 * Remember to re-run your .bashrc (. ~/.bashrc)

## Step 4
When you open your .scala or .sbt files, Metal should create two directories namely .bloop and .metals. If .bloop is not created, my experience was that this is a Java problem and bloop is not starting up.

* Check by running:

> ps -elf|grep bloop.Server|sed 's/-classpath [^ ]*//g'

Yeah, that classpath stuff just complicates life.

If bloop is not running, revisit the Java version. For this tut, I installed java 11.0.7.hs-adpt as above.

## Final step
Now bloop is running, you're still getting this error:

> INFO  [error] sbt.librarymanagement.ResolveException: Error downloading org.apache.spark:spark-graphx:2.4.4<br/> 
> INFO  [error]   Not found<br/>
> INFO  [error]   Not found<br/>

What I found is that cpying the sbt path from Maven didn't work. What Maven suggested I put in my build.sbt was this (snippet):

> 	libraryDependencies += "org.apache.spark" % "spark-core" % "2.4.4",<br/>
>	libraryDependencies += "org.apache.spark" % "spark-sql" % "2.4.4"<br/>

Which is not a path because it's being searched for here:

> INFO  [error]   not found: /home/hamish/.ivy2/local/org.apache.spark/spark-sql/2.4.4/ivys/ivy.xml<br/>
> INFO  [error]   not found: https://repo1.maven.org/maven2/org/apache/spark/spark-sql/2.4.4/spark-sql-2.4.4.pom<br/>

Which, as you can see, is not found.

A bit of _curl_ing did the trick:

> curl https://repo1.maven.org/maven2/org/apache/spark

showed me that the path was in fact not as I've put it in the dependencies, but rather
```
<a href="spark-core_2.10/" title="spark-core_2.10/">spark-core_2.10/</a>
<a href="spark-core_2.11/" title="spark-core_2.11/">spark-core_2.11/</a>
<a href="spark-core_2.12/" title="spark-core_2.12/">spark-core_2.12/</a>
```

So changing the path in the build.sbt to:

> 	libraryDependencies += "org.apache.spark" % "spark-core_2.12" % "2.4.4",<br/>
>	libraryDependencies += "org.apache.spark" % "spark-sql_2.12" % "2.4.4"<br/>

did the trick.



