---
title: 'Creating an Opensource Datawarehouse for a Small Company'
date: 2022-01-11T18:23:14+01:00
draft: false
---

In my company [Substring - The Data Company](https://substring.ch) we decided to become more data-driven and wanted to set up a simple data warehouse for our every day business. We decided to set up everything with open source software and wanted to host it in our own Kubernetes cluster.

# Open source DWH stack

Our stack for this data warehouse is quite simple:
![Open source DWH stack](/data-warehouse-architecture.drawio.png)

## Data Ingestion

[Meltano](https://meltano.com) has made Data ingestion for many SaaS applications a hell lot easier. What I personally like a lot about it, is the fact that installation and configuration is basically a no brainer and it works perfectly well on the console, K8s, in pipelines or whatever orchestrator you wish to use. Meltano originated at Gitlab and has a super helpful community. Basically it's a wrapper for [Singer.io](https://singer.io) taps which is a great open source project by itself and it offers connectors to many of the tools that we want data from already.

## Data Persistence

While [PostgreSQL](https://www.postgresql.org/) might not be the classical choice for a data warehouse, I think that it works quite well for our use case and most people with data in the millions but not in the billions. You can read more about [using PostgreSQL as a data warehouse](https://www.narrator.ai/blog/using-postgresql-as-a-data-warehouse/). Interesting extensions like [citus](https://github.com/citusdata/citus) allow PostgreSQL vertical scaling now, which will make it fit for bigger use cases as well.

## Data Transformation

We are looking for a Headless BI approach where all the metrics are already pre-calculated in the DWH. One of the best tools to create reliable and reusable SQL code is [dbt](https://getdbt.com) which allows us to build models for various different sources, outputs, metrics and more. Everything is run over the command line and can thus be scheduled with Gitlab CI easily. What I like about dbt is the additional features like data quality tests, seeding, snapshots and more that we can use un the future.

## Data Visualisation

I was quite unsure if we should go with [Apache Superset](https://superset.apache.org) or Metabase on this one, as I like both. I decided to use Superset, because it feels like it offers a bit more features. I think one of the main reasons why Metabase is awesome is that it helps you to create reports even if you don't know SQL. As we are a team full of data engineers I don't think not knowing SQL will ever be a problem for us.

## Job Orchestrator

The whole data pipeline code is hosted on [Gitlab](https://gitlab.org), which is able to run K8s pods through Gitlab Runners running on our
[microk8s](https://microk8s.org) Cluster. This means we can just configure Gitlab CI to schedule our ingestion and transformation pipeline.

# About this series

So in this series of short blog posts I will walk you through all the necessary steps to create your own minimal Headless BI and how we added [Gitlab](https://github.com/MeltanoLabs/tap-gitlab) and [Bexio](https://github.com/substringgmbh/bexio.net) data to our pipeline, how we transform it and how to display it in Apache Superset. Oh and obviously on how to write your own Meltano tap, as we had to create our own loader for Bexio.

- Setting up the data ingestion (upcoming)
- Setting up the data transformation (upcoming)
- Running the data pipelines regularly (upcoming)
- Writing your own Meltano Tap (upcoming)
- Creating a visualization layer with Apache Superset (upcoming)
