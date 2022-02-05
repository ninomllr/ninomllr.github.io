---
title: 'Data Engineering Skills 2022'
date: 2022-02-04T22:42:14+01:00
draft: false
---

One of my tasks at Substring is to always scout for technology trends to find out what technologies help our clients most to reach their target to become Data-driven. The tech field for fats engineers is huge and evolving fast.

I put together a short list of tech skills that I think data engineers in 2022 should master to give as much value to clients as possible. Obviously there is a load of so called soft skills needed as well. Maybe I will do a post about them as well in the future.

🔹Programming / Coding
In the end a data engineer is a highly specialized software engineer. So learn the most important languages to interact with data and data pipelines. If you know python, bash and SQL you will get far already. If you ever encounter someone that tells you SQL is an old language or that it's not useful anymore, just laugh and walk away 🤣

Some important tools like Spark rely heavily on Java and Scala so it can be important that you know this too.

- Basics SQL: https://www.dataquest.io/blog/sql-basics/
- Basics Python: https://www.python.org/about/gettingstarted/

🔹SQL databases
Many systems rely on some sort of SQL based database. Invest some time in SQL based systems like Postgres, Azure SQL, Snowflake others. 

Many developers believe that nowadays everything is about NoSQL because "it's more scalable" or "it's the way to go with big data". While this might be true, it is also quite difficult to handle transactions and consistency in data with systems like this. Not everything that starts cheaper and faster in the beginning stays like that in the long run. 🤔 Most OLTP systems and transactional data systems should and will still use an RDBMS system, so prepare for this.

🔹Cloud & Kubernetes
Learn the basics about K8s as you will need to use it a lot to run data pipelines. If you are a beginner just tinker aroune with minikube on your local computer. Later decide to learn about how to work with one of the big cloud providers AWS, Azure and GCP. I personally prefer Azure because they have a great integration of tools like Apache Databricks, MLFlow and other stuff that I need regularly. 

In the end I would choose based on who your target clients are. Swiss SMEs work with Azure, because they are used to work with Microsoft and trust in Google and Amazon is lower. Startups use AWS because it is a bit cheaper for smaller workloads.

- Learn Kubernetes: https://kubernetes.io/docs/tutorials/kubernetes-basics/

🔹NoSQL
If you get into the big data field, it's necessary to learn about NoSQL databases. Now, there are multiple types of NoSQL databases, some of them are highly available and some of them are highly consistent. Some are column-based, some are document-based and some are graph-based.

I recommend to try and learn about a couple of them:
- MongoDB (https://www.mongodb.com/)
- Cassandra (https://cassandra.apache.org/_/index.html)
- ElasticSearch (https://www.elastic.co/)
- Azure Cosmos DB (https://azure.microsoft.com/en-us/services/cosmos-db/#overview)
- neo4j (https://neo4j.com/)

Just run them locally on your docker and tinker around. You can find a couple of docker files for them here https://github.com/irbigdata/data-dockerfiles

🔹Data Warehousing
Learn about data warehouses and how to store data in them and systems of storing data like Kimball, Data Vault 2.0 or others. Learn about slowly changing dimensions, ELT, ETL and other concepts around DWHs.

- Data Vault 2.0: https://datavaultalliance.com/about/what-is-datavault/
- Kimball: https://www.astera.com/type/blog/data-warehouse-concepts/#The-Kimball-Method
- Inmon: https://www.astera.com/type/blog/data-warehouse-concepts/#The-Inmon-Method

🔹dbt
If you are in the data space I definitely recommend to learn dbt, as it helps you to create reliable and reproducable data transformations

- dbt: https://www.getdbt.com/

🔹Apache Spark
Apache Spark is the most effective data processing framework in enterprises today. Almost all companies that I encountered that have big data projects use Spark in one way or the other.
While Apache Sparks "native" language is Scala it works with python too. Performance is a bit less, but it integrates a lot easier with the rest of your data pipeline projects through using the same language. Spark is also capable of running SQL commands, which is pretty cool as well.

- PySpark: https://intellipaat.com/blog/tutorial/spark-tutorial/pyspark-tutorial/
- Learn Spark: https://sparkbyexamples.com/

🔹Databricks & Delta
Databricks combines the best of the DWH with the Data lake world. One of the big advantages in my eyes is that you can handle multiple types of data like unstructured and structured data in one plattform which makes overhead a lot smaller.

- Read more: https://databricks.com/

🔹Apache Kafka
If you need to work with data streaming I recommend to look at Apache Kafka. If you are using Azure Cloud you can also use Azure Event Hub, as it also offers support for Kafka Consumer and Producer API.

- What, when and why to use Kafka: https://www.startdataengineering.com/post/what-why-and-how-apache-kafka/
- Getting Started: https://kafka.apache.org/quickstart
- .NET and Kafka: https://github.com/kunwarshesh/Start-with-Kafka-DotNetCore

What other technical skills are needed as a data engineer? Please let me know in the comments 📩

