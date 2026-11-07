# Practice questions 201-250

[Home](../README.md) · [All sets](README.md)

Answer notes are source-provided unless labeled suggested. These sets preserve the supplied PDF; they are not official AWS exams.

## Question 201

[Review topic](../sections/exam-revision.md) · Source PDF page 72

A company is developing a marketing communications service that targets mobile app users. The company needs to send confirmation messages
with Short Message Service (SMS) to its users. The users must be able to reply to the SMS messages. The company must store the responses for
a year for analysis.
What should a solutions architect do to meet these requirements?

**A.** Create an Amazon Connect contact flow to send the SMS messages. Use AWS Lambda to process the responses.

**B.** Build an Amazon Pinpoint journey. Configure Amazon Pinpoint to send events to an Amazon Kinesis data stream for analysis and archiving.

**C.** Use Amazon Simple Queue Service (Amazon SQS) to distribute the SMS messages. Use AWS Lambda to process the responses.

**D.** Create an Amazon Simple Notification Service (Amazon SNS) FIFO topic. Subscribe an Amazon Kinesis data stream to the SNS topic for
analysis and archiving.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is developing a marketing communications service that targets mobile app users. The company needs to send its users confirmation messages with Short Message Service (SMS). The users must be able to reply to the SMS messages. The company must store the responses for a year for analysis.

What should a solutions architect do to meet these requirements?


**B.** Build an Amazon Pinpoint journey. Configure Amazon Pinpoint to send events to an Amazon Kinesis data stream for analysis and archiving.

Amazon Pinpoint is a fully managed service for sending messages to mobile app users. With Amazon Pinpoint journeys, you can create multi-step campaigns to engage with users. By configuring Amazon Pinpoint to send events to an Amazon Kinesis data stream, you can capture the responses for further analysis and archiving. This solution provides a comprehensive approach to managing SMS messages and their responses in a scalable and efficient manner.

</details>

---

## Question 202

[Review topic](../sections/s3.md) · Source PDF page 72

A company is planning to move its data to an Amazon S3 bucket. The data must be encrypted when it is stored in the S3 bucket. Additionally, the
encryption key must be automatically rotated every year.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Move the data to the S3 bucket. Use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Use the built-in key
rotation behavior of SSE-S3 encryption keys.

**B.** Create an AWS Key Management Service (AWS KMS) customer managed key. Enable automatic key rotation. Set the S3 bucket’s default
encryption behavior to use the customer managed KMS key. Move the data to the S3 bucket.

**C.** Create an AWS Key Management Service (AWS KMS) customer managed key. Set the S3 bucket’s default encryption behavior to use the
customer managed KMS key. Move the data to the S3 bucket. Manually rotate the KMS key every year.

**D.** Encrypt the data with customer key material before moving the data to the S3 bucket. Create an AWS Key Management Service (AWS KMS)
key without key material. Import the customer key material into the KMS key. Enable automatic key rotation.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is planning to move its data to an Amazon S3 bucket. The data must be encrypted when it is stored in the S3 bucket. Additionally, the encryption key must be automatically rotated every year.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Create an AWS Key Management Service (AWS KMS) customer managed key. Enable automatic key rotation. Set the S3 bucket’s default encryption behavior to use the customer managed KMS key. Move the data to the S3 bucket.

In this option, you use AWS KMS to create a customer managed key, enable automatic key rotation, and set it as the default encryption key for the S3 bucket. This ensures that the data is encrypted with a key managed by AWS KMS, and the key rotation is handled automatically. This approach minimizes manual intervention and provides a secure and automated solution for data encryption with key rotation.

</details>

---

## Question 203

[Review topic](../sections/messaging.md) · Source PDF page 73

The customers of a finance company request appointments with financial advisors by sending text messages. A web application that runs on
Amazon EC2 instances accepts the appointment requests. The text messages are published to an Amazon Simple Queue Service (Amazon SQS)
queue through the web application. Another application that runs on EC2 instances then sends meeting invitations and meeting confirmation
email messages to the customers. After successful scheduling, this application stores the meeting information in an Amazon DynamoDB
database.
As the company expands, customers report that their meeting invitations are taking longer to arrive.
What should a solutions architect recommend to resolve this issue?

**A.** Add a DynamoDB Accelerator (DAX) cluster in front of the DynamoDB database.

**B.** Add an Amazon API Gateway API in front of the web application that accepts the appointment requests.

**C.** Add an Amazon CloudFront distribution. Set the origin as the web application that accepts the appointment requests.

**D.** Add an Auto Scaling group for the application that sends meeting invitations. Configure the Auto Scaling group to scale based on the depth
of the SQS queue.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

The customers of a finance company request appointments with financial advisors by sending text messages. A web application that runs on Amazon EC2 instances accepts the appointment requests. The text messages are published to an Amazon Simple Queue Service (Amazon SQS) queue through the web application. Another application that runs on EC2 instances then sends meeting invitations and meeting confirmation email messages to the customers. After successful scheduling, this application stores the meeting information in an Amazon DynamoDB database.

As the company expands, customers report that their meeting invitations are taking longer to arrive.

What should a solutions architect recommend to resolve this issue?


**D.** Add an Auto Scaling group for the application that sends meeting invitations. Configure the Auto Scaling group to scale based on the depth of the SQS queue.

To resolve the issue of longer delivery times for meeting invitations, the solutions architect can recommend adding an Auto Scaling group for the application that sends meeting invitations and configuring the Auto Scaling group to scale based on the depth of the SQS queue. This will allow the application to scale up as the number of appointment requests increases, improving the performance and delivery times of the meeting invitations.

</details>

---

## Question 204

[Review topic](../sections/exam-revision.md) · Source PDF page 73

An online retail company has more than 50 million active customers and receives more than 25,000 orders each day. The company collects
purchase data for customers and stores this data in Amazon S3. Additional customer data is stored in Amazon RDS.
The company wants to make all the data available to various teams so that the teams can perform analytics. The solution must provide the ability
to manage fine-grained permissions for the data and must minimize operational overhead.
Which solution will meet these requirements?

**A.** Migrate the purchase data to write directly to Amazon RDS. Use RDS access controls to limit access.

**B.** Schedule an AWS Lambda function to periodically copy data from Amazon RDS to Amazon S3. Create an AWS Glue crawler. Use Amazon
Athena to query the data. Use S3 policies to limit access.

**C.** Create a data lake by using AWS Lake Formation. Create an AWS Glue JDBC connection to Amazon RDS. Register the S3 bucket in Lake
Formation. Use Lake Formation access controls to limit access.

**D.** Create an Amazon Redshift cluster. Schedule an AWS Lambda function to periodically copy data from Amazon S3 and Amazon RDS to
Amazon Redshift. Use Amazon Redshift access controls to limit access.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An online retail company has more than 50 million active customers and receives more than 25,000 orders each day. The company collects purchase data for customers and stores this data in Amazon S3. Additional customer data is stored in Amazon RDS.

The company wants to make all the data available to various teams so that the teams can perform analytics. The solution must provide the ability to manage fine-grained permissions for the data and must minimize operational overhead.

Which solution will meet these requirements?


**C.** Create a data lake by using AWS Lake Formation. Create an AWS Glue JDBC connection to Amazon RDS. Register the S3 bucket in Lake Formation. Use Lake Formation access controls to limit access.

AWS Lake Formation is designed to create a secure and scalable data lake in Amazon S3. By creating a data lake with Lake Formation, you can centrally manage access controls, fine-grained permissions, and define granular data access policies. This simplifies the process of granting and managing permissions for various teams.

In this scenario, you can use AWS Glue to create a JDBC connection to Amazon RDS for accessing the additional customer data. The S3 bucket, where the purchase data is stored, can be registered in Lake Formation. Lake Formation allows you to set up fine-grained access controls and permissions, providing the ability to manage who can access specific data within the data lake.

</details>

---

## Question 205

[Review topic](../sections/global-delivery.md) · Source PDF page 74

A company hosts a marketing website in an on-premises data center. The website consists of static documents and runs on a single server. An
administrator updates the website content infrequently and uses an SFTP client to upload new documents.
The company decides to host its website on AWS and to use Amazon CloudFront. The company’s solutions architect creates a CloudFront
distribution. The solutions architect must design the most cost-effective and resilient architecture for website hosting to serve as the CloudFront
origin.
Which solution will meet these requirements?

**A.** Create a virtual server by using Amazon Lightsail. Configure the web server in the Lightsail instance. Upload website content by using an
SFTP client.

**B.** Create an AWS Auto Scaling group for Amazon EC2 instances. Use an Application Load Balancer. Upload website content by using an SFTP
client.

**C.** Create a private Amazon S3 bucket. Use an S3 bucket policy to allow access from a CloudFront origin access identity (OAI). Upload website
content by using the AWS CLI.

**D.** Create a public Amazon S3 bucket. Configure AWS Transfer for SFTP. Configure the S3 bucket for website hosting. Upload website content
by using the SFTP client.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company hosts a marketing website in an on-premises data center. The website consists of static documents and runs on a single server. An administrator updates the website content infrequently and uses an SFTP client to upload new documents.

The company decides to host its website on AWS and to use Amazon CloudFront. The company’s solutions architect creates a CloudFront distribution. The solutions architect must design the most cost-effective and resilient architecture for website hosting to serve as the CloudFront origin.

Which solution will meet these requirements?


**C.** Create a private Amazon S3 bucket. Use an S3 bucket policy to allow access from a CloudFront origin access identity (OAI). Upload website content by using the AWS CLI.

This option leverages Amazon S3 as the origin for CloudFront. By creating a private S3 bucket and using a bucket policy to allow access from a CloudFront origin access identity (OAI), you ensure that the content is served securely from S3 and that only CloudFront can access the bucket.

</details>

---

## Question 206

[Review topic](../sections/exam-revision.md) · Source PDF page 74

A company wants to manage Amazon Machine Images (AMIs). The company currently copies AMIs to the same AWS Region where the AMIs were
created. The company needs to design an application that captures AWS API calls and sends alerts whenever the Amazon EC2 CreateImage API
operation is called within the company’s account.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create an AWS Lambda function to query AWS CloudTrail logs and to send an alert when a CreateImage API call is detected.

