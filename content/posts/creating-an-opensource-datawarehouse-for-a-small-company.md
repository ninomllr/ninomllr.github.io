---
title: 'Creating an Opensource Datawarehouse for a Small Company'
date: 2022-01-05T22:42:14+01:00
draft: true
---

In my company [Substring - The Data Company](https://substring.ch) we decided to become more data-driven and wanted to set up a simple data warehouse for our every day business. We decided to set up everything with open source software and wanted to host it in our own Kubernetes cluster.

# Open source DWH stack

Our stack for this data warehouse is quite simple:

## Data Ingestion

[Meltano](https://meltano.com)

## Data Persistence

While [PostgreSQL](https://www.postgresql.org/) might not be the classical choice for a data warehouse, I think that it works quite well for our use case and most people with data in the millions but not in the billions. You can read more about [using PostgreSQL as a data warehouse](https://www.narrator.ai/blog/using-postgresql-as-a-data-warehouse/). Interesting extensions like [citus](https://github.com/citusdata/citus) allow PostgreSQL vertical scaling now, which will make it fit for bigger use cases as well.

## Data Transformation

[dbt](https://getdbt.com)

## Data Visualisation

[Superset](https://superset.apache.org)

## Job Orchestrator

[Gitlab](https://gitlab.org)
[microk8s](https://microk8s.org)

# Setting up the ingestion

# Setting up the data transformation

# Running the pipelines regularly
