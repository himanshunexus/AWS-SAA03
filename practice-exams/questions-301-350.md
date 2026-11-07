# Practice questions 301-350

[Home](../README.md) · [All sets](README.md)

Answer notes are source-provided unless labeled suggested. These sets preserve the supplied PDF; they are not official AWS exams.

## Question 301

[Review topic](../sections/migration.md) · Source PDF page 109

A university research laboratory needs to migrate 30 TB of data from an on-premises Windows file server to Amazon FSx for Windows File Server.
The laboratory has a 1 Gbps network link that many other departments in the university share.
The laboratory wants to implement a data migration service that will maximize the performance of the data transfer. However, the laboratory
needs to be able to control the amount of bandwidth that the service uses to minimize the impact on other departments. The data migration must
take place within the next 5 days.
Which AWS solution will meet these requirements?

**A.** AWS Snowcone

**B.** Amazon FSx File Gateway

**C.** AWS DataSync

**D.** AWS Transfer Family

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

301Topic 1
A university research laboratory needs to migrate 30 TB of data from an on-premises Windows file server to Amazon FSx for Windows File Server. The laboratory has a 1 Gbps network link that many other departments in the university share.

The laboratory wants to implement a data migration service that will maximize the performance of the data transfer. However, the laboratory needs to be able to control the amount of bandwidth that the service uses to minimize the impact on other departments. The data migration must take place within the next 5 days.

Which AWS solution will meet these requirements?


**C.** AWS DataSync

AWS DataSync is a fully managed data transfer service that can be used to simplify, automate, and accelerate copying large amounts of data between on-premises storage systems and Amazon S3, Amazon EFS, or Amazon FSx for Windows File Server.
With AWS DataSync, you can control the bandwidth to minimize the impact on other departments by configuring the maximum bandwidth that the data transfer service is allowed to use.
AWS DataSync is designed for high-speed data transfers, and it can take advantage of the available network bandwidth to maximize performance.
AWS DataSync can be quickly set up and configured for the migration, allowing the laboratory to meet the 5-day migration timeline.

</details>

---

## Question 302

[Review topic](../sections/s3.md) · Source PDF page 109

A company wants to create a mobile app that allows users to stream slow-motion video clips on their mobile devices. Currently, the app captures
video clips and uploads the video clips in raw format into an Amazon S3 bucket. The app retrieves these video clips directly from the S3 bucket.
However, the videos are large in their raw format.
Users are experiencing issues with buffering and playback on mobile devices. The company wants to implement solutions to maximize the
performance and scalability of the app while minimizing operational overhead.
Which combination of solutions will meet these requirements? (Choose two.)

**A.** Deploy Amazon CloudFront for content delivery and caching.

**B.** Use AWS DataSync to replicate the video files across AW'S Regions in other S3 buckets.

**C.** Use Amazon Elastic Transcoder to convert the video files to more appropriate formats.

**D.** Deploy an Auto Sealing group of Amazon EC2 instances in Local Zones for content delivery and caching.

**E.** Deploy an Auto Scaling group of Amazon EC2 instances to convert the video files to more appropriate formats.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to create a mobile app that allows users to stream slow-motion video clips on their mobile devices. Currently, the app captures video clips and uploads the video clips in raw format into an Amazon S3 bucket. The app retrieves these video clips directly from the S3 bucket. However, the videos are large in their raw format.

Users are experiencing issues with buffering and playback on mobile devices. The company wants to implement solutions to maximize the performance and scalability of the app while minimizing operational overhead.

Which combination of solutions will meet these requirements? (Choose two.)


**A.** Deploy Amazon CloudFront for content delivery and caching.


**C.** Use Amazon Elastic Transcoder to convert the video files to more appropriate formats.

Amazon CloudFront is a content delivery network (CDN) that can distribute your video content globally, reducing latency and improving the speed of delivery.
CloudFront can cache the video content at edge locations, which helps in minimizing the load on the S3 bucket and improves playback performance for users.

Amazon Elastic Transcoder can convert the raw video files into more appropriate formats suitable for streaming, reducing the size of the videos.
By using Elastic Transcoder, you can create different versions of the video files optimized for different devices, bitrates, and resolutions, which can significantly improve the playback experience on mobile devices

</details>

---

## Question 303

[Review topic](../sections/containers.md) · Source PDF page 109

A company is launching a new application deployed on an Amazon Elastic Container Service (Amazon ECS) cluster and is using the Fargate
launch type for ECS tasks. The company is monitoring CPU and memory usage because it is expecting high traffic to the application upon its
launch. However, the company wants to reduce costs when utilization decreases.
What should a solutions architect recommend?

**A.** Use Amazon EC2 Auto Scaling to scale at certain periods based on previous traffic patterns.

**B.** Use an AWS Lambda function to scale Amazon ECS based on metric breaches that trigger an Amazon CloudWatch alarm.

**C.** Use Amazon EC2 Auto Scaling with simple scaling policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.

**D.** Use AWS Application Auto Scaling with target tracking policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is launching a new application deployed on an Amazon Elastic Container Service (Amazon ECS) cluster and is using the Fargate launch type for ECS tasks. The company is monitoring CPU and memory usage because it is expecting high traffic to the application upon its launch. However, the company wants to reduce costs when utilization decreases.

What should a solutions architect recommend?


**D.** Use AWS Application Auto Scaling with target tracking policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.

AWS Application Auto Scaling is a service that can automatically adjust the number of running ECS tasks or services based on specified CloudWatch metrics.
Target tracking policies allow you to set a target value for a specific metric, and AWS Application Auto Scaling automatically adjusts the desired task count to maintain the target.
By using target tracking policies, you can ensure that the ECS cluster scales up or down based on the application's demand while maintaining a balance between cost efficiency and performance.

</details>

---

## Question 304

[Review topic](../sections/disaster-recovery.md) · Source PDF page 110

A company recently created a disaster recovery site in a different AWS Region. The company needs to transfer large amounts of data back and
forth between NFS file systems in the two Regions on a periodic basis.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use AWS DataSync.

**B.** Use AWS Snowball devices.

**C.** Set up an SFTP server on Amazon EC2.

**D.** Use AWS Database Migration Service (AWS DMS).

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company recently created a disaster recovery site in a different AWS Region. The company needs to transfer large amounts of data back and forth between NFS file systems in the two Regions on a periodic basis.

Which solution will meet these requirements with the LEAST operational overhead?


**A.** Use AWS DataSync. 

If we want to transfer large amount of data we can used AWS Datasync.

</details>

---

## Question 305

[Review topic](../sections/ec2-storage.md) · Source PDF page 110

A company is designing a shared storage solution for a gaming application that is hosted in the AWS Cloud. The company needs the ability to use
SMB clients to access data. The solution must be fully managed.
Which AWS solution meets these requirements?

**A.** Create an AWS DataSync task that shares the data as a mountable file system. Mount the file system to the application server.

**B.** Create an Amazon EC2 Windows instance. Install and configure a Windows file share role on the instance. Connect the application server to
the file share.

**C.** Create an Amazon FSx for Windows File Server file system. Attach the file system to the origin server. Connect the application server to the
file system.

**D.** Create an Amazon S3 bucket. Assign an IAM role to the application to grant access to the S3 bucket. Mount the S3 bucket to the
application server.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is designing a shared storage solution for a gaming application that is hosted in the AWS Cloud. The company needs the ability to use SMB clients to access data. The solution must be fully managed.

Which AWS solution meets these requirements?


**C.** Create an Amazon FSx for Windows File Server file system. Attach the file system to the origin server. Connect the application server to the file system.

Amazon FSx for Windows File Server is a fully managed file storage service that is compatible with the Server Message Block (SMB) protocol, making it suitable for use with SMB clients, including Windows-based systems.
With Amazon FSx for Windows File Server, you can create a file system that can be mounted on application servers, providing shared storage for the gaming application.
Amazon FSx for Windows File Server handles the management aspects such as server provisioning, maintenance, and backups, making it a fully managed solution.

</details>

---

## Question 306

[Review topic](../sections/ec2.md) · Source PDF page 110

A company wants to run an in-memory database for a latency-sensitive application that runs on Amazon EC2 instances. The application
processes more than 100,000 transactions each minute and requires high network throughput. A solutions architect needs to provide a cost-
effective network design that minimizes data transfer charges.
Which solution meets these requirements?

**A.** Launch all EC2 instances in the same Availability Zone within the same AWS Region. Specify a placement group with cluster strategy when
launching EC2 instances.

**B.** Launch all EC2 instances in different Availability Zones within the same AWS Region. Specify a placement group with partition strategy
when launching EC2 instances.

**C.** Deploy an Auto Scaling group to launch EC2 instances in different Availability Zones based on a network utilization target.

**D.** Deploy an Auto Scaling group with a step scaling policy to launch EC2 instances in different Availability Zones.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to run an in-memory database for a latency-sensitive application that runs on Amazon EC2 instances. The application processes more than 100,000 transactions each minute and requires high network throughput. A solutions architect needs to provide a cost-effective network design that minimizes data transfer charges.

Which solution meets these requirements?


**A.** Launch all EC2 instances in the same Availability Zone within the same AWS Region. Specify a placement group with cluster strategy when launching EC2 instances.

A placement group is a logical grouping of instances within a single Availability Zone. The "cluster" strategy for placement groups places instances in close proximity to each other, providing low-latency, high-throughput communication between instances.
By launching all EC2 instances in the same Availability Zone within the same AWS Region, you minimize data transfer charges because data transfer within the same Availability Zone is not subject to additional costs.

</details>

---

## Question 307

[Review topic](../sections/exam-revision.md) · Source PDF page 111

A company that primarily runs its application servers on premises has decided to migrate to AWS. The company wants to minimize its need to
scale its Internet Small Computer Systems Interface (iSCSI) storage on premises. The company wants only its recently accessed data to remain
stored locally.
Which AWS solution should the company use to meet these requirements?

**A.** Amazon S3 File Gateway

**B.** AWS Storage Gateway Tape Gateway

**C.** AWS Storage Gateway Volume Gateway stored volumes

**D.** AWS Storage Gateway Volume Gateway cached volumes

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company that primarily runs its application servers on premises has decided to migrate to AWS. The company wants to minimize its need to scale its Internet Small Computer Systems Interface (iSCSI) storage on premises. The company wants only its recently accessed data to remain stored locally.

Which AWS solution should the company use to meet these requirements?


**D.** AWS Storage Gateway Volume Gateway cached volumes.

AWS Storage Gateway provides a hybrid cloud storage service that enables on-premises applications to use cloud storage seamlessly.
Volume Gateway offers two modes: cached volumes and stored volumes.
In the cached volumes mode, the entire dataset is stored in Amazon S3, and the most frequently accessed data is cached on-premises. This allows the company to keep recently accessed data locally, minimizing the need for on-premises scaling.

</details>

---

## Question 308