**B.** Configure AWS CloudTrail with an Amazon Simple Notification Service (Amazon SNS) notification that occurs when updated logs are sent to
Amazon S3. Use Amazon Athena to create a new table and to query on CreateImage when an API call is detected.

**C.** Create an Amazon EventBridge (Amazon CloudWatch Events) rule for the CreateImage API call. Configure the target as an Amazon Simple
Notification Service (Amazon SNS) topic to send an alert when a CreateImage API call is detected.

**D.** Configure an Amazon Simple Queue Service (Amazon SQS) FIFO queue as a target for AWS CloudTrail logs. Create an AWS Lambda
function to send an alert to an Amazon Simple Notification Service (Amazon SNS) topic when a CreateImage API call is detected.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to manage Amazon Machine Images (AMIs). The company currently copies AMIs to the same AWS Region where the AMIs were created. The company needs to design an application that captures AWS API calls and sends alerts whenever the Amazon EC2 CreateImage API operation is called within the company’s account.

Which solution will meet these requirements with the LEAST operational overhead?


**C.** Create an Amazon EventBridge (Amazon CloudWatch Events) rule for the CreateImage API call. Configure the target as an Amazon Simple Notification Service (Amazon SNS) topic to send an alert when a CreateImage API call is detected.

Amazon EventBridge (formerly CloudWatch Events) provides a simple and efficient way to respond to events in AWS services. By creating an EventBridge rule specifically for the CreateImage API call, you can easily configure an SNS topic as the target to send alerts when the event is detected.

</details>

---

## Question 207

[Review topic](../sections/serverless.md) · Source PDF page 75

A company owns an asynchronous API that is used to ingest user requests and, based on the request type, dispatch requests to the appropriate
microservice for processing. The company is using Amazon API Gateway to deploy the API front end, and an AWS Lambda function that invokes
Amazon DynamoDB to store user requests before dispatching them to the processing microservices.
The company provisioned as much DynamoDB throughput as its budget allows, but the company is still experiencing availability issues and is
losing user requests.
What should a solutions architect do to address this issue without impacting existing users?

**A.** Add throttling on the API Gateway with server-side throttling limits.

**B.** Use DynamoDB Accelerator (DAX) and Lambda to buffer writes to DynamoDB.

**C.** Create a secondary index in DynamoDB for the table with the user requests.

**D.** Use the Amazon Simple Queue Service (Amazon SQS) queue and Lambda to buffer writes to DynamoDB.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: D**

SQS buffers writes and absorbs bursts while Lambda drains requests at a sustainable DynamoDB write rate.

</details>

---

## Question 208

[Review topic](../sections/s3.md) · Source PDF page 75

A company needs to move data from an Amazon EC2 instance to an Amazon S3 bucket. The company must ensure that no API calls and no data
are routed through public internet routes. Only the EC2 instance can have access to upload data to the S3 bucket.
Which solution will meet these requirements?

**A.** Create an interface VPC endpoint for Amazon S3 in the subnet where the EC2 instance is located. Attach a resource policy to the S3 bucket
to only allow the EC2 instance’s IAM role for access.

**B.** Create a gateway VPC endpoint for Amazon S3 in the Availability Zone where the EC2 instance is located. Attach appropriate security
groups to the endpoint. Attach a resource policy to the S3 bucket to only allow the EC2 instance’s IAM role for access.

**C.** Run the nslookup tool from inside the EC2 instance to obtain the private IP address of the S3 bucket’s service API endpoint. Create a route
in the VPC route table to provide the EC2 instance with access to the S3 bucket. Attach a resource policy to the S3 bucket to only allow the
EC2 instance’s IAM role for access.

**D.** Use the AWS provided, publicly available ip-ranges.json file to obtain the private IP address of the S3 bucket’s service API endpoint. Create
a route in the VPC route table to provide the EC2 instance with access to the S3 bucket. Attach a resource policy to the S3 bucket to only allow
the EC2 instance’s IAM role for access.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs to move data from an Amazon EC2 instance to an Amazon S3 bucket. The company must ensure that no API calls and no data are routed through public internet routes. Only the EC2 instance can have access to upload data to the S3 bucket.

Which solution will meet these requirements?


**B.** Create a gateway VPC endpoint for Amazon S3 in the Availability Zone where the EC2 instance is located. Attach appropriate security
 groups to the endpoint. Attach a resource policy to the S3 bucket to only allow the EC2 instance’s IAM role for access.

Interface VPC endpoints for Amazon S3 (powered by AWS PrivateLink) allow communication between resources in your VPC and Amazon S3 without relying on public internet routes. It provides a secure and private connection.
By creating an interface VPC endpoint for Amazon S3 in the subnet where the EC2 instance is located, you ensure that the data doesn't travel over the public internet.
Attaching a resource policy to the S3 bucket allows you to control access and restrict it to the IAM role associated with the EC2 instance, ensuring only authorized entities can upload data to the bucket.

</details>

---

## Question 209

[Review topic](../sections/elb-asg.md) · Source PDF page 75

A solutions architect is designing the architecture of a new application being deployed to the AWS Cloud. The application will run on Amazon EC2
On-Demand Instances and will automatically scale across multiple Availability Zones. The EC2 instances will scale up and down frequently
throughout the day. An Application Load Balancer (ALB) will handle the load distribution. The architecture needs to support distributed session
data management. The company is willing to make changes to code if needed.
What should the solutions architect do to ensure that the architecture supports distributed session data management?

**A.** Use Amazon ElastiCache to manage and store session data.

**B.** Use session affinity (sticky sessions) of the ALB to manage session data.

**C.** Use Session Manager from AWS Systems Manager to manage the session.

**D.** Use the GetSessionToken API operation in AWS Security Token Service (AWS STS) to manage the session.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing the architecture of a new application being deployed to the AWS Cloud. The application will run on Amazon EC2 On-Demand Instances and will automatically scale across multiple Availability Zones. The EC2 instances will scale up and down frequently throughout the day. An Application Load Balancer (ALB) will handle the load distribution. The architecture needs to support distributed session data management. The company is willing to make changes to code if needed.

What should the solutions architect do to ensure that the architecture supports distributed session data management?


**A.** Use Amazon ElastiCache to manage and store session data.

Amazon ElastiCache is a fully managed, in-memory data store service. It is commonly used for caching and session management in distributed applications.
By utilizing ElastiCache for session data management, you can store and retrieve session data in a scalable and high-performance manner.
The use of ElastiCache allows for a distributed and shared data store for session management across multiple instances and Availability Zones.

</details>

---

## Question 210

[Review topic](../sections/ec2.md) · Source PDF page 76

A company offers a food delivery service that is growing rapidly. Because of the growth, the company’s order processing system is experiencing
scaling problems during peak traffic hours. The current architecture includes the following:
• A group of Amazon EC2 instances that run in an Amazon EC2 Auto Scaling group to collect orders from the application
• Another group of EC2 instances that run in an Amazon EC2 Auto Scaling group to fulfill orders
The order collection process occurs quickly, but the order fulfillment process can take longer. Data must not be lost because of a scaling event.
A solutions architect must ensure that the order collection process and the order fulfillment process can both scale properly during peak traffic
hours. The solution must optimize utilization of the company’s AWS resources.
Which solution meets these requirements?

**A.** Use Amazon CloudWatch metrics to monitor the CPU of each instance in the Auto Scaling groups. Configure each Auto Scaling group’s
minimum capacity according to peak workload values.

**B.** Use Amazon CloudWatch metrics to monitor the CPU of each instance in the Auto Scaling groups. Configure a CloudWatch alarm to invoke
an Amazon Simple Notification Service (Amazon SNS) topic that creates additional Auto Scaling groups on demand.

**C.** Provision two Amazon Simple Queue Service (Amazon SQS) queues: one for order collection and another for order fulfillment. Configure the
EC2 instances to poll their respective queue. Scale the Auto Scaling groups based on notifications that the queues send.

**D.** Provision two Amazon Simple Queue Service (Amazon SQS) queues: one for order collection and another for order fulfillment. Configure the
EC2 instances to poll their respective queue. Create a metric based on a backlog per instance calculation. Scale the Auto Scaling groups
based on this metric.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: D**

Separate durable queues decouple collection and fulfillment; backlog per instance scales each worker fleet according to work remaining.

</details>

---

## Question 211

[Review topic](../sections/messaging.md) · Source PDF page 76

A company hosts multiple production applications. One of the applications consists of resources from Amazon EC2, AWS Lambda, Amazon RDS,
Amazon Simple Notification Service (Amazon SNS), and Amazon Simple Queue Service (Amazon SQS) across multiple AWS Regions. All company
resources are tagged with a tag name of “application” and a value that corresponds to each application. A solutions architect must provide the
quickest solution for identifying all of the tagged components.
Which solution meets these requirements?

**A.** Use AWS CloudTrail to generate a list of resources with the application tag.

**B.** Use the AWS CLI to query each service across all Regions to report the tagged components.

**C.** Run a query in Amazon CloudWatch Logs Insights to report on the components with the application tag.

**D.** Run a query with the AWS Resource Groups Tag Editor to report on the resources globally with the application tag.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company hosts multiple production applications. One of the applications consists of resources from Amazon EC2, AWS Lambda, Amazon RDS, Amazon Simple Notification Service (Amazon SNS), and Amazon Simple Queue Service (Amazon SQS) across multiple AWS Regions. All company resources are tagged with a tag name of “application” and a value that corresponds to each application. A solutions architect must provide the quickest solution for identifying all of the tagged components.

Which solution meets these requirements?


**D.** Run a query with the AWS Resource Groups Tag Editor to report on the resources globally with the application tag.

AWS Resource Groups Tag Editor allows you to search and filter resources based on tags across multiple AWS Regions.
It provides a centralized view of resources and their corresponding tags, making it easier to identify and manage resources with specific tags.
This option provides a quick and efficient way to report on resources with the application tag globally.

</details>

---

## Question 212

[Review topic](../sections/s3.md) · Source PDF page 77

A company needs to export its database once a day to Amazon S3 for other teams to access. The exported object size varies between 2 GB and 5
GB. The S3 access pattern for the data is variable and changes rapidly. The data must be immediately available and must remain accessible for up
to 3 months. The company needs the most cost-effective solution that will not increase retrieval time.
Which S3 storage class should the company use to meet these requirements?

**A.** S3 Intelligent-Tiering

