---
title: Overview
description: BrithSpark - a continerized compute engine for all your needs.
weight: 1
---

{{% pageinfo %}}

BrightSpark is a compute engine that combines AWS Elastic Container Service and AWS Elastic Kubernetes Service fronted by APIs. 

{{% /pageinfo %}}

BrightSpark is a cost-effect, fully managed compute engine. It is ideal replacement for traditional compute engines for tasks such as processing large volumnes of data, running machine learning or handling incoming streaming data. It is built entirely on containers to allow maximum flexibility for the developer.

Try answering these questions for your user in this page:

## What is it?

It's a compute engine, controlled by APIs. It runs in your company account to keep data secure thereby offering your organisation a wide range of capabilities of compute. Whether you want to optimize for cost, or improve speed, BrightSpark offers your development teams a variety of options, from running on AWS Fargate to EC2. All this without your teams needing to manage any of the infrastructure.

Now they don't have to worry about Kubernetes, AWS EMR clusters, AWS Glue or any other engine - they can simply tell BrightSpark their job-name, provide parameters and submit the job to run. BrightSpark handles all the complexity to make the compute happen.

Best of all, built into BrightSpark is all the management reporting you need as a leader. Questions such as:

* "How much have these jobs cost the organisation over the last 7 days?",
* "What are the most expensive jobs we're currently running?", or
* "Over the lifespan of these 20 jobs, how much have they cost and what is the least efficient job?"

All of this is built into BrightSpark at no extra cost to you.

## Why do I want it?

Compute cost is the biggest driving factor for most organisations and it is getting worse as companies drive more Machine Learning, Generative AI and other data driven requirements. BrightSpark aims to reduce these costs for the customer.

What problems does it solve?

- **Cost**: AWS costs are driving up organisational costs and with everything in the cloud, many companies didn't bargin on their compute costs being this high. We see anywhere between 50% and 90% savings over jobs running on AWS Glue.

- **Ease**: Most engineering organsations - especially in the data engineering world - are constantly striving to reduce complexity. Data and machine learning pipelines, data scientists notebooks, job development all add significant complexity. BrightSpark's API first approach, simplifies these by ensuring engineers can worry about their code. BrightSpark takes care of where that code runs, how it's reported and the costs associated with the runs.

- **Speed**: Depending on the compute option that's chosen, BrightSpark jobs can be optimised for cost or speed - sometimes both. If the developer chooses speed, they can run the jobs on EC2 without having to manage ANY EC2 instances. Alternatively, they may choose to run the jobs on Fargate - sacrificing speed for sometimes, astonishingly reduced cost.

- **Versitlity**: If you implement BrightSpark, it's implemented for the whole organisation. Since BrightSpark runs in your account, you data are secure - never leaving your organisation. What this means is that whether you're a data engineer in the platform space, or a data scientist in the descision space, all your engineers can use BrightSpark and take advantage of the cost savings.

- **Diverity**: Compute engines are good for so many things, whether you're dealing with Jupyter Notebooks, heavy-duty Apache Spark, intense Python compute, or needing to manage moving files to AWS Glacier Deep Archive, you can use the same compute engine across your organisation for a variey of jobs.

- **Reporting/management**: Built into every BrightSpark job is reporting. In fact it's not been added as an afterthought, it was built with management in mind from day one. We believe that reporting goes beyond reporting on a single job. We allow our customers to tag jobs with multiple tags and report based on those tags. An example may be: The marketing department requires 3 or 4 jobs to make up a campaign. Those different jobs can be tagged with the same campaign tag and later, they can pull a report showing the costs of the campaign. Equally, the engineer may want to investigate the slowest running jobs to apply improvements. This sort of reporting is built into BrightSpark.

## So what can't it do?
- **What is it good for?**: As of today, it can handle Python jobs - a direct replacement for running those jobs on AWS Glue.

- **What is it not good for?**: Scala is currently not supported for our automated code changes, so if you have a Scala job, you would need to make changes in your code to allow it to run on BrightSpark.

- **What is it _not yet_ good for?**: Two feature that many customers are wanting are some method of handling data quality and data lineage. To address those, we're in the process of building [Apache Expectations](https://github.com/Nike-Inc/spark-expectations) and [Spline](https://github.com/AbsaOSS/spline) into BrightSpark to allow customers to address these two significant data processing challenges.

Unlike other companies, we like to keep things simple. As a result we're not adding loads of overhead to the product that you may never use. Without those complexities, you don't have to pay for "features" you never use!

## Where should I go next?

Run-time graphs of cost savings.

- [Example run-time graphs](/docs/run-times/): Runtimes for jobs on $project
- [Getting Started](/docs/getting-started/): Get started with $project
- [Examples](/docs/examples/): Check out some example code!
