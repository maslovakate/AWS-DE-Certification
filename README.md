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

# DWH Designing 
## Characteristics of a Data Warehouse
![image](https://github.com/user-attachments/assets/e54df4ab-bf3e-436e-acb5-0d97ec431bd4)
  - **Subject-Oriented**: A data warehouse uses a theme, and delivers information about a specific subject instead of a company’s current operations. In other words, the data warehousing process is more equipped to handle a specific theme. Examples of themes or subjects include sales, distributions, marketing, etc.
  - **Integrated**: Integration is defined as establishing a connection between large amount of data from multiple databases or sources. However, it is also essential for the data to be stored in the data warehouse in a unified manner. The process of data warehousing integrates data from multiple sources, such as a mainframe, relational databases, flat files, etc. Furthermore, it helps maintain consistent codes, attribute measures, naming conventions, and, formats.
  - **Time-variant**: Time-variant in a DW is more extensive as compared to other operating systems. Data stored in a data warehouse is recalled with a specific time period and provides information from a historical perspective.
  - **Non-volatile**: In the non-volatile data warehouse, data is permanent i.e. when new data is inserted, previous data is not replaced, omitted, or deleted. In this data warehouse, data is read-only and only refreshes at certain intervals.  The two data operations performed in the data warehouse are data access and data loading.

## Functions of a Data Warehouse
  - Data Extraction;
  - Data Cleaning;
  - Data Transformation;
  - Data Integration;
  - Data Loading;
  - Data Mapping;
  - Refreshing.
## Normalization vs. Denormalization Approach
Normalization is defined as a way of data re-organization. This helps meet two main requirements in an EDW: 
  - eliminating data redundancy;
  - protecting data dependency.
On the other hand, denormalization increases the functionality of the database system’s infrastructure.

## Database vs Data Warehouse
|Database  |  Data Warehouse |
| ------------- | ------------- |
| A database is an amalgamation of related data | Data warehouse serves as an information system that contains historical and commutative data from one or several sources|
| A database is used for recording data  | A data warehouse is used for analyzing data  |
| A database is an application-oriented collection of data | Data warehouse is the subject-oriented collection of data |
| A database uses **Online Transactional Processing (OLTP)** | Data warehouse uses **Online Analytical Processing (OLAP)** |
| Database tables and joins are normalized, therefore, more complicated | Data warehouse tables and joins are denormalized, hence simpler |
| **Entity relationship (ER)** modeling techniques are used for designing | Data modeling techniques are used for designing |

## Ralph Kimball vs Bill Inmon 
![image](https://github.com/user-attachments/assets/42304ffa-83d7-4312-b70c-42760b7e0b03)
![image](https://github.com/user-attachments/assets/18a58fee-59b6-4289-9c65-9f951ba9bdf0)
Kimball model does not have the integration layer. Data moves directly from the source system(s) to the data marts. So there is no **ODS**(operational data store)/Stage/Landing layer in Kimball;

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
- `Use cases that need a flexible schema or nested data structures`.

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
- `Use cases: where reading specific columns instead of entire records is beneficial`;
- Storing data on distributed systems where I/O operations and storage need optimization.

Systems: Hadoop ecosystem, Apache Spark, Apache Hive, Apache Impala, Amazon Redshift Spectrum.

# Kimball vs Inmon DWH 

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

`Use Cases: Big Data analytics, mobile & gaming applications, content distribution`

## S3 Storage Classes – Infrequent Access
- For data that is less frequently accessed, but requires rapid access when needed;
- Lower cost than S3 Standard.

- **Amazon S3 Standard-Infrequent Access** (S3 Standard-IA)
  - 99.9% Availability;
 ` Use cases: Disaster Recovery, backups`.

- **Amazon S3 One Zone-Infrequent Access** (S3 One Zone-IA)
  - High durability (99.999999999%) in a single AZ; data lost when AZ is destroyed;
  - 99.5% Availability;
`Use Cases: Storing secondary backup copies of on-premises data, or data you can recreate`.

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
- Mounting 100s of instances across AZ;
- EFS share website files (WordPress);
- Only for Linux Instances (POSIX);
- EFS has a higher price point than EBS;
- Can leverage Storage Tiers for cost savings.
    - Remember: **EFS vs EBS vs Instance Store**.

## AWS Backup
- Fully managed service;
- Centrally manage and automate backups across AWS services;
- No need to create custom scripts and manual processes.
- Supported services:
  - Amazon EC2 / Amazon EBS;
  - Amazon S3;
  - Amazon RDS (all DBs engines) / Amazon Aurora / Amazon DynamoDB;
  - Amazon DocumentDB / Amazon Neptune;
  - Amazon EFS / Amazon FSx (Lustre & Windows File Server);
  - AWS Storage Gateway (Volume Gateway).
- Supports cross-region backups;
- Supports cross-account backups;
- Supports PITR for supported services;
- On-Demand and Scheduled backups;
- Tag-based backup policies;
- You create backup policies known as Backup Plans;
- Backup frequency (every 12 hours, daily, weekly, monthly, cron expression);
- Backup window;
- Transition to Cold Storage (Never, Days, Weeks, Months, Years);
- Retention Period (Always, Days, Weeks, Months, Years).
![image](https://github.com/user-attachments/assets/896b78aa-5147-41a6-b369-894e403722c8)
## AWS Backup Vault Lock
- Enforce a WORM (Write Once Read Many) state for all the backups that you store in your AWS Backup Vault.
- Additional layer of defense to protect your backups against:
  - Inadvertent or malicious delete operations;
  - Updates that shorten or alter retention periods;
  - Even the root user cannot delete backups when enabled.

# Database
Managing and querying structured and semi-structured data.

## Amazon DynamoDB
NoSQL Serverless Database.

## Traditional Architecture
![image](https://github.com/user-attachments/assets/107366d5-ccdd-47ef-9387-ac22a72a46d4)
- Traditional applications leverage RDBMS databases;
- These databases have the SQL query language;
- Strong requirements about how the data should be modeled;
- Ability to do query joins, aggregations, complex computations;
- Vertical scaling (getting a more powerful CPU / RAM / IO);
- Horizontal scaling (increasing reading capability by adding EC2 / RDS Read Replicas.

## NoSQL databases
- NoSQL databases are non-relational databases and are distributed;
- NoSQL databases include MongoDB, DynamoDB, …;
- NoSQL databases do not support query joins (or just limited support);
- All the data that is needed for a query is present in one row;
- NoSQL databases don’t perform aggregations such as “SUM”, “AVG”, …;
- NoSQL databases scale horizontally;
  - There’s no “right or wrong” for NoSQL vs SQL, they just require to model the data differently and think about user queries differently.

## Amazon DynamoDB 
- Fully managed, highly available with replication across multiple AZs;
- NoSQL database - not a relational database;
- Scales to massive workloads, distributed database;
- Millions of requests per seconds, trillions of row, 100s of TB of storage;
- Fast and consistent in performance (low latency on retrieval);
- Integrated with IAM for security, authorization and administration;
- Enables event driven programming with DynamoDB Streams;
- Low cost and auto-scaling capabilities;
- Standard & Infrequent Access (IA) Table Clas.

## DynamoDB - Basics
- DynamoDB is made of Tables;
- Each table has a Primary Key (must be decided at creation time);
- Each table can have an infinite number of items (= rows);
- Each item has attributes (can be added over time – can be null);
- Maximum size of an item is 400KB.
- Data types supported are:
  - Scalar Types: String, Number, Binary, Boolean, Null;
  - Document Types: List, Map;
  - Set Types – String Set, Number Set, Binary Set.
 
## DynamoDB – Primary Keys 
- **Option 1**: Partition Key **(HASH)**
  - Partition key must be unique for each item;
  - Partition key must be “diverse” so that the data is distributed;
Example: “User_ID” for a users table
![image](https://github.com/user-attachments/assets/c0f061b5-2dce-41af-8d5a-c84c77123e9a)
- **Option 2**: Partition Key + Sort Key **(HASH + RANGE)**
  - The combination must be unique for each item;
  - Data is grouped by partition key.
Example: users-games table, “User_ID” for Partition Key and “Game_ID” for Sort Key.
![image](https://github.com/user-attachments/assets/81f62e11-eef5-4648-a65b-0699c8db5d75)

## DynamoDB in Big Data
**Common use cases include**: 
- Mobile apps; 
- Gaming;
- Digital ad serving;
- Live voting;
- Audience interaction for live events;
- Sensor networks;
- Log ingestion;
- Access control for web-based content;
- Metadata storage for Amazon S3 objects;
- E-commerce shopping carts;
- Web session management.

**Anti Pattern**:
- Prewritten application tied to a traditional relational database: use RDS instead;
- Joins or complex transactions ;
- Binary Large Object (BLOB) data: store data in S3 & metadata in DynamoDB;
- Large data with low I/O rate: use S3 instead.

## DynamoDB – Read/Write Capacity Modes
Control how you manage your table’s capacity (read/write throughput)
1. Provisioned Mode (default)
- You specify the number of reads/writes per second;
- You need to plan capacity beforehand;
- Pay for provisioned read & write capacity units.
2. On-Demand Mode
- Read/writes automatically scale up/down with your workloads;
- No capacity planning needed;
- Pay for what you use, more expensive ($$$).

You can switch between different modes once every 24 hours.

## R/W Capacity Modes – Provisioned
- Table must have provisioned read and write capacity units;
- Read Capacity Units **(RCU)** – throughput for reads;
- Write Capacity Units **(WCU)** – throughput for writes;
- Option to setup auto-scaling of throughput to meet demand;
- Throughput can be exceeded temporarily using “Burst Capacity”;
- If Burst Capacity has been consumed, you’ll get a “ProvisionedThroughputExceededException”;
- It’s then advised to do an exponential backoff retry.

## DynamoDB – Write Capacity Units (WCU)
- One Write Capacity Unit (WCU) represents **one write per second for an item up to 1 KB in size**
- If the items are larger than 1 KB, more WCUs are consumed

- **Example 1**: we write 10 items per second, with item size 2 KB;

        10 ∗ (2 𝐾𝐵 / 1 𝐾𝐵) = 20 𝑊𝐶𝑈𝑠
- **Example 2**: we write 6 items per second, with item size 4.5 KB;

        6 ∗ (5 𝐾𝐵 / 1 𝐾𝐵) = 30 𝑊𝐶𝑈𝑠 (4.5 gets rounded to the upper KB)
- **Example 3**: we write 120 items per minute, with item size 2 KB.

        120 / 60 ∗ (2 𝐾𝐵 / 1 𝐾𝐵) = 4 𝑊𝐶𝑈𝑠

## Strongly Consistent Read vs. Eventually Consistent Read
1. Eventually Consistent Read (default)
- If we read just after a write, it’s possible we’ll get some stale data because of replication
2. Strongly Consistent Read
- If we read just after a write, we will get the correct data;
- Set “ConsistentRead” parameter to True in API calls (GetItem, BatchGetItem, Query, Scan);
- Consumes twice the RCU.

## DynamoDB – Read Capacity Units (RCU)
One Read Capacity Unit (RCU) represents one Strongly Consistent Read per second, or two Eventually Consistent Reads per second, for an item up to 4 KB in size.
If the items are larger than 4 KB, more RCUs are consumed.
- **Example 1**: 10 Strongly Consistent Reads per second, with item size 4 KB;

        10 ∗ (4 𝐾𝐵 / 4 𝐾𝐵) = 10 𝑅𝐶𝑈𝑠
- **Example 2**: 16 Eventually Consistent Reads per second, with item size 12 KB;

        16 / 2 ∗ (12 𝐾𝐵 / 4 𝐾𝐵) = 24 𝑅𝐶𝑈𝑠
- **Example 3**: 10 Strongly Consistent Reads per second, with item size 6 KB.

        10 ∗ (8 𝐾𝐵 / 4 𝐾𝐵) = 20 𝑅𝐶𝑈𝑠 (we must round up 6 KB to 8 KB)

## DynamoDB – Partitions Internal
- Data is stored in partitions;
- Partition Keys go through a hashing algorithm to know to which partition they go to.

To compute the number of partitions:
![image](https://github.com/user-attachments/assets/018ae4ac-abf3-41f9-9b88-c238dd7e8d4e)

**WCUs and RCUs are spread evenly across partitions**.

## DynamoDB – Throttling
**If we exceed provisioned RCUs or WCUs, we get “ProvisionedThroughputExceededException”**
- **Reasons**:
  - Hot Keys – one partition key is being read too many times (e.g., popular item);
  - Hot Partitions;
  - Very large items, remember RCU and WCU depends on size of items.
- **Solutions**:
  - Exponential backoff when exception is encountered (already in SDK);
  - Distribute partition keys as much as possible;
  - If RCU issue, we can use **DynamoDB Accelerator (DAX)**.

## R/W Capacity Modes – On-Demand
- Read/writes automatically scale up/down with your workloads;
- No capacity planning needed (WCU / RCU);
- Unlimited WCU & RCU, no throttle, more expensive;
- You’re charged for reads/writes that you use in terms of RRU and WRU;
- Read Request Units (RRU) – throughput for reads (same as RCU);
- Write Request Units (WRU) – throughput for writes (same as WCU);
- 2.5x more expensive than provisioned capacity (use with care).

`Use cases: unknown workloads, unpredictable application traffic`

## DynamoDB – Writing Data
**1. PutItem**
  - Creates a new item or fully replace an old item (same Primary Key);
  - Consumes WCUs.
**2. UpdateItem**
  - Edits an existing item’s attributes or adds a new item if it doesn’t exist;
  - Can be used to implement Atomic Counters – a numeric attribute that’s unconditionally incremented.
**3. Conditional Writes**
  - Accept a write/update/delete only if conditions are met, otherwise returns an error;
  - Helps with concurrent access to items;
  - No performance impact.

## DynamoDB – Reading Data
**GetItem**
  - Read based on Primary key;
  - Primary Key can be **HASH** or **HASH + RANGE**;
  - Eventually Consistent Read (default);
  - Option to use Strongly Consistent Reads (more RCU - might take longer);
  - **ProjectionExpression** can be specified to retrieve only certain attributes.

## DynamoDB – Reading Data (Query)
- **Query** returns items based on:
  - **KeyConditionExpression**;
    - **Partition Key value** (must be = operator) – required;
    - **Sort Key value** (=, <, <=, >, >=, Between, Begins with) – optional.
  - **FilterExpression**
    - Additional filtering after the Query operation (before data returned to you);
    - Use only with non-key attributes (does not allow HASH or RANGE attributes).
- Returns:
  - The number of items specified in Limit;
  - Or up to 1 MB of data.
- Ability to do pagination on the results
- Can query table, a Local Secondary Index, or a Global Secondary Index.

## DynamoDB – Reading Data (Scan)
- Scan the entire table and then filter out data (inefficient);
- Returns up to 1 MB of data – use pagination to keep on reading;
- Consumes a lot of RCU;
- Limit impact using Limit or reduce the size of the result and pause;
- For faster performance, use **Parallel Scan**:
  - Multiple workers scan multiple data segments at the same time;
  - Increases the throughput and RCU consumed;
  - Limit the impact of parallel scans just like you would for Scans.
- Can use ProjectionExpression & FilterExpression (no changes to RCU).

## DynamoDB – Deleting Data
**1. DeleteItem**
  - Delete an individual item;
  - Ability to perform a conditional delete.
**2. DeleteTable**
  - Delete a whole table and all its items;
  - Much quicker deletion than calling DeleteItem on all items.

## DynamoDB – Batch Operations
- Allows you to save in latency by reducing the number of API calls;
- Operations are done in parallel for better efficiency;
- Part of a batch can fail; in which case we need to try again for the failed items.

**1. BatchWriteItem**
  - Up to 25 PutItem and/or DeleteItem in one call
  - Up to 16 MB of data written, up to 400 KB of data per item
  - Can’t update items (use UpdateItem)
  - **UnprocessedItems** for failed write operations (exponential backoff or add WCU)

**2. BatchGetItem**
  - Return items from one or more tables;
  - Up to 100 items, up to 16 MB of data;
  - Items are retrieved in parallel to minimize latency;
  - UnprocessedKeys for failed read operations (exponential backoff or add RCU).

## DynamoDB – PartiQL
SQL-compatible query language for DynamoDB
- Allows you to select, insert, update, and delete data in DynamoDB using SQL;
- Run queries across multiple DynamoDB tables;
- Run PartiQL queries from:
  - AWS Management Console;
  - NoSQL Workbench for DynamoDB;
  - DynamoDB APIs;
  - AWS CLI;
  - AWS SDK.
  
  Use a SQL-like syntax to manipulate DynamoDB tables
1. Supports some (but not all) statements:
  - INSERT
  - UPDATE
  - SELECT
  - DELETE
2. It supports Batch operations.

## DynamoDB – Local Secondary Index (LSI)
- **Alternative Sort Key** for your table (same Partition Key as that of base table);
- The Sort Key consists of one scalar attribute (String, Number, or Binary);
- Up to 5 Local Secondary Indexes per table;
- **Must be defined at table creation time**;
- **Attribute Projections** – can contain some or all the attributes of the base table (KEYS_ONLY, INCLUDE, ALL).
  ![image](https://github.com/user-attachments/assets/3e08280f-540b-46c9-a42d-13d355d62898)

## DynamoDB – Global Secondary Index (GSI)
- Alternative Primary Key (HASH or HASH+RANGE) from the base table;
- Speed up queries on non-key attributes;
- The Index Key consists of scalar attributes (String, Number, or Binary);
- Attribute Projections – some or all the attributes of the base table (KEYS_ONLY, INCLUDE, ALL);
- Must provision RCUs & WCUs for the index;
- Can be added/modified after table creation.

## DynamoDB – Indexes and Throttling
1. Global Secondary Index (GSI):
- If the writes are throttled on the GSI, then the main table will be throttled! Even if the WCU on the main tables are fine.
- Choose your GSI partition key carefully!
- Assign your WCU capacity carefully!
2. Local Secondary Index (LSI):
- Uses the WCUs and RCUs of the main table;
- No special throttling consideration.

## DynamoDB Accelerator (DAX)
- Fully-managed, highly available, seamless inmemory cache for DynamoDB
- Microseconds latency for cached reads & queries
- Doesn’t require application logic modification (compatible with existing DynamoDB APIs)
- Solves the “Hot Key” problem (too many reads)
- 5 minutes TTL for cache (default)
- Up to 10 nodes in the cluster
- Multi-AZ (3 nodes minimum recommended for production)
- Secure (Encryption at rest with KMS, VPC, IAM, CloudTrail, …)

## DynamoDB Accelerator (DAX) vs. ElastiCache
![image](https://github.com/user-attachments/assets/e0e892d2-ac00-4630-9404-4f2df63cf2e2)

## DynamoDB Streams
- Ordered stream of item-level modifications (create/update/delete) in a table
- Stream records can be:
  - Sent to Kinesis Data Streams
  - Read by AWS Lambda
  - Read by Kinesis Client Library applications
- Data Retention for up to 24 hours
- Use cases:
  - react to changes in real-time (welcome email to users)
  - Analytics
  - Insert into derivative tables
  - Insert into OpenSearch Service
  - Implement cross-region replication
![image](https://github.com/user-attachments/assets/24029356-c6ed-4ae9-b25d-7ebeafa2a115)
Ability to choose the information that will be written to the stream:
- KEYS_ONLY – only the key attributes of the modified item
- NEW_IMAGE – the entire item, as it appears after it was modified
- OLD_IMAGE – the entire item, as it appeared before it was modified
- NEW_AND_OLD_IMAGES – both the new and the old images of the item
DynamoDB Streams are made of shards, just like Kinesis Data Streams. You don’t provision shards, this is automated by AWS.

## DynamoDB Streams & AWS Lambda
- You need to define an Event Source Mapping to read from a DynamoDB Streams;
- You need to ensure the Lambda function has the appropriate permissions;
- Your Lambda function is invoked synchronously.

## DynamoDB – Time To Live (TTL)
1. Automatically delete items after an expiry timestamp
2. Doesn’t consume any WCUs (i.e., no extra cost)
3. The TTL attribute must be a “Number” data type with “Unix Epoch timestamp” value
4. Expired items deleted within 48 hours of expiration
5. Expired items, that haven’t been deleted, appears in reads/queries/scans (if you don’t want them, filter them out)
6. Expired items are deleted from both LSIs and GSIs
7. A delete operation for each expired item enters the DynamoDB Streams (can help recover expired items)
`Use cases: reduce stored data by keeping only current items, adhere to regulatory obligations`
![Untitled](https://github.com/user-attachments/assets/682af4ea-2b6f-42e4-b2b8-92d7c218f4bc)

##DynamoDB – Large Objects Pattern
![Untitled](https://github.com/user-attachments/assets/498cb597-e253-4b4d-9157-148b98d5fe13)

## DynamoDB – Indexing S3 Objects Metadata
![image](https://github.com/user-attachments/assets/867984fc-0ca4-420d-9cb0-ec0433e43830)
## DynamoDB – Security & Other Features
1. Security
  - VPC Endpoints available to access DynamoDB without using the Internet
  - Access fully controlled by IAM
  - Encryption at rest using AWS KMS and in-transit using SSL/TLS
2. Backup and Restore feature available
  - Point-in-time Recovery (PITR) like RDS
  - No performance impact
3. Global Tables
  - Multi-region, multi-active, fully replicated, high performance
4. DynamoDB Local
  - Develop and test apps locally without accessing the DynamoDB web service (without Internet)
5. AWS Database Migration Service (AWS DMS) can be used to migrate to DynamoDB (from MongoDB, Oracle, MySQL, S3, …)

## DynamoDB – Users Interact with DynamoDB Directly
![Untitled](https://github.com/user-attachments/assets/88bdaee6-3540-42b8-826f-6a3a858cdbc1)

##DynamoDB – Fine-Grained Access Control
- Using Web Identity Federation or Cognito Identity Pools, each user gets AWS credentials;
- You can assign an IAM Role to these users with a Conditionto limit their API access to DynamoDB;
- LeadingKeys – limit row-level access for users on the Primary Key;
- Attributes – limit specific attributes the user can see.
![image](https://github.com/user-attachments/assets/89d6beca-9afd-45a5-93ce-94e6e2e299f4)

# Amazon RDS
Relational Database Service
## What is RDS?
- Hosted relational database
  - Amazon Aurora
  - MySQL
  - PostgreSQL
  - MariaDB (Open Source MySQL)
  - Oracle
  - SQL Server
- Not for “big data”
- Might appear on exam as an example of what not to use
- Or in the context of migrating from RDS to Redshift etc;

## Amazon Aurora
- MySQL and PostgreSQL – compatible;
- Up to 5X faster than MySQL, 3X faster than PostgreSQL;
- 1/10 the cost of commercial databases;
- Up to 128TB per database volume;
- Up to 15 read replicas;
- Continuous backup to S3;
- Replication across regions and availability zones;
- Automatic scaling with Aurora Serverless.

## Aurora Security 
- VPC network isolation
- At-rest with KMS
- Data, backup, snapshots, and replicas can be encrypted
- In-transit with SSL

## Using the LOCK command
- Relational databases implicitly “lock” tables to prevent two things writing to it at the same time, or reading while a write is in process.
- Tables or rows can also be explicitly locked to ensure data integrity and concurrency control.
- Types of locks: 
  - **Shared Locks**: Allow reads, prevent writes. Can be held by multiple transactions. (FOR SHARE)
  - **Exclusive Locks**: Prevent all reads and writes to a resource. Only one transaction can hold an exclusive lock.(FORE UPDATE)
 
 ## Examples (MySQL)
- **Lock an entire table**
  - `LOCK TABLES employees WRITE;` -- Locks the entire 'employees' table for write operations
  - Use `UNLOCK TABLES;` to release the lock.
  - Note: Redshift also has a LOCK command for the same purpose
- **Shared lock** (allow reads, prevent other writes during this transaction.)
  - `SELECT * FROM employees WHERE department = 'Finance' FOR SHARE;`
- **Exclusive lock** (prevent all reads and writes during this transaction)
  - `SELECT * FROM employees WHERE employee_id = 123 FOR UPDATE;`
Make sure the transactions any locks are in complete, or you could end up with a "deadlock".

## Amazon RDS best practices
**Amazon RDS operational guidelines**
1. Use **CloudWatch** to monitor memory, CPU, storage, replica lag;
2. Perform automatic **backups** during daily low in write IOPS;
3. **Insufficient I/O** will make recovery after failure slow
  - Migrate to DB instance with more I/O
  - Move to General Purpose or Provisioned IOPS storage
4. Set **TTL** on DNS for your DB instances to 30 seconds or less from your apps;
5. Test **failover** before you need it;
6. Provision **enough RAM** to include your entire working set;
  - If your ReadIOPS metric is small and stable, you’re good
7. **Rate limits** in Amazon API Gateway can be used to protect your databas.

## Query optimization in RDS
1. Use **indexes** to accelerate SELECT statements;
2. Use **EXPLAIN plans** to identify the indexes you need;
3. Avoid full table scans;
4. Use **ANALYZE TABLE** periodically ;
5. Simplify WHERE clauses;
6. Engine-specific optimizations.

## DB-specific tweak
- **SQL Server**
  - Use RDS DB Events to monitor failovers;
  - Do not enable simple recover mode, offline mode, or read-only mode (this breaks Multi-AZ);
  - Deploy into all AZ’s.
- **Oracle is its own beast**

## DocumentDB
- Aurora is an “AWS-implementation” of PostgreSQL / MySQL ;
- DocumentDB is the same for MongoDB (which is a NoSQL database);
- MongoDB is used to store, query, and index JSON data;
- Similar “deployment concepts” as Aurora;
- Fully Managed, highly available with replication across 3 AZ;
- DocumentDB storage automatically grows in increments of 10GB;
- Automatically scales to workloads with millions of requests per second.

## Amazon MemoryDB for Redis
**Redis** - compatible, durable, in-memory database service
- Ultra-fast performance with over 160 millions requests/second;
- Durable in-memory data storage with Multi-AZ transactional log;
- Scale seamlessly from 10s GBs to 100s TBs of storage.
`Use cases: web and mobile apps, online gaming, media streaming`
![image](https://github.com/user-attachments/assets/b39ed835-cd4a-47a1-bd72-b911cb9ef5d4)

## Amazon Keyspaces (for Apache Cassandra)
**Apache Cassandra** is an open-source NoSQL distributed database
- A managed Apache Cassandra-compatible database service;
- Serverless, Scalable, highly available, fully managed by AWS;
- Automatically scale tables up/down based on the application’s traffic;
- Tables are replicated 3 times across multiple AZ;
- Using the Cassandra Query Language (CQL);
- Single-digit millisecond latency at any scale, 1000s of requests per second;
- Capacity: On-demand mode or provisioned mode with auto-scaling;
- Encryption, backup, Point-In-Time Recovery (PITR) up to 35 days.

`Use cases: store IoT devices info, time-series data...`

## Amazon Neptune
Fully managed graph database 
- A popular graph dataset would be a social network:
  - Users have friends
  - Posts have comments
  - Comments have likes from users
  - Users share and like posts…
- Highly available across 3 AZ, with up to 15 read replicas;
- Build and run applications working with highly connected datasets – optimized for these complex and hard queries;
- Can store up to billions of relations and query the graph with milliseconds latency;
- Highly available with replications across multiple AZs;
- Great for knowledge graphs (Wikipedia), fraud detection, recommendation engines, social networking.

## Amazon Timestream
- Fully managed, fast, scalable, serverless time series database;
- Automatically scales up/down to adjust capacity;
- Store and analyze trillions of events per day;
- 1000s times faster & 1/10th the cost of relational databases;
- Scheduled queries, multi-measure records, SQL compatibility;
- Data storage tiering: recent data kept in memory and historical data kept in a cost-optimized storage;
- Built-in time series analytics functions (helps you identify patterns in your data in near real-time);
- Encryption in transit and at rest.

`Use cases: IoT apps, operational applications, real-time analytics.`

## Amazon Timestream – Architecture
![image](https://github.com/user-attachments/assets/9178b265-0f02-44de-b1af-5cbe7b792a5a)

# Amazon Redshift
**Fully-managed, petabyte-scale data warehouse**
## What is Redshift?
- Fully-managed, petabyte scale data warehouse service;
- 10X better performance than other DW’s
  - Via machine learning
  - Massively parallel query execution
  - Columnar storage
- Designed for OLAP, not OLTP;
- Cost effective;
- SQL, ODBC, JDBC interfaces;
- Scale up or down on demand;
- Built-in replication & backups;
- Monitoring via CloudWatch / CloudTra.

## Redshift Use-Cases
- Accelerate analytics workloads;
- Unified data warehouse & data lake;
- Data warehouse modernization;
- Analyze global sales data;
- Store historical stock trade data;
- Analyze ad impressions & clicks;
- Aggregate gaming data;
- Analyze social trends.

## Redshift architecture
![image](https://github.com/user-attachments/assets/d07efbf9-2437-4f5c-94fe-d195237fb1c1)

## Redshift Spectrum 
- Query exabytes of unstructured data in S3 without loading;
- Limitless concurrency;
- Horizontal scaling;
- Separate storage & compute resources;
- Wide variety of data formats;
- Support of Gzip and Snappy compression.

## Redshift Performance
- Massively Parallel Processing (MPP);
- Columnar Data Storage;
- Column Compression.

## Redshift Durability
- Replication within cluster
- Backup to S3
  - Asynchronously replicated to another region
- Automated snapshots
- Failed drives / nodes automatically replaced
- However – limited to a single availability zone (AZ)
  - Multi-AZ for RA3 clusters now available

## Scaling Redshift
- Vertical and horizontal scaling on demand;
  - During scaling a new cluster is created while your old one remains available for reads;
- CNAME is flipped to new cluster (a few minutes of downtime);
- Data moved in parallel to new compute nodes.

## Redshift Distribution Styles
- **AUTO**
  - Redshift figures it out based on size of data
- **EVEN**
  - Rows distributed across slices in round-robin
![image](https://github.com/user-attachments/assets/b059f7c0-3d20-4539-b6ef-acd12c8054ca)
- **KEY**
  - Rows distributed based on one column
![image](https://github.com/user-attachments/assets/af1989cb-a4ea-4f4a-8511-14cd6905ccab)
- **ALL**
  - Entire table is copied to every node
![image](https://github.com/user-attachments/assets/22bcfe42-4602-479d-9064-9a8a84228d0f)

## Importing / Exporting data - 
- `COPY` command;
  - Parallelized; efficient
  - From S3, EMR, DynamoDB, remote hosts
  - S3 requires a manifest file and IAM role
- `UNLOAD` command;
  - Unload from a table into files in S3
- Enhanced VPC routing;
- Auto-copy from Amazon S3;
- Amazon Aurora zero-ETL integration;
  - Auto replication from Aurora -> Redshift
- Redshift Streaming Ingestion;
  - From Kinesis Data Streams or MSK

 ## COPY command
- Use COPY to load large amounts of data from outside of Redshift;
- If your data is already in Redshift in another table;
  - Use `INSERT INTO …SELECT`
  - Or `CREATE TABLE AS`
- `COPY` can decrypt data as it is loaded from S3;
  - Hardware-accelerated SSL used to keep it fast
- `Gzip`, `lzop`, and `bzip2` compression supported to speed it up further;
- Automatic compression option;
  - Analyzes data being loaded and figures out optimal compression scheme for storing it
- Special case: narrow tables (lots of rows, few columns);
  - Load with a single `COPY` transaction if possible
  - Otherwise hidden metadata columns consume too much space

## Redshift copy grants for cross-region snapshot copies
Let’s say you have a KMS-encrypted Redshift cluster and a snapshot of it. You want to copy that snapshot to another region for backup.
- In the destination AWS region:
  - Create a KMS key if you don’t have one already
  - Specify a unique name for your snapshot copy grant
  - Specify the KMS key ID for which you’re creating the copy grant
- In the source AWS region:
  - Enable copying of snapshots to the copy grant you just created
 
## DBLINK
- Connect Redshift to PostgreSQL (possibly in RDS);
- Good way to copy and sync data between PostgreSQL and Redshift.
  CREATE EXTENSION postgres_fdw;
  
`CREATE EXTENSION dblink;
CREATE SERVER foreign_server
FOREIGN DATA WRAPPER postgres_fdw
OPTIONS (host '<amazon_redshift _ip>', port '<port>', dbname '<database_name>', sslmode
'require');
CREATE USER MAPPING FOR <rds_postgresql_username>
SERVER foreign_server
OPTIONS (user '<amazon_redshift_username>', password '<password>')`

## Integration with other services
1. S3
2. DynamoDB
3. EMR / EC2
4. Data Pipeline
5. Database Migration Service
![image](https://github.com/user-attachments/assets/c4a5ed18-1390-42a4-833b-25b8961cef03)

## Redshift Workload Management (WLM)
- Prioritize short, fast queries vs. long, slow queries
- Query queues
- Via console, CLI, or API

## Concurrency Scaling
- Automatically adds cluster capacity to handle increase in concurrent read queries
- Support virtually unlimited concurrent users & queries
- WLM queues manage which queries are sent to the concurrency scaling cluster

## Automatic Workload Management
- Creates up to 8 queues
- Default 5 queues with even memory allocation
- Large queries (ie big hash joins) -> concurrency lowered
- Small queries (ie inserts, scans, aggregations) -> concurrency raised
  - Configuring query queues
  - Priority
  - Concurrency scaling mode
  - User
  - Query groups
  - Query monitoring rules
 
## Manual Workload Management
- One default queue with concurrency level of 5 (5 queries at once)
- Superuser queue with concurrency level 1
- Define up to 8 queues, up to concurrency level 50
- Each can have defined concurrency scaling mode, concurrency level, user groups, query groups, memory, timeout, query monitoring rules
  - Can also enable query queue hopping
  - Timed out queries “hop” to next queue to try again

## Short Query Acceleration (SQA)
- Prioritize short-running queries over longer-running ones
- Short queries run in a dedicated space, won’t wait in queue behind long queries
- Can be used in place of WLM queues for short queries
- Works with:
  - `CREATE TABLE AS` (CTAS)
  - Read-only queries (SELECT statements)
- Uses machine learning to predict a query’s execution time
- Can configure how many seconds is “short” sundog

## Resizing Redshift Clusters
- Elastic resize
  - Quickly add or remove nodes of same type
    - (It *can* change node types, but not without dropping connections – it creates a whole new cluster)
  - Cluster is down for a few minutes
  - Tries to keep connections open across the downtime
  - Limited to doubling or halving for some dc2 and ra3 node types.
- Classic resize
  - Change node type and/or number of nodes
  - Cluster is read-only for hours to days
- Snapshot, restore, resize
  - Used to keep cluster available during a classic resize
  - Copy cluster, resize new cluster

## VACUUM command
- Recovers space from deleted rows and restores sort order;
- `VACUUM FULL`;
- `VACUUM DELETE ONLY`;
  - Skips the sort ;
- `VACUUM SORT ONLY `;
  - Does not reclaim space!;
- VACUUM REINDEX;
  - Re-analyzes distribution of sort key columns;
  - Then does a full VACUUM.
 
## Newer Redshift features
- **RA3 nodes with managed storage**;
  - Enable independent scaling of compute and storage;
  - SSD-based;
- R**edshift data lake export**;
  - Unload Redshift query to S3 in Apache Parquet format;
  - Parquet is 2x faster to unload and consumes up to 6X less storage;
  - Compatible with Redshift Spectrum, Athena, EMR, SageMaker;
  - Automatically partitioned;
- **Spatial data types**;
  - GEOMETRY, GEOGRAPHY;
- **Cross-Region Data Sharing**;
  - Share live data across Redshift clusters without copying;
  - Requires new RA3 node type;
  - Secure, across regions and across accounts.

## Redshift anti-patterns
- **Small data sets**;
  - Use RDS instead;
-** OLTP**;
  - Use RDS or DynamoDB instead;
- **Unstructured data**;
  - ETL first with EMR etc;
- **BLOB data**;
  - Store references to large binary files in S3, not the files themselves.

## Redshift security concerns
- Using a Hardware Security Module **(HSM)**;
  - Must use a client and server certificate to configure a trusted connection between Redshift and the HSM;
  - If migrating an unencrypted cluster to an HSM-encrypted cluster, you must create the new encrypted cluster and then move data to it;
- Defining access privileges for user or group
  - Use the `GRANT` or `REVOKE` commands in SQL
  - Example: grant select on table foo to bob.

## Redshift Serverless
- Automatic scaling and provisioning for your workload;
- Optimizes costs & performance;
  - Pay only when in use;
- Uses ML to maintain performance across variable & sporadic workloads;
- Easy spinup of development and test environments;
- Easy ad-hoc business analysis;
- You get back a serverless endpoint, JDBC/ODBC connection, or just query via the console’s query editor.


## Redshift Serverless: Monitoring
**Monitoring views**
  - `SYS_QUERY_HISTORY`
  - `SYS_LOAD_HISTORY`
  - `SYS_SERVERLESS_USAGE`
**CloudWatch logs**
  - Connection & user logs enabled by default
  - Optional user activity log data
  - Under /aws/redshift/serverless/
**CloudWatch metrics**
  - QueriesCompletedPerSecond, QueryDuration, QueriesRunning,etc.
  - Dimensions: DatabaseName, latency (short/medium/long), QueryType, stage.

## Redshift Materialized Views
- Contain precomputed results based on SQL queries over one or more base tables;
  - This differs from a “normal” view in that it actually stores the results of the query;
- Provide a way to speed up complex queries in a data warehouse environment, especially on large tables;
- You can query materialized views just like any other tables or views;
- Queries return results faster since they use precomputed results without accessing base tables;
- They're particularly beneficial for predictable and recurring queries, e.g., populating dashboards like Amazon QuickSight.

## Using Materialized Views
- `CREATE MATERIALIZED VIEW`…;
- Keeping them refreshed;
  - `REFRESH MATERIALIZED VIEW`…;
  - Set `AUTO REFRESH` option on creation;
- Query them just like any other table or view;
- Materialized views can be built from other materialized views;
  - Useful for re-using expensive joins.

           CREATE MATERIALIZED VIEW tickets_mv AS
           select catgroup,
           sum(qtysold) as sold
           from category c, event e, sales s
           where c.catid = e.catid
           and e.eventid = s.eventid
           group by catgroup;

## Redshift System Tables and Views
- Contains info about how Redshift is functioning;
- Types of system tables / views;
  - **SYS views**: Monitor query & workload usage;
  - **STV tables**: Transient data containing snapshots of current system data;
  - **SVV views**: metadata about DB objects that reference STV tables;
  - **STL views**: Generated from logs persisted to disk;
  - **SVCS views**: Details about queries on main & concurrency scaling clusters;
  - **SVL views**: Details about queries on main clusters;
- Many system monitoring views & tables are only for provisioned clusters, not serverles.

# Migration and Transfer
Moving data into AWS

## AWS Application Discovery Service
- Plan migration projects by gathering information about on-premises data centers;
- Server utilization data and dependency mapping are important for migrations;
- Agentless Discovery (AWS Agentless Discovery Connector);
  - VM inventory, configuration, and performance history such as CPU, memory, and disk usage;
- Agent-based Discovery (AWS Application Discovery Agent);
  - System configuration, system performance, running processes, and details of the network connections between systems;
- Resulting data can be viewed within AWS Migration Hub.

## AWS Application Migration Service (MGN)
- The “AWS evolution” of CloudEndure Migration, replacing AWS Server Migration Service (SMS);
- Lift-and-shift (rehost) solution which simplify migrating applications to AWS;
- Converts your physical, virtual, and cloud-based servers to run natively on AWS;
- Supports wide range of platforms, Operating Systems, and databases;
- Minimal downtime, reduced costs.
![Untitled](https://github.com/user-attachments/assets/6bed617f-92b2-4c67-af7e-47e8927e57b0)

## DMS – Database Migration Service
- Quickly and securely migrate databases to AWS, resilient, self healing;
- The source database remains available during the migration;
- Supports:
  - Homogeneous migrations: ex Oracle to Oracle;
  - Heterogeneous migrations: ex Microsoft SQL Server to Aurora;
- Continuous Data Replication using CDC;
- You must create an EC2 instance to perform the replication tasks.

## DMS Sources and Targets
|SOURCES  |  TARGETS |
| ------------- | ------------- |
| On-Premises and EC2 instances databases: Oracle, MS SQL Server, MySQL, MariaDB, PostgreSQL, MongoDB, SAP, DB2 | On-Premises and EC2 instances databases: Oracle, MS SQL Server, MySQL, MariaDB, PostgreSQL, SAP |
| Azure: Azure SQL Database | Amazon RDS |
| Amazon RDS: all including Aurora | Redshift, DynamoDB, S3 |
| Amazon S3 | OpenSearch Service |
| DocumentDB | Kinesis Data Streams |
|  | Apache Kafka |
|  | DocumentDB & Amazon Neptune |
|  | Redis & Babelfish |

## AWS Schema Conversion Tool (SCT)
- Convert your Database’s Schema from one engine to another;
- Example OLTP: (SQL Server or Oracle) to MySQL, PostgreSQL, Aurora;
- Example OLAP: (Teradata or Oracle) to Amazon Redshift;
- Prefer compute-intensive instances to optimize data conversions;
![image](https://github.com/user-attachments/assets/e99f205d-b79a-4520-82c1-3e137957704d)
- **You do not need to use SCT if you are migrating the same DB engine**;
  - Ex: On-Premise PostgreSQL => RDS PostgreSQL;
  - The DB engine is still PostgreSQL (RDS is the platform).

## DMS - Continuous Replication
![image](https://github.com/user-attachments/assets/6f5d71b8-9a4b-4579-8ab8-21d0c6bb273a)

## AWS DMS – Multi-AZ Deployment
- When Multi-AZ Enabled, DMS provisions and maintains a synchronously stand replica in a different AZ;
- Advantages:
  - Provides Data Redundancy;
  - Eliminates I/O freezes;
  - Minimizes latency spike.
![image](https://github.com/user-attachments/assets/6774ddaf-33ed-4c28-abd4-899b7bb49de7)

## AWS DataSync
- Move large amount of data to and from;
  - On-premises / other cloud to AWS (NFS, SMB, HDFS, S3 API…) –needs agent;
  - AWS to AWS (different storage services) – no agent needed;
- Can synchronize to:
  - Amazon S3 (any storage classes – including Glacier);
  - Amazon EFS;
  - Amazon FSx (Windows, Lustre, NetApp, OpenZFS...);
- Replication tasks can be scheduled hourly, daily, weekly;
- File permissions and metadata are preserved (NFS POSIX, SMB…);
- One agent task can use 10 Gbps, can setup a bandwidth limit.

## AWS DataSyncNFS / SMB to AWS (S3, EFS, FSx…)
![Untitled](https://github.com/user-attachments/assets/87b2655e-cc94-4002-aeb2-85e36c4149da)

## AWS DataSyncTransfer between AWS storage services
![image](https://github.com/user-attachments/assets/cd30dc12-7a73-4452-982f-1b134bacbf0a)

## AWS Snow Family
- Highly-secure, portable devices to collect and process data at the edge, and migrate data into and out of AWS
![image](https://github.com/user-attachments/assets/1a4252c4-5b7a-4437-8f62-af3ec83d500e)

## Data Migrations with AWS Snow Family
Challenges:
- Limited connectivity;
- Limited bandwidth;
- High network cost;
- Shared bandwidth (can’t maximize the line);
- Connection stability.
**AWS Snow Family: offline devices to perform data migrations If it takes more than a week to transfer over the network, use Snowball devices!**
![image](https://github.com/user-attachments/assets/4082b404-e9e5-4f92-9668-b34394171a23)

## Diagrams
- Direct upload to S3
![image](https://github.com/user-attachments/assets/aefdc116-51b6-4851-b3ac-87c327a04d9e)
- With Snow Family
![image](https://github.com/user-attachments/assets/d705780b-763a-4dfe-b345-23296082f815)

## Snow Family – Usage Process
1. Request Snowball devices from the AWS console for delivery;
2. Install the snowball client / AWS OpsHub on your servers;
3. Connect the snowball to your servers and copy files using the client;
4. Ship back the device when you’re done (goes to the right AWS facility);
5. Data will be loaded into an S3 bucket;
6. Snowball is completely wiped.

## What is Edge Computing?
- Process data while it’s being created on an edge location;
  - A truck on the road, a ship on the sea, a mining station underground...;
- These locations may have limited internet and no access to computing power;
- We setup a Snowball Edge / Snowcone device to do edge computing;
  - Snowcone: 2 CPUs, 4 GB of memory, wired or wireless access;
  - Snowball Edge Compute Optimized (dedicated for that use case) & Storage Optimized;
  - Run EC2 Instances or Lambda functions at the edge;
- Use cases: preprocess data, machine learning, transcoding media.

## AWS Transfer Family
- A fully-managed service for file transfers into and out of Amazon S3 orAmazon EFS using the FTP protocol
- Supported Protocols;
  - **AWS Transfer for FTP** (File Transfer Protocol (FTP));
  - **AWS Transfer for FTPS** (File Transfer Protocol over SSL (FTPS));
  - **AWS Transfer for SFTP** (Secure File Transfer Protocol (SFTP));
- Managed infrastructure, Scalable, Reliable, Highly Available (multi-AZ);
- Pay per provisioned endpoint per hour + data transfers in GB;
- Store and manage users’ credentials within the service;
- Integrate with existing authentication systems (Microsoft Active Directory, LDAP, Okta, Amazon Cognito, custom);
- Usage: sharing files, public datasets, CRM, ERP.

## AWS Transfer Family
![image](https://github.com/user-attachments/assets/693eff16-fa32-4872-af47-514164da3c80)

# Compute
Transforming Data in AWS

## EC2 in Big Data
- On demand, Spot & Reserved instances:
  - Spot: can tolerate loss, low cost => checkpointing feature (ML, etc);
  - Reserved: long running clusters, databases (over a year);
  - On demand: remaining workloads;
- Auto Scaling: 
  - Leverage for EMR, etc;
  - Automated for DynamoDB, Auto Scaling Groups, etc…;
- EC2 is behind EMR ;
  - Master Nodes;
  - Compute Nodes (contain data) + Tasks Nodes (do not contain data).

## AWS Graviton
- Amazon’s own family of processors, powers several EC2 instance types;
  - General purpose: M7, T4;
  - Compute optimized: C7, C6;
  - Memory optimized: R7, X2;
  - Storage optimized: Im4, Is4;
  - Accelerated computing (game streaming, ML inference): G5;
- Offers best price performance;
- Option for many data engineering services;
  - MSK, RDS, MemoryDB, ElastiCache, OpenSearch, EMR, Lambda, Fargat.

# AWS Lambda
Serverless data processing

## What is Lambda?
- A way to run code snippets “in thecloud”;
- Serverless;
- Continuous scaling;
- Often used to process data as it’s moved around.

## Example: Serverless Website
![image](https://github.com/user-attachments/assets/20fc7820-867a-46f2-9681-e430d353d026)

## Example:Order history app
![image](https://github.com/user-attachments/assets/a4217867-3d72-47de-8a63-0b8d8cdb3aa7)

## Example: Transaction rate alarm
![image](https://github.com/user-attachments/assets/4298850d-017f-48ba-805f-d5a3cf5f0784)

## Why not just run a server?
1. Server management (patches, monitoring, hardware failures, etc.);
2. Servers can be cheap, but scaling gets expensive really fast;
3. You don’t pay for processing time you don’t use;
4. Easier to split up development between front-end and back-end.

## Main uses of Lambda
1. Real-time file processing;
2. Real-time stream processing;
3. ETL;
4. Cron replacement;
5. Process AWS events.

## Supported languages
- Node.js;
- Python;
- Java;
- C#;
- Go;
- Powershell;
- Ruby.

## Lambda and Amazon Opensearch Service
![image](https://github.com/user-attachments/assets/3cb7c381-6e31-41d1-bc1d-04a5c0994474)

## Lambda and Data Pipeline
![image](https://github.com/user-attachments/assets/44400677-ed0b-4553-965d-555b2dbb93e9)

## Lambda and Redshift
Best practice for loading data into Redshift is the COPY command;
But, you can use Lambda if you need to respond to new data that shows up at any time;
Can use DynamoDB to keep track of what’s been loaded.Lambda can batch up new data and load them with COPY.
![image](https://github.com/user-attachments/assets/92c95a12-8ad8-45b8-bb54-4847e796a9f5)

## Lambda + Kinesis
- Your Lambda code receives an event with a batch of stream records;
  - You specify a batch size when setting up the trigger (up to 10,000 records);
  - Too large a batch size can cause timeouts!;
  - Batches may also be split beyond Lambda’s payload limit (6 MB);
- Lambda will retry the batch until it succeeds or the data expires;
  - This can stall the shard if you don’t handle errors properly;
  - Use more shards to ensure processing isn’t totally held up by errors;
- Lambda processes shard data synchronousl.
![image](https://github.com/user-attachments/assets/44967643-a050-4651-aa02-b35193aeffc1)

## Cost Model
- “Pay for what you use”
- Generous free tier (1M requests / month, 400K GB-seconds compute time)
- $0.20 / million requests
- $.00001667 per GB/second

## Other promises
- High availability;
  - No scheduled downtime;
  - Retries failed code 3 times;
- Unlimited scalability*;
  - Safety throttle of 1,000 concurrent executions per region;
-  High performance;
  -  New functions callable in seconds;
  -  Events processed in milliseconds;
  -  Code is cached automatically;
  -  But you do specify a timeout! This can cause problems. Max is 900 seconds (15 min).

## Anti-patterns
- Long-running applications;
  - Use EC2 instead, or chain functions;
- Dynamic websites;
  - Although Lambda can be used to develop “serverless” apps that rely on client-side AJAX;
- Stateful applications;
  - But you can work in DynamoDB or S3 to keep track of state.
 
## Lambda – File Systems Mounting
- Lambda functions can access EFS file systems if they are running in a VPC;
- Configure Lambda to mount EFS file systems to local directory during initialization;
- Must leverage EFS Access Points;
- Limitations: watch out for the EFS connection limits (one function instance = one connection) and connection burst limit.

## Lambda – Storage Options
![image](https://github.com/user-attachments/assets/a5a1015f-30ce-4dea-bb04-228e2110035a)

## AWS SAM
**SAM** = **Serverless Application Model**
- Framework for developing and deploying serverless applications;
- All the configuration is YAML code;
- Generate complex CloudFormation from simple SAM YAML file;
- Supports anything from CloudFormation: Outputs, Mappings, Parameters, Resources… ;
- SAM can use CodeDeploy to deploy Lambda functions;
- SAM can help you to run Lambda, API Gateway, DynamoDB locally.

## AWS SAM – Recipe 
- **Transform Header indicates it’s SAM template**:
  - Transform: 'AWS::Serverless-2016-10-31';
- **Write Code**
  - AWS::Serverless::Function;
  - AWS::Serverless::Api;
  - AWS::Serverless::SimpleTable;
- **Package & Deploy**: sam deploy **(optionally preceded by** “sam package”**)**;
- Quickly sync local changes to AWS Lambda (SAM Accelerate): `sam sync --watch`.

## Deep Dive into SAM Deployment
![image](https://github.com/user-attachments/assets/2804058e-40f2-47f1-aa8d-ae0aba26b06d)

## SAM Accelerate (sam sync)
- SAM Accelerate is a set of features to reduce latency while deploying resources to AWS;
- sam sync;
  - Synchronizes your project declared in SAM templates to AWS;
  - Synchronizes code changes to AWS without updating infrastructure (uses service APIs & bypass CloudFormation).
![image](https://github.com/user-attachments/assets/42c6c583-327e-4bab-896a-0b3092819ceb)

## SAM Accelerate (sam sync) – Examples
- `sam sync` (no options);
  - Synchronize code and infrastructure;
- `sam sync --code`;
  - Synchronize code changes without updating infrastructure (bypass CloudFormation, update in seconds);
- `sam sync --code --resource AWS::Serverless::Function`;
  - Synchronize only all Lambda functions and their dependencies;
- `sam sync --code --resource-id HelloWorldLambdaFunction`;
  - Synchronize only a specific resource by its ID;
- `sam sync --watch`;
  - Monitor for file changes and automatically synchronize when changes are detected;
  - If changes include configuration, it uses `sam sync`;
  - If changes are code only, it uses `sam sync --code`.

## SAM – CLI Debugging
- Locally build, test, and debug your serverless applications that are defined using AWS SAM templates;
- Provides a lambda-like execution environment locally;
- SAM CLI + AWS Toolkits => stepthrough and debug your code;
- Supported IDEs: AWS Cloud9, Visual Studio Code, JetBrains, PyCharm, IntelliJ, …;
- **AWS Toolkits**: IDE plugins which allows you to build, test, debug, deploy, and invoke Lambda functions built using AWS SAM.

![image](https://github.com/user-attachments/assets/04b07660-96c6-4e26-b5d6-6354558069de)

## AWS Batch
- Run batch jobs as Docker images;
- Dynamic provisioning of the instances (EC2 & Spot Instances);
- Optimal quantity and type based on volume and requirements;
- No need to manage clusters, fully serverless;
- You just pay for the underlying EC2 instances;
- Schedule Batch Jobs using CloudWatch Events;
- Orchestrate Batch Jobs using AWS Step Functions.

## AWS Batch vs Glue
- **Glue**:
  - Glue ETL - Run Apache Spark code, Scala or Python based, focus on the ETL;
  - Glue ETL - Do not worry about configuring or managing the resources;
  - Data Catalog to make the data available to Athena or Redshift Spectrum.
- **Batch**:
  - For any computing job regardless of the job (must provide Docker image);
  - Resources are created in your account, managed by Batch;
  - For any non-ETL related work, Batch is probably bette.

# Containers
Packaging applications in AWS

## What is Docker?
- Docker is a software development platform to deploy apps;
- Apps are packaged in containers that can be run on any OS;
  - Apps run the same, regardless of where they’re run ;
  - Any machine;
  - No compatibility issues;
  - Predictable behavior;
  - Less work;
  - Easier to maintain and deploy;
  - Works with any language, any OS, any technology;
- **Use cases**: microservices architecture, lift-and-shift apps from on-premises to the AWS cloud.

## Docker on an OS
![image](https://github.com/user-attachments/assets/c012ba9b-b9b9-42a0-b4b0-03494a7e1a19)

## Where are Docker images stored?
- Docker images are stored in Docker Repositories;
- Docker Hub (https://hub.docker.com);
  - Public repository;
  - Find base images for many technologies or OS (e.g., Ubuntu, MySQL, …);
- Amazon ECR (Amazon Elastic Container Registry);
  - Private repository;
  - Public repository (Amazon ECR Public Gallery https://gallery.ecr.aws).

## Docker vs. Virtual Machines
- Docker is ”sort of” a virtualization technology, but not exactly;
- Resources are shared with the host => many containers on one server.
![image](https://github.com/user-attachments/assets/644c69db-4158-4fa7-9608-0d0d9bd6b3b9)

## Getting Started with Docker
![image](https://github.com/user-attachments/assets/27fa787a-bfab-404d-9930-1777bfb64302)

## Docker Containers Management on AWS
- Amazon Elastic Container Service (**Amazon ECS**);
  - Amazon’s own container platform;
- Amazon Elastic Kubernetes Service (**Amazon EKS**);
  - Amazon’s managed Kubernetes (open source);
- **AWS Fargate**:
  - Amazon’s own Serverless container platform;
  - Works with ECS and with EKS;
- **Amazon ECR**:
  - Store container images.

## Amazon ECS - EC2 Launch Type
- **ECS = Elastic Container Service**;
- Launch Docker containers on AWS = Launch ECS Tasks on ECS Clusters;
- **EC2 Launch Type: you must provision & maintain the infrastructure (the EC2 instances)**;
- Each EC2 Instance must run the ECS Agent to register in the ECS Cluster;
- AWS takes care of starting / stopping containers.

## Amazon ECS – Fargate Launch Type
- Launch Docker containers on AWS;
- **You do not provision the infrastructure (no EC2 instances to manage)**;
- **It’s all Serverless!**;
- You just create task definitions;
- AWS just runs ECS Tasks for you based on the CPU / RAM you need;
- To scale, just increase the number of tasks. Simple - no more EC2 instances.

## Amazon ECS – IAM Roles for ECS
- EC2 Instance Profile (EC2 Launch Type only): 
  - Used by the ECS agent;
  - Makes API calls to ECS service;
  - Send container logs to CloudWatch Logs;
  - Pull Docker image from ECR;
  - Reference sensitive data in Secrets Manager or SSM Parameter Store.
- **ECS Task Role**:
  - Allows each task to have a specific role;
  - Use different roles for the different ECS Services you run;
  - Task Role is defined in the **task definition**.
![Untitled](https://github.com/user-attachments/assets/5e1a7e00-1ad7-40af-91b8-633f2c82a3f9)

## Amazon ECS – Load Balancer Integrations
- **Application Load Balancer** supported and works for most use cases;
- **Network Load Balancer** recommended only for high throughput / high performance use cases, or to pair it with AWS Private Link;
- **Classic Load Balancer** supported but not recommended (no advanced features – no Fargate);
![image](https://github.com/user-attachments/assets/528f1982-d12b-4eb1-890b-5a7dce907f9b)

## Amazon ECS – Data Volumes (EFS)
- Mount EFS file systems onto ECS tasks;
- Works for both EC2 and Fargate launch types;
- Tasks running in any AZ will share the same data in the EFS file system;
- **Fargate + EFS = Serverless**;
- Use cases: persistent multi-AZ shared storage for your containers;
- **Note: Amazon S3 cannot be mounted as a file system**.
![image](https://github.com/user-attachments/assets/1d212c8d-47d0-45ba-8722-da3756cd0eb4)

## Amazon ECR
- **ECR = Elastic Container Registry**;
- Store and manage Docker images on AWS;
- Private and Public repository (Amazon ECR Public Gallery https://gallery.ecr.aws);
- Fully integrated with ECS, backed by Amazon S3;
- Access is controlled through IAM (permission errors => policy);
- Supports image vulnerability scanning, versioning, image tags, image lifecycle.
![image](https://github.com/user-attachments/assets/4ce0f1c3-1ea2-4594-9038-27f7afad93f5)

## Amazon EKS Overview
- Amazon EKS = Amazon Elastic Kubernetes Service;
- It is a way to launch managed Kubernetes clusters on AWS;
- Kubernetes is an open-source system for automatic deployment, scaling and management of containerized (usually Docker) application;
- It’s an alternative to ECS, similar goal but different API;
- EKS supports EC2 if you want to deploy worker nodes or Fargate to deploy serverless containers;
- Use case: if your company is already using Kubernetes on-premises or in another cloud, and wants to migrate to AWS using Kubernetes;
- **Kubernetes is cloud-agnostic (can be used in any cloud – Azure, GCP…)**;
- For multiple regions, deploy one EKS cluster per region;
- Collect logs and metrics using CloudWatch Container Insights.

![image](https://github.com/user-attachments/assets/623e0e30-0f6b-4c43-a789-674be65ec781)

## Amazon EKS – Node Types
- **Managed Node Groups**;
  - Creates and manages Nodes (EC2 instances) for you;
  - Nodes are part of an ASG managed by EKS;
  - Supports On-Demand or Spot Instances;
- **Self-Managed Nodes**;
  - Nodes created by you and registered to the EKS cluster and managed by an ASG;
  - You can use prebuilt AMI - Amazon EKS Optimized AMI;
  - Supports On-Demand or Spot Instances;
- **AWS Fargate**;
  - No maintenance required; no nodes manage.

## Amazon EKS – Data Volumes 
- Need to specify **StorageClass** manifest on your EKS cluster;
- Leverages a **Container Storage Interface (CSI)** compliant driver;
- Support for:
  - Amazon EBS;
  - Amazon EFS (works with Fargate);
  - Amazon FSx for Lustre;
  - Amazon FSx for NetApp ONTAP.
________________________________________________________________________________________________________________________________________________________________________________________________________

# Analytics

# AWS Glue 
Table definitions and ETL.

## What is Glue? 
- Serverless discovery and definition of table definitions and schema:
  - S3 “data lakes”;
  - RDS;
  - Redshift;
  - DynamoDB;
  - Most other SQL databases.
- Custom ETL jobs:
  - Trigger-driven, on a schedule, or on demand;
  - Fully managed.

## Glue Crawler / Data Catalog
- Glue crawler scans data in S3, creates schema;
- Can run periodically;
- Populates the Glue Data Catalog:
  - Stores only table definition;
  - Original data stays in S3;
- Once cataloged, you can treat your unstructured data like it’s structured:
  - Redshift Spectrum;
  - Athena;
  - EMR;
  - Quicksigh.
![image](https://github.com/user-attachments/assets/712648d5-5d47-43f5-9af6-fb8d41c1ada0)

## Glue and S3 Partitions
- Glue crawler will extract partitions based on how your S3 data is organized
- Think up front about how you will be querying your data lake in S3
- Example: devices send sensor data every hour
- Do you query primarily by time ranges?
  - If so, organize your buckets as yyyy/mm/dd/device
- Do you query primarily by device?
  - If so, organize your buckets as device/yyyy/mm/dd

## Glue + Hive
- Hive lets you run SQL-like queries from EMR;
- The Glue Data Catalog can serve as a Hive “metastore”;
- You can also import a Hive metastore into Glue.

## Glue ETL
- Automatic code generation;
- Scala or Python;
- Encryption:
  - Server-side (at rest);
  - SSL (in transit);
- Can be event-driven;
- Can provision additional “DPU’s” (data processing units) to increase performance of underlying Spark jobs;
  - Enabling job metrics can help you understand the maximum capacity in DPU’s you need;
- Errors reported to CloudWatch:
  - Could tie into SNS for notification.

## Glue ETL
- Transform data, Clean Data, Enrich Data (before doing analysis);
  - Generate ETL code in Python or Scala, you can modify the code;
  - Can provide your own Spark or PySpark scripts;
  - Target can be S3, JDBC (RDS, Redshift), or in Glue Data Catalog;
- Fully managed, cost effective, pay only for the resources consumed;
- Jobs are run on a serverless Spark platform;
- Glue Scheduler to schedule the jobs;
- Glue Triggers to automate job runs based on "events".

## Glue ETL: The DynamicFrame
- A DynamicFrame is a collection of DynamicRecords;
- DynamicRecords are self-describing, have a schema;
- Very much like a Spark DataFrame, but with more ETL stuff;
- Scala and Python APIs.

`val pushdownEvents = glueContext.getCatalogSource(
database = "githubarchive_month", tableName = "data“)
val projectedEvents = pushdownEvents.applyMapping(Seq(
("id", "string", "id", "long"), ("type", "string", "type",
"string"), ("actor.login", "string", "actor", "string"),
("repo.name", "string", "repo", "string"),
("payload.action", "string", "action", "string"),
("org.login", "string", "org", "string"), ("year",
"string", "year", "int"), ("month", "string", "month",
"int"), ("day", "string", "day", "int") ))`

## Glue ETL - Transformations
- **Bundled Transformations**:
  - DropFields, DropNullFields – remove (null) fields;
  - Filter – specify a function to filter records;
  - Join – to enrich data;
  - Map - add fields, delete fields, perform external lookups ;
- Machine Learning Transformations: 
  - FindMatches ML: identify duplicate or matching records in your dataset, even when the records do not have a common unique identifier and no fields match exactly; 
- Format conversions: CSV, JSON, Avro, Parquet, ORC, XML;
- Apache Spark transformations (example: K-Means);
  - Can convert between Spark DataFrame and Glue DynamicFram.

## Glue ETL: ResolveChoice
- Deals with ambiguities in a DynamicFrame and returns a new one;
- For example, two fields with the same name;
- make_cols: creates a new column for each type:
  - price_double, price_string;
- cast: casts all values to specified type;
- make_struct: Creates a structure that contains each data type;
- project: Projects every type to a given type, for example project:string.

`"myList": [ { "price": 100.00 }, { "price": "$100.00" }]`
`df1 = df.resolveChoice(choice = "make_cols") 
df2 = df.resolveChoice(specs = [("myList[].price", 
"make_struct"), ("columnA", "cast:double")])`

## Glue ETL: Modifying the Data Catalog
- ETL scripts can update your schema and partitions if necessary;
- Adding new partitions:
  - Re-run the crawler, or;
  - Have the script use enableUpdateCatalog and partitionKeys options;
- Updating table schema:
  - Re-run the crawler, or;
-   Use enableUpdateCatalog / updateBehavior from script;
- Creating new tables:
  - enableUpdateCatalog / updateBehavior with setCatalogInfo;
- Restrictions:
  - S3 only;
  - Json, csv, avro, parquet only;
  - Parquet requires special code;
  - Nested schemas are not supported.

## AWS Glue Development Endpoints
- Develop ETL scripts using a notebook;
  - Then create an ETL job that runs your script (using Spark and Glue);
- Endpoint is in a VPC controlled by security groups, connect via:
  - Apache Zeppelin on your local machine;
  - Zeppelin notebook server on EC2 (via Glue console);
  - SageMaker notebook;
  - Terminal window;
  - PyCharm professional edition;
  - Use Elastic IP’s to access a private endpoint address.

## Running Glue jobs
- Time-based schedules (cron style);
- Job bookmarks:
  - Persists state from the job run;
  - Prevents reprocessing of old data;
  - Allows you to process new data only when re-running on a schedule;
  - Works with S3 sources in a variety of formats; 
  - Works with relational databases via JDBC (if PK’s are in sequential order);
    - Only handles new rows, not updated rows;
- CloudWatch Events:
- Fire off a Lambda function or SNS notification when ETL succeeds or fails;
- Invoke EC2 run, send event to Kinesis, activate a Step Function.

## Glue cost model 
- Billed by the second for crawler and ETL jobs;
- First million objects stored and accesses are free for the Glue Data Catalog;
- Development endpoints for developing ETL code charged by the minute.

## Glue Anti-patterns
- Multiple ETL engines;
- Glue ETL is based on Spark;
- If you want to use other engines (Hive, Pig, etc) Data Pipeline EMR would be a better fit.

## No longer an anti-pattern: streaming
- As of April 2020, Glue ETL supports serverless streaming ETL;
  - Consumes from Kinesis or Kafka;
  - Clean & transform in-flight;
  - Store results into S3 or other data stores;
- Runs on Apache Spark Structured Streaming.

## AWS Glue Studio 
- Visual interface for ETL workflows;
- Visual job editor;
  - Create DAG’s for complex workflows;
  - Sources include S3, Kinesis, Kafka, JDBC;
  - Transform / sample / join data - Target to S3 or Glue Data Catalog;
  - Support partitioning;
- Visual job dashboard - Overviews, status, run times.

## AWS Glue Data Quality 
- Data quality rules may be created manually or recommended automatically;
- Integrates into Glue jobs - Uses Data Quality Definition Language (DQDL);
- Results can be used to fail the job, or just be reported to CloudWatch;
![image](https://github.com/user-attachments/assets/fb557b28-467e-4b57-9bbc-57c34cb9568d)

## AWS Glue DataBrew
- A visual data preparation tool:
  - UI for pre-processing large data sets;
  - Input from S3, data warehouse, or database;
  - Output to S3;
- Over 250 ready-made transformations;
- You create “recipes” of transformations that can be saved as jobs within a larger project;
- May define data quality rules;
- May create datasets with custom SQL from Redshift and Snowflake;
- Security:
  - Can integrate with KMS (with customer master keys only);
  - SSL in transit;
  - IAM can restrict who can do what;
  - CloudWatch & CloudTrai.

`{
 "RecipeAction": {
 "Operation": "NEST_TO_MAP",
 "Parameters": {
 "sourceColumns": 
"[\"age\",\"weight_kg\",\"height_cm\"]",
 "targetColumn": "columnName",
 "removeSourceColumns": "true"
 }
 }
}`

## Handling Personally Identifiable Information (PII) in DataBrew Transformations 
- Enable PII statistics in a DataBrew profile job to identify PII;
- Substitution (REPLACE_WITH_RANDOM…);
- Shuffling (SHUFFLE_ROWS) - Deterministic encryption (DETERMINISTIC_ENCRYPT);
- Probabilistic encryption (ENCRYPT) - Decryption (DECRYPT) - Nulling out or deletion (DELETE) - Masking out (MASK_CUSTOM, _DATE, _DELIMITER, _RANGE);
- Hashing (CRYPTOGRAPHIC_HASH).

## Glue Workflows
- Design multi-job, multi-crawler ETL processes run together;
- Create from AWS Glue blueprint, from the console, or API;
- This is only for orchestrating complex ETL operations using Glue.

## Glue Workflow Triggers 
- Triggers within workflows start jobs or crawlers;
  - Or can be fired when jobs or crawlers complete;
- Schedule;
  - Based on a cron expression;
- On demand;
- EventBridge events;
  - Start on single event or batch of events;
  - For example, arrival of a new object in S3;
    - Optional batch conditions - Batch size (number of events);
    - Batch window (within X seconds, default is 15 min);

## AWS Lake Formation 
- “Makes it easy to set up a secure data lake in days”;
- Loading data & monitoring data flows;
- Setting up partitions;
- Encryption & managing keys;
- Defining transformation jobs & monitoring them;
- Access control 
- Auditing 
- Built on top of Glue.

## AWS Lake Formation
![image](https://github.com/user-attachments/assets/bb3fc915-3a46-4d43-a106-b8cbc420ff13)

## AWS Lake Formation: Pricing 
- No cost for Lake Formation itself;
- But underlying services incur charges:
  - Glue; 
  - S3;
  - EMR;
  - Athen;
  - Redshift.

## AWS Lake Formation: Building a Data Lake
![image](https://github.com/user-attachments/assets/bc8ee14c-9672-480a-a030-98824fec144d)

## AWS Lake Formation: The Finer Points
- Cross-account Lake Formation permission;
  - Recipient must be set up as a data lake administrator;
  - Can use AWS Resource Access Manager for accounts external to your organization;
  - IAM permissions for cross-account access;
- Lake Formation does not support manifests in Athena or Redshift queries;
- IAM permissions on the KMS encryption key are needed for encrypted data catalogs in Lake Formation;
- IAM permissions needed to create blueprints and workflows.

## AWS Lake Formation: Governed Tables and Security
- Now supports “Governed Tables” that support ACID transactions across multiple tables;
  - New type of S3 table;
  - Can’t change choice of governed afterwards;
  - Works with streaming data too (Kinesis);
  - Can query with Athena;
- Storage Optimization with Automatic Compaction;
- Granular Access Control with Row and CellLevel Security;
  - Both for governed and S3 tables;
- Above features incur additional charges based on usage.

## Data Permissions in Lake Formation
- Can tie to IAM users/roles, SAML, or external AWS accounts;
- Can use policy tags on databases, tables, or columns;
- Can select specific permissions for tables or columns.

## Data Filters in Lake Formation
- Column, row, or cell-level security - Apply when granting SELECT permission on tables;
- “All columns” + row filter = row-level security;
- “All rows” + specific columns = column-level security;
- Specific columns + specific rows = cell-level security;
- Create filters via the console (seen here) or via `CreateDataCellsFilter` API.
