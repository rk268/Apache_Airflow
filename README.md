
# Reddit Data Pipeline Project Using Apache Airflow and AWS Services

![Architecture Diagram](https://drive.google.com/uc?id=17uObEhtCD_jXBvQCGoZsWw-FhEEHlKcN)

## Project Overview
This project is a full end-to-end data pipeline designed to extract data from Reddit, process it using Apache Airflow, and move it through various AWS services for storage, querying, and analytics. The final output is a clean, structured data source that can be visualized and analyzed through Redshift and Chartbot dashboards.

The core idea was to automate Reddit data ingestion and set up a cloud-native architecture that supports scalable, reliable data processing and real-time monitoring.

## What I Built

- **Reddit Application Integration:** Created a Reddit Developer Application to securely access Reddit API using client ID, secret, and user agent.
- **Apache Airflow Environment:** Set up an Airflow environment using CeleryExecutor backed by PostgreSQL, fully containerized with Docker Compose. Managed tasks across Webserver, Scheduler, Workers, and Metadata Database.
- **Dockerization:** Built and orchestrated multiple Docker containers for Airflow components. Managed environment variables using `.env` files, custom `docker-compose.yml` files, and organized Python dependencies with `requirements.txt`.
- **Airflow DAGs:** Created dynamic Python DAGs to fetch Reddit posts and comments, perform lightweight transformations, and push the data into an Amazon S3 bucket.
- **AWS S3 Storage:** Configured S3 buckets to receive raw JSON/CSV Reddit data for further processing.
- **AWS Glue Crawlers:** Set up AWS Glue Crawlers to catalog new Reddit data and maintain schema consistency despite evolving data structures.
- **AWS Glue ETL Jobs:** Wrote Glue jobs to clean and transform the raw Reddit data, preparing it for analytics.
- **Amazon Athena:** Queried Reddit data using Athena to validate schema, perform preliminary analytics, and debug transformations.
- **Amazon Redshift:** Loaded cleaned and structured Reddit datasets into Redshift tables, creating an enterprise-grade warehouse ready for complex analytics.
- **Chartbot Dashboards:** Connected Chartbot directly to Redshift to create dynamic dashboards visualizing Reddit metrics like post volumes, popular subreddits, and engagement patterns.
- **Security and Secrets Management:** Used Docker secrets, environment files, and AWS IAM Roles to securely manage API keys, database access, and AWS service permissions.
- **Error Handling:** Implemented retry logic in Airflow tasks and configured Airflow alerting and logging to track failures or API limit breaches.
- **Testing and Validation:** Systematically tested each stage by uploading dummy data, simulating API failures, and validating outputs at every point across S3, Glue, Athena, and Redshift.

## Technologies and Tools Used

- **Apache Airflow** (Scheduler, Webserver, Workers, Metadata DB)
- **Docker** (docker-compose, custom Dockerfiles, container orchestration)
- **PostgreSQL** (Airflow metadata database)
- **AWS S3** (raw Reddit data storage)
- **AWS Glue** (crawlers and ETL transformations)
- **AWS Athena** (ad-hoc SQL queries for validation)
- **AWS Redshift** (final data warehouse)
- **Chartbot** (dashboarding and visualization)
- **Python** (Reddit API access scripts, DAG creation)
- **Reddit API** (data source)

## Challenges Faced

- Handling Reddit API rate limits without data loss.
- Managing dynamic and evolving Reddit data schemas.
- Ensuring Dockerized Airflow components worked seamlessly with AWS services.
- Securing credentials and access keys across the whole pipeline.
- Dealing with Redshift schema mismatches and transformation inconsistencies.
- Orchestrating retries and failure recoveries in Airflow.

## Final Note

This project helped me understand how to design production-grade data pipelines that are fully event-driven, secure, scalable, and modular. It combined real-world API data, Airflow orchestration, Docker-based environments, and full integration into AWS cloud services, preparing a strong foundation for future cloud-native data engineering solutions.

---

> **Note:** You can click on the architecture diagram at the top for a better view.

---

Feel free to fork this repository, raise issues, or suggest improvements!