[Review topic](../sections/operations.md) · Source PDF page 111

A company has multiple AWS accounts that use consolidated billing. The company runs several active high performance Amazon RDS for Oracle
On-Demand DB instances for 90 days. The company’s finance team has access to AWS Trusted Advisor in the consolidated billing account and all
other AWS accounts.
The finance team needs to use the appropriate AWS account to access the Trusted Advisor check recommendations for RDS. The finance team
must review the appropriate Trusted Advisor check to reduce RDS costs.
Which combination of steps should the finance team take to meet these requirements? (Choose two.)

**A.** Use the Trusted Advisor recommendations from the account where the RDS instances are running.

**B.** Use the Trusted Advisor recommendations from the consolidated billing account to see all RDS instance checks at the same time.

**C.** Review the Trusted Advisor check for Amazon RDS Reserved Instance Optimization.

**D.** Review the Trusted Advisor check for Amazon RDS Idle DB Instances.

**E.** Review the Trusted Advisor check for Amazon Redshift Reserved Node Optimization.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: A, C**

Review RDS Reserved Instance Optimization in the account running the databases. Reserved capacity can reduce sustained On-Demand costs.

**Original companion notes (not independently verified):**

A company has multiple AWS accounts that use consolidated billing. The company runs several active high performance Amazon RDS for Oracle On-Demand DB instances for 90 days. The company’s finance team has access to AWS Trusted Advisor in the consolidated billing account and all other AWS accounts.

The finance team needs to use the appropriate AWS account to access the Trusted Advisor check recommendations for RDS. The finance team must review the appropriate Trusted Advisor check to reduce RDS costs.

Which combination of steps should the finance team take to meet these requirements? (Choose two.)

</details>

---

## Question 309

[Review topic](../sections/exam-revision.md) · Source PDF page 111

A solutions architect needs to optimize storage costs. The solutions architect must identify any Amazon S3 buckets that are no longer being
accessed or are rarely accessed.
Which solution will accomplish this goal with the LEAST operational overhead?

**A.** Analyze bucket access patterns by using the S3 Storage Lens dashboard for advanced activity metrics.

**B.** Analyze bucket access patterns by using the S3 dashboard in the AWS Management Console.

**C.** Turn on the Amazon CloudWatch BucketSizeBytes metric for buckets. Analyze bucket access patterns by using the metrics data with
Amazon Athena.

**D.** Turn on AWS CloudTrail for S3 object monitoring. Analyze bucket access patterns by using CloudTrail logs that are integrated with Amazon
CloudWatch Logs.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect needs to optimize storage costs. The solutions architect must identify any Amazon S3 buckets that are no longer being accessed or are rarely accessed.

Which solution will accomplish this goal with the LEAST operational overhead?


**A.** Analyze bucket access patterns by using the S3 Storage Lens dashboard for advanced activity metrics.

S3 Storage Lens is a feature of Amazon S3 that provides a detailed set of reports and metrics to help you understand, analyze, and optimize your storage usage.
The S3 Storage Lens dashboard provides advanced activity metrics, including insights into access patterns, data transfer, and other storage-related activities.
By using the S3 Storage Lens dashboard, you can easily identify buckets that are no longer being accessed or are rarely accessed without the need for additional setup or operational overhead.

</details>

---

## Question 310

[Review topic](../sections/s3.md) · Source PDF page 112

A company sells datasets to customers who do research in artificial intelligence and machine learning (AI/ML). The datasets are large, formatted
files that are stored in an Amazon S3 bucket in the us-east-1 Region. The company hosts a web application that the customers use to purchase
access to a given dataset. The web application is deployed on multiple Amazon EC2 instances behind an Application Load Balancer. After a
purchase is made, customers receive an S3 signed URL that allows access to the files.
The customers are distributed across North America and Europe. The company wants to reduce the cost that is associated with data transfers
and wants to maintain or improve performance.
What should a solutions architect do to meet these requirements?

**A.** Configure S3 Transfer Acceleration on the existing S3 bucket. Direct customer requests to the S3 Transfer Acceleration endpoint. Continue
to use S3 signed URLs for access control.

**B.** Deploy an Amazon CloudFront distribution with the existing S3 bucket as the origin. Direct customer requests to the CloudFront URL.
Switch to CloudFront signed URLs for access control.

**C.** Set up a second S3 bucket in the eu-central-1 Region with S3 Cross-Region Replication between the buckets. Direct customer requests to
the closest Region. Continue to use S3 signed URLs for access control.

**D.** Modify the web application to enable streaming of the datasets to end users. Configure the web application to read the data from the
existing S3 bucket. Implement access control directly in the application.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company sells datasets to customers who do research in artificial intelligence and machine learning (AI/ML). The datasets are large, formatted files that are stored in an Amazon S3 bucket in the us-east-1 Region. The company hosts a web application that the customers use to purchase access to a given dataset. The web application is deployed on multiple Amazon EC2 instances behind an Application Load Balancer. After a purchase is made, customers receive an S3 signed URL that allows access to the files.

The customers are distributed across North America and Europe. The company wants to reduce the cost that is associated with data transfers and wants to maintain or improve performance.

What should a solutions architect do to meet these requirements?


**B.** Deploy an Amazon CloudFront distribution with the existing S3 bucket as the origin. Direct customer requests to the CloudFront URL. Switch to CloudFront signed URLs for access control.

Amazon CloudFront: CloudFront is a content delivery network (CDN) service that distributes content globally with low latency and high data transfer speeds. It helps reduce data transfer costs and improves performance by caching content at edge locations.
S3 Bucket as the Origin: By configuring the existing S3 bucket as the origin for CloudFront, you allow CloudFront to cache and serve the datasets from edge locations around the world.
CloudFront Signed URLs: CloudFront provides the ability to generate signed URLs, allowing you to control access to your content. You can use CloudFront signed URLs for access control, providing a secure way for customers to access datasets.

</details>

---

## Question 311

[Review topic](../sections/exam-revision.md) · Source PDF page 112

A company is using AWS to design a web application that will process insurance quotes. Users will request quotes from the application. Quotes
must be separated by quote type, must be responded to within 24 hours, and must not get lost. The solution must maximize operational efficiency
and must minimize maintenance.
Which solution meets these requirements?

**A.** Create multiple Amazon Kinesis data streams based on the quote type. Configure the web application to send messages to the proper data
stream. Configure each backend group of application servers to use the Kinesis Client Library (KCL) to pool messages from its own data
stream.

**B.** Create an AWS Lambda function and an Amazon Simple Notification Service (Amazon SNS) topic for each quote type. Subscribe the
Lambda function to its associated SNS topic. Configure the application to publish requests for quotes to the appropriate SNS topic.

**C.** Create a single Amazon Simple Notification Service (Amazon SNS) topic. Subscribe Amazon Simple Queue Service (Amazon SQS) queues
to the SNS topic. Configure SNS message filtering to publish messages to the proper SQS queue based on the quote type. Configure each
backend application server to use its own SQS queue.

**D.** Create multiple Amazon Kinesis Data Firehose delivery streams based on the quote type to deliver data streams to an Amazon OpenSearch
Service cluster. Configure the application to send messages to the proper delivery stream. Configure each backend group of application
servers to search for the messages from OpenSearch Service and process them accordingly.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: C**

SNS subscription filtering routes quote types into durable SQS queues; each worker group consumes its own queue.

**Original companion notes (not independently verified):**

A company is using AWS to design a web application that will process insurance quotes. Users will request quotes from the application. Quotes must be separated by quote type, must be responded to within 24 hours, and must not get lost. The solution must maximize operational efficiency and must minimize maintenance.

Which solution meets these requirements?

</details>

---

## Question 312

[Review topic](../sections/ec2.md) · Source PDF page 113

A company has an application that runs on several Amazon EC2 instances. Each EC2 instance has multiple Amazon Elastic Block Store (Amazon
EBS) data volumes attached to it. The application’s EC2 instance configuration and data need to be backed up nightly. The application also needs
to be recoverable in a different AWS Region.
Which solution will meet these requirements in the MOST operationally efficient way?

**A.** Write an AWS Lambda function that schedules nightly snapshots of the application’s EBS volumes and copies the snapshots to a different
Region.

**B.** Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EC2
instances as resources.

**C.** Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EBS
volumes as resources.

**D.** Write an AWS Lambda function that schedules nightly snapshots of the application's EBS volumes and copies the snapshots to a different
Availability Zone.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an application that runs on several Amazon EC2 instances. Each EC2 instance has multiple Amazon Elastic Block Store (Amazon EBS) data volumes attached to it. The application’s EC2 instance configuration and data need to be backed up nightly. The application also needs to be recoverable in a different AWS Region.

Which solution will meet these requirements in the MOST operationally efficient way?


**B.** Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EC2 instances as resources.

AWS Backup: AWS Backup is a fully managed backup service that centralizes and automates the backup of data across AWS services. It provides a simple and efficient way to back up your EC2 instances and their associated EBS volumes.
Backup Plan: With AWS Backup, you can create backup plans to define when and how your backups are performed. Backup plans allow you to schedule nightly backups and define retention policies.
Explanation: Adding only the EBS volumes as resources backs up the data but not the instance configuration, so recovery would mean manually rebuilding the EC2 instance and reattaching volumes. Adding the EC2 instances themselves as resources backs up the instance and its attached volumes together, in one operationally simpler recovery step.

</details>

---

## Question 313

[Review topic](../sections/exam-revision.md) · Source PDF page 113

A company is building a mobile app on AWS. The company wants to expand its reach to millions of users. The company needs to build a platform
so that authorized users can watch the company’s content on their mobile devices.
What should a solutions architect recommend to meet these requirements?

**A.** Publish content to a public Amazon S3 bucket. Use AWS Key Management Service (AWS KMS) keys to stream content.

**B.** Set up IPsec VPN between the mobile app and the AWS environment to stream content.

**C.** Use Amazon CloudFront. Provide signed URLs to stream content.

**D.** Set up AWS Client VPN between the mobile app and the AWS environment to stream content.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is building a mobile app on AWS. The company wants to expand its reach to millions of users. The company needs to build a platform so that authorized users can watch the company’s content on their mobile devices.

What should a solutions architect recommend to meet these requirements?


**C.** Use Amazon CloudFront. Provide signed URLs to stream content.

Amazon CloudFront: CloudFront is a content delivery network (CDN) service provided by AWS. It accelerates the delivery of content by caching it at edge locations globally, reducing latency for end-users.
Signed URLs: CloudFront supports the generation of signed URLs, which can be used to control access to content. You can create time-limited URLs with specific permissions, allowing only authorized users to access the content.

</details>

---

## Question 314

[Review topic](../sections/rds-aurora.md) · Source PDF page 113

A company has an on-premises MySQL database used by the global sales team with infrequent access patterns. The sales team requires the
database to have minimal downtime. A database administrator wants to migrate this database to AWS without selecting a particular instance type
in anticipation of more users in the future.
Which service should a solutions architect recommend?

