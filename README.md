# AWS DEA-C01 certification
# Types of data:
## 1. Structured

Data that is organized in a defined manner or schema, typically found in relational databases.

Characteristics: 
- Easily queryable;
- Organized in rows and columns;
- Has a consistent structure.
  
Examples:
- Database tables;
- CSV files with consistent columns;
- Excel spreadsheet.
  
## 2. Unstructured

Data that doesn't have a predefined structure or schema.

Characteristics:
- Not easily queryable without preprocessing;
- May come in various formats.

Examples: 
- Text files without a fixed format;
- Videos and audio files;
- Images;
- Emails and word processing documents.

## 3. Semi-Structured Data

Data that is not as organized as structured data but has some level of structure in the form of tags, hierarchies, or other patterns.

Characteristics: 
- Elements might be tagged or categorized in some way;
- More flexible than structured data but not as chaotic as unstructured data.

Examples: 
- XML and JSON files;
- Email headers (which have a mix of structured fields like date, subject, etc., and unstructured data in the body);
- Log files with varied format.

# Properties of Data (3V)
## 1. Volume

Refers to the amount or size of data that organizations are dealing with at any given time.

Characteristics:
- May range from gigabytes to petabytes or even more;
- Challenges in storing, processing, and analyzing high volumes of data.

Examples:
- Social media platform processing terabytes of data daily from user posts, 
images, and videos;
- Retailers collecting years' worth of transaction data, amounting to several petabytes.

## 2. Velocity

Refers to the speed at which new data is generated, collected, and processed.

Characteristics:
- High velocity requires real-time or near-real-time processing capabilities;
- Rapid (fast) ingestion and processing can be critical for certain applications.

Examples:
- Sensor data from IoT devices streaming readings every millisecond (Streaming data aplications);
- High-frequency trading systems where milliseconds can make a difference in decision-making.

## 3. Variety

Refers to the different types, structures, and sources of data.

Characteristics:
- Data can be structured, semi-structured, or unstructured;
- Data can come from multiple sources and in various formats.

Examples:
- A business analyzing data from relational databases (structured), emails (unstructured), and JSON logs (semi-structured);
- Healthcare systems collecting data from electronic medical records, wearable health devices, and patient feedback forms.

# Data Warehouse vs Data Lake

## Data Warehouse 

A centralized repository optimized for analysis where data from different sources is stored in a structured format.

Characteristics:
- Designed for complex queries and analysis;
- Data is cleaned, transformed, and loaded (ETL process);
- Typically uses a star or snowflake schema;
- Optimized for read-heavy operations.

Examples:
- Amazon Redshift;
- Google BigQuery;
- Microsoft Azure SQL Data Warehous.

## Data Lake

A storage repository that holds vast amounts of raw data in its native format, including structured, semi-structured, and unstructured data.

Characteristics:
- Can store large volumes of raw data without predefined schema;
- Data is loaded as-is, no need for preprocessing;
- Supports batch, real-time, and stream processing;
- Can be queried for data transformation or exploration purposes.

Examples:
- Amazon Simple Storage Service (S3) when used as a data lake;
- Azure Data Lake Storage;
- Hadoop Distributed File System (HDFS).

## Comparing the two 

**Schema:**
- Data Warehouse:Schema-on-write (predefined schema before writing data):
  - Extract – Transform – Load (ETL);
- Data Lake: Schema-on-read (schema is defined at the time of reading data):
  - Extract – Load – Transform (ELT).

**Data Types:**
- Data Warehouse: Primarily structured data;
- Data Lake: Both structured and unstructured data;

**Agility:**
- Data Warehouse: Less agile due to predefined schema;
- Data Lake: More agile as it accepts raw data without a predefined structure.

**Processing:** 
- Data Warehouse: ETL (Extract, Transform, Load);
- Data Lake: ELT (Extract, Load, Transform) or just Load for storage purposes.

**Cost:**
- Data Warehouse: Typically more expensive because of optimizations for complex queries;
- Data Lake: Cost-effective storage solutions, but costs can rise when processing large amounts of data.

## Choosing a Warehouse vs. a Lake

Use a Data Warehouse when: 
- You have structured data sources and require fast and complex queries;
- Data integration from different sources is essential;
-  Business intelligence and analytics are the primary use cases.

