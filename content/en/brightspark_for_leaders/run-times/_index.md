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

## 1 day's worth of data

This is a small job. It was run on a small BrightSpark [t-shirt size](/brightspark_for_leaders/concepts#T-shirt-sizes) size (2 vCPU, 8GB RAM containers). For AWS Glue, the job was run with the smallest DPUs available: 2 x G.1X.

The data we used for the tests was about 7.5GB.

![Runtime and cost vs different compute types](/brightspark_for_leaders/runtime_results/storage-lens-1day-1.png) ![Percentage savings and runtimes when compared with AWS Glue](/brightspark_for_leaders/runtime_results/storage-lens-1day-2.png) 

| Observations (all observations are relative to AWS Glue) |
| :--- |
| <ul> <li>Fargate spot is the cheapest form of compute, reducing costs by 92%</li><li>However using Fargate spot, compute runtime was only 18% faster than AWS Glue</li><li>Savings range from $2.1c to $2.2c per job</li><li>Running on EC2, the savings are smaller [red] ($1.8c), however compute time [blue] is considerably faster (>70% performance improvement over AWS Glue)</li></ul> |

| Conclusions |
| :--- |
| <ul><li>If you need your jobs completed fast, choose EC2 or EC2 Spot</li><li>If you want to achive maximum savings, use Fargate or Fargate Spot, but at the expense of speed</li></ul> |

## 1 week's worth of data

This is a medium job. It was run on a medium BrightSpark [t-shirt size](/brightspark_for_leaders/concepts#T-shirt-sizes) (2 vCPU, 8GB RAM containers). For AWS Glue, the job was run with the smallest DPUs available: 2 x G.1X.

The data we used for the tests was about 7.5GB.

![Runtime and cost vs different compute types](/brightspark_for_leaders/runtime_results/storage-lens-1week-1.png) ![Percentage savings and runtimes when compared with AWS Glue](/brightspark_for_leaders/runtime_results/storage-lens-1week-2.png) 

| Observations (all observations are relative to AWS Glue) |
| :--- |
| <ul> <li>Fargate spot is the cheapest form of compute, reducing costs by 95%</li><li>Fargate and Fargate spot, compute runtime has a 35% performance improvement over AWS Glue</li><li>Savings range from $2.6c to $2.9c per job</li><li>Running on EC2, the savings are smaller [red] ($2.1 to 2.2c), however compute time [blue] is considerably faster (>80% performance improvement over AWS Glue)</li></ul> |

| Conclusions |
| :--- |
| <ul><li>If you need your jobs completed fast, choose EC2 or EC2 Spot</li><li>If you want to achive maximum savings, use Fargate or Fargate Spot, but at the expense of some speed over EC2</li></ul> |

## 1 month's worth of data

This is a large job. It was run on a large BrightSpark [t-shirt size](/brightspark_for_leaders/concepts#T-shirt-sizes) (2 vCPU, 8GB RAM containers). For AWS Glue, the job was run with the smallest DPUs available: 2 x G.1X.

The data we used for the tests was about 15GB.

![Runtime and cost vs different compute types](/brightspark_for_leaders/runtime_results/storage-lens-1month-1.png) ![Percentage savings and runtimes when compared with AWS Glue](/brightspark_for_leaders/runtime_results/storage-lens-1month-2.png) 

| Observations (all observations are relative to AWS Glue) |
| :--- |
| <ul> <li>Fargate spot is the cheapest form of compute, reducing costs by 83%. However, choosing this option shows a drastic performance degradation for this larger dataset</li><li>Both Fargate and Fargate spot, compute runtime has degraded significantly over AWS Glue</li><li>Savings are maximized at $3.4c but choosing savings over runtime is not advised</li><li>Running on EC2, the savings are smaller [red] ($2.2 to 2.3c), however compute time [blue] is consistently faster (>57% performance improvement over AWS Glue)</li></ul> |

| Conclusions |
| :--- |
| <ul><li>For larger jobs, don't choose Fargate. Instead choose EC2</li><li>If you need your jobs completed fast, choose EC2 or EC2 Spot</li><li>If you want to achive maximum savings, use Fargate or Fargate Spot, but at the expense of some speed over EC2</li></ul> |

## 6 months worth of data

This is a large job. It was run on a large BrightSpark [t-shirt size](/brightspark_for_leaders/concepts#T-shirt-sizes) (2 vCPU, 8GB RAM containers). For AWS Glue, the job was run with the smallest DPUs available: 2 x G.1X.

The data we used for the tests was about 15GB.

![Runtime and cost vs different compute types](/brightspark_for_leaders/runtime_results/storage-lens-6month-1.png) ![Percentage savings and runtimes when compared with AWS Glue](/brightspark_for_leaders/runtime_results/storage-lens-6month-2.png) 

| Observations (all observations are relative to AWS Glue) |
| :--- |
| <ul> <li>Using Fargate is both more expensive than AWS Glue and performs significatly worse too. We strongly advise that you choose only EC2 for all your compute at this (or larger) size data</li><li>Fargate spot is not much better (cheaper, but still terrible performance!)</li><li>Savings are maximized at $7.3c by using EC2 spot</li><li>Running on EC2, the compute time [blue] is consistently faster (>73% performance improvement over AWS Glue)</li></ul> |

| Conclusions |
| :--- |
| <ul><li>For larger jobs, don't choose Fargate. Instead choose EC2</li><li>If you need your jobs completed fast, choose EC2 or EC2 Spot</li></ul>

## 1 year's worth of data

This is a extra-large job. It was run on a extra-large BrightSpark [t-shirt size](/brightspark_for_leaders/concepts#T-shirt-sizes) (2 vCPU, 8GB RAM containers). For AWS Glue (Flex), the job was run with the smallest DPUs available: 2 x G.1X.

The data we used for the tests was about 15GB.

![Runtime and cost vs different compute types](/brightspark_for_leaders/runtime_results/storage-lens-1year-1.png) ![Percentage savings and runtimes when compared with AWS Glue](/brightspark_for_leaders/runtime_results/storage-lens-1year-2.png) 

| Observations (all observations are relative to AWS Glue - Flex in this case) |
| :--- |
| <ul> <li>Using Fargate is both more expensive than AWS Glue and performs significatly worse too. We strongly advise that you choose only EC2 for all your compute at this (or larger) size data</li><li>Fargate spot is not much better (cheaper, but still terrible performance!)</li><li>Savings are maximized at $4.3c by using EC2 spot</li><li>Running on EC2, the compute time [blue] is consistently faster (>67% performance improvement over AWS Glue Flex)</li></ul> |

| Conclusions |
| :--- |
| <ul><li>For larger jobs, don't choose Fargate. Instead choose EC2</li><li>If you need your jobs completed fast, choose EC2 or EC2 Spot</li><li>It is still preferebable to use BrightSpark over using AWS Glue Flex</li></ul>