**A.** Amazon Aurora MySQL

**B.** Amazon Aurora Serverless for MySQL

**C.** Amazon Redshift Spectrum

**D.** Amazon RDS for MySQL

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an on-premises MySQL database used by the global sales team with infrequent access patterns. The sales team requires the database to have minimal downtime. A database administrator wants to migrate this database to AWS without selecting a particular instance type in anticipation of more users in the future.

Which service should a solutions architect recommend?


**B.** Amazon Aurora Serverless for MySQL

Amazon Aurora Serverless: Aurora Serverless is a fully managed, on-demand, and auto-scaling relational database engine provided by AWS. It is suitable for infrequent access patterns and allows the database to automatically start up, shut down, and scale capacity based on actual usage.

</details>

---

## Question 315

[Review topic](../sections/ec2.md) · Source PDF page 114

A company experienced a breach that affected several applications in its on-premises data center. The attacker took advantage of vulnerabilities
in the custom applications that were running on the servers. The company is now migrating its applications to run on Amazon EC2 instances. The
company wants to implement a solution that actively scans for vulnerabilities on the EC2 instances and sends a report that details the findings.
Which solution will meet these requirements?

**A.** Deploy AWS Shield to scan the EC2 instances for vulnerabilities. Create an AWS Lambda function to log any findings to AWS CloudTrail.

**B.** Deploy Amazon Macie and AWS Lambda functions to scan the EC2 instances for vulnerabilities. Log any findings to AWS CloudTrail.

**C.** Turn on Amazon GuardDuty. Deploy the GuardDuty agents to the EC2 instances. Configure an AWS Lambda function to automate the
generation and distribution of reports that detail the findings.

**D.** Turn on Amazon Inspector. Deploy the Amazon Inspector agent to the EC2 instances. Configure an AWS Lambda function to automate the
generation and distribution of reports that detail the findings.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: D**

Amazon Inspector scans EC2 workloads for vulnerabilities. Current Inspector can use Systems Manager agents or supported agentless scanning; the option uses historical agent terminology.

**Original companion notes (not independently verified):**

A company experienced a breach that affected several applications in its on-premises data center. The attacker took advantage of vulnerabilities in the custom applications that were running on the servers. The company is now migrating its applications to run on Amazon EC2 instances. The company wants to implement a solution that actively scans for vulnerabilities on the EC2 instances and sends a report that details the findings.

Which solution will meet these requirements?

</details>

---

## Question 316

[Review topic](../sections/messaging.md) · Source PDF page 114

A company uses an Amazon EC2 instance to run a script to poll for and process messages in an Amazon Simple Queue Service (Amazon SQS)
queue. The company wants to reduce operational costs while maintaining its ability to process a growing number of messages that are added to
the queue.
What should a solutions architect recommend to meet these requirements?

**A.** Increase the size of the EC2 instance to process messages faster.

**B.** Use Amazon EventBridge to turn off the EC2 instance when the instance is underutilized.

**C.** Migrate the script on the EC2 instance to an AWS Lambda function with the appropriate runtime.

**D.** Use AWS Systems Manager Run Command to run the script on demand.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses an Amazon EC2 instance to run a script to poll for and process messages in an Amazon Simple Queue Service (Amazon SQS) queue. The company wants to reduce operational costs while maintaining its ability to process a growing number of messages that are added to the queue.

What should a solutions architect recommend to meet these requirements?


**C.** Migrate the script on the EC2 instance to an AWS Lambda function with the appropriate runtime.

AWS Lambda: Lambda is a serverless computing service that allows you to run code without provisioning or managing servers. It automatically scales based on the number of incoming requests.
Cost-Efficiency: With Lambda, you only pay for the compute time consumed during code execution. This can be more cost-effective than running and maintaining an EC2 instance, especially for sporadic or event-driven workloads.
Automatic Scaling: Lambda automatically scales based on the number of incoming events. As the number of messages in the SQS queue grows, Lambda can scale out to handle the increased workload.
Event-Driven: Lambda is well-suited for event-driven architectures, making it a good fit for scenarios where messages are added to an SQS queue.

</details>

---

## Question 317

[Review topic](../sections/s3.md) · Source PDF page 114

A company uses a legacy application to produce data in CSV format. The legacy application stores the output data in Amazon S3. The company is
deploying a new commercial off-the-shelf (COTS) application that can perform complex SQL queries to analyze data that is stored in Amazon
Redshift and Amazon S3 only. However, the COTS application cannot process the .csv files that the legacy application produces.
The company cannot update the legacy application to produce data in another format. The company needs to implement a solution so that the
COTS application can use the data that the legacy application produces.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create an AWS Glue extract, transform, and load (ETL) job that runs on a schedule. Configure the ETL job to process the .csv files and store
the processed data in Amazon Redshift.

**B.** Develop a Python script that runs on Amazon EC2 instances to convert the .csv files to .sql files. Invoke the Python script on a cron
schedule to store the output files in Amazon S3.

**C.** Create an AWS Lambda function and an Amazon DynamoDB table. Use an S3 event to invoke the Lambda function. Configure the Lambda
function to perform an extract, transform, and load (ETL) job to process the .csv files and store the processed data in the DynamoDB table.

**D.** Use Amazon EventBridge to launch an Amazon EMR cluster on a weekly schedule. Configure the EMR cluster to perform an extract,
transform, and load (ETL) job to process the .csv files and store the processed data in an Amazon Redshift table.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses a legacy application to produce data in CSV format. The legacy application stores the output data in Amazon S3. The company is deploying a new commercial off-the-shelf (COTS) application that can perform complex SQL queries to analyze data that is stored in Amazon Redshift and Amazon S3 only. However, the COTS application cannot process the .csv files that the legacy application produces.

The company cannot update the legacy application to produce data in another format. The company needs to implement a solution so that the COTS application can use the data that the legacy application produces.

Which solution will meet these requirements with the LEAST operational overhead?


**A.** Create an AWS Glue extract, transform, and load (ETL) job that runs on a schedule. Configure the ETL job to process the .csv files and store the processed data in Amazon Redshift.

</details>

---

## Question 318

[Review topic](../sections/vpc.md) · Source PDF page 115

A company recently migrated its entire IT environment to the AWS Cloud. The company discovers that users are provisioning oversized Amazon
EC2 instances and modifying security group rules without using the appropriate change control process. A solutions architect must devise a
strategy to track and audit these inventory and configuration changes.
Which actions should the solutions architect take to meet these requirements? (Choose two.)

**A.** Enable AWS CloudTrail and use it for auditing.

**B.** Use data lifecycle policies for the Amazon EC2 instances.

**C.** Enable AWS Trusted Advisor and reference the security dashboard.

**D.** Enable AWS Config and create rules for auditing and compliance purposes.

**E.** Restore previous resource configurations with an AWS CloudFormation template.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company recently migrated its entire IT environment to the AWS Cloud. The company discovers that users are provisioning oversized Amazon EC2 instances and modifying security group rules without using the appropriate change control process. A solutions architect must devise a strategy to track and audit these inventory and configuration changes.

Which actions should the solutions architect take to meet these requirements? (Choose two.)


**A.** Enable AWS CloudTrail and use it for auditing.


**D.** Enable AWS Config and create rules for auditing and compliance purposes.


**A.** Enable AWS CloudTrail and use it for auditing. CloudTrail provides event history of your AWS account activity, including actions taken through the AWS Management Console, AWS Command Line Interface (CLI), and AWS SDKs and APIs. By enabling CloudTrail, the company can track user activity and changes to AWS resources, and monitor compliance with internal policies and external regulations.


**D.** Enable AWS Config and create rules for auditing and compliance purposes. AWS Config provides a detailed inventory of the AWS resources in your account, and continuously records changes to the configurations of those resources. By creating rules in AWS Config, the company can automate the evaluation of resource configurations against desired state, and receive alerts when configurations drift from compliance.

</details>

---

## Question 319

[Review topic](../sections/ec2.md) · Source PDF page 115

A company has hundreds of Amazon EC2 Linux-based instances in the AWS Cloud. Systems administrators have used shared SSH keys to manage
the instances. After a recent audit, the company’s security team is mandating the removal of all shared keys. A solutions architect must design a
solution that provides secure access to the EC2 instances.
Which solution will meet this requirement with the LEAST amount of administrative overhead?

**A.** Use AWS Systems Manager Session Manager to connect to the EC2 instances.

**B.** Use AWS Security Token Service (AWS STS) to generate one-time SSH keys on demand.

**C.** Allow shared SSH access to a set of bastion instances. Configure all other instances to allow only SSH access from the bastion instances.

**D.** Use an Amazon Cognito custom authorizer to authenticate users. Invoke an AWS Lambda function to generate a temporary SSH key.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has hundreds of Amazon EC2 Linux-based instances in the AWS Cloud. Systems administrators have used shared SSH keys to manage the instances. After a recent audit, the company’s security team is mandating the removal of all shared keys. A solutions architect must design a solution that provides secure access to the EC2 instances.

Which solution will meet this requirement with the LEAST amount of administrative overhead?


**A.** Use AWS Systems Manager Session Manager to connect to the EC2 instances.

AWS Systems Manager Session Manager: AWS Systems Manager provides a service called Session Manager that allows you to securely connect to your EC2 instances without the need for an external bastion host or direct access to the instances. Session Manager uses IAM roles for authentication and provides an auditable and controlled way to access instances.

</details>

---

## Question 320

[Review topic](../sections/ec2.md) · Source PDF page 115

A company is using a fleet of Amazon EC2 instances to ingest data from on-premises data sources. The data is in JSON format and ingestion
rates can be as high as 1 MB/s. When an EC2 instance is rebooted, the data in-flight is lost. The company’s data science team wants to query
ingested data in near-real time.
Which solution provides near-real-time data querying that is scalable with minimal data loss?

**A.** Publish data to Amazon Kinesis Data Streams, Use Kinesis Data Analytics to query the data.

**B.** Publish data to Amazon Kinesis Data Firehose with Amazon Redshift as the destination. Use Amazon Redshift to query the data.

**C.** Store ingested data in an EC2 instance store. Publish data to Amazon Kinesis Data Firehose with Amazon S3 as the destination. Use
Amazon Athena to query the data.

**D.** Store ingested data in an Amazon Elastic Block Store (Amazon EBS) volume. Publish data to Amazon ElastiCache for Redis. Subscribe to
the Redis channel to query the data.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is using a fleet of Amazon EC2 instances to ingest data from on-premises data sources. The data is in JSON format and ingestion rates can be as high as 1 MB/s. When an EC2 instance is rebooted, the data in-flight is lost. The company’s data science team wants to query ingested data in near-real time.

Which solution provides near-real-time data querying that is scalable with minimal data loss?


**A.** Publish data to Amazon Kinesis Data Streams, Use Kinesis Data Analytics to query the data.