**B.** S3 Glacier Instant Retrieval

**C.** S3 Standard

**D.** S3 Standard-Infrequent Access (S3 Standard-IA)

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs to export its database once a day to Amazon S3 for other teams to access. The exported object size varies between 2 GB and 5 GB. The S3 access pattern for the data is variable and changes rapidly. The data must be immediately available and must remain accessible for up to 3 months. The company needs the most cost-effective solution that will not increase retrieval time.

Which S3 storage class should the company use to meet these requirements?


**A.** S3 Intelligent-Tiering

S3 Intelligent-Tiering is designed to optimize costs by automatically moving objects between two access tiers: frequent and infrequent access. It is suitable for data with unknown or changing access patterns.
With S3 Intelligent-Tiering, Amazon S3 automatically and transparently moves objects between access tiers based on changing access patterns. It is cost-effective for a wide range of storage access patterns.
The objects can be immediately accessed, and the storage cost is lower than using S3 Standard, making it a suitable choice for varying access patterns.

</details>

---

## Question 213

[Review topic](../sections/elb-asg.md) · Source PDF page 77

A company is developing a new mobile app. The company must implement proper traffic filtering to protect its Application Load Balancer (ALB)
against common application-level attacks, such as cross-site scripting or SQL injection. The company has minimal infrastructure and operational
staff. The company needs to reduce its share of the responsibility in managing, updating, and securing servers for its AWS environment.
What should a solutions architect recommend to meet these requirements?

**A.** Configure AWS WAF rules and associate them with the ALB.

**B.** Deploy the application using Amazon S3 with public hosting enabled.

**C.** Deploy AWS Shield Advanced and add the ALB as a protected resource.

**D.** Create a new ALB that directs traffic to an Amazon EC2 instance running a third-party firewall, which then passes the traffic to the current
ALB.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is developing a new mobile app. The company must implement proper traffic filtering to protect its Application Load Balancer (ALB) against common application-level attacks, such as cross-site scripting or SQL injection. The company has minimal infrastructure and operational staff. The company needs to reduce its share of the responsibility in managing, updating, and securing servers for its AWS environment.

What should a solutions architect recommend to meet these requirements?


**A.** Configure AWS WAF rules and associate them with the ALB.

AWS WAF (Web Application Firewall) is a service that helps protect web applications from common web exploits by allowing you to define customizable web security rules. It can be associated with an Application Load Balancer (ALB) to filter and block malicious traffic before it reaches the application.
AWS WAF is a managed service, which means it reduces the operational burden on the company by handling the infrastructure, updates, and security configurations.

</details>

---

## Question 214

[Review topic](../sections/s3.md) · Source PDF page 77

A company’s reporting system delivers hundreds of .csv files to an Amazon S3 bucket each day. The company must convert these files to Apache
Parquet format and must store the files in a transformed data bucket.
Which solution will meet these requirements with the LEAST development effort?

**A.** Create an Amazon EMR cluster with Apache Spark installed. Write a Spark application to transform the data. Use EMR File System (EMRFS)
to write files to the transformed data bucket.

**B.** Create an AWS Glue crawler to discover the data. Create an AWS Glue extract, transform, and load (ETL) job to transform the data. Specify
the transformed data bucket in the output step.

**C.** Use AWS Batch to create a job definition with Bash syntax to transform the data and output the data to the transformed data bucket. Use
the job definition to submit a job. Specify an array job as the job type.

**D.** Create an AWS Lambda function to transform the data and output the data to the transformed data bucket. Configure an event notification
for the S3 bucket. Specify the Lambda function as the destination for the event notification.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company’s reporting system delivers hundreds of .csv files to an Amazon S3 bucket each day. The company must convert these files to Apache Parquet format and must store the files in a transformed data bucket.

Which solution will meet these requirements with the LEAST development effort?


**B.** Create an AWS Glue crawler to discover the data. Create an AWS Glue extract, transform, and load (ETL) job to transform the data. Specify the transformed data bucket in the output step.

AWS Glue is a fully managed extract, transform, and load (ETL) service that makes it easy to prepare and load data for analysis. In this scenario:
The AWS Glue crawler can automatically discover the schema of your data stored in Amazon S3, including the .csv files.
The AWS Glue ETL job allows you to define the transformation logic easily. You can create a job using a visual interface or script in Python/Spark.
You can specify the transformed data bucket as the output location for the ETL job.

</details>

---

## Question 215

[Review topic](../sections/disaster-recovery.md) · Source PDF page 78

A company has 700 TB of backup data stored in network attached storage (NAS) in its data center. This backup data need to be accessible for
infrequent regulatory requests and must be retained 7 years. The company has decided to migrate this backup data from its data center to AWS.
The migration must be complete within 1 month. The company has 500 Mbps of dedicated bandwidth on its public internet connection available
for data transfer.
What should a solutions architect do to migrate and store the data at the LOWEST cost?

**A.** Order AWS Snowball devices to transfer the data. Use a lifecycle policy to transition the files to Amazon S3 Glacier Deep Archive.

**B.** Deploy a VPN connection between the data center and Amazon VPC. Use the AWS CLI to copy the data from on premises to Amazon S3
Glacier.

**C.** Provision a 500 Mbps AWS Direct Connect connection and transfer the data to Amazon S3. Use a lifecycle policy to transition the files to
Amazon S3 Glacier Deep Archive.

**D.** Use AWS DataSync to transfer the data and deploy a DataSync agent on premises. Use the DataSync task to copy files from the on-premises
NAS storage to Amazon S3 Glacier.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has 700 TB of backup data stored in network attached storage (NAS) in its data center. This backup data need to be accessible for infrequent regulatory requests and must be retained 7 years. The company has decided to migrate this backup data from its data center to AWS. The migration must be complete within 1 month. The company has 500 Mbps of dedicated bandwidth on its public internet connection available for data transfer.

What should a solutions architect do to migrate and store the data at the LOWEST cost?


**A.** Order AWS Snowball devices to transfer the data. Use a lifecycle policy to transition the files to Amazon S3 Glacier Deep Archive.

AWS Snowball: AWS Snowball is a physical data transfer service that allows you to securely transfer large amounts of data into and out of AWS. In this scenario, with 700 TB of data, using Snowball devices can expedite the transfer process. It's a one-time cost-efficient solution for large data transfers.
Amazon S3 Glacier Deep Archive: After transferring the data to Amazon S3 using Snowball, you can use a lifecycle policy to transition the files to Amazon S3 Glacier Deep Archive. This storage class is designed for infrequently accessed data with a retention requirement of 7 years, aligning with the regulatory compliance needs.

</details>

---

## Question 216

[Review topic](../sections/s3.md) · Source PDF page 78

A company has a serverless website with millions of objects in an Amazon S3 bucket. The company uses the S3 bucket as the origin for an
Amazon CloudFront distribution. The company did not set encryption on the S3 bucket before the objects were loaded. A solutions architect
needs to enable encryption for all existing objects and for all objects that are added to the S3 bucket in the future.
Which solution will meet these requirements with the LEAST amount of effort?

**A.** Create a new S3 bucket. Turn on the default encryption settings for the new S3 bucket. Download all existing objects to temporary local
storage. Upload the objects to the new S3 bucket.

**B.** Turn on the default encryption settings for the S3 bucket. Use the S3 Inventory feature to create a .csv file that lists the unencrypted
objects. Run an S3 Batch Operations job that uses the copy command to encrypt those objects.

**C.** Create a new encryption key by using AWS Key Management Service (AWS KMS). Change the settings on the S3 bucket to use server-side
encryption with AWS KMS managed encryption keys (SSE-KMS). Turn on versioning for the S3 bucket.

**D.** Navigate to Amazon S3 in the AWS Management Console. Browse the S3 bucket’s objects. Sort by the encryption field. Select each
unencrypted object. Use the Modify button to apply default encryption settings to every unencrypted object in the S3 bucket.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a serverless website with millions of objects in an Amazon S3 bucket. The company uses the S3 bucket as the origin for an Amazon CloudFront distribution. The company did not set encryption on the S3 bucket before the objects were loaded. A solutions architect needs to enable encryption for all existing objects and for all objects that are added to the S3 bucket in the future.


Which solution will meet these requirements with the LEAST amount of effort?


**B.** Turn on the default encryption settings for the S3 bucket. Use the S3 Inventory feature to create a .csv file that lists the unencrypted objects. Run an S3 Batch Operations job that uses the copy command to encrypt those objects.

This option utilizes the S3 Inventory feature to generate a list of unencrypted objects in the S3 bucket. It then leverages S3 Batch Operations to perform a copy operation, allowing the encryption of the objects during the copy process. This approach is efficient and does not require downloading and re-uploading all existing objects.

</details>

---

## Question 217

[Review topic](../sections/elb-asg.md) · Source PDF page 79

A company runs a global web application on Amazon EC2 instances behind an Application Load Balancer. The application stores data in Amazon
Aurora. The company needs to create a disaster recovery solution and can tolerate up to 30 minutes of downtime and potential data loss. The
solution does not need to handle the load when the primary infrastructure is healthy.
What should a solutions architect do to meet these requirements?

**A.** Deploy the application with the required infrastructure elements in place. Use Amazon Route 53 to configure active-passive failover. Create
an Aurora Replica in a second AWS Region.

**B.** Host a scaled-down deployment of the application in a second AWS Region. Use Amazon Route 53 to configure active-active failover.
Create an Aurora Replica in the second Region.

**C.** Replicate the primary infrastructure in a second AWS Region. Use Amazon Route 53 to configure active-active failover. Create an Aurora
database that is restored from the latest snapshot.

**D.** Back up data with AWS Backup. Use the backup to create the required infrastructure in a second AWS Region. Use Amazon Route 53 to
configure active-passive failover. Create an Aurora second primary instance in the second Region.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a global web application on Amazon EC2 instances behind an Application Load Balancer. The application stores data in Amazon Aurora. The company needs to create a disaster recovery solution and can tolerate up to 30 minutes of downtime and potential data loss. The solution does not need to handle the load when the primary infrastructure is healthy.

What should a solutions architect do to meet these requirements?


**A.** Deploy the application with the required infrastructure elements in place. Use Amazon Route 53 to configure active-passive failover. Create an Aurora Replica in a second AWS Region.

</details>

---

## Question 218

