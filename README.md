LibraPulse: Scalable Library Pipeline with PySpark

An end-to-end Data Engineering platform for processing, validating, storing, and analyzing 
continuous library transaction and borrowing data at scale.

Overview:
LibraPulse is a distributed data processing and streaming analytics platform designed to 
handle high-volume, continuously generated library data with minimal latency.

The system collects raw library operational events from multiple sources such as checkout logs, 
member registration records, digital catalog metadata, and university administrative APIs. 
These events are processed and transformed using PySpark, validated for data quality, 
stored using scalable storage technologies, and analyzed for circulation patterns and reporting.

The platform combines distributed data engineering with advanced analytics to convert raw, 
unstructured transactional logs into clean, reliable, and actionable library intelligence.

Problem Statement:

Modern academic and public library systems continuously generate massive volumes of 
checkout logs, member records, and catalog updates across distributed databases.

Traditional relational databases and legacy batch-processing systems struggle with high 
throughput, introducing significant delays and making real-time circulation monitoring difficult.
Raw library datasets often contain:

Missing ISBNs or book metadata  
Duplicate checkout records  
Schema inconsistencies across branches  
Malformed borrowing date/time formats  
Untracked overdue and inventory anomalies

LibraPulse addresses these challenges by providing an integrated pipeline for end-to-end 
data ingestion, distributed transformation, quality validation, and real-time dashboarding.

Objectives:
Build a scalable, low-latency library data processing pipeline using PySpark. 
Efficiently process large volumes of book, member, and checkout data across distributed storage.  
Perform automated data cleaning, deduplication, and schema enforcement.  
Identify borrowing trends, peak checkout hours, most active members, and highly requested genres.  
Store processed analytical data in a central, structured data store for rapid querying.  
Provide interactive monitoring dashboards for library administrators and faculty.  
Build a modular and containerized Medallion Data Architecture (Bronze, Silver, Gold).  

Proposed Solution:
LibraPulse provides an end-to-end data pipeline consisting of multiple architecture stages:

1. Data Ingestion (Bronze Layer)
Python data generation scripts and event hooks ingest raw checkout logs (JSON) and book catalog metadata (CSV) into containerized staging storage.

2. Stream & Batch Processing (Silver Layer)
PySpark and Spark Structured Streaming clean missing values, strip duplicate transactions, standardize date formats, and enforce strict type schemas.

3. Data Quality & Orchestration
Apache Airflow orchestrates workflow schedules and triggers processing DAGs inside Docker environments to ensure consistent pipeline execution.

4. Storage & Aggregation (Gold Layer)
Processed datasets and aggregated analytics are written to high-performance storage:
Parquet / S3: Efficient analytical file storage for historical records.
PostgreSQL / Amazon Redshift: Structured persistence for production queries and reporting.

5. Analytics & Visualization
Power BI and Metabase connect directly to the Gold database layer to serve interactive
operational dashboards for circulation metrics and inventory demand.



Workflow Explanation:
1) Library interaction logs and checkout events are generated continuously from distributed campus systems.
2) Raw data is ingested in batch/stream formats into the Bronze landing zone.
3) PySpark transformation pipelines process the records, handling missing values and duplicate checkouts.
4) Apache Airflow schedules and monitors pipeline execution within Docker containers.
5) Cleaned, aggregated metrics are written to the Gold storage layer in PostgreSQL and Amazon Redshift.
6) Power BI dashboards render real-time circulation reports, top borrowed genres, and active member statistics.

Workflow Summary:
Collect → Process → Validate → Store → Aggregate → Serve → Monitor

Key Features:
1) Distributed ingestion of high-volume library transactional logs  
2) Automated data cleansing, deduplication, and schema standardization using PySpark  
3) Medallion Architecture (Bronze → Silver → Gold) for data reliability  
4) Orchestrated pipeline DAGs managed via Apache Airflow  
5) Centralized storage integration with PostgreSQL and AWS Redshift  
6) Active member profiling and popular book demand forecasting  
7) Interactive visual reporting via Power BI and Metabase dashboards  
8) Full containerization using Docker for reproducible deployment

Novelty:
The main novelty of LibraPulse lies in its end-to-end integration of distributed big-data processing with a Medallion Architecture specifically tailored for academic library systems.  
Rather than relying on traditional SQL batch scripts or single-node relational databases, LibraPulse unifies:
Distributed Ingestion + PySpark Medallion Pipeline + Automated Airflow Orchestration + Redshift Storage + Real-Time BI Dashboards  
The novelty is primarily architectural and operational, transforming legacy library reporting into a scalable, automated data engineering platform.

Expected Outcomes:
Accelerated processing of high-volume library transactions via PySpark.  
Increased data quality through automated deduplication and cleansing.  
Clear insights into top-borrowed titles, peak checkout times, and inactive inventories.  
Robust centralized storage supporting fast complex reporting queries.  
Automated pipeline orchestration removing the need for manual ETL runs

Future Scope:
Integration of predictive machine learning models for book recommendation systems.  
Automated alerting for overdue anomalies and stock replenishment thresholds.  
Real-time streaming integration with Apache Kafka for live checkout feeds.  
Cloud-native serverless deployment on AWS Glue. 

Team: Adhithya-2420030571, Teja-2420030737, Vivek-2420030350

Project Guide:
Dr. N. Shirisha, Associate Professor

Academic Information
Course: Fundamentals of Data Engineering (FDE) | Course Code: 24DEA3101 | Academic Year: 2026–2027

Project Focus:
LibraPulse: Scalable Library Pipeline with PySpark.
Transforming raw, scattered library transactions and member 
activity into clean, structured, and actionable intelligence 
through PySpark data engineering pipelines.
