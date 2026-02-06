# Airline-Data-Ingestion-Incrementally

Tech Stack: Python (PySpark/Boto3), SQL, AWS S3, AWS Glue, AWS Glue Crawler, AWS Glue Catalog, AWS Redshift, AWS Step Functions, AWS EventBridge, AWS SNS

# Project Overview

This project demonstrates a serverless, event-driven ETL pipeline for ingesting daily flight data into AWS Redshift. The pipeline leverages incremental processing with AWS Glue Job Bookmarking and orchestrates tasks with AWS Step Functions, ensuring real-time, reliable, and production-ready datasets.
The system integrates SNS notifications for monitoring job success/failure and EventBridge triggers to automate workflow execution.

# Features

1. Incremental ingestion of daily flight data and airport codes into Redshift.

2. Automated data cataloging using AWS Glue Crawlers for schema management.

3. Orchestrated ETL workflow with Step Functions and EventBridge triggers.

4. Real-time monitoring and alerting through AWS SNS.

5. Optimized for reliability, scalability, and minimal manual intervention.

# Pipeline Workflow

Data Upload:

Place airport_codes and daily flight data in S3 buckets.

Table Setup:

Pre-load airport_codes into Redshift.

Create target schema for daily flights.

Data Cataloging:

Use AWS Glue Crawler to register S3 and Redshift tables in Glue Catalog.

Incremental ETL Processing:

Run AWS Glue PySpark jobs to process daily flight data incrementally using Job Bookmarking.

Orchestration:

Use AWS Step Functions to manage the ETL workflow and handle dependencies.

Trigger Step Functions automatically via EventBridge notifications.

Monitoring & Alerts:

Configure AWS SNS for job success/failure notifications to ensure reliability.