Amazon Kinesis Data Streams: It is a scalable and durable real-time data streaming service. It allows you to ingest, buffer, and process streaming data in real time. In this scenario, you can publish data to a Kinesis Data Stream from your EC2 instances.

Kinesis Data Analytics: It provides an SQL-like language for querying and analyzing data in real time. You can use Kinesis Data Analytics to process and analyze the ingested data directly within the Kinesis pipeline.

</details>

---

## Question 321

[Review topic](../sections/s3.md) · Source PDF page 116

What should a solutions architect do to ensure that all objects uploaded to an Amazon S3 bucket are encrypted?

**A.** Update the bucket policy to deny if the PutObject does not have an s3:x-amz-acl header set.

**B.** Update the bucket policy to deny if the PutObject does not have an s3:x-amz-acl header set to private.

**C.** Update the bucket policy to deny if the PutObject does not have an aws:SecureTransport header set to true.

**D.** Update the bucket policy to deny if the PutObject does not have an x-amz-server-side-encryption header set.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

What should a solutions architect do to ensure that all objects uploaded to an Amazon S3 bucket are encrypted?


**D.** Update the bucket policy to deny if the PutObject does not have an x-amz-server-side-encryption header set.

x-amz-server-side-encryption header: This header specifies the server-side encryption algorithm to be used for the object. If an object is uploaded without the x-amz-server-side-encryption header or with an incorrect value, it can be denied.

</details>

---

## Question 322

[Review topic](../sections/exam-revision.md) · Source PDF page 116

A solutions architect is designing a multi-tier application for a company. The application's users upload images from a mobile device. The
application generates a thumbnail of each image and returns a message to the user to confirm that the image was uploaded successfully.
The thumbnail generation can take up to 60 seconds, but the company wants to provide a faster response time to its users to notify them that the
original image was received. The solutions architect must design the application to asynchronously dispatch requests to the different application
tiers.
What should the solutions architect do to meet these requirements?

**A.** Write a custom AWS Lambda function to generate the thumbnail and alert the user. Use the image upload process as an event source to
invoke the Lambda function.

**B.** Create an AWS Step Functions workflow. Configure Step Functions to handle the orchestration between the application tiers and alert the
user when thumbnail generation is complete.

**C.** Create an Amazon Simple Queue Service (Amazon SQS) message queue. As images are uploaded, place a message on the SQS queue for
thumbnail generation. Alert the user through an application message that the image was received.

**D.** Create Amazon Simple Notification Service (Amazon SNS) notification topics and subscriptions. Use one subscription with the application
to generate the thumbnail after the image upload is complete. Use a second subscription to message the user's mobile app by way of a push
notification after thumbnail generation is complete.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing a multi-tier application for a company. The application's users upload images from a mobile device. The application generates a thumbnail of each image and returns a message to the user to confirm that the image was uploaded successfully.

The thumbnail generation can take up to 60 seconds, but the company wants to provide a faster response time to its users to notify them that the original image was received. The solutions architect must design the application to asynchronously dispatch requests to the different application tiers.

What should the solutions architect do to meet these requirements?


**C.** Create an Amazon Simple Queue Service (Amazon SQS) message queue. As images are uploaded, place a message on the SQS queue for thumbnail generation. Alert the user through an application message that the image was received.

Amazon SQS (Simple Queue Service): SQS is a fully managed message queuing service that enables decoupling of the components of a cloud application. By creating an SQS message queue, the image upload process can place messages in the queue for thumbnail generation.

</details>

---

## Question 323

[Review topic](../sections/exam-revision.md) · Source PDF page 116

A company’s facility has badge readers at every entrance throughout the building. When badges are scanned, the readers send a message over
HTTPS to indicate who attempted to access that particular entrance.
A solutions architect must design a system to process these messages from the sensors. The solution must be highly available, and the results
must be made available for the company’s security team to analyze.
Which system architecture should the solutions architect recommend?

**A.** Launch an Amazon EC2 instance to serve as the HTTPS endpoint and to process the messages. Configure the EC2 instance to save the
results to an Amazon S3 bucket.

**B.** Create an HTTPS endpoint in Amazon API Gateway. Configure the API Gateway endpoint to invoke an AWS Lambda function to process the
messages and save the results to an Amazon DynamoDB table.

**C.** Use Amazon Route 53 to direct incoming sensor messages to an AWS Lambda function. Configure the Lambda function to process the
messages and save the results to an Amazon DynamoDB table.

**D.** Create a gateway VPC endpoint for Amazon S3. Configure a Site-to-Site VPN connection from the facility network to the VPC so that sensor
data can be written directly to an S3 bucket by way of the VPC endpoint.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company’s facility has badge readers at every entrance throughout the building. When badges are scanned, the readers send a message over HTTPS to indicate who attempted to access that particular entrance.

A solutions architect must design a system to process these messages from the sensors. The solution must be highly available, and the results must be made available for the company’s security team to analyze.

Which system architecture should the solutions architect recommend?


**B.** Create an HTTPS endpoint in Amazon API Gateway. Configure the API Gateway endpoint to invoke an AWS Lambda function to process the messages and save the results to an Amazon DynamoDB table.

</details>

---

## Question 324

[Review topic](../sections/disaster-recovery.md) · Source PDF page 117

A company wants to implement a disaster recovery plan for its primary on-premises file storage volume. The file storage volume is mounted from
an Internet Small Computer Systems Interface (iSCSI) device on a local storage server. The file storage volume holds hundreds of terabytes (TB)
of data.
The company wants to ensure that end users retain immediate access to all file types from the on-premises systems without experiencing latency.
Which solution will meet these requirements with the LEAST amount of change to the company's existing infrastructure?

**A.** Provision an Amazon S3 File Gateway as a virtual machine (VM) that is hosted on premises. Set the local cache to 10 TB. Modify existing
applications to access the files through the NFS protocol. To recover from a disaster, provision an Amazon EC2 instance and mount the S3
bucket that contains the files.

**B.** Provision an AWS Storage Gateway tape gateway. Use a data backup solution to back up all existing data to a virtual tape library. Configure
the data backup solution to run nightly after the initial backup is complete. To recover from a disaster, provision an Amazon EC2 instance and
restore the data to an Amazon Elastic Block Store (Amazon EBS) volume from the volumes in the virtual tape library.

**C.** Provision an AWS Storage Gateway Volume Gateway cached volume. Set the local cache to 10 TB. Mount the Volume Gateway cached
volume to the existing file server by using iSCSI, and copy all files to the storage volume. Configure scheduled snapshots of the storage
volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to
an Amazon EC2 instance.

**D.** Provision an AWS Storage Gateway Volume Gateway stored volume with the same amount of disk space as the existing file storage volume.
Mount the Volume Gateway stored volume to the existing file server by using iSCSI, and copy all files to the storage volume. Configure
scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS)
volume and attach the EBS volume to an Amazon EC2 instance.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to implement a disaster recovery plan for its primary on-premises file storage volume. The file storage volume is mounted from an Internet Small Computer Systems Interface (iSCSI) device on a local storage server. The file storage volume holds hundreds of terabytes (TB) of data.

The company wants to ensure that end users retain immediate access to all file types from the on-premises systems without experiencing latency.

Which solution will meet these requirements with the LEAST amount of change to the company's existing infrastructure?


**D.** Provision an AWS Storage Gateway Volume Gateway stored volume sized to hold all the existing data. Mount the Volume Gateway stored volume to the existing file server by using iSCSI, and copy all files to the storage volume. Configure scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to an Amazon EC2 instance.

Explanation: A cached volume only keeps the most frequently accessed data locally — anything not in cache has to be fetched from S3 first, adding latency, so it fails the "immediate access to all file types" requirement. A stored volume keeps the entire dataset on-premises (with async backup to S3), giving true zero-latency access to every file.

</details>

---

## Question 325

[Review topic](../sections/s3.md) · Source PDF page 117

A company is hosting a web application from an Amazon S3 bucket. The application uses Amazon Cognito as an identity provider to authenticate
users and return a JSON Web Token (JWT) that provides access to protected resources that are stored in another S3 bucket.
Upon deployment of the application, users report errors and are unable to access the protected content. A solutions architect must resolve this
issue by providing proper permissions so that users can access the protected content.
Which solution meets these requirements?

**A.** Update the Amazon Cognito identity pool to assume the proper IAM role for access to the protected content.

**B.** Update the S3 ACL to allow the application to access the protected content.

**C.** Redeploy the application to Amazon S3 to prevent eventually consistent reads in the S3 bucket from affecting the ability of users to access
the protected content.

**D.** Update the Amazon Cognito pool to use custom attribute mappings within the identity pool and grant users the proper permissions to
access the protected content.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is hosting a web application from an Amazon S3 bucket. The application uses Amazon Cognito as an identity provider to authenticate users and return a JSON Web Token (JWT) that provides access to protected resources that are stored in another S3 bucket.

Upon deployment of the application, users report errors and are unable to access the protected content. A solutions architect must resolve this issue by providing proper permissions so that users can access the protected content.

Which solution meets these requirements?


**A.** Update the Amazon Cognito identity pool to assume the proper IAM role for access to the protected content.

Amazon Cognito Identity Pool: When users authenticate through Amazon Cognito, they assume roles that determine their access to AWS resources. By updating the Cognito identity pool, you can configure it to assume the proper IAM role that has the necessary permissions to access the protected content stored in the S3 bucket.

IAM Role Permissions: The IAM role associated with the identity pool should have the required permissions (e.g., S3 getObject permissions) to access the protected content in the S3 bucket.

</details>

---

## Question 326

[Review topic](../sections/s3.md) · Source PDF page 118

An image hosting company uploads its large assets to Amazon S3 Standard buckets. The company uses multipart upload in parallel by using S3
APIs and overwrites if the same object is uploaded again. For the first 30 days after upload, the objects will be accessed frequently. The objects
will be used less frequently after 30 days, but the access patterns for each object will be inconsistent. The company must optimize its S3 storage
costs while maintaining high availability and resiliency of stored assets.
Which combination of actions should a solutions architect recommend to meet these requirements? (Choose two.)

**A.** Move assets to S3 Intelligent-Tiering after 30 days.

**B.** Configure an S3 Lifecycle policy to clean up incomplete multipart uploads.

**C.** Configure an S3 Lifecycle policy to clean up expired object delete markers.

**D.** Move assets to S3 Standard-Infrequent Access (S3 Standard-IA) after 30 days.

**E.** Move assets to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 30 days.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An image hosting company uploads its large assets to Amazon S3 Standard buckets. The company uses multipart upload in parallel by using S3 APIs and overwrites if the same object is uploaded again. For the first 30 days after upload, the objects will be accessed frequently. The objects will be used less frequently after 30 days, but the access patterns for each object will be inconsistent. The company must optimize its S3 storage costs while maintaining high availability and resiliency of stored assets.

Which combination of actions should a solutions architect recommend to meet these requirements? (Choose two.)


