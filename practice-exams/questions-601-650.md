# Practice questions 601-650

[Home](../README.md) · [All sets](README.md)

Answer notes are source-provided unless labeled suggested. These sets preserve the supplied PDF; they are not official AWS exams.

## Question 601

[Review topic](../sections/rds-aurora.md) · Source PDF page 219

A company runs its critical database on an Amazon RDS for PostgreSQL DB instance. The company wants to migrate to Amazon Aurora
PostgreSQL with minimal downtime and data loss.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create a DB snapshot of the RDS for PostgreSQL DB instance to populate a new Aurora PostgreSQL DB cluster.

**B.** Create an Aurora read replica of the RDS for PostgreSQL DB instance. Promote the Aurora read replicate to a new Aurora PostgreSQL DB
cluster.

**C.** Use data import from Amazon S3 to migrate the database to an Aurora PostgreSQL DB cluster.

**D.** Use the pg_dump utility to back up the RDS for PostgreSQL database. Restore the backup to a new Aurora PostgreSQL DB cluster.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs its critical database on an Amazon RDS for PostgreSQL DB instance. The company wants to migrate to Amazon Aurora PostgreSQL with minimal downtime and data loss.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Create an Aurora read replica of the RDS for PostgreSQL DB instance. Promote the Aurora read replicate to a new Aurora PostgreSQL DB cluster.

Aurora Read Replica: Creating an Aurora read replica from the RDS for PostgreSQL DB instance is a low-impact operation that allows you to replicate the data to Aurora with minimal downtime.
Promote to Aurora PostgreSQL DB Cluster: Once the read replica is in sync with the primary RDS instance, you can promote the Aurora read replica to become the new primary cluster.

</details>

---

## Question 602

[Review topic](../sections/ec2.md) · Source PDF page 220

A company's infrastructure consists of hundreds of Amazon EC2 instances that use Amazon Elastic Block Store (Amazon EBS) storage. A
solutions architect must ensure that every EC2 instance can be recovered after a disaster.
What should the solutions architect do to meet this requirement with the LEAST amount of effort?

**A.** Take a snapshot of the EBS storage that is attached to each EC2 instance. Create an AWS CloudFormation template to launch new EC2
instances from the EBS storage.

**B.** Take a snapshot of the EBS storage that is attached to each EC2 instance. Use AWS Elastic Beanstalk to set the environment based on the
EC2 template and attach the EBS storage.

**C.** Use AWS Backup to set up a backup plan for the entire group of EC2 instances. Use the AWS Backup API or the AWS CLI to speed up the
restore process for multiple EC2 instances.

**D.** Create an AWS Lambda function to take a snapshot of the EBS storage that is attached to each EC2 instance and copy the Amazon
Machine Images (AMIs). Create another Lambda function to perform the restores with the copied AMIs and attach the EBS storage.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company's infrastructure consists of hundreds of Amazon EC2 instances that use Amazon Elastic Block Store (Amazon EBS) storage. A solutions architect must ensure that every EC2 instance can be recovered after a disaster.

What should the solutions architect do to meet this requirement with the LEAST amount of effort?


**C.** Use AWS Backup to set up a backup plan for the entire group of EC2 instances. Use the AWS Backup API or the AWS CLI to speed up the restore process for multiple EC2 instances.

AWS Backup: AWS Backup is a fully managed backup service that centralizes and automates the backup of data across AWS services. 
Backup Plan: You can set up a backup plan in AWS Backup to create and manage backups of the entire group of EC2 instances. 
AWS Backup provides a streamlined process for restoring data. You can use the AWS Backup console, API, or AWS CLI to initiate the restore process for multiple EC2 instances.

</details>

---

## Question 603

[Review topic](../sections/s3.md) · Source PDF page 220

A company recently migrated to the AWS Cloud. The company wants a serverless solution for large-scale parallel on-demand processing of a
semistructured dataset. The data consists of logs, media files, sales transactions, and IoT sensor data that is stored in Amazon S3. The company
wants the solution to process thousands of items in the dataset in parallel.
Which solution will meet these requirements with the MOST operational efficiency?

**A.** Use the AWS Step Functions Map state in Inline mode to process the data in parallel.

**B.** Use the AWS Step Functions Map state in Distributed mode to process the data in parallel.

**C.** Use AWS Glue to process the data in parallel.

**D.** Use several AWS Lambda functions to process the data in parallel.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company recently migrated to the AWS Cloud. The company wants a serverless solution for large-scale parallel on-demand processing of a semistructured dataset. The data consists of logs, media files, sales transactions, and IoT sensor data that is stored in Amazon S3. The company wants the solution to process thousands of items in the dataset in parallel.

Which solution will meet these requirements with the MOST operational efficiency?


**B.** Use the AWS Step Functions Map state in Distributed mode to process the data in parallel.

The Map state in AWS Step Functions is designed for parallel processing. In Distributed mode, it efficiently processes items in parallel, providing a scalable solution. This allows you to process thousands of items concurrently, achieving high throughput.

</details>

---

## Question 604

[Review topic](../sections/s3.md) · Source PDF page 220

A company will migrate 10 PB of data to Amazon S3 in 6 weeks. The current data center has a 500 Mbps uplink to the internet. Other on-premises
applications share the uplink. The company can use 80% of the internet bandwidth for this one-time migration task.
Which solution will meet these requirements?

**A.** Configure AWS DataSync to migrate the data to Amazon S3 and to automatically verify the data.

**B.** Use rsync to transfer the data directly to Amazon S3.

**C.** Use the AWS CLI and multiple copy processes to send the data directly to Amazon S3.

**D.** Order multiple AWS Snowball devices. Copy the data to the devices. Send the devices to AWS to copy the data to Amazon S3.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company will migrate 10 PB of data to Amazon S3 in 6 weeks. The current data center has a 500 Mbps uplink to the internet. Other on-premises applications share the uplink. The company can use 80% of the internet bandwidth for this one-time migration task.

Which solution will meet these requirements?


**D.** Order multiple AWS Snowball devices. Copy the data to the devices. Send the devices to AWS to copy the data to Amazon S3.

With only a 500 Mbps uplink bandwidth shared among other on-premises applications, transferring 10 PB of data over the internet would be impractical and time-consuming. AWS Snowball provides a physical device that can be shipped to the company to facilitate faster initial data transfer.

</details>

---

## Question 605

[Review topic](../sections/exam-revision.md) · Source PDF page 221

A company has several on-premises Internet Small Computer Systems Interface (ISCSI) network storage servers. The company wants to reduce
the number of these servers by moving to the AWS Cloud. A solutions architect must provide low-latency access to frequently used data and
reduce the dependency on on-premises servers with a minimal number of infrastructure changes.
Which solution will meet these requirements?

**A.** Deploy an Amazon S3 File Gateway.

**B.** Deploy Amazon Elastic Block Store (Amazon EBS) storage with backups to Amazon S3.

**C.** Deploy an AWS Storage Gateway volume gateway that is configured with stored volumes.

**D.** Deploy an AWS Storage Gateway volume gateway that is configured with cached volumes.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has several on-premises Internet Small Computer Systems Interface (ISCSI) network storage servers. The company wants to reduce the number of these servers by moving to the AWS Cloud. A solutions architect must provide low-latency access to frequently used data and reduce the dependency on on-premises servers with a minimal number of infrastructure changes.

Which solution will meet these requirements?


**D.** Deploy an AWS Storage Gateway volume gateway that is configured with cached volumes. 

A volume gateway with cached volumes is a good fit when you want to keep frequently accessed data on-premises for low-latency access while still having a copy in the AWS Cloud. Cached volumes store the entire dataset in Amazon S3 while retaining the most frequently accessed data locally.

</details>

---

## Question 606

[Review topic](../sections/s3.md) · Source PDF page 221

A solutions architect is designing an application that will allow business users to upload objects to Amazon S3. The solution needs to maximize
object durability. Objects also must be readily available at any time and for any length of time. Users will access objects frequently within the first
30 days after the objects are uploaded, but users are much less likely to access objects that are older than 30 days.
Which solution meets these requirements MOST cost-effectively?

**A.** Store all the objects in S3 Standard with an S3 Lifecycle rule to transition the objects to S3 Glacier after 30 days.

**B.** Store all the objects in S3 Standard with an S3 Lifecycle rule to transition the objects to S3 Standard-Infrequent Access (S3 Standard-IA)
after 30 days.

**C.** Store all the objects in S3 Standard with an S3 Lifecycle rule to transition the objects to S3 One Zone-Infrequent Access (S3 One Zone-IA)
after 30 days.

**D.** Store all the objects in S3 Intelligent-Tiering with an S3 Lifecycle rule to transition the objects to S3 Standard-Infrequent Access (S3
Standard-IA) after 30 days.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing an application that will allow business users to upload objects to Amazon S3. The solution needs to maximize object durability. Objects also must be readily available at any time and for any length of time. Users will access objects frequently within the first 30 days after the objects are uploaded, but users are much less likely to access objects that are older than 30 days.

Which solution meets these requirements MOST cost-effectively?


**B.** Store all the objects in S3 Standard with an S3 Lifecycle rule to transition the objects to S3 Standard-Infrequent Access (S3 Standard-IA) after 30 days.

 Storing objects in S3 Standard ensures low-latency access and high durability. After 30 days, transitioning objects to S3 Standard-IA allows you to take advantage of a lower storage cost for objects that are less frequently accessed.

