# Spotify Data Engineering Project
In this project, we are building a data pipeline using AWS - Lambda, S3, Glue, CloudWatch.


### Project Architecture: 
![Architecture Diagram](https://github.com/Mockbee/nyc-taxi-end-to-end-de-project/blob/main/Screenshot%202024-12-22%20174534.png)

### About Dataset/API Used
This project utilizes the **Spotify API**, which provides detailed information about music artists, albums, and songs. You can explore the API documentation [here](https://developer.spotify.com/documentation/web-api).

---

### Services Used

1. **Amazon S3 (Simple Storage Service):**
   - Highly scalable object storage service used to store and retrieve data from anywhere on the web.
   - Common use cases include storing large media files, data backups, and static website files.

2. **AWS Lambda:**
   - A serverless computing service that allows you to run your code without provisioning or managing servers.
   - Used to run code in response to events such as changes in S3, DynamoDB, or other AWS services.

3. **Amazon CloudWatch:**
   - A monitoring service for AWS resources and applications.
   - Collects and tracks metrics, monitors log files, and sets alarms to keep track of system health and performance.

4. **AWS Glue Crawler:**
   - A fully managed service that automatically crawls data sources, identifies data, and infers schemas.
   - Creates a data catalog and loads the schema into Amazon Athena for efficient querying.

5. **AWS Glue Data Catalog:**
   - A fully managed metadata repository for discovering and managing data.
   - Integrates seamlessly with other AWS services such as Athena to enable efficient querying and data analysis.

6. **Amazon Athena:**
   - An interactive query service that simplifies analyzing data stored in Amazon S3.
   - Can query data from the AWS Glue Data Catalog or other S3 buckets using standard SQL.

---

### Project Execution Flow

1. **Extract Data From Spotify API:**
   - A scheduled Lambda function triggers every hour to execute the extraction script.
   
2. **Store Raw Data in S3:**
   - The extracted data is stored in raw format in an Amazon S3 bucket.

3. **Transform and Load Data:**
   - Another Lambda function is triggered to process and transform the raw data.
   - The cleaned and processed data is stored back in S3.

4. **Generate Schema Using AWS Glue Crawler:**
   - AWS Glue Crawler is used to generate the schema for the processed data.
   - The schema is loaded into the AWS Glue Data Catalog.

5. **Query Data Using Amazon Athena:**
   - Athena is used to perform interactive queries on the transformed data.
   - The data schema and metadata from the Glue Data Catalog optimize querying efficiency.

---

This execution flow ensures efficient data processing and analysis, leveraging serverless and fully managed AWS services for seamless operation.
