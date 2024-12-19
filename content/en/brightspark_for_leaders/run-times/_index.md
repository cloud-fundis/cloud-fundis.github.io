---
title: Example of runtimes
description: On this page, you can judge for yourself on the costs savings and performance improvements 
categories: [Examples, Placeholders]
tags: [tests, runs, docs]
weight: 2
---

{{% pageinfo %}}

Real job runs and associated costs.
{{% /pageinfo %}}

In the following example jobs, we used approximately 20GB of S3 Storage Lens data. This encompassed about a years worth of data from a large datalake. We did some transformations of the data (such as anonymising the data) as well as computed averages, means, maxes, etc. 

The jobs were split into a single days worth of data, to a week, a month, 6-months and a years worth of data, each time performing the same jobs on BrightSpark and then on AWS Glue for comparison.

We ran these jobs many times and the graphs represent an average of runtimes.

## 1 days worth of data

This is a small job. It was run on a small BrightSpark t-shirt size (2 vCPU, 8GB RAM containers). For AWS Glue, the job was run with the smallest DPUs available: 2 x G.1X.

The data we used for the tests was about 7.5GB.

![Runtime and cost vs different compute types](/brightspark_for_leaders/run-times/storage-lens-1day-1.png) |![Percentage savings and runtimes when compared with AWS Glue](/brightspark_for_leaders/run-times/storage-lens-1day-2.png) 

| Observations (all observations are relative to AWS Glue) |
| :--- |
| <ul> <li>Fargate spot is the cheapest form of compute, reducing costs by 92%</li><li>However using Fargate spot, compute runtime was only 18% faster than AWS Glue</li><li>iSavings range from $2.1c to $2.2c per job</li><li>Running on EC2, the savings are smaller [red] ($1.8c), however compute time [blue] is considerably faster (>70% performance improvement over AWS Glue)</li></ul> |

| Conclusions |
| :--- |
| <ul><li>If you need your jobs completed fast, choose EC2 or EC2 Spot</li><li>If you want to achive maximum savings, use Fargate or Fargate Spot, but at the expense of speed></li></ul> |

## Prerequisites

Are there any system requirements for using your project? What languages are supported (if any)? Do users need to already have any software or tools installed?

## Installation

Where can your user find your project code? How can they install it (binaries, installable package, build from source)? Are there multiple options/versions they can install and how should they choose the right one for them?

## Setup

Is there any initial setup users need to do after installation to try your project?

## Try it out!

Can your users test their installation, for example by running a command or deploying a Hello World example?