</details>

---

## Question 607

[Review topic](../sections/rds-aurora.md) · Source PDF page 221

A company has migrated a two-tier application from its on-premises data center to the AWS Cloud. The data tier is a Multi-AZ deployment of
Amazon RDS for Oracle with 12 TB of General Purpose SSD Amazon Elastic Block Store (Amazon EBS) storage. The application is designed to
process and store documents in the database as binary large objects (blobs) with an average document size of 6 MB.
The database size has grown over time, reducing the performance and increasing the cost of storage. The company must improve the database
performance and needs a solution that is highly available and resilient.
Which solution will meet these requirements MOST cost-effectively?

**A.** Reduce the RDS DB instance size. Increase the storage capacity to 24 TiB. Change the storage type to Magnetic.

**B.** Increase the RDS DB instance size. Increase the storage capacity to 24 TiChange the storage type to Provisioned IOPS.

**C.** Create an Amazon S3 bucket. Update the application to store documents in the S3 bucket. Store the object metadata in the existing
database.

**D.** Create an Amazon DynamoDB table. Update the application to use DynamoDB. Use AWS Database Migration Service (AWS DMS) to migrate
data from the Oracle database to DynamoDB.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has migrated a two-tier application from its on-premises data center to the AWS Cloud. The data tier is a Multi-AZ deployment of Amazon RDS for Oracle with 12 TB of General Purpose SSD Amazon Elastic Block Store (Amazon EBS) storage. The application is designed to process and store documents in the database as binary large objects (blobs) with an average document size of 6 MB.

The database size has grown over time, reducing the performance and increasing the cost of storage. The company must improve the database performance and needs a solution that is highly available and resilient.

Which solution will meet these requirements MOST cost-effectively?


**C.** Create an Amazon S3 bucket. Update the application to store documents in the S3 bucket. Store the object metadata in the existing database.

Amazon S3 is highly scalable, durable, and cost-effective for storing objects, making it well-suited for binary large objects (blobs) such as documents. It provides low-latency access and is designed to handle large volumes of data.

</details>

---

## Question 608

[Review topic](../sections/elb-asg.md) · Source PDF page 222

A company has an application that serves clients that are deployed in more than 20.000 retail storefront locations around the world. The
application consists of backend web services that are exposed over HTTPS on port 443. The application is hosted on Amazon EC2 instances
behind an Application Load Balancer (ALB). The retail locations communicate with the web application over the public internet. The company
allows each retail location to register the IP address that the retail location has been allocated by its local ISP.
The company's security team recommends to increase the security of the application endpoint by restricting access to only the IP addresses
registered by the retail locations.
What should a solutions architect do to meet these requirements?

**A.** Associate an AWS WAF web ACL with the ALB. Use IP rule sets on the ALB to filter traffic. Update the IP addresses in the rule to include the
registered IP addresses.

**B.** Deploy AWS Firewall Manager to manage the ALConfigure firewall rules to restrict traffic to the ALModify the firewall rules to include the
registered IP addresses.

**C.** Store the IP addresses in an Amazon DynamoDB table. Configure an AWS Lambda authorization function on the ALB to validate that
incoming requests are from the registered IP addresses.

**D.** Configure the network ACL on the subnet that contains the public interface of the ALB. Update the ingress rules on the network ACL with
entries for each of the registered IP addresses.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: A**

Attach a WAF web ACL to the ALB with allowlisted IP sets and a default block action. Split the storefront list across IP sets as required by current quotas.

**Original companion notes (not independently verified):**

A company has an application that serves clients that are deployed in more than 20.000 retail storefront locations around the world. The application consists of backend web services that are exposed over HTTPS on port 443. The application is hosted on Amazon EC2 instances behind an Application Load Balancer (ALB). The retail locations communicate with the web application over the public internet. The company allows each retail location to register the IP address that the retail location has been allocated by its local ISP.

The company's security team recommends to increase the security of the application endpoint by restricting access to only the IP addresses registered by the retail locations.

What should a solutions architect do to meet these requirements?

</details>

---

## Question 609

[Review topic](../sections/analytics.md) · Source PDF page 222

A company is building a data analysis platform on AWS by using AWS Lake Formation. The platform will ingest data from different sources such
as Amazon S3 and Amazon RDS. The company needs a secure solution to prevent access to portions of the data that contain sensitive
information.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create an IAM role that includes permissions to access Lake Formation tables.

**B.** Create data filters to implement row-level security and cell-level security.

**C.** Create an AWS Lambda function that removes sensitive information before Lake Formation ingests the data.

**D.** Create an AWS Lambda function that periodically queries and removes sensitive information from Lake Formation tables.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is building a data analysis platform on AWS by using AWS Lake Formation. The platform will ingest data from different sources such as Amazon S3 and Amazon RDS. The company needs a secure solution to prevent access to portions of the data that contain sensitive information.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Create data filters to implement row-level security and cell-level security.

AWS Lake Formation allows you to create data filters that can be used for row-level security and cell-level security.

</details>

---

## Question 610

[Review topic](../sections/ec2.md) · Source PDF page 222

A company deploys Amazon EC2 instances that run in a VPC. The EC2 instances load source data into Amazon S3 buckets so that the data can be
processed in the future. According to compliance laws, the data must not be transmitted over the public internet. Servers in the company's on-
premises data center will consume the output from an application that runs on the EC2 instances.
Which solution will meet these requirements?

**A.** Deploy an interface VPC endpoint for Amazon EC2. Create an AWS Site-to-Site VPN connection between the company and the VPC.

**B.** Deploy a gateway VPC endpoint for Amazon S3. Set up an AWS Direct Connect connection between the on-premises network and the VPC.

**C.** Set up an AWS Transit Gateway connection from the VPC to the S3 buckets. Create an AWS Site-to-Site VPN connection between the
company and the VPC.

**D.** Set up proxy EC2 instances that have routes to NAT gateways. Configure the proxy EC2 instances to fetch S3 data and feed the application
instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company deploys Amazon EC2 instances that run in a VPC. The EC2 instances load source data into Amazon S3 buckets so that the data can be processed in the future. According to compliance laws, the data must not be transmitted over the public internet. Servers in the company's on-premises data center will consume the output from an application that runs on the EC2 instances.

Which solution will meet these requirements?


**B.** Deploy a gateway VPC endpoint for Amazon S3. Set up an AWS Direct Connect connection between the on-premises network and the VPC.
 
A gateway VPC endpoint allows communication between resources in your VPC and Amazon S3 without traversing the public internet.
AWS Direct Connect provides a dedicated network connection from the on-premises data center to the VPC. This dedicated connection enhances security and ensures a reliable and consistent connection between on-premises servers and the EC2 instances in the VPC.

</details>

---

## Question 611

[Review topic](../sections/ec2.md) · Source PDF page 223

A company has an application with a REST-based interface that allows data to be received in near-real time from a third-party vendor. Once
received, the application processes and stores the data for further analysis. The application is running on Amazon EC2 instances.
The third-party vendor has received many 503 Service Unavailable Errors when sending data to the application. When the data volume spikes, the
compute capacity reaches its maximum limit and the application is unable to process all requests.
Which design should a solutions architect recommend to provide a more scalable solution?

**A.** Use Amazon Kinesis Data Streams to ingest the data. Process the data using AWS Lambda functions.

**B.** Use Amazon API Gateway on top of the existing application. Create a usage plan with a quota limit for the third-party vendor.

**C.** Use Amazon Simple Notification Service (Amazon SNS) to ingest the data. Put the EC2 instances in an Auto Scaling group behind an
Application Load Balancer.

**D.** Repackage the application as a container. Deploy the application using Amazon Elastic Container Service (Amazon ECS) using the EC2
launch type with an Auto Scaling group.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an application with a REST-based interface that allows data to be received in near-real time from a third-party vendor. Once received, the application processes and stores the data for further analysis. The application is running on Amazon EC2 instances.

The third-party vendor has received many 503 Service Unavailable Errors when sending data to the application. When the data volume spikes, the compute capacity reaches its maximum limit and the application is unable to process all requests.

Which design should a solutions architect recommend to provide a more scalable solution?


**A.** Use Amazon Kinesis Data Streams to ingest the data. Process the data using AWS Lambda functions.

Kinesis Data Streams is designed for ingesting and processing real-time streaming data at scale. It can handle large volumes of data and provides the ability to scale horizontally.
 Using Lambda functions allows for serverless, event-driven processing of the data. Lambda automatically scales based on the number of incoming events, providing the needed elasticity to handle spikes in data volume without the need to manage underlying infrastructure.

</details>

---

## Question 612

[Review topic](../sections/s3.md) · Source PDF page 223

A company has an application that runs on Amazon EC2 instances in a private subnet. The application needs to process sensitive information
from an Amazon S3 bucket. The application must not use the internet to connect to the S3 bucket.
Which solution will meet these requirements?

**A.** Configure an internet gateway. Update the S3 bucket policy to allow access from the internet gateway. Update the application to use the
new internet gateway.

**B.** Configure a VPN connection. Update the S3 bucket policy to allow access from the VPN connection. Update the application to use the new
VPN connection.

**C.** Configure a NAT gateway. Update the S3 bucket policy to allow access from the NAT gateway. Update the application to use the new NAT
gateway.