[Review topic](../sections/vpc.md) · Source PDF page 79

A company has a web server running on an Amazon EC2 instance in a public subnet with an Elastic IP address. The default security group is
assigned to the EC2 instance. The default network ACL has been modified to block all traffic. A solutions architect needs to make the web server
accessible from everywhere on port 443.
Which combination of steps will accomplish this task? (Choose two.)

**A.** Create a security group with a rule to allow TCP port 443 from source 0.0.0.0/0.

**B.** Create a security group with a rule to allow TCP port 443 to destination 0.0.0.0/0.

**C.** Update the network ACL to allow TCP port 443 from source 0.0.0.0/0.

**D.** Update the network ACL to allow inbound/outbound TCP port 443 from source 0.0.0.0/0 and to destination 0.0.0.0/0.

**E.** Update the network ACL to allow inbound TCP port 443 from source 0.0.0.0/0 and outbound TCP port 32768-65535 to destination
0.0.0.0/0.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a web server running on an Amazon EC2 instance in a public subnet with an Elastic IP address. The default security group is assigned to the EC2 instance. The default network ACL has been modified to block all traffic. A solutions architect needs to make the web server accessible from everywhere on port 443.

Which combination of steps will accomplish this task? (Choose two.)


**A.** Create a security group with a rule to allow TCP port 443 from source 0.0.0.0/0.


**E.** Update the network ACL to allow inbound TCP port 443 from source 0.0.0.0/0 and outbound TCP port 32768-65535 to destination 0.0.0.0/0.

</details>

---

## Question 219

[Review topic](../sections/ec2.md) · Source PDF page 80

A company’s application is having performance issues. The application is stateful and needs to complete in-memory tasks on Amazon EC2
instances. The company used AWS CloudFormation to deploy infrastructure and used the M5 EC2 instance family. As traffic increased, the
application performance degraded. Users are reporting delays when the users attempt to access the application.
Which solution will resolve these issues in the MOST operationally efficient way?

**A.** Replace the EC2 instances with T3 EC2 instances that run in an Auto Scaling group. Make the changes by using the AWS Management
Console.

**B.** Modify the CloudFormation templates to run the EC2 instances in an Auto Scaling group. Increase the desired capacity and the maximum
capacity of the Auto Scaling group manually when an increase is necessary.

**C.** Modify the CloudFormation templates. Replace the EC2 instances with R5 EC2 instances. Use Amazon CloudWatch built-in EC2 memory
metrics to track the application performance for future capacity planning.

**D.** Modify the CloudFormation templates. Replace the EC2 instances with R5 EC2 instances. Deploy the Amazon CloudWatch agent on the EC2
instances to generate custom application latency metrics for future capacity planning.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: D**

Memory-optimized R5 instances suit in-memory workloads. Preserve infrastructure changes in CloudFormation and publish custom latency metrics. EC2 does not publish memory utilization by default.

**Original companion notes (not independently verified):**

A company’s application is having performance issues. The application is stateful and needs to complete in-memory tasks on Amazon EC2 instances. The company used AWS CloudFormation to deploy infrastructure and used the M5 EC2 instance family. As traffic increased, the application performance degraded. Users are reporting delays when the users attempt to access the application.

Which solution will resolve these issues in the MOST operationally efficient way?

</details>

---

## Question 220

[Review topic](../sections/serverless.md) · Source PDF page 80

A solutions architect is designing a new API using Amazon API Gateway that will receive requests from users. The volume of requests is highly
variable; several hours can pass without receiving a single request. The data processing will take place asynchronously, but should be completed
within a few seconds after a request is made.
Which compute service should the solutions architect have the API invoke to deliver the requirements at the lowest cost?

**A.** An AWS Glue job

**B.** An AWS Lambda function

**C.** A containerized service hosted in Amazon Elastic Kubernetes Service (Amazon EKS)

**D.** A containerized service hosted in Amazon ECS with Amazon EC2

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing a new API using Amazon API Gateway that will receive requests from users. The volume of requests is highly variable; several hours can pass without receiving a single request. The data processing will take place asynchronously, but should be completed within a few seconds after a request is made.

Which compute service should the solutions architect have the API invoke to deliver the requirements at the lowest cost?


**B.** An AWS Lambda function

AWS Lambda supports asynchronous invocation, which is suitable for scenarios where data processing can take place independently of the API request and complete within a few seconds. This aligns with the requirement of processing data asynchronously.

</details>

---

## Question 221

[Review topic](../sections/ec2.md) · Source PDF page 80

A company runs an application on a group of Amazon Linux EC2 instances. For compliance reasons, the company must retain all application log
files for 7 years. The log files will be analyzed by a reporting tool that must be able to access all the files concurrently.
Which storage solution meets these requirements MOST cost-effectively?

**A.** Amazon Elastic Block Store (Amazon EBS)

**B.** Amazon Elastic File System (Amazon EFS)

**C.** Amazon EC2 instance store

**D.** Amazon S3

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs an application on a group of Amazon Linux EC2 instances. For compliance reasons, the company must retain all application log files for 7 years. The log files will be analyzed by a reporting tool that must be able to access all the files concurrently.

Which storage solution meets these requirements MOST cost-effectively?


**D.** Amazon S3

S3 is a highly durable and scalable object storage service. It is designed for high availability and can store large amounts of data. S3 is cost-effective for long-term storage, and its pricing is based on the amount of data stored.

</details>

---

## Question 222

[Review topic](../sections/iam.md) · Source PDF page 81

A company has hired an external vendor to perform work in the company’s AWS account. The vendor uses an automated tool that is hosted in an
AWS account that the vendor owns. The vendor does not have IAM access to the company’s AWS account.
How should a solutions architect grant this access to the vendor?

**A.** Create an IAM role in the company’s account to delegate access to the vendor’s IAM role. Attach the appropriate IAM policies to the role for
the permissions that the vendor requires.

**B.** Create an IAM user in the company’s account with a password that meets the password complexity requirements. Attach the appropriate
IAM policies to the user for the permissions that the vendor requires.

**C.** Create an IAM group in the company’s account. Add the tool’s IAM user from the vendor account to the group. Attach the appropriate IAM
policies to the group for the permissions that the vendor requires.

**D.** Create a new identity provider by choosing “AWS account” as the provider type in the IAM console. Supply the vendor’s AWS account ID and
user name. Attach the appropriate IAM policies to the new provider for the permissions that the vendor requires.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has hired an external vendor to perform work in the company’s AWS account. The vendor uses an automated tool that is hosted in an AWS account that the vendor owns. The vendor does not have IAM access to the company’s AWS account.

How should a solutions architect grant this access to the vendor?


**A.** Create an IAM role in the company’s account to delegate access to the vendor’s IAM role. Attach the appropriate IAM policies to the role for the permissions that the vendor requires.

IAM roles allow you to delegate access to resources in your AWS account to another AWS account. In this case, you can create a role in your account and grant the vendor's IAM role permission to assume that role.

By doing this, the vendor can use temporary security credentials obtained by assuming the role to access resources in your account. This ensures that the vendor doesn't need IAM credentials from your account.

</details>

---

## Question 223

[Review topic](../sections/dynamodb-caching.md) · Source PDF page 81

A company has deployed a Java Spring Boot application as a pod that runs on Amazon Elastic Kubernetes Service (Amazon EKS) in private
subnets. The application needs to write data to an Amazon DynamoDB table. A solutions architect must ensure that the application can interact
with the DynamoDB table without exposing traffic to the internet.
Which combination of steps should the solutions architect take to accomplish this goal? (Choose two.)

**A.** Attach an IAM role that has sufficient privileges to the EKS pod.

**B.** Attach an IAM user that has sufficient privileges to the EKS pod.

**C.** Allow outbound connectivity to the DynamoDB table through the private subnets’ network ACLs.

**D.** Create a VPC endpoint for DynamoDB.

**E.** Embed the access keys in the Java Spring Boot code.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has deployed a Java Spring Boot application as a pod that runs on Amazon Elastic Kubernetes Service (Amazon EKS) in private subnets. The application needs to write data to an Amazon DynamoDB table. A solutions architect must ensure that the application can interact with the DynamoDB table without exposing traffic to the internet.

Which combination of steps should the solutions architect take to accomplish this goal? (Choose two.)


**A.** Attach an IAM role that has sufficient privileges to the EKS pod. Most Voted


**D.** Create a VPC endpoint for DynamoDB. Most Voted

This IAM role should have the necessary permissions to interact with DynamoDB. You can attach the IAM role to the pod using Kubernetes service account annotations or other mechanisms.

By creating a VPC endpoint for DynamoDB, you allow your EKS pods to access DynamoDB directly within the AWS network without traversing the public internet. This enhances security and reduces the risk of exposure.

</details>

---

## Question 224

[Review topic](../sections/ec2.md) · Source PDF page 81

A company recently migrated its web application to AWS by rehosting the application on Amazon EC2 instances in a single AWS Region. The
company wants to redesign its application architecture to be highly available and fault tolerant. Traffic must reach all running EC2 instances
randomly.
Which combination of steps should the company take to meet these requirements? (Choose two.)

**A.** Create an Amazon Route 53 failover routing policy.

**B.** Create an Amazon Route 53 weighted routing policy.

**C.** Create an Amazon Route 53 multivalue answer routing policy.

**D.** Launch three EC2 instances: two instances in one Availability Zone and one instance in another Availability Zone.

**E.** Launch four EC2 instances: two instances in one Availability Zone and two instances in another Availability Zone.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: C, E**

Multivalue routing returns healthy records and distributes client choices. Two instances per Availability Zone provide balanced redundancy; DNS routing is not a replacement for a load balancer when strict load distribution is needed.

</details>

---

## Question 225

[Review topic](../sections/exam-revision.md) · Source PDF page 82

A media company collects and analyzes user activity data on premises. The company wants to migrate this capability to AWS. The user activity
data store will continue to grow and will be petabytes in size. The company needs to build a highly available data ingestion solution that facilitates
on-demand analytics of existing data and new data with SQL.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Send activity data to an Amazon Kinesis data stream. Configure the stream to deliver the data to an Amazon S3 bucket.

**B.** Send activity data to an Amazon Kinesis Data Firehose delivery stream. Configure the stream to deliver the data to an Amazon Redshift
cluster.