**A.** Move assets to S3 Intelligent-Tiering after 30 days.


**B.** Configure an S3 Lifecycle policy to clean up incomplete multipart uploads.

Move assets to S3 Intelligent-Tiering after 30 days: This option is suitable for objects with unknown or changing access patterns. S3 Intelligent-Tiering automatically moves objects between two access tiers (frequent and infrequent access) based on changing access patterns. It helps optimize costs by automatically selecting the most cost-effective tier for each object.

Configure an S3 Lifecycle policy to clean up incomplete multipart uploads: This is a good practice to clean up any incomplete multipart uploads, which can consume additional storage space without contributing to the actual objects. Cleaning up incomplete uploads helps manage storage costs efficiently.

</details>

---

## Question 327

[Review topic](../sections/ec2.md) · Source PDF page 118

A solutions architect must secure a VPC network that hosts Amazon EC2 instances. The EC2 instances contain highly sensitive data and run in a
private subnet. According to company policy, the EC2 instances that run in the VPC can access only approved third-party software repositories on
the internet for software product updates that use the third party’s URL. Other internet traffic must be blocked.
Which solution meets these requirements?

**A.** Update the route table for the private subnet to route the outbound traffic to an AWS Network Firewall firewall. Configure domain list rule
groups.

**B.** Set up an AWS WAF web ACL. Create a custom set of rules that filter traffic requests based on source and destination IP address range
sets.

**C.** Implement strict inbound security group rules. Configure an outbound rule that allows traffic only to the authorized software repositories on
the internet by specifying the URLs.

**D.** Configure an Application Load Balancer (ALB) in front of the EC2 instances. Direct all outbound traffic to the ALB. Use a URL-based rule
listener in the ALB’s target group for outbound access to the internet.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: A**

Network Firewall domain-list rules restrict outbound HTTP hostnames and TLS SNI domains. Route traffic through the firewall and configure the required egress path.

**Original companion notes (not independently verified):**

A solutions architect must secure a VPC network that hosts Amazon EC2 instances. The EC2 instances contain highly sensitive data and run in a private subnet. According to company policy, the EC2 instances that run in the VPC can access only approved third-party software repositories on the internet for software product updates that use the third party’s URL. Other internet traffic must be blocked.

Which solution meets these requirements?

</details>

---

## Question 328

[Review topic](../sections/ec2.md) · Source PDF page 119

A company is hosting a three-tier ecommerce application in the AWS Cloud. The company hosts the website on Amazon S3 and integrates the
website with an API that handles sales requests. The company hosts the API on three Amazon EC2 instances behind an Application Load
Balancer (ALB). The API consists of static and dynamic front-end content along with backend workers that process sales requests
asynchronously.
The company is expecting a significant and sudden increase in the number of sales requests during events for the launch of new products.
What should a solutions architect recommend to ensure that all the requests are processed successfully?

**A.** Add an Amazon CloudFront distribution for the dynamic content. Increase the number of EC2 instances to handle the increase in traffic.

**B.** Add an Amazon CloudFront distribution for the static content. Place the EC2 instances in an Auto Scaling group to launch new instances
based on network traffic.

**C.** Add an Amazon CloudFront distribution for the dynamic content. Add an Amazon ElastiCache instance in front of the ALB to reduce traffic
for the API to handle.

**D.** Add an Amazon CloudFront distribution for the static content. Add an Amazon Simple Queue Service (Amazon SQS) queue to receive
requests from the website for later processing by the EC2 instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is hosting a three-tier ecommerce application in the AWS Cloud. The company hosts the website on Amazon S3 and integrates the website with an API that handles sales requests. The company hosts the API on three Amazon EC2 instances behind an Application Load Balancer (ALB). The API consists of static and dynamic front-end content along with backend workers that process sales requests asynchronously.

The company is expecting a significant and sudden increase in the number of sales requests during events for the launch of new products.

What should a solutions architect recommend to ensure that all the requests are processed successfully?


**B.** Add an Amazon CloudFront distribution for the static content. Place the EC2 instances in an Auto Scaling group to launch new instances based on network traffic.

Amazon CloudFront for Static Content: By using CloudFront, you can distribute static content (like images, stylesheets) globally, reducing latency for end-users and offloading some of the traffic from your backend instances.

Auto Scaling Group: An Auto Scaling group allows you to automatically adjust the number of EC2 instances to handle changes in demand. By placing the EC2 instances in an Auto Scaling group, you can dynamically scale the number of instances based on network traffic, ensuring that the application can handle increased load during events.

</details>

---

## Question 329

[Review topic](../sections/ec2.md) · Source PDF page 119

A security audit reveals that Amazon EC2 instances are not being patched regularly. A solutions architect needs to provide a solution that will run
regular security scans across a large fleet of EC2 instances. The solution should also patch the EC2 instances on a regular schedule and provide a
report of each instance’s patch status.
Which solution will meet these requirements?

**A.** Set up Amazon Macie to scan the EC2 instances for software vulnerabilities. Set up a cron job on each EC2 instance to patch the instance
on a regular schedule.

**B.** Turn on Amazon GuardDuty in the account. Configure GuardDuty to scan the EC2 instances for software vulnerabilities. Set up AWS
Systems Manager Session Manager to patch the EC2 instances on a regular schedule.

**C.** Set up Amazon Detective to scan the EC2 instances for software vulnerabilities. Set up an Amazon EventBridge scheduled rule to patch the
EC2 instances on a regular schedule.

**D.** Turn on Amazon Inspector in the account. Configure Amazon Inspector to scan the EC2 instances for software vulnerabilities. Set up AWS
Systems Manager Patch Manager to patch the EC2 instances on a regular schedule.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A security audit reveals that Amazon EC2 instances are not being patched regularly. A solutions architect needs to provide a solution that will run regular security scans across a large fleet of EC2 instances. The solution should also patch the EC2 instances on a regular schedule and provide a report of each instance’s patch status.

Which solution will meet these requirements?


**D.** Turn on Amazon Inspector in the account. Configure Amazon Inspector to scan the EC2 instances for software vulnerabilities. Set up AWS Systems Manager Patch Manager to patch the EC2 instances on a regular schedule.

</details>

---

## Question 330

[Review topic](../sections/rds-aurora.md) · Source PDF page 119

A company is planning to store data on Amazon RDS DB instances. The company must encrypt the data at rest.
What should a solutions architect do to meet this requirement?

**A.** Create a key in AWS Key Management Service (AWS KMS). Enable encryption for the DB instances.

**B.** Create an encryption key. Store the key in AWS Secrets Manager. Use the key to encrypt the DB instances.

**C.** Generate a certificate in AWS Certificate Manager (ACM). Enable SSL/TLS on the DB instances by using the certificate.

**D.** Generate a certificate in AWS Identity and Access Management (IAM). Enable SSL/TLS on the DB instances by using the certificate.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is planning to store data on Amazon RDS DB instances. The company must encrypt the data at rest.

What should a solutions architect do to meet this requirement?


**A.** Create a key in AWS Key Management Service (AWS KMS). Enable encryption for the DB instances.

By creating a key in AWS KMS and enabling encryption for the RDS DB instances, you ensure that the data at rest is encrypted using the specified key.

AWS RDS supports encryption at rest, and you can use AWS KMS to manage the encryption keys. When you enable encryption for an RDS DB instance, you can specify a KMS key to use for encryption.

</details>

---

## Question 331

[Review topic](../sections/exam-revision.md) · Source PDF page 120

A company must migrate 20 TB of data from a data center to the AWS Cloud within 30 days. The company’s network bandwidth is limited to 15
Mbps and cannot exceed 70% utilization.
What should a solutions architect do to meet these requirements?

**A.** Use AWS Snowball.

**B.** Use AWS DataSync.

**C.** Use a secure VPN connection.

**D.** Use Amazon S3 Transfer Acceleration.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company must migrate 20 TB of data from a data center to the AWS Cloud within 30 days. The company’s network bandwidth is limited to 15 Mbps and cannot exceed 70% utilization.

What should a solutions architect do to meet these requirements?


**A.** Use AWS Snowball.

AWS Snowball is a physical data transport solution that helps customers transfer large amounts of data into and out of AWS. It addresses challenges associated with large-scale data transfers, particularly when network constraints, transfer times, or security concerns make online data transfer less practical.

</details>

---

## Question 332

[Review topic](../sections/exam-revision.md) · Source PDF page 120

A company needs to provide its employees with secure access to confidential and sensitive files. The company wants to ensure that the files can
be accessed only by authorized users. The files must be downloaded securely to the employees’ devices.
The files are stored in an on-premises Windows file server. However, due to an increase in remote usage, the file server is running out of capacity.
.
Which solution will meet these requirements?

**A.** Migrate the file server to an Amazon EC2 instance in a public subnet. Configure the security group to limit inbound traffic to the employees’
IP addresses.

**B.** Migrate the files to an Amazon FSx for Windows File Server file system. Integrate the Amazon FSx file system with the on-premises Active
Directory. Configure AWS Client VPN.

**C.** Migrate the files to Amazon S3, and create a private VPC endpoint. Create a signed URL to allow download.

**D.** Migrate the files to Amazon S3, and create a public VPC endpoint. Allow employees to sign on with AWS IAM Identity Center (AWS Single
Sign-On).

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs to provide its employees with secure access to confidential and sensitive files. The company wants to ensure that the files can be accessed only by authorized users. The files must be downloaded securely to the employees’ devices.

The files are stored in an on-premises Windows file server. However, due to an increase in remote usage, the file server is running out of capacity.

Which solution will meet these requirements?


**B.** Migrate the files to an Amazon FSx for Windows File Server file system. Integrate the Amazon FSx file system with the on-premises Active Directory. Configure AWS Client VPN.

Amazon FSx for Windows File Server: It is a fully managed file storage service built on Windows Server. It is designed to be integrated with on-premises Active Directory, allowing for a seamless extension of your existing directory and authentication infrastructure to the AWS Cloud.

Integrate with On-Premises Active Directory: With Amazon FSx, you can integrate the file system with your on-premises Active Directory, ensuring that the same user accounts and permissions are used both on-premises and in the cloud.

</details>

---

## Question 333

[Review topic](../sections/ec2.md) · Source PDF page 120

A company’s application runs on Amazon EC2 instances behind an Application Load Balancer (ALB). The instances run in an Amazon EC2 Auto
Scaling group across multiple Availability Zones. On the first day of every month at midnight, the application becomes much slower when the
month-end financial calculation batch runs. This causes the CPU utilization of the EC2 instances to immediately peak to 100%, which disrupts the
application.
What should a solutions architect recommend to ensure the application is able to handle the workload and avoid downtime?

**A.** Configure an Amazon CloudFront distribution in front of the ALB.

**B.** Configure an EC2 Auto Scaling simple scaling policy based on CPU utilization.

**C.** Configure an EC2 Auto Scaling scheduled scaling policy based on the monthly schedule.