**D.** Configure a VPC endpoint. Update the S3 bucket policy to allow access from the VPC endpoint. Update the application to use the new VPC
endpoint.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an application that runs on Amazon EC2 instances in a private subnet. The application needs to process sensitive information from an Amazon S3 bucket. The application must not use the internet to connect to the S3 bucket.

Which solution will meet these requirements?


**D.** Configure a VPC endpoint. Update the S3 bucket policy to allow access from the VPC endpoint. Update the application to use the new VPC endpoint.

VPC Endpoint for S3: A VPC endpoint allows you to privately connect your VPC to supported AWS services, including Amazon S3, without traversing the public internet. This ensures secure and direct access to S3 from within your VPC.

</details>

---

## Question 613

[Review topic](../sections/containers.md) · Source PDF page 223

A company uses Amazon Elastic Kubernetes Service (Amazon EKS) to run a container application. The EKS cluster stores sensitive information in
the Kubernetes secrets object. The company wants to ensure that the information is encrypted.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use the container application to encrypt the information by using AWS Key Management Service (AWS KMS).

**B.** Enable secrets encryption in the EKS cluster by using AWS Key Management Service (AWS KMS).

**C.** Implement an AWS Lambda function to encrypt the information by using AWS Key Management Service (AWS KMS).

**D.** Use AWS Systems Manager Parameter Store to encrypt the information by using AWS Key Management Service (AWS KMS).

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses Amazon Elastic Kubernetes Service (Amazon EKS) to run a container application. The EKS cluster stores sensitive information in the Kubernetes secrets object. The company wants to ensure that the information is encrypted.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Enable secrets encryption in the EKS cluster by using AWS Key Management Service (AWS KMS).

Amazon EKS provides built-in support for encrypting Kubernetes secrets using AWS Key Management Service (AWS KMS). You can enable this feature at the EKS cluster level.

</details>

---

## Question 614

[Review topic](../sections/elb-asg.md) · Source PDF page 224

A company is designing a new multi-tier web application that consists of the following components:
• Web and application servers that run on Amazon EC2 instances as part of Auto Scaling groups
• An Amazon RDS DB instance for data storage
A solutions architect needs to limit access to the application servers so that only the web servers can access them.
Which solution will meet these requirements?

**A.** Deploy AWS PrivateLink in front of the application servers. Configure the network ACL to allow only the web servers to access the
application servers.

**B.** Deploy a VPC endpoint in front of the application servers. Configure the security group to allow only the web servers to access the
application servers.

**C.** Deploy a Network Load Balancer with a target group that contains the application servers' Auto Scaling group. Configure the network ACL
to allow only the web servers to access the application servers.

**D.** Deploy an Application Load Balancer with a target group that contains the application servers' Auto Scaling group. Configure the security
group to allow only the web servers to access the application servers.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is designing a new multi-tier web application that consists of the following components:

• Web and application servers that run on Amazon EC2 instances as part of Auto Scaling groups
• An Amazon RDS DB instance for data storage

A solutions architect needs to limit access to the application servers so that only the web servers can access them.

Which solution will meet these requirements?


**D.** Deploy an Application Load Balancer with a target group that contains the application servers' Auto Scaling group. Configure the security group to allow only the web servers to access the application servers.

An ALB is a load balancer service provided by AWS that allows you to distribute incoming application traffic across multiple targets, such as EC2 instances. In this scenario, the ALB is deployed in front of the application servers.
The ALB is configured with a target group that includes the application servers' Auto Scaling group instances. The target group defines where the ALB directs traffic.

</details>

---

## Question 615

[Review topic](../sections/containers.md) · Source PDF page 224

A company runs a critical, customer-facing application on Amazon Elastic Kubernetes Service (Amazon EKS). The application has a microservices
architecture. The company needs to implement a solution that collects, aggregates, and summarizes metrics and logs from the application in a
centralized location.
Which solution meets these requirements?

**A.** Run the Amazon CloudWatch agent in the existing EKS cluster. View the metrics and logs in the CloudWatch console.

**B.** Run AWS App Mesh in the existing EKS cluster. View the metrics and logs in the App Mesh console.

**C.** Configure AWS CloudTrail to capture data events. Query CloudTrail by using Amazon OpenSearch Service.

**D.** Configure Amazon CloudWatch Container Insights in the existing EKS cluster. View the metrics and logs in the CloudWatch console.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a critical, customer-facing application on Amazon Elastic Kubernetes Service (Amazon EKS). The application has a microservices architecture. The company needs to implement a solution that collects, aggregates, and summarizes metrics and logs from the application in a centralized location.

Which solution meets these requirements?


**D.** Configure Amazon CloudWatch Container Insights in the existing EKS cluster. View the metrics and logs in the CloudWatch console.

CloudWatch Container Insights is specifically designed for monitoring containerized applications on Amazon EKS and ECS. It provides visibility into the performance of containers, clusters, and microservices.

</details>

---

## Question 616

[Review topic](../sections/elb-asg.md) · Source PDF page 224

A company has deployed its newest product on AWS. The product runs in an Auto Scaling group behind a Network Load Balancer. The company
stores the product’s objects in an Amazon S3 bucket.
The company recently experienced malicious attacks against its systems. The company needs a solution that continuously monitors for malicious
activity in the AWS account, workloads, and access patterns to the S3 bucket. The solution must also report suspicious activity and display the
information on a dashboard.
Which solution will meet these requirements?

**A.** Configure Amazon Macie to monitor and report findings to AWS Config.

**B.** Configure Amazon Inspector to monitor and report findings to AWS CloudTrail.

**C.** Configure Amazon GuardDuty to monitor and report findings to AWS Security Hub.

**D.** Configure AWS Config to monitor and report findings to Amazon EventBridge.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has deployed its newest product on AWS. The product runs in an Auto Scaling group behind a Network Load Balancer. The company stores the product’s objects in an Amazon S3 bucket.

The company recently experienced malicious attacks against its systems. The company needs a solution that continuously monitors for malicious activity in the AWS account, workloads, and access patterns to the S3 bucket. The solution must also report suspicious activity and display the information on a dashboard.

Which solution will meet these requirements?


**C.** Configure Amazon GuardDuty to monitor and report findings to AWS Security Hub.

Amazon GuardDuty:

GuardDuty is a threat detection service that continuously monitors for malicious activity and unauthorized behavior in your AWS account. It analyzes events, such as API calls and network traffic, to detect potentially malicious activity.
AWS Security Hub:
AWS Security Hub is a comprehensive security service that aggregates and prioritizes security findings from various AWS services, including GuardDuty. It provides a centralized dashboard for security alerts and findings.

</details>

---

## Question 617

[Review topic](../sections/ec2-storage.md) · Source PDF page 225

A company wants to migrate an on-premises data center to AWS. The data center hosts a storage server that stores data in an NFS-based file
system. The storage server holds 200 GB of data. The company needs to migrate the data without interruption to existing services. Multiple
resources in AWS must be able to access the data by using the NFS protocol.
Which combination of steps will meet these requirements MOST cost-effectively? (Choose two.)

**A.** Create an Amazon FSx for Lustre file system.

**B.** Create an Amazon Elastic File System (Amazon EFS) file system.

**C.** Create an Amazon S3 bucket to receive the data.

**D.** Manually use an operating system copy command to push the data into the AWS destination.

**E.** Install an AWS DataSync agent in the on-premises data center. Use a DataSync task between the on-premises location and AWS.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to migrate an on-premises data center to AWS. The data center hosts a storage server that stores data in an NFS-based file system. The storage server holds 200 GB of data. The company needs to migrate the data without interruption to existing services. Multiple resources in AWS must be able to access the data by using the NFS protocol.

Which combination of steps will meet these requirements MOST cost-effectively? (Choose two.)


**B.** Create an Amazon Elastic File System (Amazon EFS) file system.


**E.** Install an AWS DataSync agent in the on-premises data center. Use a DataSync task between the on-premises location and AWS.

Amazon EFS is a scalable, fully managed file system that supports the NFSv4 protocol. It is designed to be highly available and can be mounted on multiple EC2 instances concurrently.
Creating an Amazon EFS file system allows you to easily migrate the data and have multiple AWS resources access it concurrently.
AWS DataSync is a service for efficiently transferring large amounts of data between on-premises storage and AWS. By installing a DataSync agent in the on-premises data center, you can use DataSync to perform the migration task.
DataSync ensures efficient and secure transfer of data, making it suitable for migrating large amounts of data to AWS.

</details>

---

## Question 618

[Review topic](../sections/ec2-storage.md) · Source PDF page 225

A company wants to use Amazon FSx for Windows File Server for its Amazon EC2 instances that have an SMB file share mounted as a volume in
the us-east-1 Region. The company has a recovery point objective (RPO) of 5 minutes for planned system maintenance or unplanned service
disruptions. The company needs to replicate the file system to the us-west-2 Region. The replicated data must not be deleted by any user for 5
years.
Which solution will meet these requirements?

**A.** Create an FSx for Windows File Server file system in us-east-1 that has a Single-AZ 2 deployment type. Use AWS Backup to create a daily
backup plan that includes a backup rule that copies the backup to us-west-2. Configure AWS Backup Vault Lock in compliance mode for a
target vault in us-west-2. Configure a minimum duration of 5 years.

**B.** Create an FSx for Windows File Server file system in us-east-1 that has a Multi-AZ deployment type. Use AWS Backup to create a daily
backup plan that includes a backup rule that copies the backup to us-west-2. Configure AWS Backup Vault Lock in governance mode for a
target vault in us-west-2. Configure a minimum duration of 5 years.