Use a Data Lake when: 
- You have a mix of structured, semi-structured, or unstructured data;
- You need a scalable and cost-effective solution to store massive amounts of data;
- Future needs for data are uncertain, and you want flexibility in storage and processing;
- Advanced analytics, machine learning, or data discovery are key goals.

Often, organizations use a combination of both, ingesting raw data into a data lake and then processing and moving refined data into a data warehouse for analysis.

## Data Lakehouse

A hybrid data architecture that combines the best features of data lakes and data warehouses, aiming to provide the performance, reliability, and capabilities of a data warehouse while maintaining the flexibility, scale, and low-cost storage of data lakes.

Characteristics: 
- Supports both structured and unstructured data;
- Allows for schema-on-write and schema-on-read;
- Provides capabilities for both detailed analytics and machine learning tasks;
- Typically built on top of cloud or distributed architectures;
- Benefits from technologies like Delta Lake, which bring ACID transactions to big data.

Examples: 
- AWS Lake Formation (with S3 and Redshift Spectrum);
- Delta Lake: An open-source storage layer that brings ACID transactions to Apache Spark and big data workloads;
- Databricks Lakehouse Platform: A unified platform that combines the capabilities of data lakes and data warehouses;
- Azure Synapse Analytics: Microsoft's analytics service that brings together big data and data warehousing.

# Data Mesh

A data mesh is a decentralized data architecture that organizes data by a specific business domain—for example, marketing, sales, customer service and more—to provide more ownership to the producers of a given data set.

it’s more about governance and organization.

Data lakes, warehouses, etc. may be part of a data mesh, but a “data mesh” is more about the “data management paradigm” and not the specific technologies or architectures.

# ETL Pipelines

ETL stands for Extract, Transform, Load. It's a process used to move data from source systems into a data warehouse.

Extract:
- Retrieve raw data from source systems, which can be databases, CRMs, flat files, APIs, or other data repositories;
- Ensure data integrity during the extraction phase;
- Can be done in real-time or in batches, depending on requirements.

Transform:
- Convert the extracted data into a format suitable for the target data warehouse;
- Can involve various operations such as:
  - Data cleansing (e.g., removing duplicates, fixing errors);
  - Data enrichment (e.g., adding additional data from other sources);
  - Format changes (e.g., date formatting, string manipulation);
  - Aggregations or computations (e.g., calculating totals or averages);
  - Encoding or decoding data;
  - Handling missing values.

Load:
- Move the transformed data into the target data warehouse or another data repository;
- Can be done in batches (all at once) or in a streaming manner (as data becomes available);
- Ensure that data maintains its integrity during the loading phase.

## Managing ETL Pipelines 
ETL Pipelines must be automated in some reliable way.
- AWS Glue;
- Orchestration services:
  - EventBridge;
  - Amazon Managed Workflows for Apache Airflow [Amazon MWAA];
  - AWS Step Functions;
  - Lambda;
  - Glue Workflows.

# Data Sources 

## 1. JDBC (Java Database Connectivity)
- Platform-independent;
- Language-dependent.

## 2. ODBC (Open Database Connectivity)
- Platform-dependent (thx to drivers);
- Language-independent;
- Raw logs;
- API’s;
- Streams.

# Common Data Formats

## 1. CSV (Comma-Separated Values)

Text-based format that represents data in a tabular form where each line corresponds to a row and values within a row are separated by commas.

When to Use: 
- For small to medium datasets;
- For data interchange between systems with different technologies;
- For human-readable and editable data storage;
- Importing/Exporting data from databases or spreadsheets.

Systems: Databases (SQL-based), Excel, Pandas in Python, R, many ETL tools.

## 2. JSON (JavaScript Object Notation)

Lightweight, text-based, and human-readable data interchange format that represents structured or semistructured data based on key-value pairs.

When to Use:
- Data interchange between a web server and a web client;
- Configurations and settings for software applications;
- Use cases that need a flexible schema or nested data structures.

Systems: Web browsers, many programming languages (like JavaScript, Python, Java, etc.), RESTful APIs, NoSQL databases (like MongoDB)

## 3. Avro

Binary format that stores both the data and its schema, allowing it to be processed later with different systems without needing the original system's context.

When to Use:
- With big data and real-time processing systems;
- When schema evolution (changes in data structure) is needed;
- Efficient serialization for data transport between systems.

