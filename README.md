Project Overview
<img width="394" height="282" alt="Project2_Archiecture-NdEFELlnQR" src="https://github.com/user-attachments/assets/983c07f0-f9e9-4445-b863-0ae8681e8925" />

The process begins with ingesting raw data, delivered in CSV format, into Azure Data Lake Storage (ADLS). This serves as the centralized landing zone where data first arrives. From here, the workflow ensures that only high-quality, validated data moves forward, while erroneous or duplicate data is captured for review.

The next stage of the pipeline uses Azure Databricks as the transformation and validation engine. Databricks notebooks perform a series of data quality checks:

Duplicate Detection: Identifies and removes redundant records from the ingested dataset.

Date Validation: Ensures that date fields adhere to the correct format and are logically valid. For this check, Databricks cross-references the incoming data with Azure SQL Database, which stores reference rules and acceptable formats.

Based on these checks:

Valid Data: Routed into a staging zone in ADLS for further downstream processing or analytics.

Invalid Data: Segregated into a rejected zone, making it easy to audit errors and maintain transparency.

This separation ensures clean, reliable, and traceable data pipelines that align with enterprise data governance standards.

Tools and Technologies Used

Azure Data Lake Storage (ADLS): Landing, staging, and rejected zones for data.

Azure Databricks: Data processing, duplicate detection, and transformation logic.

Azure SQL Database: Validation layer for date formats and business rules.

Key Outcomes

Built an end-to-end ingestion and validation pipeline tailored to financial services use cases.

Implemented data quality checks for duplicates and date validation, reducing downstream errors.

Ensured proper segregation of valid and invalid data, enabling governance and auditability.

Created a scalable and reusable architecture that can be extended to other domains.