**C.** Create an FSx for Windows File Server file system in us-east-1 that has a Multi-AZ deployment type. Use AWS Backup to create a daily
backup plan that includes a backup rule that copies the backup to us-west-2. Configure AWS Backup Vault Lock in compliance mode for a
target vault in us-west-2. Configure a minimum duration of 5 years.

**D.** Create an FSx for Windows File Server file system in us-east-1 that has a Single-AZ 2 deployment type. Use AWS Backup to create a daily
backup plan that includes a backup rule that copies the backup to us-west-2. Configure AWS Backup Vault Lock in governance mode for a
target vault in us-west-2. Configure a minimum duration of 5 years.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to use Amazon FSx for Windows File Server for its Amazon EC2 instances that have an SMB file share mounted as a volume in the us-east-1 Region. The company has a recovery point objective (RPO) of 5 minutes for planned system maintenance or unplanned service disruptions. The company needs to replicate the file system to the us-west-2 Region. The replicated data must not be deleted by any user for 5 years.

Which solution will meet these requirements?


**C.** Create an FSx for Windows File Server file system in us-east-1 that has a Multi-AZ deployment type. Use AWS Backup to create a daily backup plan that includes a backup rule that copies the backup to us-west-2. Configure AWS Backup Vault Lock in compliance mode for a target vault in us-west-2. Configure a minimum duration of 5 years.

FSx for Windows File Server:
Create an FSx for Windows File Server file system in the us-east-1 Region with a Multi-AZ deployment type. The Multi-AZ deployment type ensures high availability.
AWS Backup:
Use AWS Backup to create a daily backup plan for the FSx file system. Include a backup rule that copies the backup to the us-west-2 Region. This ensures that a backup is replicated to the us-west-2 Region regularly.

</details>

---

## Question 619

[Review topic](../sections/operations.md) · Source PDF page 226

A solutions architect is designing a security solution for a company that wants to provide developers with individual AWS accounts through AWS
Organizations, while also maintaining standard security controls. Because the individual developers will have AWS account root user-level access
to their own accounts, the solutions architect wants to ensure that the mandatory AWS CloudTrail configuration that is applied to new developer
accounts is not modified.
Which action meets these requirements?

**A.** Create an IAM policy that prohibits changes to CloudTrail. and attach it to the root user.

**B.** Create a new trail in CloudTrail from within the developer accounts with the organization trails option enabled.

**C.** Create a service control policy (SCP) that prohibits changes to CloudTrail, and attach it the developer accounts.

**D.** Create a service-linked role for CloudTrail with a policy condition that allows changes only from an Amazon Resource Name (ARN) in the
management account.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing a security solution for a company that wants to provide developers with individual AWS accounts through AWS Organizations, while also maintaining standard security controls. Because the individual developers will have AWS account root user-level access to their own accounts, the solutions architect wants to ensure that the mandatory AWS CloudTrail configuration that is applied to new developer accounts is not modified.

Which action meets these requirements?


**C.** Create a service control policy (SCP) that prohibits changes to CloudTrail, and attach it the developer accounts.

SCPs are used in AWS Organizations to set fine-grained permissions and restrictions on AWS accounts within the organization.
By creating an SCP that explicitly prohibits changes to CloudTrail settings, you can enforce this restriction across all developer accounts.

</details>

---

## Question 620

[Review topic](../sections/exam-revision.md) · Source PDF page 226

A company is planning to deploy a business-critical application in the AWS Cloud. The application requires durable storage with consistent, low-
latency performance.
Which type of storage should a solutions architect recommend to meet these requirements?

**A.** Instance store volume

**B.** Amazon ElastiCache for Memcached cluster

**C.** Provisioned IOPS SSD Amazon Elastic Block Store (Amazon EBS) volume

**D.** Throughput Optimized HDD Amazon Elastic Block Store (Amazon EBS) volume

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is planning to deploy a business-critical application in the AWS Cloud. The application requires durable storage with consistent, low-latency performance.

Which type of storage should a solutions architect recommend to meet these requirements?


**C.** Provisioned IOPS SSD Amazon Elastic Block Store (Amazon EBS) volume

Provisioned IOPS (Input/Output Operations Per Second) SSD volumes are designed to deliver predictable, consistent, and low-latency performance for critical applications.
These volumes allow you to specify the amount of IOPS you need, providing a consistent level of performance regardless of the volume size.

</details>

---

## Question 621

[Review topic](../sections/cloud-foundations.md) · Source PDF page 226

An online photo-sharing company stores its photos in an Amazon S3 bucket that exists in the us-west-1 Region. The company needs to store a
copy of all new photos in the us-east-1 Region.
Which solution will meet this requirement with the LEAST operational effort?

**A.** Create a second S3 bucket in us-east-1. Use S3 Cross-Region Replication to copy photos from the existing S3 bucket to the second S3
bucket.

**B.** Create a cross-origin resource sharing (CORS) configuration of the existing S3 bucket. Specify us-east-1 in the CORS rule's AllowedOrigin
element.

**C.** Create a second S3 bucket in us-east-1 across multiple Availability Zones. Create an S3 Lifecycle rule to save photos into the second S3
bucket.

**D.** Create a second S3 bucket in us-east-1. Configure S3 event notifications on object creation and update events to invoke an AWS Lambda
function to copy photos from the existing S3 bucket to the second S3 bucket.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An online photo-sharing company stores its photos in an Amazon S3 bucket that exists in the us-west-1 Region. The company needs to store a copy of all new photos in the us-east-1 Region.

Which solution will meet this requirement with the LEAST operational effort?


**A.** Create a second S3 bucket in us-east-1. Use S3 Cross-Region Replication to copy photos from the existing S3 bucket to the second S3 bucket.

S3 Cross-Region Replication (CRR) is designed specifically for replicating objects across different AWS regions. It is a fully managed feature that automatically replicates objects from the source bucket to the destination bucket in a different region. This requires minimal operational effort as it is a built-in S3 feature for cross-region replication, and you don't have to manually trigger actions or configure additional services.

</details>

---

## Question 622

[Review topic](../sections/exam-revision.md) · Source PDF page 227

A company is creating a new web application for its subscribers. The application will consist of a static single page and a persistent database
layer. The application will have millions of users for 4 hours in the morning, but the application will have only a few thousand users during the rest
of the day. The company's data architects have requested the ability to rapidly evolve their schema.
Which solutions will meet these requirements and provide the MOST scalability? (Choose two.)

**A.** Deploy Amazon DynamoDB as the database solution. Provision on-demand capacity.

**B.** Deploy Amazon Aurora as the database solution. Choose the serverless DB engine mode.

**C.** Deploy Amazon DynamoDB as the database solution. Ensure that DynamoDB auto scaling is enabled.

**D.** Deploy the static content into an Amazon S3 bucket. Provision an Amazon CloudFront distribution with the S3 bucket as the origin.

**E.** Deploy the web servers for static content across a fleet of Amazon EC2 instances in Auto Scaling groups. Configure the instances to
periodically refresh the content from an Amazon Elastic File System (Amazon EFS) volume.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is creating a new web application for its subscribers. The application will consist of a static single page and a persistent database layer. The application will have millions of users for 4 hours in the morning, but the application will have only a few thousand users during the rest of the day. The company's data architects have requested the ability to rapidly evolve their schema.

Which solutions will meet these requirements and provide the MOST scalability? (Choose two.)


**C.** Deploy Amazon DynamoDB as the database solution. Ensure that DynamoDB auto scaling is enabled.

DynamoDB auto scaling allows the database to automatically adjust its read and write capacity based on the application's traffic, making it well-suited for varying workloads.


**D.** Deploy the static content into an Amazon S3 bucket. Provision an Amazon CloudFront distribution with the S3 bucket as the origin.

Amazon S3 is a highly scalable and durable object storage service, and using CloudFront, a content delivery network (CDN), helps distribute static content globally, reducing latency and providing scalability.

</details>

---

## Question 623

[Review topic](../sections/serverless.md) · Source PDF page 227

A company uses Amazon API Gateway to manage its REST APIs that third-party service providers access. The company must protect the REST
APIs from SQL injection and cross-site scripting attacks.
What is the MOST operationally efficient solution that meets these requirements?

**A.** Configure AWS Shield.

**B.** Configure AWS WAF.

**C.** Set up API Gateway with an Amazon CloudFront distribution. Configure AWS Shield in CloudFront.

**D.** Set up API Gateway with an Amazon CloudFront distribution. Configure AWS WAF in CloudFront.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses Amazon API Gateway to manage its REST APIs that third-party service providers access. The company must protect the REST APIs from SQL injection and cross-site scripting attacks.

What is the MOST operationally efficient solution that meets these requirements?


**B.** Configure AWS WAF.

AWS WAF (Web Application Firewall) is specifically designed to protect web applications from common web exploits like SQL injection and cross-site scripting (XSS) attacks. By configuring AWS WAF with API Gateway, you can create rules to filter and allow or block requests based on defined conditions, providing protection against various types of attacks.

</details>

---

## Question 624

[Review topic](../sections/iam.md) · Source PDF page 227

A company wants to provide users with access to AWS resources. The company has 1,500 users and manages their access to on-premises
resources through Active Directory user groups on the corporate network. However, the company does not want users to have to maintain another
identity to access the resources. A solutions architect must manage user access to the AWS resources while preserving access to the on-
premises resources.
What should the solutions architect do to meet these requirements?