**C.** Place activity data in an Amazon S3 bucket. Configure Amazon S3 to run an AWS Lambda function on the data as the data arrives in the S3
bucket.

**D.** Create an ingestion service on Amazon EC2 instances that are spread across multiple Availability Zones. Configure the service to forward
data to an Amazon RDS Multi-AZ database.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A media company collects and analyzes user activity data on premises. The company wants to migrate this capability to AWS. The user activity data store will continue to grow and will be petabytes in size. The company needs to build a highly available data ingestion solution that facilitates on-demand analytics of existing data and new data with SQL.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Send activity data to an Amazon Kinesis Data Firehose delivery stream. Configure the stream to deliver the data to an Amazon Redshift cluster.

Amazon Kinesis Data Firehose: It is a fully managed service that simplifies the delivery of streaming data to destinations such as Amazon S3, Amazon Redshift, or Amazon Elasticsearch Service. It handles the scaling, buffering, and delivery of data.

Amazon Redshift: It is a fully managed, petabyte-scale data warehouse service. It is optimized for high-performance analysis using standard SQL queries.

Least Operational Overhead: Kinesis Data Firehose takes care of many operational aspects, including scaling and buffering, reducing the operational overhead on your part. Configuring it to deliver data to Amazon Redshift provides a streamlined and managed solution.

</details>

---

## Question 226

[Review topic](../sections/ec2.md) · Source PDF page 82

A company collects data from thousands of remote devices by using a RESTful web services application that runs on an Amazon EC2 instance.
The EC2 instance receives the raw data, transforms the raw data, and stores all the data in an Amazon S3 bucket. The number of remote devices
will increase into the millions soon. The company needs a highly scalable solution that minimizes operational overhead.
Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)

**A.** Use AWS Glue to process the raw data in Amazon S3.

**B.** Use Amazon Route 53 to route traffic to different EC2 instances.

**C.** Add more EC2 instances to accommodate the increasing amount of incoming data.

**D.** Send the raw data to Amazon Simple Queue Service (Amazon SQS). Use EC2 instances to process the data.

**E.** Use Amazon API Gateway to send the raw data to an Amazon Kinesis data stream. Configure Amazon Kinesis Data Firehose to use the data
stream as a source to deliver the data to Amazon S3.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company collects data from thousands of remote devices by using a RESTful web services application that runs on an Amazon EC2 instance. The EC2 instance receives the raw data, transforms the raw data, and stores all the data in an Amazon S3 bucket. The number of remote devices will increase into the millions soon. The company needs a highly scalable solution that minimizes operational overhead.

Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)


**A.** Use AWS Glue to process the raw data in Amazon S3.


**E.** Use Amazon API Gateway to send the raw data to an Amazon Kinesis data stream. Configure Amazon Kinesis Data Firehose to use the data stream as a source to deliver the data to Amazon S3.


**A.** It automatically discovers the schema of the data and generates ETL code to transform it.


**E.** API Gateway can be used to receive the raw data from the remote devices via RESTful web services. It provides a scalable and managed infrastructure to handle the incoming requests. The data can then be sent to an Amazon Kinesis data stream, which is a highly scalable and durable real-time data streaming service. From there, Amazon Kinesis Data Firehose can be configured to use the data stream as a source and deliver the transformed data to Amazon S3. This combination of services allows for the seamless ingestion and processing of data while minimizing operational overhead.

</details>

---

## Question 227

[Review topic](../sections/s3.md) · Source PDF page 82

A company needs to retain its AWS CloudTrail logs for 3 years. The company is enforcing CloudTrail across a set of AWS accounts by using AWS
Organizations from the parent account. The CloudTrail target S3 bucket is configured with S3 Versioning enabled. An S3 Lifecycle policy is in
place to delete current objects after 3 years.
After the fourth year of use of the S3 bucket, the S3 bucket metrics show that the number of objects has continued to rise. However, the number
of new CloudTrail logs that are delivered to the S3 bucket has remained consistent.
Which solution will delete objects that are older than 3 years in the MOST cost-effective manner?

**A.** Configure the organization’s centralized CloudTrail trail to expire objects after 3 years.

**B.** Configure the S3 Lifecycle policy to delete previous versions as well as current versions.

**C.** Create an AWS Lambda function to enumerate and delete objects from Amazon S3 that are older than 3 years.

**D.** Configure the parent account as the owner of all objects that are delivered to the S3 bucket.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs to retain its AWS CloudTrail logs for 3 years. The company is enforcing CloudTrail across a set of AWS accounts by using AWS Organizations from the parent account. The CloudTrail target S3 bucket is configured with S3 Versioning enabled. An S3 Lifecycle policy is in place to delete current objects after 3 years.

After the fourth year of use of the S3 bucket, the S3 bucket metrics show that the number of objects has continued to rise. However, the number of new CloudTrail logs that are delivered to the S3 bucket has remained consistent.

Which solution will delete objects that are older than 3 years in the MOST cost-effective manner?


**B.** Configure the S3 Lifecycle policy to delete previous versions as well as current versions.

S3 Lifecycle Policy: Enabling S3 versioning allows you to use a lifecycle policy to manage both current and previous versions of objects in the bucket. By configuring the S3 Lifecycle policy to delete objects older than 3 years, it will automatically delete both the current and previous versions that meet the specified criteria.

</details>

---

## Question 228

[Review topic](../sections/operations.md) · Source PDF page 83

A company has an API that receives real-time data from a fleet of monitoring devices. The API stores this data in an Amazon RDS DB instance for
later analysis. The amount of data that the monitoring devices send to the API fluctuates. During periods of heavy traffic, the API often returns
timeout errors.
After an inspection of the logs, the company determines that the database is not capable of processing the volume of write traffic that comes
from the API. A solutions architect must minimize the number of connections to the database and must ensure that data is not lost during periods
of heavy traffic.
Which solution will meet these requirements?

**A.** Increase the size of the DB instance to an instance type that has more available memory.

**B.** Modify the DB instance to be a Multi-AZ DB instance. Configure the application to write to all active RDS DB instances.

**C.** Modify the API to write incoming data to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function that
Amazon SQS invokes to write data from the queue to the database.

**D.** Modify the API to write incoming data to an Amazon Simple Notification Service (Amazon SNS) topic. Use an AWS Lambda function that
Amazon SNS invokes to write data from the topic to the database.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an API that receives real-time data from a fleet of monitoring devices. The API stores this data in an Amazon RDS DB instance for later analysis. The amount of data that the monitoring devices send to the API fluctuates. During periods of heavy traffic, the API often returns timeout errors.

After an inspection of the logs, the company determines that the database is not capable of processing the volume of write traffic that comes from the API. A solutions architect must minimize the number of connections to the database and must ensure that data is not lost during periods of heavy traffic.

Which solution will meet these requirements?


**C.** Modify the API to write incoming data to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function that Amazon SQS invokes to write data from the queue to the database.

Amazon SQS: SQS is a fully managed message queuing service that decouples the components of a cloud application. It acts as a buffer between the API and the database, allowing for better handling of varying write traffic.

AWS Lambda: Using Lambda to process the data from the SQS queue helps in efficiently managing the connection to the database. Lambda functions can be scaled automatically based on the incoming workload.

</details>

---

## Question 229

[Review topic](../sections/ec2.md) · Source PDF page 83

A company manages its own Amazon EC2 instances that run MySQL databases. The company is manually managing replication and scaling as
demand increases or decreases. The company needs a new solution that simplifies the process of adding or removing compute capacity to or
from its database tier as needed. The solution also must offer improved performance, scaling, and durability with minimal effort from operations.
Which solution meets these requirements?

**A.** Migrate the databases to Amazon Aurora Serverless for Aurora MySQL.

**B.** Migrate the databases to Amazon Aurora Serverless for Aurora PostgreSQL.

**C.** Combine the databases into one larger MySQL database. Run the larger database on larger EC2 instances.

**D.** Create an EC2 Auto Scaling group for the database tier. Migrate the existing databases to the new environment.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company manages its own Amazon EC2 instances that run MySQL databases. The company is manually managing replication and scaling as demand increases or decreases. The company needs a new solution that simplifies the process of adding or removing compute capacity to or from its database tier as needed. The solution also must offer improved performance, scaling, and durability with minimal effort from operations.

Which solution meets these requirements?


**A.** Migrate the databases to Amazon Aurora Serverless for Aurora MySQL.

Amazon Aurora Serverless: Aurora Serverless is an on-demand, auto-scaling configuration for Amazon Aurora. It automatically adjusts the database capacity based on actual consumption, enabling seamless scaling without manual intervention. It is a fully managed service, reducing operational overhead.

</details>

---

## Question 230

[Review topic](../sections/vpc.md) · Source PDF page 83

A company is concerned that two NAT instances in use will no longer be able to support the traffic needed for the company’s application. A
solutions architect wants to implement a solution that is highly available, fault tolerant, and automatically scalable.
What should the solutions architect recommend?

**A.** Remove the two NAT instances and replace them with two NAT gateways in the same Availability Zone.

**B.** Use Auto Scaling groups with Network Load Balancers for the NAT instances in different Availability Zones.

**C.** Remove the two NAT instances and replace them with two NAT gateways in different Availability Zones.

**D.** Replace the two NAT instances with Spot Instances in different Availability Zones and deploy a Network Load Balancer.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is concerned that two NAT instances in use will no longer be able to support the traffic needed for the company’s application. A solutions architect wants to implement a solution that is highly available, fault tolerant, and automatically scalable.

What should the solutions architect recommend?


**C.** Remove the two NAT instances and replace them with two NAT gateways in different Availability Zones.

NAT Gateway: NAT Gateways are managed, highly available, and scalable components provided by AWS. They are designed to handle the network address translation for instances in private subnets. By deploying NAT gateways in different Availability Zones, you ensure high availability.

Benefits of NAT Gateway:
Managed Service: NAT Gateway is a fully managed service, reducing operational overhead.
High Availability: Deploying NAT gateways in different Availability Zones ensures fault tolerance and high availability.
Automatically Scalable: NAT Gateways automatically scale based on the traffic volume, eliminating the need for manual adjustments.

</details>

---

## Question 231

[Review topic](../sections/vpc.md) · Source PDF page 84

An application runs on an Amazon EC2 instance that has an Elastic IP address in VPC A. The application requires access to a database in VPC B.
Both VPCs are in the same AWS account.
Which solution will provide the required access MOST securely?