**D.** Configure Amazon ElastiCache to remove some of the workload from the EC2 instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company’s application runs on Amazon EC2 instances behind an Application Load Balancer (ALB). The instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. On the first day of every month at midnight, the application becomes much slower when the month-end financial calculation batch runs. This causes the CPU utilization of the EC2 instances to immediately peak to 100%, which disrupts the application.

What should a solutions architect recommend to ensure the application is able to handle the workload and avoid downtime?


**C.** Configure an EC2 Auto Scaling scheduled scaling policy based on the monthly schedule.

By configuring a scheduled scaling policy, the EC2 Auto Scaling group can proactively launch additional EC2 instances before the CPU utilization peaks to 100%. This will ensure that the application can handle the workload during the month-end financial calculation batch, and avoid any disruption or downtime.

Configuring a simple scaling policy based on CPU utilization or adding Amazon CloudFront distribution or Amazon ElastiCache will not directly address the issue of handling the monthly peak workload.

</details>

---

## Question 334

[Review topic](../sections/iam.md) · Source PDF page 121

A company wants to give a customer the ability to use on-premises Microsoft Active Directory to download files that are stored in Amazon S3. The
customer’s application uses an SFTP client to download the files.
Which solution will meet these requirements with the LEAST operational overhead and no changes to the customer’s application?

**A.** Set up AWS Transfer Family with SFTP for Amazon S3. Configure integrated Active Directory authentication.

**B.** Set up AWS Database Migration Service (AWS DMS) to synchronize the on-premises client with Amazon S3. Configure integrated Active
Directory authentication.

**C.** Set up AWS DataSync to synchronize between the on-premises location and the S3 location by using AWS IAM Identity Center (AWS Single
Sign-On).

**D.** Set up a Windows Amazon EC2 instance with SFTP to connect the on-premises client with Amazon S3. Integrate AWS Identity and Access
Management (IAM).

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to give a customer the ability to use on-premises Microsoft Active Directory to download files that are stored in Amazon S3. The customer’s application uses an SFTP client to download the files.

Which solution will meet these requirements with the LEAST operational overhead and no changes to the customer’s application?


**A.** Set up AWS Transfer Family with SFTP for Amazon S3. Configure integrated Active Directory authentication.

AWS Transfer Family with SFTP for Amazon S3: AWS Transfer Family is a fully managed service that allows you to set up an SFTP (Secure File Transfer Protocol) service for Amazon S3. It enables you to transfer files directly to and from Amazon S3 using the SFTP protocol.

Integrated Active Directory Authentication: AWS Transfer Family allows you to configure authentication with Microsoft Active Directory. By integrating with Active Directory, you can provide users with seamless access to S3 resources using their existing credentials without modifying their applications.

</details>

---

## Question 335

[Review topic](../sections/elb-asg.md) · Source PDF page 121

A company is experiencing sudden increases in demand. The company needs to provision large Amazon EC2 instances from an Amazon Machine
Image (AMI). The instances will run in an Auto Scaling group. The company needs a solution that provides minimum initialization latency to meet
the demand.
Which solution meets these requirements?

**A.** Use the aws ec2 register-image command to create an AMI from a snapshot. Use AWS Step Functions to replace the AMI in the Auto
Scaling group.

**B.** Enable Amazon Elastic Block Store (Amazon EBS) fast snapshot restore on a snapshot. Provision an AMI by using the snapshot. Replace
the AMI in the Auto Scaling group with the new AMI.

**C.** Enable AMI creation and define lifecycle rules in Amazon Data Lifecycle Manager (Amazon DLM). Create an AWS Lambda function that
modifies the AMI in the Auto Scaling group.

**D.** Use Amazon EventBridge to invoke AWS Backup lifecycle policies that provision AMIs. Configure Auto Scaling group capacity limits as an
event source in EventBridge.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is experiencing sudden increases in demand. The company needs to provision large Amazon EC2 instances from an Amazon Machine Image (AMI). The instances will run in an Auto Scaling group. The company needs a solution that provides minimum initialization latency to meet the demand.

Which solution meets these requirements?


**B.** Enable Amazon Elastic Block Store (Amazon EBS) fast snapshot restore on a snapshot. Provision an AMI by using the snapshot. Replace the AMI in the Auto Scaling group with the new AMI.

Amazon EBS Fast Snapshot Restore: Enabling fast snapshot restore allows you to provision Amazon EBS volumes based on snapshots with faster performance. This is particularly useful when creating AMIs from snapshots, as it reduces the time it takes to create EBS volumes from those snapshots.

Minimum Initialization Latency: Fast snapshot restore helps in minimizing initialization latency as it provides a way to quickly create EBS volumes from snapshots.

Provisioning AMI from Snapshot: You can create an Amazon Machine Image (AMI) from an Amazon EBS snapshot. This allows you to capture a point-in-time snapshot of the file system, and then use that snapshot to create new instances.

</details>

---

## Question 336

[Review topic](../sections/rds-aurora.md) · Source PDF page 122

A company hosts a multi-tier web application that uses an Amazon Aurora MySQL DB cluster for storage. The application tier is hosted on
Amazon EC2 instances. The company’s IT security guidelines mandate that the database credentials be encrypted and rotated every 14 days.
What should a solutions architect do to meet this requirement with the LEAST operational effort?

**A.** Create a new AWS Key Management Service (AWS KMS) encryption key. Use AWS Secrets Manager to create a new secret that uses the
KMS key with the appropriate credentials. Associate the secret with the Aurora DB cluster. Configure a custom rotation period of 14 days.

**B.** Create two parameters in AWS Systems Manager Parameter Store: one for the user name as a string parameter and one that uses the
SecureString type for the password. Select AWS Key Management Service (AWS KMS) encryption for the password parameter, and load these
parameters in the application tier. Implement an AWS Lambda function that rotates the password every 14 days.

**C.** Store a file that contains the credentials in an AWS Key Management Service (AWS KMS) encrypted Amazon Elastic File System (Amazon
EFS) file system. Mount the EFS file system in all EC2 instances of the application tier. Restrict the access to the file on the file system so that
the application can read the file and that only super users can modify the file. Implement an AWS Lambda function that rotates the key in
Aurora every 14 days and writes new credentials into the file.

**D.** Store a file that contains the credentials in an AWS Key Management Service (AWS KMS) encrypted Amazon S3 bucket that the application
uses to load the credentials. Download the file to the application regularly to ensure that the correct credentials are used. Implement an AWS
Lambda function that rotates the Aurora credentials every 14 days and uploads these credentials to the file in the S3 bucket.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company hosts a multi-tier web application that uses an Amazon Aurora MySQL DB cluster for storage. The application tier is hosted on Amazon EC2 instances. The company’s IT security guidelines mandate that the database credentials be encrypted and rotated every 14 days.

What should a solutions architect do to meet this requirement with the LEAST operational effort?


**A.** Create a new AWS Key Management Service (AWS KMS) encryption key. Use AWS Secrets Manager to create a new secret that uses the KMS key with the appropriate credentials. Associate the secret with the Aurora DB cluster. Configure a custom rotation period of 14 days.

A proposes to create a new AWS KMS encryption key and use AWS Secrets Manager to create a new secret that uses the KMS key with the appropriate credentials. Then, the secret will be associated with the Aurora DB cluster, and a custom rotation period of 14 days will be configured. AWS Secrets Manager will automate the process of rotating the database credentials, which will reduce the operational effort required to meet the IT security guidelines.

</details>

---

## Question 337

[Review topic](../sections/rds-aurora.md) · Source PDF page 122

A company has deployed a web application on AWS. The company hosts the backend database on Amazon RDS for MySQL with a primary DB
instance and five read replicas to support scaling needs. The read replicas must lag no more than 1 second behind the primary DB instance. The
database routinely runs scheduled stored procedures.
As traffic on the website increases, the replicas experience additional lag during periods of peak load. A solutions architect must reduce the
replication lag as much as possible. The solutions architect must minimize changes to the application code and must minimize ongoing
operational overhead.
Which solution will meet these requirements?

**A.** Migrate the database to Amazon Aurora MySQL. Replace the read replicas with Aurora Replicas, and configure Aurora Auto Scaling. Replace
the stored procedures with Aurora MySQL native functions.

**B.** Deploy an Amazon ElastiCache for Redis cluster in front of the database. Modify the application to check the cache before the application
queries the database. Replace the stored procedures with AWS Lambda functions.

**C.** Migrate the database to a MySQL database that runs on Amazon EC2 instances. Choose large, compute optimized EC2 instances for all
replica nodes. Maintain the stored procedures on the EC2 instances.

**D.** Migrate the database to Amazon DynamoDB. Provision a large number of read capacity units (RCUs) to support the required throughput,
and configure on-demand capacity scaling. Replace the stored procedures with DynamoDB streams.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has deployed a web application on AWS. The company hosts the backend database on Amazon RDS for MySQL with a primary DB instance and five read replicas to support scaling needs. The read replicas must lag no more than 1 second behind the primary DB instance. The database routinely runs scheduled stored procedures.

As traffic on the website increases, the replicas experience additional lag during periods of peak load. A solutions architect must reduce the replication lag as much as possible. The solutions architect must minimize changes to the application code and must minimize ongoing operational overhead.

Which solution will meet these requirements?


**A.** Migrate the database to Amazon Aurora MySQL. Replace the read replicas with Aurora Replicas, and configure Aurora Auto Scaling. Replace the stored procedures with Aurora MySQL native functions.

Amazon Aurora MySQL: Aurora Replicas in Amazon Aurora MySQL are designed to have minimal replication lag compared to traditional MySQL read replicas. Aurora is built for high performance and low replication lag, making it a suitable choice for reducing lag in read replicas.

Aurora Auto Scaling: Aurora Auto Scaling allows you to automatically adjust the number of Aurora Replicas based on actual application usage. This ensures that you have the right amount of read capacity during periods of peak load, minimizing replication lag.

</details>

---

## Question 338

[Review topic](../sections/rds-aurora.md) · Source PDF page 123

A solutions architect must create a disaster recovery (DR) plan for a high-volume software as a service (SaaS) platform. All data for the platform
is stored in an Amazon Aurora MySQL DB cluster.
The DR plan must replicate data to a secondary AWS Region.
Which solution will meet these requirements MOST cost-effectively?

**A.** Use MySQL binary log replication to an Aurora cluster in the secondary Region. Provision one DB instance for the Aurora cluster in the
secondary Region.

**B.** Set up an Aurora global database for the DB cluster. When setup is complete, remove the DB instance from the secondary Region.

**C.** Use AWS Database Migration Service (AWS DMS) to continuously replicate data to an Aurora cluster in the secondary Region. Remove the
DB instance from the secondary Region.

**D.** Set up an Aurora global database for the DB cluster. Specify a minimum of one DB instance in the secondary Region.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect must create a disaster recovery (DR) plan for a high-volume software as a service (SaaS) platform. All data for the platform is stored in an Amazon Aurora MySQL DB cluster.