**A.** Create an IAM user for each user in the company. Attach the appropriate policies to each user.

**B.** Use Amazon Cognito with an Active Directory user pool. Create roles with the appropriate policies attached.

**C.** Define cross-account roles with the appropriate policies attached. Map the roles to the Active Directory groups.

**D.** Configure Security Assertion Markup Language (SAML) 2 0-based federation. Create roles with the appropriate policies attached Map the
roles to the Active Directory groups.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to provide users with access to AWS resources. The company has 1,500 users and manages their access to on-premises resources through Active Directory user groups on the corporate network. However, the company does not want users to have to maintain another identity to access the resources. A solutions architect must manage user access to the AWS resources while preserving access to the on-premises resources.

What should the solutions architect do to meet these requirements?


**D.** Configure Security Assertion Markup Language (SAML) 2 0-based federation. Create roles with the appropriate policies attached Map the roles to the Active Directory groups.

using SAML 2.0-based federation, which allows you to integrate AWS with your existing Active Directory infrastructure. This approach enables single sign-on (SSO) for users, meaning they can use their existing corporate credentials to access both on-premises and AWS resources without maintaining separate identities.

</details>

---

## Question 625

[Review topic](../sections/exam-revision.md) · Source PDF page 228

A company is hosting a website behind multiple Application Load Balancers. The company has different distribution rights for its content around
the world. A solutions architect needs to ensure that users are served the correct content without violating distribution rights.
Which configuration should the solutions architect choose to meet these requirements?

**A.** Configure Amazon CloudFront with AWS WAF.

**B.** Configure Application Load Balancers with AWS WAF

**C.** Configure Amazon Route 53 with a geolocation policy

**D.** Configure Amazon Route 53 with a geoproximity routing policy

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is hosting a website behind multiple Application Load Balancers. The company has different distribution rights for its content around the world. A solutions architect needs to ensure that users are served the correct content without violating distribution rights.

Which configuration should the solutions architect choose to meet these requirements?


**C.** Configure Amazon Route 53 with a geolocation policy

Geolocation routing in Amazon Route 53 allows you to route traffic based on the geographic location of the user.
You can create different records for your website content and associate them with specific geographic locations. This way, users from different regions will be directed to the appropriate servers or load balancers hosting the content that adheres to the distribution rights for that region.

</details>

---

## Question 626

[Review topic](../sections/s3.md) · Source PDF page 228

A company stores its data on premises. The amount of data is growing beyond the company's available capacity.
The company wants to migrate its data from the on-premises location to an Amazon S3 bucket. The company needs a solution that will
automatically validate the integrity of the data after the transfer.
Which solution will meet these requirements?

**A.** Order an AWS Snowball Edge device. Configure the Snowball Edge device to perform the online data transfer to an S3 bucket

**B.** Deploy an AWS DataSync agent on premises. Configure the DataSync agent to perform the online data transfer to an S3 bucket.

**C.** Create an Amazon S3 File Gateway on premises Configure the S3 File Gateway to perform the online data transfer to an S3 bucket

**D.** Configure an accelerator in Amazon S3 Transfer Acceleration on premises. Configure the accelerator to perform the online data transfer to
an S3 bucket.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company stores its data on premises. The amount of data is growing beyond the company's available capacity.

The company wants to migrate its data from the on-premises location to an Amazon S3 bucket. The company needs a solution that will automatically validate the integrity of the data after the transfer.

Which solution will meet these requirements?


**B.** Deploy an AWS DataSync agent on premises. Configure the DataSync agent to perform the online data transfer to an S3 bucket.

AWS DataSync is a service designed for fast and secure online data transfer between on-premises storage and Amazon S3, Amazon EFS, or Amazon FSx for Windows File Server.
DataSync automatically performs integrity validation by ensuring that the data transferred to S3 matches the source data. It uses checksums to validate the integrity of the files.

</details>

---

## Question 627

[Review topic](../sections/exam-revision.md) · Source PDF page 228

A company wants to migrate two DNS servers to AWS. The servers host a total of approximately 200 zones and receive 1 million requests each
day on average. The company wants to maximize availability while minimizing the operational overhead that is related to the management of the
two servers.
What should a solutions architect recommend to meet these requirements?

**A.** Create 200 new hosted zones in the Amazon Route 53 console Import zone files.

**B.** Launch a single large Amazon EC2 instance Import zone tiles. Configure Amazon CloudWatch alarms and notifications to alert the company
about any downtime.

**C.** Migrate the servers to AWS by using AWS Server Migration Service (AWS SMS). Configure Amazon CloudWatch alarms and notifications to
alert the company about any downtime.

**D.** Launch an Amazon EC2 instance in an Auto Scaling group across two Availability Zones. Import zone files. Set the desired capacity to 1 and
the maximum capacity to 3 for the Auto Scaling group. Configure scaling alarms to scale based on CPU utilization.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to migrate two DNS servers to AWS. The servers host a total of approximately 200 zones and receive 1 million requests each day on average. The company wants to maximize availability while minimizing the operational overhead that is related to the management of the two servers.

What should a solutions architect recommend to meet these requirements?


**A.** Create 200 new hosted zones in the Amazon Route 53 console Import zone files.

Amazon Route 53 is a highly available and scalable domain name system (DNS) web service provided by AWS.
By creating 200 new hosted zones in the Amazon Route 53 console and importing the existing zone files, you can take advantage of the fully managed and highly available nature of Route 53 without the need to manage servers.

</details>

---

## Question 628

[Review topic](../sections/cost-governance.md) · Source PDF page 229

A global company runs its applications in multiple AWS accounts in AWS Organizations. The company's applications use multipart uploads to
upload data to multiple Amazon S3 buckets across AWS Regions. The company wants to report on incomplete multipart uploads for cost
compliance purposes.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Configure AWS Config with a rule to report the incomplete multipart upload object count.

**B.** Create a service control policy (SCP) to report the incomplete multipart upload object count.

**C.** Configure S3 Storage Lens to report the incomplete multipart upload object count.

**D.** Create an S3 Multi-Region Access Point to report the incomplete multipart upload object count.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A global company runs its applications in multiple AWS accounts in AWS Organizations. The company's applications use multipart uploads to upload data to multiple Amazon S3 buckets across AWS Regions. The company wants to report on incomplete multipart uploads for cost compliance purposes.

Which solution will meet these requirements with the LEAST operational overhead?


**C.** Configure S3 Storage Lens to report the incomplete multipart upload object count.

S3 Storage Lens is a feature in Amazon S3 that provides a comprehensive view of your storage usage and activity across multiple accounts. It helps you understand, analyze, and optimize your storage usage.
You can use S3 Storage Lens to generate reports on various metrics, including the incomplete multipart upload object count.

</details>

---

## Question 629

[Review topic](../sections/rds-aurora.md) · Source PDF page 229

A company runs a production database on Amazon RDS for MySQL. The company wants to upgrade the database version for security compliance
reasons. Because the database contains critical data, the company wants a quick solution to upgrade and test functionality without losing any
data.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create an RDS manual snapshot. Upgrade to the new version of Amazon RDS for MySQL.

**B.** Use native backup and restore. Restore the data to the upgraded new version of Amazon RDS for MySQL.

**C.** Use AWS Database Migration Service (AWS DMS) to replicate the data to the upgraded new version of Amazon RDS for MySQL.

**D.** Use Amazon RDS Blue/Green Deployments to deploy and test production changes.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a production database on Amazon RDS for MySQL. The company wants to upgrade the database version for security compliance reasons. Because the database contains critical data, the company wants a quick solution to upgrade and test functionality without losing any data.

Which solution will meet these requirements with the LEAST operational overhead?


**D.** Use Amazon RDS Blue/Green Deployments to deploy and test production changes.

</details>

---

## Question 630

[Review topic](../sections/exam-revision.md) · Source PDF page 229

A solutions architect is creating a data processing job that runs once daily and can take up to 2 hours to complete. If the job is interrupted, it has
to restart from the beginning.
How should the solutions architect address this issue in the MOST cost-effective manner?

**A.** Create a script that runs locally on an Amazon EC2 Reserved Instance that is triggered by a cron job.

**B.** Create an AWS Lambda function triggered by an Amazon EventBridge scheduled event.

**C.** Use an Amazon Elastic Container Service (Amazon ECS) Fargate task triggered by an Amazon EventBridge scheduled event.

**D.** Use an Amazon Elastic Container Service (Amazon ECS) task running on Amazon EC2 triggered by an Amazon EventBridge scheduled
event.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is creating a data processing job that runs once daily and can take up to 2 hours to complete. If the job is interrupted, it has to restart from the beginning.

How should the solutions architect address this issue in the MOST cost-effective manner?


**C.** Use an Amazon Elastic Container Service (Amazon ECS) Fargate task triggered by an Amazon EventBridge scheduled event.

ECS Fargate is a serverless container service, and it abstracts away the underlying infrastructure. With Fargate, you don't need to manage or provision EC2 instances directly. You can run containers without worrying about the infrastructure, and AWS takes care of scaling and resource allocation.

</details>

---

## Question 631

[Review topic](../sections/exam-revision.md) · Source PDF page 230

A social media company wants to store its database of user profiles, relationships, and interactions in the AWS Cloud. The company needs an
application to monitor any changes in the database. The application needs to analyze the relationships between the data entities and to provide
recommendations to users.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use Amazon Neptune to store the information. Use Amazon Kinesis Data Streams to process changes in the database.