Systems: Apache Kafka, Apache Spark, Apache Flink, Hadoop ecosystem.

## 4. Parquet
Columnar storage format optimized for analytics. Allows for efficient compression and encoding schemes.

When to Use:
- Analyzing large datasets with analytics engines;
- - Use cases where reading specific columns instead of entire records is beneficial;
- Storing data on distributed systems where I/O operations and storage need optimization.

Systems: Hadoop ecosystem, Apache Spark, Apache Hive, Apache Impala, Amazon Redshift Spectrum.

# Data Modeling
**1. Relational Model**

Usually found in OLTP systems.

**2. Dimensional Model**

## 1. Star Schema
![image](https://github.com/user-attachments/assets/aca61b0d-3603-402e-a417-1bbd6e555849)

  
  This schema consists of a central table, called the fact table, and a number of directly connected other tables, called dimension tables. The fact table contains information about metrics or measures, while the dimension tables contain information about descriptive attributes.
  
## 2. Snowflake Schema
![image](https://github.com/user-attachments/assets/db4ed9e1-3e66-426d-bf18-22fd1666f0e7)
  This schema consists of a central fact table, connected to the fact table dimension tables and additional dimension tables connected to the dimension tables.

## 6 key differences between star schema and snowflake schema:
1. A star schema has denormalized dimension tables, while a snowflake schema has normalized dimension tables;
2. A star schema is easier to design and implement than a snowflake schema;
3. A star schema can be more efficient to query than a snowflake schema, because there are fewer JOINs between tables;
4. A star schema can require more storage space than a snowflake schema, because of the denormalized data;
5. A star schema can be more difficult to update than a snowflake schema, because of the denormalized data;
6. A star schema can be more difficult to troubleshoot than a snowflake schema, because of the denormalized data.

# Data Lineage
![image](https://github.com/user-attachments/assets/ebe19641-825d-4b17-bdd6-b6f2c9d686d2)

A visual representation that traces the flow and transformation of data through its lifecycle, from its source to its final destination.

**Importance:** 
- Helps in tracking errors back to their source;
- Ensures compliance with regulations;
- Provides a clear understanding of how data is moved, transformed, and consumed within systems.

# Schema Evolution 

The ability to adapt and change the schema of a dataset over time without disrupting existing processes or systems.

Importance: 
- Ensures data systems can adapt to changing business requirements;
- Allows for the addition, removal, or modification of columns/fields in a dataset;
- Maintains backward compatibility with older data records.

Tool: Glue Schema Registry
- Schema discovery, compatibility, validation, registration.

# Database Performance Optimization
## 1. Indexing
- Avoid full table scans!
- Enforce data uniqueness and integrity.

## 2. Partitioning
- Reduce amount of data scanned;
- Helps with data lifecycle management;
- Enables parallel processing.

## 3. Compression
- Speed up data transfer, reduce storage & disk reads;
- GZIP, LZOP, BZIP2, ZSTD (Redshift examples);
- Various tradeoffs between compression & speed;
- Columnar compression.

# Data Sampling Techniques

When you need to take data from a big dataset for exploratory data analysis or any other analytical purpose.

## 1. Random Sampling
- Everything has an equal chance

## 2. Stratified Sampling
![image](https://github.com/user-attachments/assets/a4cc418c-25ec-46ec-83bd-9fd511489cb2)

- Divide population into homogenous subgroups (strata);
- Random sample within each stratum;
- Ensures representation of each subgroup.

## 3. Others

Systemic: give me every third item for the data sample
![image](https://github.com/user-attachments/assets/2e7dc043-1081-43f0-9486-21f7772dadf7)

- Systemic, Cluster, Convenience, Judgmental

# Data Skew Mechanisms 

Data skew refers to the unequal distribution or imbalance of data across various nodes or partitions in distributed computing systems.

**Causes:** 
- Non-uniform distribution of data;
- Inadequate partitioning strategy;
- Temporal skew;
- Important to monitor data distribution and alert when skew issues arise.

## Addressing Data Skew

**1. Adaptive Partitioning:**
Dynamically adjust partitioning based on data characteristics to ensure a more balanced distribution.

**2. Salting:**
Introduce a random factor or "salt" to the data to distribute it more uniformly.

**3. Repartitioning:**
Regularly redistribute the data based on its current distribution characteristics.

**4. Sampling:**
Use a sample of the data to determine the distribution and adjust the processing strategy accordingly.

**5. Custom Partitioning:**
Define custom rules or functions for partitioning data based on domain knowledge

# Data Validation and Profiling
## 1. Completeness
Ensures all required data is present and no essential parts are missing.

Checks: 
- Missing values, null counts, percentage of populated fields.

Importance: 
- Missing data can lead to inaccurate analyses and insights.

## 2. Consistency
Ensures data values are consistent across datasets and do not contradict each other.

Checks: 
- Cross-field validation, comparing data from different sources or periods.

Importance: 
- Inconsistent data can cause confusion and result in incorrect conclusions.

## 3. Accuracy
Ensures data is correct, reliable, and represents what it is supposed to.

Checks: 
- Comparing with trusted sources, validation against known standards or rules.

Importance: 
- Inaccurate data can lead to false insights and poor decision-making.

## 4. Integrity
Ensures data maintains its correctness and consistency over its lifecycle and across systems.

Checks: 
- Referential integrity (e.g., foreign key checks in databases), relationship validations.

Importance: 
- Ensures relationships between data elements are preserved, and data remains trustworthy over time.

# SQL 
# Joins
![image](https://github.com/user-attachments/assets/fc3a55dd-9b02-4337-ab41-23848a54b4a3)
# Regular Expressions
![image](https://github.com/user-attachments/assets/ad0a585c-6061-4f5e-872a-1b55d8a50214)

# Sign names in english cheat sheet:
    ~ The tilde 
    ! The exclamation mark
    ^ The caret
    | The pipe
    \ The backslash
    - The dash
    '' The single quotes
    () The parentheses
    [] The square brackets
    {} The curly brackets
    
# Git commands
## Setting Up and Configuration:
- git init: Initialize a new Git repository;
- git config: Set configuration values for user info, aliases, and more:
  - git config --global user.name "Your Name": Set your name;
  - git config --global user.email "your@email.com": Set your email;

## Basic Commands:
- git clone <repository>: Clone (or download) a repository from an existing URL;
- git status: Check the status of your changes in the working directory;
- git add <filename>: Add changes in the file to the staging area;
  - git add .: Add all new and changed files to the staging area;
- git commit -m "Commit message here": Commit the staged changes with a message;
- git log: View commit logs.

## Branching with git
- git branch: List all local branches;
  - git branch <branchname>: Create a new branch;
- git checkout <branchname>: Switch to a specific branch;
  - git checkout -b <branchname>: Create a new branch and switch to it;
- git merge <branchname>: Merge the specified branch into the current branch;
- git branch -d <branchname>: Delete a branch.

## Remote repositories
- git remote add <name> <url>: Add a remote repository;
- git remote: List all remote repositories;
- git push <remote> <branch>: Push a branch to a remote repository;
- git pull <remote> <branch>: Pull changes from a remote repository branch into the current local branch.

## Undoing changes
- git reset: Reset your staging area to match the most recent commit, without affecting the working directory;
- git reset --hard: Reset the staging area and the working directory to match the most recent commit;
- git revert <commit>: Create a new commit that undoes all of the changes from a previous commit.

## Advanced git
- git stash: Temporarily save changes that are not yet ready for a commit;
- git stash pop: Restore the most recently stashed changes;
- git rebase <branch>: Reapply changes from one branch onto another, often used to integrate changes from one branch into another;
- git cherry-pick <commit>: Apply changes from a specific commit to the current branch.

## Git collaboration and inspection
- git blame <file>: Show who made changes to a file and when;
- git diff: Show changes between commits, commit and working tree, etc;
- git fetch: Fetch changes from a remote repository without merging them.

## Git maintenance and data recovery
- git fsck: Check the database for errors;
- git gc: Clean up and optimize the local repository;
- git reflog: Record when refs were updated in the local repository, useful for recovering lost commits.




# Storage
Storing, accessing, and backing up data in AWS

# Amazon S3
Amazon S3 is ”infinitely scaling” storage
## Amazon S3 Use cases:
- Backup and storage;
- Disaster Recovery;
- Archive;
- Hybrid Cloud storage;
- Application hosting;
- Media hosting;
- Data lakes & big data analytics;
- Software delivery;
- Static website.

## Amazon S3 – Objects (cont.)
- Object values are the content of the body:
  - Max. Object Size is 5TB (5000GB);
  - If uploading more than 5GB, must use “multi-part upload”;
- Metadata (list of text key / value pairs – system or user metadata);
- Tags (Unicode key / value pair – up to 10) – useful for security / lifecycle; 
- Version ID (if versioning is enabled).

## Amazon S3 – Security
- User-Based:
  - IAM Policies – which API calls should be allowed for a specific user from IAM;
- Resource-Based:
  - Bucket Policies – bucket wide rules from the S3 console - allows cross account;
  - Object Access Control List (ACL) – finer grain (can be disabled);
  - Bucket Access Control List (ACL) – less common (can be disabled);
- Note: an IAM principal can access an S3 object if:
  - The user IAM permissions ALLOW it OR the resource policy ALLOWS it;
  - AND there’s no explicit DENY;
- Encryption: encrypt objects in Amazon S3 using encryption key.

## S3 Bucket Policies 
- JSON based policies:
  - Resources: buckets and objects;
  - Effect: Allow / Deny;
  - Actions: Set of API to Allow or Deny;
  - Principal: The account or user to apply the policy to;
- Use S3 bucket for policy to:
  - Grant public access to the bucket;
  - Force objects to be encrypted at upload;
  - Grant access to another account (Cross Account).

## Amazon S3 - Versioning
- You can version your files in Amazon S3;
- It is enabled at the **bucket level**;
- Same key overwrite will change the “version”: 1, 2, 3…;
- It is best practice to version your buckets;
  - Protect against unintended deletes (ability to restore a version);
  - Easy roll back to previous version;
- Notes:
  - Any file that is not versioned prior to enabling versioning will have version “null”;
  - Suspending versioning does not delete the previous versions.

## Amazon S3 – Replication (CRR & SRR)
- **Must enable Versioning** in source and destination buckets;
- **Cross-Region Replication (CRR)**;
- **Same-Region Replication (SRR)**;
- Buckets can be in different AWS accounts;
- Copying is asynchronous;
- Must give proper IAM permissions to S3;
- Use cases:
  - **CRR** - compliance, lower latency access, replication across accounts;
  - **SRR** - log aggregation, live replication between production and test accounts.

## Amazon S3 – Replication (Notes)
- After you enable Replication, only new objects are replicated;
- Optionally, you can replicate existing objects using S3 Batch Replication;
  - Replicates existing objects and objects that failed replication;
- For DELETE operations:
  - Can replicate delete markers from source to target (optional setting);
  - Deletions with a version ID are not replicated (to avoid malicious deletes);
- There is no “chaining” of replication:
  - If bucket 1 has replication into bucket 2, which has replication into bucket 3;
  - Then objects created in bucket 1 are not replicated to bucket 3.

## S3 Storage Classes
- Amazon S3 Standard - General Purpose;
- Amazon S3 Standard-Infrequent Access (IA);
- Amazon S3 One Zone-Infrequent Access;
- Amazon S3 Glacier Instant Retrieval;
- Amazon S3 Glacier Flexible Retrieval;
- Amazon S3 Glacier Deep Archive;
- Amazon S3 Intelligent Tiering.

- Can move between classes manually or using S3 Lifecycle configurations

## S3 Durability and Availability
- Durability:
  - High durability (99.999999999%, 11 9’s) of objects across multiple AZ;
  - If you store 10,000,000 objects with Amazon S3, you can on average expect to incur a loss of a single object once every 10,000 years;
  - Same for all storage classes;
- Availability:
  - Measures how readily available a service is;
  - Varies depending on storage class;
  - Example: S3 standard has 99.99% availability = not available 53 minutes a year.

## S3 Standard – General Purpose
- 99.99% Availability;
- Used for frequently accessed data;
- Low latency and high throughput;
- Sustain 2 concurrent facility failures.

- Use Cases: Big Data analytics, mobile & gaming applications, content distribution…

## S3 Storage Classes – Infrequent Access
- For data that is less frequently accessed, but requires rapid access when needed;
- Lower cost than S3 Standard.

- **Amazon S3 Standard-Infrequent Access** (S3 Standard-IA)
  - 99.9% Availability;
  - Use cases: Disaster Recovery, backups.

- **Amazon S3 One Zone-Infrequent Access** (S3 One Zone-IA)
  - High durability (99.999999999%) in a single AZ; data lost when AZ is destroyed;
  - 99.5% Availability;
  - Use Cases: Storing secondary backup copies of on-premises data, or data you can recreate.

## Amazon S3 Glacier Storage Classes
- Low-cost object storage meant for archiving / backup;
- Pricing: price for storage + object retrieval cost.

- Amazon S3 Glacier Instant Retrieval:
  - Millisecond retrieval, great for data accessed once a quarter;
  - Minimum storage duration of 90 days;
- Amazon S3 Glacier Flexible Retrieval (formerly Amazon S3 Glacier):
  - Expedited (1 to 5 minutes), Standard (3 to 5 hours), Bulk (5 to 12 hours) – free;
  - Minimum storage duration of 90 days;
- Amazon S3 Glacier Deep Archive – for long term storage:
  - Standard (12 hours), Bulk (48 hours);
  - Minimum storage duration of 180 days

## S3 Intelligent-Tiering
- Small monthly monitoring and auto-tiering fee;
- Moves objects automatically between Access Tiers based on usage;
- There are no retrieval charges in S3 Intelligent-Tiering;

- Frequent Access tier (automatic): default tier;
- Infrequent Access tier (automatic): objects not accessed for 30 days;
- Archive Instant Access tier (automatic): objects not accessed for 90 days;
- Archive Access tier (optional): configurable from 90 days to 700+ days;
- Deep Archive Access tier (optional): config. from 180 days to 700+ days.

## S3 Storage Classes Comparison
![image](https://github.com/user-attachments/assets/731023bd-f5fe-463d-9ab3-0c56bfe32dfd)

## S3 Storage Classes – Price Comparison
Example: us-east-1
![image](https://github.com/user-attachments/assets/637a5a19-4b7c-44e7-bd6d-333abaa0deab)

## Amazon S3 – Lifecycle Rules
- Transition Actions – configure objects to transition to another storage class;
  - Move objects to Standard IA class 60 days after creation;
  - Move to Glacier for archiving after 6 months;
- Expiration actions – configure objects to expire (delete) after some time;
  - Access log files can be set to delete after a 365 days;
  - Can be used to delete old versions of files (if versioning is enabled);
  - Can be used to delete incomplete Multi-Part uploads;
- Rules can be created for a certain prefix (example: s3://mybucket/mp3/*);
- Rules can be created for certain objects Tags (example: Department: Finance).

## Amazon S3 – Lifecycle Rules (Scenario 1)
Your application on EC2 creates images thumbnails after profile photos are uploaded to Amazon S3. These thumbnails can be easily recreated, and only need to be kept for 60 days. The source images should be able to be immediately retrieved for these 60 days, and afterwards, the user can wait up to 6 hours. How would you design this?
- S3 source images can be on Standard, with a lifecycle configuration to transition them to Glacier after 60 days;
- S3 thumbnails can be on One-Zone IA, with a lifecycle configuration to expire them (delete them) after 60 days.

## Amazon S3 – Lifecycle Rules (Scenario 2)
A rule in your company states that you should be able to recover your deleted S3 objects immediately for 30 days, although this may happen rarely. After this time, and for up to 365 days, deleted objects should be recoverable within 48 hours.
- Enable S3 Versioning in order to have object versions, so that “deleted objects” are in fact hidden by a “delete marker” and can be recovered;
- Transition the “noncurrent versions” of the object to Standard IA;
- Transition afterwards the “noncurrent versions” to Glacier Deep Archive.

## S3 Event Notifications
S3:ObjectCreated, S3:ObjectRemoved, S3:ObjectRestore, S3:Replication…

## S3 Event Notifications with Amazon EventBridge
![image](https://github.com/user-attachments/assets/24e1e838-e487-44fd-9682-8c92d3880164)
- Advanced filtering options with JSON rules (metadata, object size, name...);
- Multiple Destinations – ex Step Functions, Kinesis Streams / Firehose…;
- EventBridge Capabilities – Archive, Replay Events, Reliable delivery.

## S3 – Baseline Performance
- Amazon S3 automatically scales to high request rates, latency 100-200 ms;
- Your application can achieve at least 3,500 PUT/COPY/POST/DELETE or 5,500 GET/HEAD requests per second per prefix in a bucket; 
- There are no limits to the number of prefixes in a bucket;
- Example (object path => prefix):
  - bucket/folder1/sub1/file => /folder1/sub1/;
  - bucket/folder1/sub2/file => /folder1/sub2/;
  - bucket/1/file => /1/;
  - bucket/2/file => /2/;
- If you spread reads across all four prefixes evenly, you can achieve 22,000 requests per second for GET and HEAD.

## S3 Performance
- Multi-Part upload: 
  - recommended for files > 100MB, must use for files > 5GB;
  - Can help parallelize uploads (speed up transfers);
- **S3 Transfer Acceleration**:
  - Increase transfer speed by transferring file to an AWS edge location which will forward the data to the S3 bucket in the target region;
  - Compatible with multi-part upload.

## S3 Performance – S3 Byte-Range Fetches
![image](https://github.com/user-attachments/assets/617cfccd-dcca-4305-81bf-2afc7647606b)

## S3 Select & Glacier Select
- Retrieve less data using SQL by performing server-side filtering;
- Can filter by rows & columns (simple SQL statements);
- Less network transfer, less CPU cost client-side.
![image](https://github.com/user-attachments/assets/28e1398f-37c4-4b1f-9d03-5d764483fd19)

## Amazon S3 – Object Encryption
You can encrypt objects in S3 buckets using one of 4 methods
- Server-Side Encryption (SSE);
  - Server-Side Encryption with Amazon S3-Managed Keys **(SSE-S3)** – Enabled by Default. Encrypts S3 objects using keys handled, managed, and owned by AWS;
  - Server-Side Encryption with KMS Keys stored in AWS KMS **(SSE-KMS)**. Leverage AWS Key Management Service (AWS KMS) to manage encryption keys;
  - Server-Side Encryption with Customer-Provided Keys **(SSE-C)** ;
- Client-Side Encryption. When you want to manage your own encryption keys.

## Amazon S3 Encryption – SSE-S3
- Encryption using keys handled, managed, and owned by AWS;
- Object is encrypted server-side;
- Encryption type is AES-256;
- Must set header **"x-amz-server-side-encryption": "AES256"**;
- **Enabled by default for new buckets & new objects**.

## Amazon S3 Encryption – SSE-KMS
- Encryption using keys handled and managed by AWS KMS (Key Management Service);
- KMS advantages: user control + audit key usage using CloudTrail;
- Object is encrypted server side;
- Must set header **"x-amz-server-side-encryption": "aws:kms"**.

## SSE-KMS Limitation
- If you use SSE-KMS, you may be impacted by the KMS limits;
- When you upload, it calls the GenerateDataKey KMS API;
- When you download, it calls the Decrypt KMS API;
- Count towards the KMS quota per second (5500, 10000, 30000 req/s based on region);
- You can request a quota increase using the Service Quotas Console.

## Amazon S3 Encryption – SSE-C
- Server-Side Encryption using keys fully managed by the customer outside of AWS;
- Amazon S3 does NOT store the encryption key you provide;
- HTTPS must be used;
- Encryption key must provided in HTTP headers, for every HTTP request made.

## Amazon S3 Encryption – Client-Side Encryption
- Use client libraries such as Amazon S3 Client-Side Encryption Library;
- Clients must encrypt data themselves before sending to Amazon S3;
- Clients must decrypt data themselves when retrieving from Amazon S3;
- Customer fully manages the keys and encryption cycle.

## S3 – Access Points
![image](https://github.com/user-attachments/assets/9ffb7206-7b12-4fe8-bf61-9906a78b2469)

## S3 Object Lambda
- Use AWS Lambda Functions to change the object before it is retrieved by the caller application;
- Only one S3 bucket is needed, on top of which we create S3 Access Point and S3 Object Lambda Access Points.
- Use Cases:
  - Redacting personally identifiable information for analytics or nonproduction environments;
  - Converting across data formats, such as converting XML to JSON;
- Resizing and watermarking images on the fly using callerspecific details, such as the user who requested the object;
![image](https://github.com/user-attachments/assets/025be4ff-deb3-4d9d-81e9-020da2a37300)

# EC2 Instance Storage Section
## What’s an EBS Volume?
An EBS (Elastic Block Store) Volume is a network drive you can attach to your instances while they run.
- It allows your instances to persist data, even after their termination;
- They can only be mounted to one instance at a time (at the CCP level);
- They are bound to a specific availability zone;
- Analogy: Think of them as a “network USB stick”; 
- Free tier: 30 GB of free EBS storage of type General Purpose (SSD) or Magnetic per month.

## EBS Volume
- It’s a network drive (i.e. not a physical drive);
- It uses the network to communicate the instance, which means there might be a bit of latency;
- It can be detached from an EC2 instance and attached to another one quickly;
- It’s locked to an Availability Zone (AZ);
  - An EBS Volume in us-east-1a cannot be attached to us-east-1b;
  - To move a volume across, you first need to snapshot it;
- Have a provisioned capacity (size in GBs, and IOPS);
- You get billed for all the provisioned capacity;
- You can increase the capacity of the drive over time.

## Amazon EBS Elastic Volumes
- You don’t have to detach a volume or restart your instance to change it! (Just go to actions / modify volume from the console);
- Increase volume size. (You can only increase, not decrease);
- Change volume type. (Gp2 -> Gp3);
- Specify desired IOPS or throughput performance (or it will guess);
- Adjust performance. (Increase or decrease).

## Amazon EFS – Elastic File System
- Managed NFS (network file system) that can be mounted on many EC2;
- EFS works with EC2 instances in multi-AZ;
- Highly available, scalable, expensive (3x gp2), pay per use.
![image](https://github.com/user-attachments/assets/6a324f78-de91-48a4-a4ac-cdbf182b352b)

## Amazon EFS – Elastic File System
Use cases: 
- content management;
- web serving;
- data sharing;
- wordpress.

  - Uses NFSv4.1 protocol;
  - Uses security group to control access to EFS;
  - **Compatible with Linux based AMI (not Windows)**;
  - Encryption at rest using KMS;
  - POSIX file system (~Linux) that has a standard file API;
  - File system scales automatically, pay-per-use, no capacity planning.

## EFS – Performance & Storage Classes
- EFS Scale:
  - 1000s of concurrent NFS clients, 10 GB+ /s throughput;
  - Grow to Petabyte-scale network file system, automatically;
- Performance Mode (set at EFS creation time):
  - General Purpose (default) – latency-sensitive use cases (web server, CMS, etc…);
  - Max I/O – higher latency, throughput, highly parallel (big data, media processing);
- Throughput Mode:
  - Bursting – 1 TB = 50MiB/s + burst of up to 100MiB/s;
  - Provisioned – set your throughput regardless of storage size, ex: 1 GiB/s for 1 TB storage;
  - Elastic – automatically scales throughput up or down based on your workloads:
    - Up to 3GiB/s for reads and 1GiB/s for writes;
    - Used for unpredictable workloads.

## EFS – Storage Classes
- Storage Tiers (lifecycle management feature – move file after N days);
- Standard: for frequently accessed files;
- Infrequent access (EFS-IA): cost to retrieve files, lower price to store;
- Archive: rarely accessed data (few times each year), 50% cheaper;
- Implement lifecycle policies to move files between storage tiers;
- Availability and durability;
- Standard: Multi-AZ, great for prod;
- One Zone: One AZ, great for dev, backup enabled by default, compatible with IA (EFS One Zone-IA);
- Over 90% in cost savings.

## EBS vs EFS – Elastic Block Storage
- EBS volumes:
  - one instance (except multi-attach io1/io2);
  - are locked at the Availability Zone (AZ) level;
  - gp2: IO increases if the disk size increases;
  - gp3 & io1: can increase IO independently.
- To migrate an EBS volume across AZ:
  - Take a snapshot; 
  - Restore the snapshot to another AZ;
  - EBS backups use IO and you shouldn’t run them while your application is handling a lot of traffic.
- Root EBS Volumes of instances get terminated by default if the EC2 instance gets terminated. (you can disable that).

## EBS vs EFS – Elastic File System
- Mounting 100s of instances across AZ
- EFS share website files (WordPress)
- Only for Linux Instances (POSIX)
- EFS has a higher price point than EBS
- Can leverage Storage Tiers for cost savings
      - Remember: **EFS vs EBS vs Instance Store**