The DR plan must replicate data to a secondary AWS Region.

Which solution will meet these requirements MOST cost-effectively?


**D.** Set up an Aurora global database for the DB cluster. Specify a minimum of one DB instance in the secondary Region.

</details>

---

## Question 339

[Review topic](../sections/rds-aurora.md) · Source PDF page 123

A company has a custom application with embedded credentials that retrieves information from an Amazon RDS MySQL DB instance.
Management says the application must be made more secure with the least amount of programming effort.
What should a solutions architect do to meet these requirements?

**A.** Use AWS Key Management Service (AWS KMS) to create keys. Configure the application to load the database credentials from AWS KMS.
Enable automatic key rotation.

**B.** Create credentials on the RDS for MySQL database for the application user and store the credentials in AWS Secrets Manager. Configure the
application to load the database credentials from Secrets Manager. Create an AWS Lambda function that rotates the credentials in Secret
Manager.

**C.** Create credentials on the RDS for MySQL database for the application user and store the credentials in AWS Secrets Manager. Configure
the application to load the database credentials from Secrets Manager. Set up a credentials rotation schedule for the application user in the
RDS for MySQL database using Secrets Manager.

**D.** Create credentials on the RDS for MySQL database for the application user and store the credentials in AWS Systems Manager Parameter
Store. Configure the application to load the database credentials from Parameter Store. Set up a credentials rotation schedule for the
application user in the RDS for MySQL database using Parameter Store.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a custom application with embedded credentials that retrieves information from an Amazon RDS MySQL DB instance. Management says the application must be made more secure with the least amount of programming effort.

What should a solutions architect do to meet these requirements?


**C.** Create credentials on the RDS for MySQL database for the application user and store the credentials in AWS Secrets Manager. Configure the application to load the database credentials from Secrets Manager. Set up a credentials rotation schedule for the application user in the RDS for MySQL database using Secrets Manager.

C is a valid solution for securing the custom application with the least amount of programming effort. It involves creating credentials on the RDS for MySQL database for the application user and storing them in AWS Secrets Manager. The application can then be configured to load the database credentials from Secrets Manager. Additionally, the solution includes setting up a credentials rotation schedule for the application user in the RDS for MySQL database using Secrets Manager, which will automatically rotate the credentials at a specified interval without requiring any programming effort.

</details>

---

## Question 340

[Review topic](../sections/elb-asg.md) · Source PDF page 123

A media company hosts its website on AWS. The website application’s architecture includes a fleet of Amazon EC2 instances behind an
Application Load Balancer (ALB) and a database that is hosted on Amazon Aurora. The company’s cybersecurity team reports that the application
is vulnerable to SQL injection.
How should the company resolve this issue?

**A.** Use AWS WAF in front of the ALB. Associate the appropriate web ACLs with AWS WAF.

**B.** Create an ALB listener rule to reply to SQL injections with a fixed response.

**C.** Subscribe to AWS Shield Advanced to block all SQL injection attempts automatically.

**D.** Set up Amazon Inspector to block all SQL injection attempts automatically.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A media company hosts its website on AWS. The website application’s architecture includes a fleet of Amazon EC2 instances behind an Application Load Balancer (ALB) and a database that is hosted on Amazon Aurora. The company’s cybersecurity team reports that the application is vulnerable to SQL injection.

How should the company resolve this issue?


**A.** Use AWS WAF in front of the ALB. Associate the appropriate web ACLs with AWS WAF.

AWS WAF (Web Application Firewall): AWS WAF is designed to protect web applications from common web exploits, including SQL injection. It allows you to create web access control lists (web ACLs) to define rules that filter and monitor HTTP traffic to your application.

Associating Web ACLs with AWS WAF: By using AWS WAF in front of the ALB, you can define rules to block or allow web requests based on conditions that you specify. This includes protection against SQL injection attempts. AWS WAF provides a range of conditions and rulesets that you can use to mitigate common security threats.

</details>

---

## Question 341

[Review topic](../sections/analytics.md) · Source PDF page 124

A company has an Amazon S3 data lake that is governed by AWS Lake Formation. The company wants to create a visualization in Amazon
QuickSight by joining the data in the data lake with operational data that is stored in an Amazon Aurora MySQL database. The company wants to
enforce column-level authorization so that the company’s marketing team can access only a subset of columns in the database.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use Amazon EMR to ingest the data directly from the database to the QuickSight SPICE engine. Include only the required columns.

**B.** Use AWS Glue Studio to ingest the data from the database to the S3 data lake. Attach an IAM policy to the QuickSight users to enforce
column-level access control. Use Amazon S3 as the data source in QuickSight.

**C.** Use AWS Glue Elastic Views to create a materialized view for the database in Amazon S3. Create an S3 bucket policy to enforce column-
level access control for the QuickSight users. Use Amazon S3 as the data source in QuickSight.

**D.** Use a Lake Formation blueprint to ingest the data from the database to the S3 data lake. Use Lake Formation to enforce column-level
access control for the QuickSight users. Use Amazon Athena as the data source in QuickSight.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: D**

Ingest into the governed data lake and use Lake Formation column permissions with Athena-backed QuickSight access. Check current blueprint and connector availability.

**Original companion notes (not independently verified):**

A company has an Amazon S3 data lake that is governed by AWS Lake Formation. The company wants to create a visualization in Amazon QuickSight by joining the data in the data lake with operational data that is stored in an Amazon Aurora MySQL database. The company wants to enforce column-level authorization so that the company’s marketing team can access only a subset of columns in the database.

Which solution will meet these requirements with the LEAST operational overhead?

</details>

---

## Question 342

[Review topic](../sections/elb-asg.md) · Source PDF page 124

A transaction processing company has weekly scripted batch jobs that run on Amazon EC2 instances. The EC2 instances are in an Auto Scaling
group. The number of transactions can vary, but the baseline CPU utilization that is noted on each run is at least 60%. The company needs to
provision the capacity 30 minutes before the jobs run.
Currently, engineers complete this task by manually modifying the Auto Scaling group parameters. The company does not have the resources to
analyze the required capacity trends for the Auto Scaling group counts. The company needs an automated way to modify the Auto Scaling group’s
desired capacity.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create a dynamic scaling policy for the Auto Scaling group. Configure the policy to scale based on the CPU utilization metric. Set the target
value for the metric to 60%.

**B.** Create a scheduled scaling policy for the Auto Scaling group. Set the appropriate desired capacity, minimum capacity, and maximum
capacity. Set the recurrence to weekly. Set the start time to 30 minutes before the batch jobs run.

**C.** Create a predictive scaling policy for the Auto Scaling group. Configure the policy to scale based on forecast. Set the scaling metric to CPU
utilization. Set the target value for the metric to 60%. In the policy, set the instances to pre-launch 30 minutes before the jobs run.

**D.** Create an Amazon EventBridge event to invoke an AWS Lambda function when the CPU utilization metric value for the Auto Scaling group
reaches 60%. Configure the Lambda function to increase the Auto Scaling group’s desired capacity and maximum capacity by 20%.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A transaction processing company has weekly scripted batch jobs that run on Amazon EC2 instances. The EC2 instances are in an Auto Scaling group. The number of transactions can vary, but the baseline CPU utilization that is noted on each run is at least 60%. The company needs to provision the capacity 30 minutes before the jobs run.

Currently, engineers complete this task by manually modifying the Auto Scaling group parameters. The company does not have the resources to analyze the required capacity trends for the Auto Scaling group counts. The company needs an automated way to modify the Auto Scaling group’s desired capacity.

Which solution will meet these requirements with the LEAST operational overhead?


**C.** Create a predictive scaling policy for the Auto Scaling group. Configure the policy to scale based on forecast. Set the scaling metric to CPU utilization. Set the target value for the metric to 60%. In the policy, set the instances to pre-launch 30 minutes before the jobs run.

In general, if you have regular patterns of traffic increases and applications that take a long time to initialize, you should consider using predictive scaling. Predictive scaling can help you scale faster by launching capacity in advance of forecasted load, compared to using only dynamic scaling, which is reactive in nature.

</details>

---

## Question 343

[Review topic](../sections/disaster-recovery.md) · Source PDF page 125

A solutions architect is designing a company’s disaster recovery (DR) architecture. The company has a MySQL database that runs on an Amazon
EC2 instance in a private subnet with scheduled backup. The DR design needs to include multiple AWS Regions.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Migrate the MySQL database to multiple EC2 instances. Configure a standby EC2 instance in the DR Region. Turn on replication.

**B.** Migrate the MySQL database to Amazon RDS. Use a Multi-AZ deployment. Turn on read replication for the primary DB instance in the
different Availability Zones.

**C.** Migrate the MySQL database to an Amazon Aurora global database. Host the primary DB cluster in the primary Region. Host the secondary
DB cluster in the DR Region.

**D.** Store the scheduled backup of the MySQL database in an Amazon S3 bucket that is configured for S3 Cross-Region Replication (CRR). Use
the data backup to restore the database in the DR Region.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing a company’s disaster recovery (DR) architecture. The company has a MySQL database that runs on an Amazon EC2 instance in a private subnet with scheduled backup. The DR design needs to include multiple AWS Regions.

Which solution will meet these requirements with the LEAST operational overhead?


**C.** Migrate the MySQL database to an Amazon Aurora global database. Host the primary DB cluster in the primary Region. Host the secondary DB cluster in the DR Region.

</details>

---

## Question 344

[Review topic](../sections/messaging.md) · Source PDF page 125

A company has a Java application that uses Amazon Simple Queue Service (Amazon SQS) to parse messages. The application cannot parse
messages that are larger than 256 KB in size. The company wants to implement a solution to give the application the ability to parse messages as
large as 50 MB.
Which solution will meet these requirements with the FEWEST changes to the code?

**A.** Use the Amazon SQS Extended Client Library for Java to host messages that are larger than 256 KB in Amazon S3.

**B.** Use Amazon EventBridge to post large messages from the application instead of Amazon SQS.

**C.** Change the limit in Amazon SQS to handle messages that are larger than 256 KB.

**D.** Store messages that are larger than 256 KB in Amazon Elastic File System (Amazon EFS). Configure Amazon SQS to reference this location
in the messages.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a Java application that uses Amazon Simple Queue Service (Amazon SQS) to parse messages. The application cannot parse messages that are larger than 256 KB in size. The company wants to implement a solution to give the application the ability to parse messages as large as 50 MB.

Which solution will meet these requirements with the FEWEST changes to the code?


**A.** Use the Amazon SQS Extended Client Library for Java to host messages that are larger than 256 KB in Amazon S3.

Amazon SQS Extended Client Library for Java: This library is specifically designed to handle larger messages in Amazon SQS by transparently offloading them to Amazon S3. It allows you to send a reference to the S3 object in the SQS message while keeping the actual payload in S3.