**B.** Use Amazon Neptune to store the information. Use Neptune Streams to process changes in the database.

**C.** Use Amazon Quantum Ledger Database (Amazon QLDB) to store the information. Use Amazon Kinesis Data Streams to process changes in
the database.

**D.** Use Amazon Quantum Ledger Database (Amazon QLDB) to store the information. Use Neptune Streams to process changes in the
database.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A social media company wants to store its database of user profiles, relationships, and interactions in the AWS Cloud. The company needs an application to monitor any changes in the database. The application needs to analyze the relationships between the data entities and to provide recommendations to users.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Use Amazon Neptune to store the information. Use Neptune Streams to process changes in the database.

Amazon Neptune is a fully managed graph database service that is designed for storing and querying highly connected data. It supports the property graph and RDF graph models, making it suitable for scenarios where relationships between data entities need to be analyzed.
Neptune Streams:

Neptune Streams is a feature of Amazon Neptune that allows you to capture changes (inserts, updates, deletes) made to the graph database in a streaming fashion. This streaming capability enables you to react to changes in near real-time and trigger additional processing based on those changes.

</details>

---

## Question 632

[Review topic](../sections/ec2.md) · Source PDF page 230

A company is creating a new application that will store a large amount of data. The data will be analyzed hourly and will be modified by several
Amazon EC2 Linux instances that are deployed across multiple Availability Zones. The needed amount of storage space will continue to grow for
the next 6 months.
Which storage solution should a solutions architect recommend to meet these requirements?

**A.** Store the data in Amazon S3 Glacier. Update the S3 Glacier vault policy to allow access to the application instances.

**B.** Store the data in an Amazon Elastic Block Store (Amazon EBS) volume. Mount the EBS volume on the application instances.

**C.** Store the data in an Amazon Elastic File System (Amazon EFS) file system. Mount the file system on the application instances.

**D.** Store the data in an Amazon Elastic Block Store (Amazon EBS) Provisioned IOPS volume shared between the application instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is creating a new application that will store a large amount of data. The data will be analyzed hourly and will be modified by several Amazon EC2 Linux instances that are deployed across multiple Availability Zones. The needed amount of storage space will continue to grow for the next 6 months.

Which storage solution should a solutions architect recommend to meet these requirements?


**C.** Store the data in an Amazon Elastic File System (Amazon EFS) file system. Mount the file system on the application instances.

Amazon EFS is a scalable and fully managed file storage service that can be mounted on multiple Amazon EC2 instances simultaneously. It provides a shared file system that can be accessed concurrently from different instances.Amazon EFS can automatically scale its file system capacity to accommodate growing data sets. It can handle a large amount of data and is designed to grow and shrink as needed.

</details>

---

## Question 633

[Review topic](../sections/rds-aurora.md) · Source PDF page 230

A company manages an application that stores data on an Amazon RDS for PostgreSQL Multi-AZ DB instance. Increases in traffic are causing
performance problems. The company determines that database queries are the primary reason for the slow performance.
What should a solutions architect do to improve the application's performance?

**A.** Serve read traffic from the Multi-AZ standby replica.

**B.** Configure the DB instance to use Transfer Acceleration.

**C.** Create a read replica from the source DB instance. Serve read traffic from the read replica.

**D.** Use Amazon Kinesis Data Firehose between the application and Amazon RDS to increase the concurrency of database requests.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company manages an application that stores data on an Amazon RDS for PostgreSQL Multi-AZ DB instance. Increases in traffic are causing performance problems. The company determines that database queries are the primary reason for the slow performance.

What should a solutions architect do to improve the application's performance?


**C.** Create a read replica from the source DB instance. Serve read traffic from the read replica.

Creating read replicas allows you to offload read traffic from the primary (master) DB instance to one or more read replicas. Read replicas can serve read-only queries, distributing the load and improving overall query performance.

</details>

---

## Question 634

[Review topic](../sections/s3.md) · Source PDF page 231

A company collects 10 GB of telemetry data daily from various machines. The company stores the data in an Amazon S3 bucket in a source data
account.
The company has hired several consulting agencies to use this data for analysis. Each agency needs read access to the data for its analysts. The
company must share the data from the source data account by choosing a solution that maximizes security and operational efficiency.
Which solution will meet these requirements?

**A.** Configure S3 global tables to replicate data for each agency.

**B.** Make the S3 bucket public for a limited time. Inform only the agencies.

**C.** Configure cross-account access for the S3 bucket to the accounts that the agencies own.

**D.** Set up an IAM user for each analyst in the source data account. Grant each user access to the S3 bucket.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company collects 10 GB of telemetry data daily from various machines. The company stores the data in an Amazon S3 bucket in a source data account.

The company has hired several consulting agencies to use this data for analysis. Each agency needs read access to the data for its analysts. The company must share the data from the source data account by choosing a solution that maximizes security and operational efficiency.

Which solution will meet these requirements?


**C.** Configure cross-account access for the S3 bucket to the accounts that the agencies own.

By configuring cross-account access, you can grant permissions to specific AWS accounts (owned by the consulting agencies) to access the S3 bucket. This allows you to share the data securely with the agencies without making the data public or creating additional IAM users in the source data account.

</details>

---

## Question 635

[Review topic](../sections/cloud-foundations.md) · Source PDF page 231

A company uses Amazon FSx for NetApp ONTAP in its primary AWS Region for CIFS and NFS file shares. Applications that run on Amazon EC2
instances access the file shares. The company needs a storage disaster recovery (DR) solution in a secondary Region. The data that is replicated
in the secondary Region needs to be accessed by using the same protocols as the primary Region.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create an AWS Lambda function to copy the data to an Amazon S3 bucket. Replicate the S3 bucket to the secondary Region.

**B.** Create a backup of the FSx for ONTAP volumes by using AWS Backup. Copy the volumes to the secondary Region. Create a new FSx for
ONTAP instance from the backup.

**C.** Create an FSx for ONTAP instance in the secondary Region. Use NetApp SnapMirror to replicate data from the primary Region to the
secondary Region.

**D.** Create an Amazon Elastic File System (Amazon EFS) volume. Migrate the current data to the volume. Replicate the volume to the secondary
Region.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses Amazon FSx for NetApp ONTAP in its primary AWS Region for CIFS and NFS file shares. Applications that run on Amazon EC2 instances access the file shares. The company needs a storage disaster recovery (DR) solution in a secondary Region. The data that is replicated in the secondary Region needs to be accessed by using the same protocols as the primary Region.

Which solution will meet these requirements with the LEAST operational overhead?


**C.** Create an FSx for ONTAP instance in the secondary Region. Use NetApp SnapMirror to replicate data from the primary Region to the secondary Region.

FSx for ONTAP supports NetApp SnapMirror, which is a robust data replication technology. You can use SnapMirror to replicate data from the primary FSx for ONTAP instance in the primary Region to an FSx for ONTAP instance in the secondary Region.

</details>

---

## Question 636

[Review topic](../sections/s3.md) · Source PDF page 231

A development team is creating an event-based application that uses AWS Lambda functions. Events will be generated when files are added to an
Amazon S3 bucket. The development team currently has Amazon Simple Notification Service (Amazon SNS) configured as the event target from
Amazon S3.
What should a solutions architect do to process the events from Amazon S3 in a scalable way?

**A.** Create an SNS subscription that processes the event in Amazon Elastic Container Service (Amazon ECS) before the event runs in Lambda.

**B.** Create an SNS subscription that processes the event in Amazon Elastic Kubernetes Service (Amazon EKS) before the event runs in Lambda

**C.** Create an SNS subscription that sends the event to Amazon Simple Queue Service (Amazon SQS). Configure the SOS queue to trigger a
Lambda function.

**D.** Create an SNS subscription that sends the event to AWS Server Migration Service (AWS SMS). Configure the Lambda function to poll from
the SMS event.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A development team is creating an event-based application that uses AWS Lambda functions. Events will be generated when files are added to an Amazon S3 bucket. The development team currently has Amazon Simple Notification Service (Amazon SNS) configured as the event target from Amazon S3.

What should a solutions architect do to process the events from Amazon S3 in a scalable way?


**C.** Create an SNS subscription that sends the event to Amazon Simple Queue Service (Amazon SQS). Configure the SOS queue to trigger a Lambda function.

</details>

---

## Question 637

[Review topic](../sections/serverless.md) · Source PDF page 232

A solutions architect is designing a new service behind Amazon API Gateway. The request patterns for the service will be unpredictable and can
change suddenly from 0 requests to over 500 per second. The total size of the data that needs to be persisted in a backend database is currently
less than 1 GB with unpredictable future growth. Data can be queried using simple key-value requests.
Which combination ofAWS services would meet these requirements? (Choose two.)

**A.** AWS Fargate

**B.** AWS Lambda

**C.** Amazon DynamoDB

**D.** Amazon EC2 Auto Scaling

**E.** MySQL-compatible Amazon Aurora

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing a new service behind Amazon API Gateway. The request patterns for the service will be unpredictable and can change suddenly from 0 requests to over 500 per second. The total size of the data that needs to be persisted in a backend database is currently less than 1 GB with unpredictable future growth. Data can be queried using simple key-value requests.

Which combination ofAWS services would meet these requirements? (Choose two.)


**B.** AWS Lambda

