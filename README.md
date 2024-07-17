# AWS DEA-C01 certification
# Types of data:
## 1. Structured

Data that is organized in a defined manner or schema, typically found in relational databases.

Characteristics: 
- Easily queryable
- Organized in rows and columns
- Has a consistent structure
  
Examples:
- Database tables
- CSV files with consistent columns
- Excel spreadsheet
  
## 2. Unstructured

Data that doesn't have a predefined structure or schema.

Characteristics:
- Not easily queryable without preprocessing
- May come in various formats

Examples: 
- Text files without a fixed format
- Videos and audio files
- Images
- Emails and word processing documents

## 3. Semi-Structured Data

Data that is not as organized as structured data but has some level of structure in the form of tags, hierarchies, or other patterns.

Characteristics: 
- Elements might be tagged or categorized in some way
- More flexible than structured data but not as chaotic as unstructured data

Examples: 
- XML and JSON files
- Email headers (which have a mix of structured fields like date, subject, etc., and unstructured data in the body)
- Log files with varied format

# Properties of Data (3V)
## 1. Volume

Refers to the amount or size of data that organizations are dealing with at any given time.

Characteristics:
- May range from gigabytes to petabytes or even more
- Challenges in storing, processing, and analyzing high volumes of data

Examples:
- Social media platform processing terabytes of data daily from user posts, 
images, and videos.
- Retailers collecting years' worth of transaction data, amounting to several petabytes

## 2. Velocity

Refers to the speed at which new data is generated, collected, and processed.

Characteristics:
- High velocity requires real-time or near-real-time processing capabilities
- Rapid (fast) ingestion and processing can be critical for certain applications

Examples:
- Sensor data from IoT devices streaming readings every millisecond (Streaming data aplications)
- High-frequency trading systems where milliseconds can make a difference in decision-making

## 3. Variety

Refers to the different types, structures, and sources of data.

Characteristics:
- Data can be structured, semi-structured, or unstructured
- Data can come from multiple sources and in various formats

Examples:
- A business analyzing data from relational databases (structured), emails (unstructured), and JSON logs (semi-structured).
- Healthcare systems collecting data from electronic medical records, wearable health devices, and patient feedback forms.

# Data Warehouse vs Data Lake

## Data Warehouse 

A centralized repository optimized for analysis where data from different sources is stored in a structured format.

Characteristics:
- Designed for complex queries and analysis
- Data is cleaned, transformed, and loaded (ETL process)
- Typically uses a star or snowflake schema
- Optimized for read-heavy operations

Examples:
- Amazon Redshift
- Google BigQuery
- Microsoft Azure SQL Data Warehous

## Data Lake

A storage repository that holds vast amounts of raw data in its native format, including structured, semi-structured, and unstructured data.

Characteristics:
- Can store large volumes of raw data without predefined schema
- Data is loaded as-is, no need for preprocessing
- Supports batch, real-time, and stream processing
- Can be queried for data transformation or exploration purposes

Examples:
- Amazon Simple Storage Service (S3) when used as a data lake
- Azure Data Lake Storage
- Hadoop Distributed File System (HDFS)

## Comparing the two 
![image](https://github.com/user-attachments/assets/95027df3-ef63-4dfb-a703-c8a1da1c1ffa)

