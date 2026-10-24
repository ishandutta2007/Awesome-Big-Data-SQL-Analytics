# Awesome-Big-Data-SQL-Analytics

# Awesome-Big-Data-SQL-Analytics

## Top Big Data SQL Analytics Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Distributed Query Engines, Lakehouse Analytics & Self-Hosted SQL Federation*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Big Data SQL Analytics**. These tools enable organizations to query massive datasets across data lakes, warehouses, and federated sources using SQL—ranging from cloud-native managed warehouses to open-source distributed query engines that run on your own infrastructure.



**Examples** include Snowflake, Google BigQuery, Amazon Redshift, Databricks SQL, Starburst Galaxy, Dremio, Trino, ClickHouse, and Apache Spark (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, avoiding per-query or per-credit SaaS fees, and controlling the analytics pipeline. The open-source landscape is anchored by **Trino** (the distributed SQL federation standard), **ClickHouse** (the columnar OLAP speed champion), **Apache Spark** (the unified batch/stream/SQL engine), and **DuckDB** (the in-process analytical database), with **Apache Iceberg** providing the open table format layer that connects them all.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## Sector Overview & Market Dynamics

The global big data SQL analytics and lakehouse market is estimated at **$11.66 billion in 2026** and projected to reach **$28.04 billion by 2034** (CAGR ~11.59%). The sector is **moderately to highly fragmented** rather than winner-take-all: no single vendor holds a monopoly because enterprise architectures routinely combine hyperscaler managed warehouses (BigQuery, Redshift), dedicated cloud data platforms (Snowflake, Databricks), and open-source distributed engines (Trino, ClickHouse, DuckDB) across multi-cloud environments. Compute has decoupled from storage around open table formats like Apache Iceberg, preventing total vendor lock-in.

## SaaS/Hosted Platforms

| Product | Description | Pricing | Free Tier Limit | Company Size (Revenue/Valuation) |
| :--- | :--- | :--- | :--- | :--- |
| **[Amazon Redshift](https://aws.amazon.com/redshift/)** | Provisioned or Serverless data warehouse on AWS. | **Serverless**: **$0.375/RPU-hour** (US East). **RA3.4xlarge**: $3.26/node-hour. | **$300 Serverless credits** valid for **90 days**. Free trial only (no permanent free tier). | **AWS (Amazon)**: **$128.7B annual revenue** (2025). |
| **[Google BigQuery](https://cloud.google.com/bigquery)** | Serverless data warehouse with on-demand or slot-based capacity. | **On-demand**: **$6.25 per TiB scanned** (Standard Edition: $0.04/slot-hour). | **Permanent Free Tier**: **1 TiB scanned/month** + **10 GB active storage/month**; Sandbox mode available with no credit card required. | **Google Cloud (Alphabet)**: **$70B+ annual revenue run-rate** (2025–2026). |
| **[Databricks SQL](https://www.databricks.com/)** | Lakehouse SQL warehouse built on Spark and Delta Lake. | **SQL Warehousing**: **$0.22/DBU** (Serverless SQL Warehouse: **$0.70/DBU**). Total compute cost ~2–3x DBU with cloud infra. | **14-day free trial** with full platform capabilities. Free trial only (no permanent free tier). | **Private**: **$190B valuation**, **$7B+ annual revenue run-rate** (2026). |
| **[Dremio Cloud](https://www.dremio.com/)** | Lakehouse query engine with semantic layer and Arrow-based acceleration. | **Standard Pay-As-You-Go**: **$0.20 per DCU** (Dremio Compute Unit) per hour (e.g. Small engine = 64 DCUs/hr = $12.80/hr). | **Permanent Free Tier (Standard)**: Up to **10 users**, capped engine sizes, up to 200 tables & 1,000 views. No time limit. | **SAP (Acquired)**: Parent revenue **€36.8B (~$40B)**; Dremio peak standalone valuation was **$2B** (~$50M–$66M ARR). |
| **[Snowflake](https://www.snowflake.com/)** | Cloud data warehouse with decoupled compute/storage and multi-cluster scaling. | **Standard Edition**: **$2.00/credit** (~$226/mo for 1 Medium warehouse running 8 hrs/day + 2 TB storage). Enterprise: **$3.00/credit**. | **30-day free trial** with **$400 in free usage credits**. Free trial only (no permanent free tier). | **Public (NYSE: SNOW)**: **$4.68B annual revenue** (FY2026). |
| **[Starburst Galaxy](https://www.starburst.io/)** | Managed Trino service for lakehouse analytics and federation. | **Pro**: **$0.50/credit**. **Enterprise**: **$0.75/credit**. **Mission-Critical**: **$1.00/credit**. | **Permanent Free Tier**: **3 concurrent clusters**, standard execution mode, free forever; plus **30-day trial with $500 compute credits**. | **Private**: **$3.35B valuation** (Series D), **$100M+ ARR**. |

## Open-Source GitHub Projects



- **[Apache Spark](https://github.com/apache/spark)** [![GitHub Stars](https://img.shields.io/github/stars/apache/spark?style=social&color=white)](https://github.com/apache/spark/stargazers)  

  **The unified distributed analytics engine.** ~40k+ stars. Handles batch, streaming, machine learning, and graph processing with SQL via Spark SQL. **Strengths**: the most mature distributed data processing framework; massive ecosystem; runs on Hadoop, Kubernetes, and standalone clusters. **Trade-offs**: JVM-based with higher memory overhead than native engines; benchmark data shows native/vectorized engines like DuckDB and ClickHouse achieve order-of-magnitude lower runtimes on single-node workloads. Best for organizations already invested in the Spark ecosystem and needing unified batch/stream/ML pipelines.



- **[Trino](https://github.com/trinodb/trino)** [![GitHub Stars](https://img.shields.io/github/stars/trinodb/trino?style=social&color=white)](https://github.com/trinodb/trino/stargazers)  

  **The distributed SQL federation standard.** ~11k+ stars. Queries data across heterogeneous sources (Hive, Iceberg, PostgreSQL, Kafka, S3) without data movement. **Strengths**: massively parallel processing architecture, cost-based optimizer, and broad connector ecosystem. **Trade-offs**: JVM-based with higher latency than native engines; benchmark shows Velox-accelerated Presto outperforms Trino on single-node TPC-H. Best for federated analytics across disparate data sources without consolidation.



- **[ClickHouse](https://github.com/ClickHouse/ClickHouse)** [![GitHub Stars](https://img.shields.io/github/stars/ClickHouse/ClickHouse?style=social&color=white)](https://github.com/ClickHouse/ClickHouse/stargazers)  

  **The columnar OLAP speed champion.** ~40k+ stars. Native C++ engine with vectorized execution, designed for real-time analytics on massive datasets. **Strengths**: near-linear scaling on single-node benchmarks; among the fastest engines for TPC-H workloads. Best for real-time dashboards, log analytics, and high-throughput OLAP where raw query speed matters most.



- **[DuckDB](https://github.com/duckdb/duckdb)** [![GitHub Stars](https://img.shields.io/github/stars/duckdb/duckdb?style=social&color=white)](https://github.com/duckdb/duckdb/stargazers)  

  **The in-process analytical database.** **~36,510 stars** . Embedded OLAP engine with no server to manage—runs inside your application like SQLite for analytics. **Strengths**: native/vectorized execution delivers order-of-magnitude better performance than JVM engines on single-node workloads. Best for local analytics, data science workflows, and lightweight ETL without cluster infrastructure.



- **[Apache Iceberg](https://github.com/apache/iceberg)** [![GitHub Stars](https://img.shields.io/github/stars/apache/iceberg?style=social&color=white)](https://github.com/apache/iceberg/stargazers)  

  **The open table format standard.** **~9,138 stars** . Provides transactional consistency and schema evolution for huge analytic datasets in cloud storage, with a REST catalog interface enabling interoperability across compute engines. **Strengths**: lets Trino, Spark, Flink, and Snowflake query the same tables—decoupling storage from compute. Best as the foundational table format layer for any lakehouse architecture.



- **[Materialize](https://github.com/MaterializeInc/materialize)** [![GitHub Stars](https://img.shields.io/github/stars/MaterializeInc/materialize?style=social&color=white)](https://github.com/MaterializeInc/materialize/stargazers)  

  **The streaming SQL database.** ~6k+ stars. Continuously ingests live data from Kafka, Redpanda, PostgreSQL, and MySQL, incrementally maintaining materialized views. **Strengths**: PostgreSQL-compatible wire protocol means existing BI tools work unchanged; real-time analytics without batch delays. Best for operational analytics requiring sub-second freshness.



### Additional Strong Open-Source Options



- **Apache Doris** — Real-time analytical database with vectorized execution. Best for high-concurrency dashboard workloads.

- **StarRocks** — Analytical database with cost-based optimizer and lakehouse federation. Best for unified lakehouse analytics without Trino's JVM overhead.

- **Apache Druid** — Real-time analytics database for event-driven data. Best for user-facing analytics with sub-second latency.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- **SaaS pricing is workload-dependent and often misleading at list rates**: Snowflake's $226/mo example is for light usage; enterprise scenarios reach $25,000–$40,000/mo. Redshift Serverless at $0.375/RPU-hour looks cheap until you model sustained query volume.

- **Free tiers are for evaluation, not production**: Snowflake offers $400 trial credits; Redshift offers $300 for 90 days; Databricks offers 14 days. Only Starburst Galaxy offers a **permanent free tier** with 3 clusters.

- **Benchmark performance depends on architecture**: native/vectorized engines (ClickHouse, DuckDB) dramatically outperform JVM-based engines (Spark, Trino) on single-node workloads, but distributed engines scale horizontally when data exceeds one machine.

- **Iceberg is the quiet standard**: regardless of which query engine you choose, adopting Apache Iceberg for table storage ensures you can switch engines later without rewriting data pipelines.

- **Dremio was acquired by SAP in May 2026**; its standalone roadmap may change under SAP ownership .



---



**Made for data engineers, analytics architects, and organizations building scalable SQL analytics pipelines.**  

Let's make big data SQL analytics more open, performant, and vendor-agnostic.