**C.** Amazon DynamoDB

AWS Lambda is a serverless compute service that automatically scales with the number of incoming requests. It's suitable for unpredictable workloads, as it allows you to run code without provisioning or managing servers. Lambda functions can be triggered by API Gateway for handling HTTP requests.
Amazon DynamoDB (Option C):

DynamoDB is a fully managed NoSQL database service that can handle unpredictable and scalable workloads. It provides low-latency, high-throughput performance for simple key-value queries. DynamoDB automatically scales to accommodate varying request rates, and you pay for the throughput you provision.

</details>

---

## Question 638

[Review topic](../sections/s3.md) · Source PDF page 232

A company collects and shares research data with the company's employees all over the world. The company wants to collect and store the data
in an Amazon S3 bucket and process the data in the AWS Cloud. The company will share the data with the company's employees. The company
needs a secure solution in the AWS Cloud that minimizes operational overhead.
Which solution will meet these requirements?

**A.** Use an AWS Lambda function to create an S3 presigned URL. Instruct employees to use the URL.

**B.** Create an IAM user for each employee. Create an IAM policy for each employee to allow S3 access. Instruct employees to use the AWS
Management Console.

**C.** Create an S3 File Gateway. Create a share for uploading and a share for downloading. Allow employees to mount shares on their local
computers to use S3 File Gateway.

**D.** Configure AWS Transfer Family SFTP endpoints. Select the custom identity provider options. Use AWS Secrets Manager to manage the user
credentials Instruct employees to use Transfer Family.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: A**

Short-lived presigned URLs grant scoped object access with little infrastructure. Authenticate the requester and authorize the object before issuing each URL.

**Original companion notes (not independently verified):**

A company collects and shares research data with the company's employees all over the world. The company wants to collect and store the data in an Amazon S3 bucket and process the data in the AWS Cloud. The company will share the data with the company's employees. The company needs a secure solution in the AWS Cloud that minimizes operational overhead.

Which solution will meet these requirements?

</details>

---

## Question 639

[Review topic](../sections/ec2.md) · Source PDF page 232

A company is building a new furniture inventory application. The company has deployed the application on a fleet ofAmazon EC2 instances across
multiple Availability Zones. The EC2 instances run behind an Application Load Balancer (ALB) in their VPC.
A solutions architect has observed that incoming traffic seems to favor one EC2 instance, resulting in latency for some requests.
What should the solutions architect do to resolve this issue?

**A.** Disable session affinity (sticky sessions) on the ALB

**B.** Replace the ALB with a Network Load Balancer

**C.** Increase the number of EC2 instances in each Availability Zone

**D.** Adjust the frequency of the health checks on the ALB's target group

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is building a new furniture inventory application. The company has deployed the application on a fleet ofAmazon EC2 instances across multiple Availability Zones. The EC2 instances run behind an Application Load Balancer (ALB) in their VPC.

A solutions architect has observed that incoming traffic seems to favor one EC2 instance, resulting in latency for some requests.

What should the solutions architect do to resolve this issue?


**A.** Disable session affinity (sticky sessions) on the ALB

Session affinity, also known as sticky sessions, directs a client's requests to the same EC2 instance, based on the client's session information. While sticky sessions can be useful in some scenarios, they can lead to uneven distribution of traffic, causing latency for some requests if one EC2 instance is overloaded.

</details>

---

## Question 640

[Review topic](../sections/iam.md) · Source PDF page 233

A company has an application workflow that uses an AWS Lambda function to download and decrypt files from Amazon S3. These files are
encrypted using AWS Key Management Service (AWS KMS) keys. A solutions architect needs to design a solution that will ensure the required
permissions are set correctly.
Which combination of actions accomplish this? (Choose two.)

**A.** Attach the kms:decrypt permission to the Lambda function’s resource policy

**B.** Grant the decrypt permission for the Lambda IAM role in the KMS key's policy

**C.** Grant the decrypt permission for the Lambda resource policy in the KMS key's policy.

**D.** Create a new IAM policy with the kms:decrypt permission and attach the policy to the Lambda function.

**E.** Create a new IAM role with the kms:decrypt permission and attach the execution role to the Lambda function.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an application workflow that uses an AWS Lambda function to download and decrypt files from Amazon S3. These files are encrypted using AWS Key Management Service (AWS KMS) keys. A solutions architect needs to design a solution that will ensure the required permissions are set correctly.

Which combination of actions accomplish this? (Choose two.)


**B.** Grant the decrypt permission for the Lambda IAM role in the KMS key's policy


**E.** Create a new IAM role with the kms:decrypt permission and attach the execution role to the Lambda function.

</details>

---

## Question 641

[Review topic](../sections/cost-governance.md) · Source PDF page 233

A company wants to monitor its AWS costs for financial review. The cloud operations team is designing an architecture in the AWS Organizations
management account to query AWS Cost and Usage Reports for all member accounts. The team must run this query once a month and provide a
detailed analysis of the bill.
Which solution is the MOST scalable and cost-effective way to meet these requirements?

**A.** Enable Cost and Usage Reports in the management account. Deliver reports to Amazon Kinesis. Use Amazon EMR for analysis.

**B.** Enable Cost and Usage Reports in the management account. Deliver the reports to Amazon S3 Use Amazon Athena for analysis.

**C.** Enable Cost and Usage Reports for member accounts. Deliver the reports to Amazon S3 Use Amazon Redshift for analysis.

**D.** Enable Cost and Usage Reports for member accounts. Deliver the reports to Amazon Kinesis. Use Amazon QuickSight tor analysis.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to monitor its AWS costs for financial review. The cloud operations team is designing an architecture in the AWS Organizations management account to query AWS Cost and Usage Reports for all member accounts. The team must run this query once a month and provide a detailed analysis of the bill.

Which solution is the MOST scalable and cost-effective way to meet these requirements?


**B.** Enable Cost and Usage Reports in the management account. Deliver the reports to Amazon S3 Use Amazon Athena for analysis.

Amazon Athena is a serverless query service that allows you to analyze data directly in Amazon S3 using SQL queries.

</details>

---

## Question 642

[Review topic](../sections/elb-asg.md) · Source PDF page 233

A company wants to run a gaming application on Amazon EC2 instances that are part of an Auto Scaling group in the AWS Cloud. The application
will transmit data by using UDP packets. The company wants to ensure that the application can scale out and in as traffic increases and
decreases.
What should a solutions architect do to meet these requirements?

**A.** Attach a Network Load Balancer to the Auto Scaling group.

**B.** Attach an Application Load Balancer to the Auto Scaling group.

**C.** Deploy an Amazon Route 53 record set with a weighted policy to route traffic appropriately.

**D.** Deploy a NAT instance that is configured with port forwarding to the EC2 instances in the Auto Scaling group.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to run a gaming application on Amazon EC2 instances that are part of an Auto Scaling group in the AWS Cloud. The application will transmit data by using UDP packets. The company wants to ensure that the application can scale out and in as traffic increases and decreases.

What should a solutions architect do to meet these requirements?


**A.** Attach a Network Load Balancer to the Auto Scaling group.

 UDP is a connectionless protocol, and Network Load Balancers (NLB) support UDP, making them suitable for applications that use UDP for transmitting data.

</details>

---

## Question 643

[Review topic](../sections/cost-governance.md) · Source PDF page 234

A company runs several websites on AWS for its different brands. Each website generates tens of gigabytes of web traffic logs each day. A
solutions architect needs to design a scalable solution to give the company's developers the ability to analyze traffic patterns across all the
company's websites. This analysis by the developers will occur on demand once a week over the course of several months. The solution must
support queries with standard SQL.
Which solution will meet these requirements MOST cost-effectively?

**A.** Store the logs in Amazon S3. Use Amazon Athena tor analysis.

**B.** Store the logs in Amazon RDS. Use a database client for analysis.

**C.** Store the logs in Amazon OpenSearch Service. Use OpenSearch Service for analysis.

**D.** Store the logs in an Amazon EMR cluster Use a supported open-source framework for SQL-based analysis.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs several websites on AWS for its different brands. Each website generates tens of gigabytes of web traffic logs each day. A solutions architect needs to design a scalable solution to give the company's developers the ability to analyze traffic patterns across all the company's websites. This analysis by the developers will occur on demand once a week over the course of several months. The solution must support queries with standard SQL.

Which solution will meet these requirements MOST cost-effectively?


**A.** Store the logs in Amazon S3. Use Amazon Athena tor analysis.

Amazon Athena is a serverless query service that allows you to analyze data directly in Amazon S3 using standard SQL queries. It is cost-effective because you pay only for the queries you run, and there is no need to provision or manage infrastructure.

</details>

---

## Question 644

[Review topic](../sections/elb-asg.md) · Source PDF page 234

An international company has a subdomain for each country that the company operates in. The subdomains are formatted as example.com,
country1.example.com, and country2.example.com. The company's workloads are behind an Application Load Balancer. The company wants to
encrypt the website data that is in transit.
Which combination of steps will meet these requirements? (Choose two.)

**A.** Use the AWS Certificate Manager (ACM) console to request a public certificate for the apex top domain example com and a wildcard
certificate for *.example.com.

**B.** Use the AWS Certificate Manager (ACM) console to request a private certificate for the apex top domain example.com and a wildcard
certificate for *.example.com.

**C.** Use the AWS Certificate Manager (ACM) console to request a public and private certificate for the apex top domain example.com.