**A.** Create a DB instance security group that allows all traffic from the public IP address of the application server in VPC A.

**B.** Configure a VPC peering connection between VPC A and VPC B.

**C.** Make the DB instance publicly accessible. Assign a public IP address to the DB instance.

**D.** Launch an EC2 instance with an Elastic IP address into VPC B. Proxy all requests through the new EC2 instance.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An application runs on an Amazon EC2 instance that has an Elastic IP address in VPC A. The application requires access to a database in VPC B. Both VPCs are in the same AWS account.

Which solution will provide the required access MOST securely?


**B.** Configure a VPC peering connection between VPC A and VPC B.

VPC peering allows direct connectivity between two VPCs. This solution enables communication between instances in VPC A and VPC B using private IP addresses. It does not require public IP addresses or the exposure of databases to the public internet.

</details>

---

## Question 232

[Review topic](../sections/ec2.md) · Source PDF page 84

A company runs demonstration environments for its customers on Amazon EC2 instances. Each environment is isolated in its own VPC. The
company’s operations team needs to be notified when RDP or SSH access to an environment has been established.

**A.** Configure Amazon CloudWatch Application Insights to create AWS Systems Manager OpsItems when RDP or SSH access is detected.

**B.** Configure the EC2 instances with an IAM instance profile that has an IAM role with the AmazonSSMManagedInstanceCore policy attached.

**C.** Publish VPC flow logs to Amazon CloudWatch Logs. Create required metric filters. Create an Amazon CloudWatch metric alarm with a
notification action for when the alarm is in the ALARM state.

**D.** Configure an Amazon EventBridge rule to listen for events of type EC2 Instance State-change Notification. Configure an Amazon Simple
Notification Service (Amazon SNS) topic as a target. Subscribe the operations team to the topic.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs demonstration environments for its customers on Amazon EC2 instances. Each environment is isolated in its own VPC. The company’s operations team needs to be notified when RDP or SSH access to an environment has been established.


**B.** Configure the EC2 instances with an IAM instance profile that has an IAM role with the AmazonSSMManagedInstanceCore policy attached.

The correct option for notifying the operations team when RDP or SSH access to an environment has been established is:


**C.** Publish VPC flow logs to Amazon CloudWatch Logs. Create required metric filters. Create an Amazon CloudWatch metric alarm with a notification action for when the alarm is in the ALARM state.

Here's why:

VPC Flow Logs:** VPC flow logs capture information about the IP traffic going to and from network interfaces in your VPC. This includes information about accepted and rejected connections. To monitor RDP or SSH access, you can analyze these logs.

CloudWatch Logs:** By publishing VPC flow logs to CloudWatch Logs, you can analyze the logs using metric filters to extract relevant information.

Metric Filters:** Create metric filters to match the patterns corresponding to RDP or SSH access in the CloudWatch Logs. For example, you can create metric filters that look for specific keywords or patterns related to RDP or SSH connections.
CloudWatch Metric Alarm:** Set up CloudWatch metric alarms based on the metric filters. When the alarm is triggered (indicating that RDP or SSH access has been detected), it can take a notification action, such as sending a notification to the operations team via Amazon SNS.

</details>

---

## Question 233

[Review topic](../sections/exam-revision.md) · Source PDF page 84

A solutions architect has created a new AWS account and must secure AWS account root user access.
Which combination of actions will accomplish this? (Choose two.)

**A.** Ensure the root user uses a strong password.

**B.** Enable multi-factor authentication to the root user.

**C.** Store root user access keys in an encrypted Amazon S3 bucket.

**D.** Add the root user to a group containing administrative permissions.

**E.** Apply the required permissions to the root user with an inline policy document.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect has created a new AWS account and must secure AWS account root user access.

Which combination of actions will accomplish this? (Choose two.)


**A.** Ensure the root user uses a strong password.

**B.** Enable multi-factor authentication to the root user.

Using a strong, complex password for the root user is a fundamental security practice. This helps protect the account from unauthorized access.
Enabling MFA adds an additional layer of security. Even if someone manages to obtain the root user's password, they would still need the second factor (e.g., a mobile device or hardware token) to successfully authenticate.

</details>

---

## Question 234

[Review topic](../sections/elb-asg.md) · Source PDF page 85

A company is building a new web-based customer relationship management application. The application will use several Amazon EC2 instances
that are backed by Amazon Elastic Block Store (Amazon EBS) volumes behind an Application Load Balancer (ALB). The application will also use
an Amazon Aurora database. All data for the application must be encrypted at rest and in transit.
Which solution will meet these requirements?

**A.** Use AWS Key Management Service (AWS KMS) certificates on the ALB to encrypt data in transit. Use AWS Certificate Manager (ACM) to
encrypt the EBS volumes and Aurora database storage at rest.

**B.** Use the AWS root account to log in to the AWS Management Console. Upload the company’s encryption certificates. While in the root
account, select the option to turn on encryption for all data at rest and in transit for the account.

**C.** Use AWS Key Management Service (AWS KMS) to encrypt the EBS volumes and Aurora database storage at rest. Attach an AWS Certificate
Manager (ACM) certificate to the ALB to encrypt data in transit.

**D.** Use BitLocker to encrypt all data at rest. Import the company’s TLS certificate keys to AWS Key Management Service (AWS KMS) Attach the
KMS keys to the ALB to encrypt data in transit.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is building a new web-based customer relationship management application. The application will use several Amazon EC2 instances that are backed by Amazon Elastic Block Store (Amazon EBS) volumes behind an Application Load Balancer (ALB). The application will also use an Amazon Aurora database. All data for the application must be encrypted at rest and in transit.

Which solution will meet these requirements?


**C.** Use AWS Key Management Service (AWS KMS) to encrypt the EBS volumes and Aurora database storage at rest. Attach an AWS Certificate Manager (ACM) certificate to the ALB to encrypt data in transit.

Using AWS KMS to encrypt EBS volumes and Aurora database storage at rest is a good practice. You can specify a KMS key when creating these resources to ensure data encryption.

Attaching an ACM certificate to the ALB allows you to use HTTPS, which encrypts data in transit between clients and the ALB. This ensures secure communication over the network.

</details>

---

## Question 235

[Review topic](../sections/rds-aurora.md) · Source PDF page 85

A company is moving its on-premises Oracle database to Amazon Aurora PostgreSQL. The database has several applications that write to the
same tables. The applications need to be migrated one by one with a month in between each migration. Management has expressed concerns
that the database has a high number of reads and writes. The data must be kept in sync across both databases throughout the migration.
What should a solutions architect recommend?

**A.** Use AWS DataSync for the initial migration. Use AWS Database Migration Service (AWS DMS) to create a change data capture (CDC)
replication task and a table mapping to select all tables.

**B.** Use AWS DataSync for the initial migration. Use AWS Database Migration Service (AWS DMS) to create a full load plus change data capture
(CDC) replication task and a table mapping to select all tables.

**C.** Use the AWS Schema Conversion Tool with AWS Database Migration Service (AWS DMS) using a memory optimized replication instance.
Create a full load plus change data capture (CDC) replication task and a table mapping to select all tables.

**D.** Use the AWS Schema Conversion Tool with AWS Database Migration Service (AWS DMS) using a compute optimized replication instance.
Create a full load plus change data capture (CDC) replication task and a table mapping to select the largest tables.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: C**

Schema conversion plus DMS full load and CDC is the best listed migration approach; memory-optimized replication supports heavy workloads. Bidirectional writes also require explicit replication topology, loop prevention and conflict handling; one CDC task alone does not solve that.

</details>

---

## Question 236

[Review topic](../sections/ec2.md) · Source PDF page 86

A company has a three-tier application for image sharing. The application uses an Amazon EC2 instance for the front-end layer, another EC2
instance for the application layer, and a third EC2 instance for a MySQL database. A solutions architect must design a scalable and highly
available solution that requires the least amount of change to the application.
Which solution meets these requirements?

**A.** Use Amazon S3 to host the front-end layer. Use AWS Lambda functions for the application layer. Move the database to an Amazon
DynamoDB table. Use Amazon S3 to store and serve users’ images.

**B.** Use load-balanced Multi-AZ AWS Elastic Beanstalk environments for the front-end layer and the application layer. Move the database to an
Amazon RDS DB instance with multiple read replicas to serve users’ images.

**C.** Use Amazon S3 to host the front-end layer. Use a fleet of EC2 instances in an Auto Scaling group for the application layer. Move the
database to a memory optimized instance type to store and serve users’ images.

**D.** Use load-balanced Multi-AZ AWS Elastic Beanstalk environments for the front-end layer and the application layer. Move the database to an
Amazon RDS Multi-AZ DB instance. Use Amazon S3 to store and serve users’ images.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a three-tier application for image sharing. The application uses an Amazon EC2 instance for the front-end layer, another EC2 instance for the application layer, and a third EC2 instance for a MySQL database. A solutions architect must design a scalable and highly available solution that requires the least amount of change to the application.

Which solution meets these requirements?


**D.** Use load-balanced Multi-AZ AWS Elastic Beanstalk environments for the front-end layer and the application layer. Move the database to an Amazon RDS Multi-AZ DB instance. Use Amazon S3 to store and serve users’ images.

AWS Elastic Beanstalk provides an easy way to deploy and manage applications. By using Multi-AZ environments, the front-end and application layers can automatically scale and provide high availability across multiple Availability Zones (AZs).
Amazon RDS Multi-AZ DB Instance:
Moving the database to an Amazon RDS Multi-AZ DB instance ensures high availability and automatic failover in the event of a failure in one Availability Zone.
Amazon S3 for Storing and Serving Images:
Using Amazon S3 for storing and serving users' images is a scalable and cost-effective solution. S3 is designed for high durability and availability, making it suitable for serving static content like images.

</details>

---

## Question 237

[Review topic](../sections/vpc.md) · Source PDF page 86

An application running on an Amazon EC2 instance in VPC-A needs to access files in another EC2 instance in VPC-B. Both VPCs are in separate
AWS accounts. The network administrator needs to design a solution to configure secure access to EC2 instance in VPC-B from VPC-A. The
connectivity should not have a single point of failure or bandwidth concerns.
Which solution will meet these requirements?