Minimal Code Changes: Using the Amazon SQS Extended Client Library for Java requires minimal changes to the existing code. Developers need to integrate the library, and the library itself handles the details of storing and retrieving large messages from Amazon S3.

</details>

---

## Question 345

[Review topic](../sections/serverless.md) · Source PDF page 125

A company wants to restrict access to the content of one of its main web applications and to protect the content by using authorization
techniques available on AWS. The company wants to implement a serverless architecture and an authentication solution for fewer than 100 users.
The solution needs to integrate with the main web application and serve web content globally. The solution must also scale as the company's user
base grows while providing the lowest login latency possible.
Which solution will meet these requirements MOST cost-effectively?

**A.** Use Amazon Cognito for authentication. Use Lambda@Edge for authorization. Use Amazon CloudFront to serve the web application
globally.

**B.** Use AWS Directory Service for Microsoft Active Directory for authentication. Use AWS Lambda for authorization. Use an Application Load
Balancer to serve the web application globally.

**C.** Use Amazon Cognito for authentication. Use AWS Lambda for authorization. Use Amazon S3 Transfer Acceleration to serve the web
application globally.

**D.** Use AWS Directory Service for Microsoft Active Directory for authentication. Use Lambda@Edge for authorization. Use AWS Elastic
Beanstalk to serve the web application globally.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to restrict access to the content of one of its main web applications and to protect the content by using authorization techniques available on AWS. The company wants to implement a serverless architecture and an authentication solution for fewer than 100 users. The solution needs to integrate with the main web application and serve web content globally. The solution must also scale as the company's user base grows while providing the lowest login latency possible.

Which solution will meet these requirements MOST cost-effectively?


**A.** Use Amazon Cognito for authentication. Use Lambda@Edge for authorization. Use Amazon CloudFront to serve the web application globally.

Amazon Cognito for Authentication: Amazon Cognito is a fully managed service for user identity and access control. It provides easy integration for authentication with a serverless architecture and supports a user pool for fewer than 100 users.

Lambda@Edge for Authorization: Lambda@Edge allows you to run custom code in response to CloudFront events, including authorization. You can implement authorization logic at the edge locations closest to the end-users, providing low-latency access.

Amazon CloudFront for Content Delivery: Amazon CloudFront is a global content delivery network (CDN) that integrates seamlessly with Lambda@Edge. CloudFront can serve the web application globally, distributing content from edge locations for low-latency access.

</details>

---

## Question 346

[Review topic](../sections/migration.md) · Source PDF page 126

A company has an aging network-attached storage (NAS) array in its data center. The NAS array presents SMB shares and NFS shares to client
workstations. The company does not want to purchase a new NAS array. The company also does not want to incur the cost of renewing the NAS
array’s support contract. Some of the data is accessed frequently, but much of the data is inactive.
A solutions architect needs to implement a solution that migrates the data to Amazon S3, uses S3 Lifecycle policies, and maintains the same look
and feel for the client workstations. The solutions architect has identified AWS Storage Gateway as part of the solution.
Which type of storage gateway should the solutions architect provision to meet these requirements?

**A.** Volume Gateway

**B.** Tape Gateway

**C.** Amazon FSx File Gateway

**D.** Amazon S3 File Gateway

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an aging network-attached storage (NAS) array in its data center. The NAS array presents SMB shares and NFS shares to client workstations. The company does not want to purchase a new NAS array. The company also does not want to incur the cost of renewing the NAS array’s support contract. Some of the data is accessed frequently, but much of the data is inactive.

A solutions architect needs to implement a solution that migrates the data to Amazon S3, uses S3 Lifecycle policies, and maintains the same look and feel for the client workstations. The solutions architect has identified AWS Storage Gateway as part of the solution.

Which type of storage gateway should the solutions architect provision to meet these requirements?


**D.** Amazon S3 File Gateway

Amazon S3 File Gateway provides on-premises applications with access to virtually unlimited cloud storage using NFS and SMB file interfaces. It seamlessly moves frequently accessed data to a low-latency cache while storing colder data in Amazon S3, using S3 Lifecycle policies to transition data between storage classes over tim

</details>

---

## Question 347

[Review topic](../sections/cost-governance.md) · Source PDF page 126

A company has an application that is running on Amazon EC2 instances. A solutions architect has standardized the company on a particular
instance family and various instance sizes based on the current needs of the company.
The company wants to maximize cost savings for the application over the next 3 years. The company needs to be able to change the instance
family and sizes in the next 6 months based on application popularity and usage.
Which solution will meet these requirements MOST cost-effectively?

**A.** Compute Savings Plan

**B.** EC2 Instance Savings Plan

**C.** Zonal Reserved Instances

**D.** Standard Reserved Instances

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an application that is running on Amazon EC2 instances. A solutions architect has standardized the company on a particular instance family and various instance sizes based on the current needs of the company.

The company wants to maximize cost savings for the application over the next 3 years. The company needs to be able to change the instance family and sizes in the next 6 months based on application popularity and usage.

Which solution will meet these requirements MOST cost-effectively?


**A.** Compute Savings Plan 

Compute Savings Plans provide significant cost savings over On-Demand pricing in exchange for a commitment to a consistent amount of compute usage (measured in $/hr) for a 1 or 3 year period. They offer flexibility by allowing you to switch between instance families, sizes, and AZs (Availability Zones) while still benefiting from the savings plan pricing. This aligns well with the company's requirement to change instance family and sizes based on application needs.

</details>

---

## Question 348

[Review topic](../sections/dynamodb-caching.md) · Source PDF page 126

A company collects data from a large number of participants who use wearable devices. The company stores the data in an Amazon DynamoDB
table and uses applications to analyze the data. The data workload is constant and predictable. The company wants to stay at or below its
forecasted budget for DynamoDB.
Which solution will meet these requirements MOST cost-effectively?

**A.** Use provisioned mode and DynamoDB Standard-Infrequent Access (DynamoDB Standard-IA). Reserve capacity for the forecasted workload.

**B.** Use provisioned mode. Specify the read capacity units (RCUs) and write capacity units (WCUs).

**C.** Use on-demand mode. Set the read capacity units (RCUs) and write capacity units (WCUs) high enough to accommodate changes in the
workload.

**D.** Use on-demand mode. Specify the read capacity units (RCUs) and write capacity units (WCUs) with reserved capacity.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company collects data from a large number of participants who use wearable devices. The company stores the data in an Amazon DynamoDB table and uses applications to analyze the data. The data workload is constant and predictable. The company wants to stay at or below its forecasted budget for DynamoDB.

Which solution will meet these requirements MOST cost-effectively?


**B.** Use provisioned mode. Specify the read capacity units (RCUs) and write capacity units (WCUs).

In provisioned mode, you provision a specific amount of read and write capacity, which allows you to manage costs more effectively based on your expected workload. This approach is suitable when your workload is predictable, as you can provision the capacity to meet your known requirements. DynamoDB Standard-Infrequent Access (Option A) is designed for cost savings on long-term storage and retrieval of infrequently accessed data, and it might not be the best fit for a constant and predictable workload.

</details>

---

## Question 349

[Review topic](../sections/rds-aurora.md) · Source PDF page 127

A company stores confidential data in an Amazon Aurora PostgreSQL database in the ap-southeast-3 Region. The database is encrypted with an
AWS Key Management Service (AWS KMS) customer managed key. The company was recently acquired and must securely share a backup of the
database with the acquiring company’s AWS account in ap-southeast-3.
What should a solutions architect do to meet these requirements?

**A.** Create a database snapshot. Copy the snapshot to a new unencrypted snapshot. Share the new snapshot with the acquiring company’s
AWS account.

**B.** Create a database snapshot. Add the acquiring company’s AWS account to the KMS key policy. Share the snapshot with the acquiring
company’s AWS account.

**C.** Create a database snapshot that uses a different AWS managed KMS key. Add the acquiring company’s AWS account to the KMS key alias.
Share the snapshot with the acquiring company's AWS account.

**D.** Create a database snapshot. Download the database snapshot. Upload the database snapshot to an Amazon S3 bucket. Update the S3
bucket policy to allow access from the acquiring company’s AWS account.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company stores confidential data in an Amazon Aurora PostgreSQL database in the ap-southeast-3 Region. The database is encrypted with an AWS Key Management Service (AWS KMS) customer managed key. The company was recently acquired and must securely share a backup of the database with the acquiring company’s AWS account in ap-southeast-3.

What should a solutions architect do to meet these requirements?


**B.** Create a database snapshot. Add the acquiring company’s AWS account to the KMS key policy. Share the snapshot with the acquiring company’s AWS account.

sharing encrypted snapshots involves granting permission not only on the snapshot itself but also on the underlying AWS Key Management Service (KMS) key used for encryption.
By adding the acquiring company's AWS account to the KMS key policy, you ensure that they have the necessary permissions to decrypt and access the snapshot.
Sharing the snapshot with the acquiring company's AWS account completes the process, allowing them to restore the database from the shared snapshot.

</details>

---

## Question 350

[Review topic](../sections/rds-aurora.md) · Source PDF page 127

A company uses a 100 GB Amazon RDS for Microsoft SQL Server Single-AZ DB instance in the us-east-1 Region to store customer transactions.
The company needs high availability and automatic recovery for the DB instance.
The company must also run reports on the RDS database several times a year. The report process causes transactions to take longer than usual to
post to the customers’ accounts. The company needs a solution that will improve the performance of the report process.
Which combination of steps will meet these requirements? (Choose two.)

**A.** Modify the DB instance from a Single-AZ DB instance to a Multi-AZ deployment.

**B.** Take a snapshot of the current DB instance. Restore the snapshot to a new RDS deployment in another Availability Zone.

**C.** Create a read replica of the DB instance in a different Availability Zone. Point all requests for reports to the read replica.

**D.** Migrate the database to RDS Custom.

**E.** Use RDS Proxy to limit reporting requests to the maintenance window.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses a 100 GB Amazon RDS for Microsoft SQL Server Single-AZ DB instance in the us-east-1 Region to store customer transactions. The company needs high availability and automatic recovery for the DB instance.

The company must also run reports on the RDS database several times a year. The report process causes transactions to take longer than usual to post to the customers’ accounts. The company needs a solution that will improve the performance of the report process.

Which combination of steps will meet these requirements? (Choose two.)


**A.** Modify the DB instance from a Single-AZ DB instance to a Multi-AZ deployment:

Enabling Multi-AZ deployment provides high availability by replicating the database to a standby instance in another Availability Zone. This helps in automatic failover and recovery in case of a primary instance failure.

**C.** Create a read replica of the DB instance in a different Availability Zone. Point all requests for reports to the read replica:

By creating a read replica in a different Availability Zone, you offload the reporting workload from the primary instance, reducing the impact on transaction processing. Read replicas can be used to scale read-heavy workloads and improve overall performance.

</details>

---