**D.** Validate domain ownership by email address. Switch to DNS validation by adding the required DNS records to the DNS provider.

**E.** Validate domain ownership for the domain by adding the required DNS records to the DNS provider.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An international company has a subdomain for each country that the company operates in. The subdomains are formatted as example.com, country1.example.com, and country2.example.com. The company's workloads are behind an Application Load Balancer. The company wants to encrypt the website data that is in transit.

Which combination of steps will meet these requirements? (Choose two.)


**A.** Use the AWS Certificate Manager (ACM) console to request a public certificate for the apex top domain example com and a wildcard certificate for *.example.com.


**E.** Validate domain ownership for the domain by adding the required DNS records to the DNS provider.

AWS Certificate Manager (ACM) is a service provided by Amazon Web Services (AWS) that simplifies the process of managing and provisioning SSL/TLS (Secure Sockets Layer/Transport Layer Security) certificates for your applications and websites. SSL/TLS certificates are essential for encrypting data in transit and securing communication between clients and servers.

 ACM requires domain ownership validation before issuing certificates. For wildcard certificates, DNS validation is necessary.

</details>

---

## Question 645

[Review topic](../sections/exam-revision.md) · Source PDF page 234

A company is required to use cryptographic keys in its on-premises key manager. The key manager is outside of the AWS Cloud because of
regulatory and compliance requirements. The company wants to manage encryption and decryption by using cryptographic keys that are retained
outside of the AWS Cloud and that support a variety of external key managers from different vendors.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use AWS CloudHSM key store backed by a CloudHSM cluster.

**B.** Use an AWS Key Management Service (AWS KMS) external key store backed by an external key manager.

**C.** Use the default AWS Key Management Service (AWS KMS) managed key store.

**D.** Use a custom key store backed by an AWS CloudHSM cluster.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is required to use cryptographic keys in its on-premises key manager. The key manager is outside of the AWS Cloud because of regulatory and compliance requirements. The company wants to manage encryption and decryption by using cryptographic keys that are retained outside of the AWS Cloud and that support a variety of external key managers from different vendors.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Use an AWS Key Management Service (AWS KMS) external key store backed by an external key manager.

</details>

---

## Question 646

[Review topic](../sections/ec2-storage.md) · Source PDF page 235

A solutions architect needs to host a high performance computing (HPC) workload in the AWS Cloud. The workload will run on hundreds of
Amazon EC2 instances and will require parallel access to a shared file system to enable distributed processing of large datasets. Datasets will be
accessed across multiple instances simultaneously. The workload requires access latency within 1 ms. After processing has completed,
engineers will need access to the dataset for manual postprocessing.
Which solution will meet these requirements?

**A.** Use Amazon Elastic File System (Amazon EFS) as a shared file system. Access the dataset from Amazon EFS.

**B.** Mount an Amazon S3 bucket to serve as the shared file system. Perform postprocessing directly from the S3 bucket.

**C.** Use Amazon FSx for Lustre as a shared file system. Link the file system to an Amazon S3 bucket for postprocessing.

**D.** Configure AWS Resource Access Manager to share an Amazon S3 bucket so that it can be mounted to all instances for processing and
postprocessing.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

solutions architect needs to host a high performance computing (HPC) workload in the AWS Cloud. The workload will run on hundreds of Amazon EC2 instances and will require parallel access to a shared file system to enable distributed processing of large datasets. Datasets will be accessed across multiple instances simultaneously. The workload requires access latency within 1 ms. After processing has completed, engineers will need access to the dataset for manual postprocessing.

Which solution will meet these requirements?


**C.** Use Amazon FSx for Lustre as a shared file system. Link the file system to an Amazon S3 bucket for postprocessing.

FSx for Lustre is designed for high-performance computing workloads that require fast and scalable shared storage. It provides low-latency access to data and is well-suited for parallel processing across multiple instances.

</details>

---

## Question 647

[Review topic](../sections/disaster-recovery.md) · Source PDF page 235

A gaming company is building an application with Voice over IP capabilities. The application will serve traffic to users across the world. The
application needs to be highly available with an automated failover across AWS Regions. The company wants to minimize the latency of users
without relying on IP address caching on user devices.
What should a solutions architect do to meet these requirements?

**A.** Use AWS Global Accelerator with health checks.

**B.** Use Amazon Route 53 with a geolocation routing policy.

**C.** Create an Amazon CloudFront distribution that includes multiple origins.

**D.** Create an Application Load Balancer that uses path-based routing.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A gaming company is building an application with Voice over IP capabilities. The application will serve traffic to users across the world. The application needs to be highly available with an automated failover across AWS Regions. The company wants to minimize the latency of users without relying on IP address caching on user devices.

What should a solutions architect do to meet these requirements?


**A.** Use AWS Global Accelerator with health checks.

AWS Global Accelerator is a service that provides static IP addresses (Anycast) to route traffic over the AWS global network. It routes traffic over the optimal path to the AWS endpoint, improving availability and performance.

</details>

---

## Question 648

[Review topic](../sections/exam-revision.md) · Source PDF page 235

A weather forecasting company needs to process hundreds of gigabytes of data with sub-millisecond latency. The company has a high
performance computing (HPC) environment in its data center and wants to expand its forecasting capabilities.
A solutions architect must identify a highly available cloud storage solution that can handle large amounts of sustained throughput. Files that are
stored in the solution should be accessible to thousands of compute instances that will simultaneously access and process the entire dataset.
What should the solutions architect do to meet these requirements?

**A.** Use Amazon FSx for Lustre scratch file systems.

**B.** Use Amazon FSx for Lustre persistent file systems.

**C.** Use Amazon Elastic File System (Amazon EFS) with Bursting Throughput mode.

**D.** Use Amazon Elastic File System (Amazon EFS) with Provisioned Throughput mode.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A weather forecasting company needs to process hundreds of gigabytes of data with sub-millisecond latency. The company has a high performance computing (HPC) environment in its data center and wants to expand its forecasting capabilities.

A solutions architect must identify a highly available cloud storage solution that can handle large amounts of sustained throughput. Files that are stored in the solution should be accessible to thousands of compute instances that will simultaneously access and process the entire dataset.

What should the solutions architect do to meet these requirements?


**B.** Use Amazon FSx for Lustre persistent file systems.

 Persistent file systems in FSx for Lustre are designed for longer-term storage needs. They provide a durable and highly available solution for your data. This is important for the weather forecasting company's requirement to handle large amounts of sustained throughput.

</details>

---

## Question 649

[Review topic](../sections/rds-aurora.md) · Source PDF page 236

An ecommerce company runs a PostgreSQL database on premises. The database stores data by using high IOPS Amazon Elastic Block Store
(Amazon EBS) block storage. The daily peak I/O transactions per second do not exceed 15,000 IOPS. The company wants to migrate the database
to Amazon RDS for PostgreSQL and provision disk IOPS performance independent of disk storage capacity.
Which solution will meet these requirements MOST cost-effectively?

**A.** Configure the General Purpose SSD (gp2) EBS volume storage type and provision 15,000 IOPS.

**B.** Configure the Provisioned IOPS SSD (io1) EBS volume storage type and provision 15,000 IOPS.

**C.** Configure the General Purpose SSD (gp3) EBS volume storage type and provision 15,000 IOPS.

**D.** Configure the EBS magnetic volume type to achieve maximum IOPS.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An ecommerce company runs a PostgreSQL database on premises. The database stores data by using high IOPS Amazon Elastic Block Store (Amazon EBS) block storage. The daily peak I/O transactions per second do not exceed 15,000 IOPS. The company wants to migrate the database to Amazon RDS for PostgreSQL and provision disk IOPS performance independent of disk storage capacity.

Which solution will meet these requirements MOST cost-effectively?


**C.** Configure the General Purpose SSD (gp3) EBS volume storage type and provision 15,000 IOPS.

Amazon EBS gp3 volumes are designed for general-purpose workloads and offer a balance of price and performance. They allow you to provision IOPS independently of storage capacity, similar to io1 volumes.

</details>

---

## Question 650

[Review topic](../sections/exam-revision.md) · Source PDF page 236

A company wants to migrate its on-premises Microsoft SQL Server Enterprise edition database to AWS. The company's online application uses the
database to process transactions. The data analysis team uses the same production database to run reports for analytical processing. The
company wants to reduce operational overhead by moving to managed services wherever possible.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Migrate to Amazon RDS for Microsoft SOL Server. Use read replicas for reporting purposes

**B.** Migrate to Microsoft SQL Server on Amazon EC2. Use Always On read replicas for reporting purposes

**C.** Migrate to Amazon DynamoDB. Use DynamoDB on-demand replicas for reporting purposes

**D.** Migrate to Amazon Aurora MySQL. Use Aurora read replicas for reporting purposes

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to migrate its on-premises Microsoft SQL Server Enterprise edition database to AWS. The company's online application uses the database to process transactions. The data analysis team uses the same production database to run reports for analytical processing. The company wants to reduce operational overhead by moving to managed services wherever possible.

Which solution will meet these requirements with the LEAST operational overhead?


**A.** Migrate to Amazon RDS for Microsoft SOL Server. Use read replicas for reporting purposes

Amazon RDS supports read replicas, allowing you to offload reporting and analytical workloads to replicas without impacting the performance of the primary database. This is a cost-effective and efficient way to handle reporting without affecting transactional processing on the primary database.

</details>

---