**A.** Set up a VPC peering connection between VPC-A and VPC-B.

**B.** Set up VPC gateway endpoints for the EC2 instance running in VPC-B.

**C.** Attach a virtual private gateway to VPC-B and set up routing from VPC-A.

**D.** Create a private virtual interface (VIF) for the EC2 instance running in VPC-B and add appropriate routes from VPC-A.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An application running on an Amazon EC2 instance in VPC-A needs to access files in another EC2 instance in VPC-B. Both VPCs are in separate AWS accounts. The network administrator needs to design a solution to configure secure access to EC2 instance in VPC-B from VPC-A. The connectivity should not have a single point of failure or bandwidth concerns.

Which solution will meet these requirements?


**A.** Set up a VPC peering connection between VPC-A and VPC-B.

A VPC peering connection allows secure communication between instances in different VPCs using private IP addresses without the need for internet gateways, VPN connections, or NAT devices. By setting it up, the application running in VPC-A can directly access the EC2 in VPC-B without going through the public internet or any single point of failure.

</details>

---

## Question 238

[Review topic](../sections/ec2.md) · Source PDF page 86

A company wants to experiment with individual AWS accounts for its engineer team. The company wants to be notified as soon as the Amazon
EC2 instance usage for a given month exceeds a specific threshold for each account.
What should a solutions architect do to meet this requirement MOST cost-effectively?

**A.** Use Cost Explorer to create a daily report of costs by service. Filter the report by EC2 instances. Configure Cost Explorer to send an
Amazon Simple Email Service (Amazon SES) notification when a threshold is exceeded.

**B.** Use Cost Explorer to create a monthly report of costs by service. Filter the report by EC2 instances. Configure Cost Explorer to send an
Amazon Simple Email Service (Amazon SES) notification when a threshold is exceeded.

**C.** Use AWS Budgets to create a cost budget for each account. Set the period to monthly. Set the scope to EC2 instances. Set an alert
threshold for the budget. Configure an Amazon Simple Notification Service (Amazon SNS) topic to receive a notification when a threshold is
exceeded.

**D.** Use AWS Cost and Usage Reports to create a report with hourly granularity. Integrate the report data with Amazon Athena. Use Amazon
EventBridge to schedule an Athena query. Configure an Amazon Simple Notification Service (Amazon SNS) topic to receive a notification when
a threshold is exceeded.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to experiment with individual AWS accounts for its engineer team. The company wants to be notified as soon as the Amazon EC2 instance usage for a given month exceeds a specific threshold for each account.

What should a solutions architect do to meet this requirement MOST cost-effectively?


**C.** Use AWS Budgets to create a cost budget for each account. Set the period to monthly. Set the scope to EC2 instances. Set an alert threshold for the budget. Configure an Amazon Simple Notification Service (Amazon SNS) topic to receive a notification when a threshold is exceeded.

AWS Budgets is a cost management service that allows you to set custom cost and usage budgets that alert you when you exceed your thresholds. In this case, you can create a monthly budget specifically for EC2 instances, and when the usage exceeds the defined threshold, it triggers an alert.

</details>

---

## Question 239

[Review topic](../sections/iam.md) · Source PDF page 87

A solutions architect needs to design a new microservice for a company’s application. Clients must be able to call an HTTPS endpoint to reach the
microservice. The microservice also must use AWS Identity and Access Management (IAM) to authenticate calls. The solutions architect will write
the logic for this microservice by using a single AWS Lambda function that is written in Go 1.x.
Which solution will deploy the function in the MOST operationally efficient way?

**A.** Create an Amazon API Gateway REST API. Configure the method to use the Lambda function. Enable IAM authentication on the API.

**B.** Create a Lambda function URL for the function. Specify AWS_IAM as the authentication type.

**C.** Create an Amazon CloudFront distribution. Deploy the function to Lambda@Edge. Integrate IAM authentication logic into the
Lambda@Edge function.

**D.** Create an Amazon CloudFront distribution. Deploy the function to CloudFront Functions. Specify AWS_IAM as the authentication type.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect needs to design a new microservice for a company’s application. Clients must be able to call an HTTPS endpoint to reach the microservice. The microservice also must use AWS Identity and Access Management (IAM) to authenticate calls. The solutions architect will write the logic for this microservice by using a single AWS Lambda function that is written in Go 1.x.

Which solution will deploy the function in the MOST operationally efficient way?


**B.** Create a Lambda function URL for the function. Specify AWS_IAM as the authentication type.

Explanation: A Lambda function URL gives the function its own HTTPS endpoint directly, with no separate API Gateway resource to create or manage. Setting the auth type to AWS_IAM satisfies the IAM-authentication requirement, making this the more operationally efficient option compared to fronting the function with a full API Gateway REST API.

</details>

---

## Question 240

[Review topic](../sections/migration.md) · Source PDF page 87

A company previously migrated its data warehouse solution to AWS. The company also has an AWS Direct Connect connection. Corporate office
users query the data warehouse using a visualization tool. The average size of a query returned by the data warehouse is 50 MB and each
webpage sent by the visualization tool is approximately 500 KB. Result sets returned by the data warehouse are not cached.
Which solution provides the LOWEST data transfer egress cost for the company?

**A.** Host the visualization tool on premises and query the data warehouse directly over the internet.

**B.** Host the visualization tool in the same AWS Region as the data warehouse. Access it over the internet.

**C.** Host the visualization tool on premises and query the data warehouse directly over a Direct Connect connection at a location in the same
AWS Region.

**D.** Host the visualization tool in the same AWS Region as the data warehouse and access it over a Direct Connect connection at a location in
the same Region.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company previously migrated its data warehouse solution to AWS. The company also has an AWS Direct Connect connection. Corporate office users query the data warehouse using a visualization tool. The average size of a query returned by the data warehouse is 50 MB and each webpage sent by the visualization tool is approximately 500 KB. Result sets returned by the data warehouse are not cached.

Which solution provides the LOWEST data transfer egress cost for the company?


**D.** Host the visualization tool in the same AWS Region as the data warehouse and access it over a Direct Connect connection at a location in the same Region.

Hosting the visualization tool in the same AWS Region as the data warehouse and accessing it over a Direct Connect connection within the same Region minimizes data transfer costs. Since the data warehouse and the visualization tool are in the same Region, the data transfer between them doesn't incur the usual costs associated with data leaving the AWS network.

</details>

---

## Question 241

[Review topic](../sections/exam-revision.md) · Source PDF page 87

An online learning company is migrating to the AWS Cloud. The company maintains its student records in a PostgreSQL database. The company
needs a solution in which its data is available and online across multiple AWS Regions at all times.
Which solution will meet these requirements with the LEAST amount of operational overhead?

**A.** Migrate the PostgreSQL database to a PostgreSQL cluster on Amazon EC2 instances.

**B.** Migrate the PostgreSQL database to an Amazon RDS for PostgreSQL DB instance with the Multi-AZ feature turned on.

**C.** Migrate the PostgreSQL database to an Amazon RDS for PostgreSQL DB instance. Create a read replica in another Region.

**D.** Migrate the PostgreSQL database to an Amazon RDS for PostgreSQL DB instance. Set up DB snapshots to be copied to another Region.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

n online learning company is migrating to the AWS Cloud. The company maintains its student records in a PostgreSQL database. The company needs a solution in which its data is available and online across multiple AWS Regions at all times.

Which solution will meet these requirements with the LEAST amount of operational overhead?


**C.** Migrate the PostgreSQL database to an Amazon RDS for PostgreSQL DB instance. Create a read replica in another Region.

Amazon RDS for PostgreSQL allows you to create read replicas in different AWS Regions. This provides cross-Region availability and redundancy. Additionally, it allows you to offload read traffic from the primary database.

</details>

---

## Question 242

[Review topic](../sections/ec2.md) · Source PDF page 88

A company hosts its web application on AWS using seven Amazon EC2 instances. The company requires that the IP addresses of all healthy EC2
instances be returned in response to DNS queries.
Which policy should be used to meet this requirement?

**A.** Simple routing policy

**B.** Latency routing policy

**C.** Multivalue routing policy

**D.** Geolocation routing policy

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company hosts its web application on AWS using seven Amazon EC2 instances. The company requires that the IP addresses of all healthy EC2 instances be returned in response to DNS queries.

Which policy should be used to meet this requirement?


**C.** Multivalue routing policy

The multivalue routing policy returns multiple healthy IP addresses for the resource in response to DNS queries. This is suitable for distributing traffic across multiple resources, such as EC2 instances, and meeting the specified requirement.

Simple Routing: Gives one answer (IP address).
Latency Routing: Considers the fastest route but still gives one answer.
Multivalue Routing: Gives multiple answers (multiple IP addresses).
Geolocation Routing: Directs based on user location but typically gives one answer.

</details>

---

## Question 243

[Review topic](../sections/s3.md) · Source PDF page 88

A medical research lab produces data that is related to a new study. The lab wants to make the data available with minimum latency to clinics
across the country for their on-premises, file-based applications. The data files are stored in an Amazon S3 bucket that has read-only permissions
for each clinic.
What should a solutions architect recommend to meet these requirements?

**A.** Deploy an AWS Storage Gateway file gateway as a virtual machine (VM) on premises at each clinic

**B.** Migrate the files to each clinic’s on-premises applications by using AWS DataSync for processing.

**C.** Deploy an AWS Storage Gateway volume gateway as a virtual machine (VM) on premises at each clinic.

**D.** Attach an Amazon Elastic File System (Amazon EFS) file system to each clinic’s on-premises servers.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A medical research lab produces data that is related to a new study. The lab wants to make the data available with minimum latency to clinics across the country for their on-premises, file-based applications. The data files are stored in an Amazon S3 bucket that has read-only permissions for each clinic.

What should a solutions architect recommend to meet these requirements?


**A.** Deploy an AWS Storage Gateway file gateway as a virtual machine (VM) on premises at each clinic

This option provides a way to present an S3 bucket as a file system to on-premises applications. Each clinic can deploy an AWS Storage Gateway file gateway as a VM on-premises, allowing them to access the data in the S3 bucket as if it were local files. It minimizes latency because the data is cached locally, and read-only permissions can be controlled at the S3 bucket level.

</details>

---

## Question 244

[Review topic](../sections/ec2.md) · Source PDF page 88

A company is using a content management system that runs on a single Amazon EC2 instance. The EC2 instance contains both the web server
and the database software. The company must make its website platform highly available and must enable the website to scale to meet user
demand.
What should a solutions architect recommend to meet these requirements?

**A.** Move the database to Amazon RDS, and enable automatic backups. Manually launch another EC2 instance in the same Availability Zone.
Configure an Application Load Balancer in the Availability Zone, and set the two instances as targets.

**B.** Migrate the database to an Amazon Aurora instance with a read replica in the same Availability Zone as the existing EC2 instance. Manually
launch another EC2 instance in the same Availability Zone. Configure an Application Load Balancer, and set the two EC2 instances as targets.

**C.** Move the database to Amazon Aurora with a read replica in another Availability Zone. Create an Amazon Machine Image (AMI) from the
EC2 instance. Configure an Application Load Balancer in two Availability Zones. Attach an Auto Scaling group that uses the AMI across two
Availability Zones.

**D.** Move the database to a separate EC2 instance, and schedule backups to Amazon S3. Create an Amazon Machine Image (AMI) from the
original EC2 instance. Configure an Application Load Balancer in two Availability Zones. Attach an Auto Scaling group that uses the AMI
across two Availability Zones.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is using a content management system that runs on a single Amazon EC2 instance. The EC2 instance contains both the web server and the database software. The company must make its website platform highly available and must enable the website to scale to meet user demand.

What should a solutions architect recommend to meet these requirements?


**C.** Move the database to Amazon Aurora with a read replica in another Availability Zone. Create an Amazon Machine Image (AMI) from the EC2 instance. Configure an Application Load Balancer in two Availability Zones. Attach an Auto Scaling group that uses the AMI across two Availability Zones.

This option provides both high availability and scalability. Using Amazon Aurora with a read replica in another Availability Zone ensures data redundancy and failover capabilities. Configuring an Application Load Balancer across two Availability Zones and using Auto Scaling allows for scalability.

</details>

---

## Question 245

[Review topic](../sections/elb-asg.md) · Source PDF page 89

A company is launching an application on AWS. The application uses an Application Load Balancer (ALB) to direct traffic to at least two Amazon
EC2 instances in a single target group. The instances are in an Auto Scaling group for each environment. The company requires a development
environment and a production environment. The production environment will have periods of high traffic.
Which solution will configure the development environment MOST cost-effectively?

**A.** Reconfigure the target group in the development environment to have only one EC2 instance as a target.

**B.** Change the ALB balancing algorithm to least outstanding requests.

**C.** Reduce the size of the EC2 instances in both environments.

**D.** Reduce the maximum number of EC2 instances in the development environment’s Auto Scaling group.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is launching an application on AWS. The application uses an Application Load Balancer (ALB) to direct traffic to at least two Amazon EC2 instances in a single target group. The instances are in an Auto Scaling group for each environment. The company requires a development environment and a production environment. The production environment will have periods of high traffic.

Which solution will configure the development environment MOST cost-effectively?


**A.** Reconfigure the target group in the development environment to have only one EC2 instance as a target.

For a development environment, where high availability and scalability might not be as critical as in production, having only one EC2 instance as a target in the target group could be a cost-effective solution. This reduces the number of running instances in the development environment when compared to production.

</details>

---

## Question 246

[Review topic](../sections/elb-asg.md) · Source PDF page 89

A company runs a web application on Amazon EC2 instances in multiple Availability Zones. The EC2 instances are in private subnets. A solutions
architect implements an internet-facing Application Load Balancer (ALB) and specifies the EC2 instances as the target group. However, the
internet traffic is not reaching the EC2 instances.
How should the solutions architect reconfigure the architecture to resolve this issue?

**A.** Replace the ALB with a Network Load Balancer. Configure a NAT gateway in a public subnet to allow internet traffic.

**B.** Move the EC2 instances to public subnets. Add a rule to the EC2 instances’ security groups to allow outbound traffic to 0.0.0.0/0.

**C.** Update the route tables for the EC2 instances’ subnets to send 0.0.0.0/0 traffic through the internet gateway route. Add a rule to the EC2
instances’ security groups to allow outbound traffic to 0.0.0.0/0.

**D.** Create public subnets in each Availability Zone. Associate the public subnets with the ALB. Update the route tables for the public subnets
with a route to the private subnets.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a web application on Amazon EC2 instances in multiple Availability Zones. The EC2 instances are in private subnets. A solutions architect implements an internet-facing Application Load Balancer (ALB) and specifies the EC2 instances as the target group. However, the internet traffic is not reaching the EC2 instances.

How should the solutions architect reconfigure the architecture to resolve this issue?


**D.** Create public subnets in each Availability Zone. Associate the public subnets with the ALB. Update the route tables for the public subnets with a route to the private subnets.

This option involves creating public subnets for the ALB, allowing it to receive internet traffic. The EC2 instances can remain in private subnets. This approach follows the best practice of using public subnets for internet-facing components like ALBs.

</details>

---

## Question 247

[Review topic](../sections/rds-aurora.md) · Source PDF page 89

A company has deployed a database in Amazon RDS for MySQL. Due to increased transactions, the database support team is reporting slow
reads against the DB instance and recommends adding a read replica.
Which combination of actions should a solutions architect take before implementing this change? (Choose two.)

**A.** Enable binlog replication on the RDS primary node.

**B.** Choose a failover priority for the source DB instance.

**C.** Allow long-running transactions to complete on the source DB instance.

**D.** Create a global table and specify the AWS Regions where the table will be available.

**E.** Enable automatic backups on the source instance by setting the backup retention period to a value other than 0.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: C, E**

Enable automated backups with nonzero retention before creating an RDS MySQL replica, and let long-running transactions complete to reduce creation impact.

**Original companion notes (not independently verified):**

A company has deployed a database in Amazon RDS for MySQL. Due to increased transactions, the database support team is reporting slow reads against the DB instance and recommends adding a read replica.

Which combination of actions should a solutions architect take before implementing this change? (Choose two.)

</details>

---

## Question 248

[Review topic](../sections/ec2.md) · Source PDF page 90

A company runs analytics software on Amazon EC2 instances. The software accepts job requests from users to process data that has been
uploaded to Amazon S3. Users report that some submitted data is not being processed Amazon CloudWatch reveals that the EC2 instances have
a consistent CPU utilization at or near 100%. The company wants to improve system performance and scale the system based on user load.
What should a solutions architect do to meet these requirements?

**A.** Create a copy of the instance. Place all instances behind an Application Load Balancer.

**B.** Create an S3 VPC endpoint for Amazon S3. Update the software to reference the endpoint.

**C.** Stop the EC2 instances. Modify the instance type to one with a more powerful CPU and more memory. Restart the instances.

**D.** Route incoming requests to Amazon Simple Queue Service (Amazon SQS). Configure an EC2 Auto Scaling group based on queue size.
Update the software to read from the queue.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

Users report that some submitted data is not being processed Amazon CloudWatch reveals that the EC2 instances have a consistent CPU utilization at or near 100%. The company wants to improve system performance and scale the system based on user load.

What should a solutions architect do to meet these requirements?


**D.** Route incoming requests to Amazon Simple Queue Service (Amazon SQS). Configure an EC2 Auto Scaling group based on queue size. Update the software to read from the queue.

This option addresses the issue by offloading incoming requests to an SQS queue, allowing for decoupling of processing and scaling based on queue size. This helps improve system performance and allows for scaling based on user load.

</details>

---

## Question 249

[Review topic](../sections/ec2-storage.md) · Source PDF page 90

A company is implementing a shared storage solution for a media application that is hosted in the AWS Cloud. The company needs the ability to
use SMB clients to access data. The solution must be fully managed.
Which AWS solution meets these requirements?

**A.** Create an AWS Storage Gateway volume gateway. Create a file share that uses the required client protocol. Connect the application server
to the file share.

**B.** Create an AWS Storage Gateway tape gateway. Configure tapes to use Amazon S3. Connect the application server to the tape gateway.

**C.** Create an Amazon EC2 Windows instance. Install and configure a Windows file share role on the instance. Connect the application server to
the file share.

**D.** Create an Amazon FSx for Windows File Server file system. Attach the file system to the origin server. Connect the application server to the
file system.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

249Topic 1
A company is implementing a shared storage solution for a media application that is hosted in the AWS Cloud. The company needs the ability to use SMB clients to access data. The solution must be fully managed.

Which AWS solution meets these requirements?


**D.** Create an Amazon FSx for Windows File Server file system. Attach the file system to the origin server. Connect the application server to the file system.

Amazon FSx for Windows File Server is a fully managed file storage service that supports the SMB protocol. It provides a native Windows file system experience and is designed to be accessed by SMB clients. This option meets the requirements for a fully managed shared storage solution accessible via SMB.

</details>

---

## Question 250

[Review topic](../sections/vpc.md) · Source PDF page 90

A company’s security team requests that network traffic be captured in VPC Flow Logs. The logs will be frequently accessed for 90 days and then
accessed intermittently.
What should a solutions architect do to meet these requirements when configuring the logs?

**A.** Use Amazon CloudWatch as the target. Set the CloudWatch log group with an expiration of 90 days

**B.** Use Amazon Kinesis as the target. Configure the Kinesis stream to always retain the logs for 90 days.

**C.** Use AWS CloudTrail as the target. Configure CloudTrail to save to an Amazon S3 bucket, and enable S3 Intelligent-Tiering.

**D.** Use Amazon S3 as the target. Enable an S3 Lifecycle policy to transition the logs to S3 Standard-Infrequent Access (S3 Standard-IA) after
90 days.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company’s security team requests that network traffic be captured in VPC Flow Logs. The logs will be frequently accessed for 90 days and then accessed intermittently.

What should a solutions architect do to meet these requirements when configuring the logs?


**D.** Use Amazon S3 as the target. Enable an S3 Lifecycle policy to transition the logs to S3 Standard-Infrequent Access (S3 Standard-IA) after 90 days. 

Amazon S3 is a scalable and cost-effective object storage service. Enabling an S3 Lifecycle policy to transition logs to S3 Standard-Infrequent Access (S3 Standard-IA) after 90 days is a suitable solution. This approach allows you to store the logs in a cost-effective manner, automatically moving them to a lower-cost storage class after the initial 90 days.

</details>

---

