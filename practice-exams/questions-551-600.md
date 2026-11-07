# Practice questions 551-600

[Home](../README.md) · [All sets](README.md)

Answer notes are source-provided unless labeled suggested. These sets preserve the supplied PDF; they are not official AWS exams.

## Question 551

[Review topic](../sections/s3.md) · Source PDF page 203

A company has a financial application that produces reports. The reports average 50 KB in size and are stored in Amazon S3. The reports are
frequently accessed during the first week after production and must be stored for several years. The reports must be retrievable within 6 hours.
Which solution meets these requirements MOST cost-effectively?

**A.** Use S3 Standard. Use an S3 Lifecycle rule to transition the reports to S3 Glacier after 7 days.

**B.** Use S3 Standard. Use an S3 Lifecycle rule to transition the reports to S3 Standard-Infrequent Access (S3 Standard-IA) after 7 days.

**C.** Use S3 Intelligent-Tiering. Configure S3 Intelligent-Tiering to transition the reports to S3 Standard-Infrequent Access (S3 Standard-IA) and
S3 Glacier.

**D.** Use S3 Standard. Use an S3 Lifecycle rule to transition the reports to S3 Glacier Deep Archive after 7 days.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a financial application that produces reports. The reports average 50 KB in size and are stored in Amazon S3. The reports are frequently accessed during the first week after production and must be stored for several years. The reports must be retrievable within 6 hours.

Which solution meets these requirements MOST cost-effectively?


**A.** Use S3 Standard. Use an S3 Lifecycle rule to transition the reports to S3 Glacier after 7 days.

After the initial period, using an S3 Lifecycle rule to transition the reports to the S3 Glacier storage class is a cost-effective approach. Glacier is designed for long-term archival storage with lower storage costs compared to S3 Standard.

</details>

---

## Question 552

[Review topic](../sections/ec2.md) · Source PDF page 203

A company needs to optimize the cost of its Amazon EC2 instances. The company also needs to change the type and family of its EC2 instances
every 2-3 months.
What should the company do to meet these requirements?

**A.** Purchase Partial Upfront Reserved Instances for a 3-year term.

**B.** Purchase a No Upfront Compute Savings Plan for a 1-year term.

**C.** Purchase All Upfront Reserved Instances for a 1-year term.

**D.** Purchase an All Upfront EC2 Instance Savings Plan for a 1-year term.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs to optimize the cost of its Amazon EC2 instances. The company also needs to change the type and family of its EC2 instances every 2-3 months.

What should the company do to meet these requirements?


**B.** Purchase a No Upfront Compute Savings Plan for a 1-year term.

WHat is Upfront --- You don't pay anything upfront. You receive a smaller discount, but you free up capital for other projects.

A No Upfront option means no upfront payment is required, which provides flexibility.

1-year Term: A 1-year term aligns with the company's need to change the type and family of its EC2 instances every 2-3 months. While Compute Savings Plans have a commitment term, choosing a 1-year term allows for more frequent adjustments compared to a 3-year term.

</details>

---

## Question 553

[Review topic](../sections/cloud-foundations.md) · Source PDF page 203

A solutions architect needs to review a company's Amazon S3 buckets to discover personally identifiable information (PII). The company stores
the PII data in the us-east-1 Region and us-west-2 Region.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Configure Amazon Macie in each Region. Create a job to analyze the data that is in Amazon S3.

**B.** Configure AWS Security Hub for all Regions. Create an AWS Config rule to analyze the data that is in Amazon S3.

**C.** Configure Amazon Inspector to analyze the data that is in Amazon S3.

**D.** Configure Amazon GuardDuty to analyze the data that is in Amazon S3.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect needs to review a company's Amazon S3 buckets to discover personally identifiable information (PII). The company stores the PII data in the us-east-1 Region and us-west-2 Region.

Which solution will meet these requirements with the LEAST operational overhead?


**A.** Configure Amazon Macie in each Region. Create a job to analyze the data that is in Amazon S3.

Amazon Macie is a managed data security and data privacy service that uses machine learning to automatically discover, classify, and protect sensitive data, including personally identifiable information (PII). By configuring Amazon Macie in each region where the company stores PII data, you can create jobs to analyze the data in Amazon S3 and identify any PII.

</details>

---

## Question 554

[Review topic](../sections/exam-revision.md) · Source PDF page 204

A company's SAP application has a backend SQL Server database in an on-premises environment. The company wants to migrate its on-premises
application and database server to AWS. The company needs an instance type that meets the high demands of its SAP database. On-premises
performance data shows that both the SAP application and the database have high memory utilization.
Which solution will meet these requirements?

**A.** Use the compute optimized instance family for the application. Use the memory optimized instance family for the database.

**B.** Use the storage optimized instance family for both the application and the database.

**C.** Use the memory optimized instance family for both the application and the database.

**D.** Use the high performance computing (HPC) optimized instance family for the application. Use the memory optimized instance family for
the database.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company's SAP application has a backend SQL Server database in an on-premises environment. The company wants to migrate its on-premises application and database server to AWS. The company needs an instance type that meets the high demands of its SAP database. On-premises performance data shows that both the SAP application and the database have high memory utilization.

Which solution will meet these requirements?


**C.** Use the memory optimized instance family for both the application and the database.

Memory optimized instances are designed to provide a high memory-to-CPU ratio, which aligns well with workloads that have significant memory requirements, such as SAP applications with backend databases.

</details>

---

## Question 555

[Review topic](../sections/messaging.md) · Source PDF page 204

A company runs an application in a VPC with public and private subnets. The VPC extends across multiple Availability Zones. The application runs
on Amazon EC2 instances in private subnets. The application uses an Amazon Simple Queue Service (Amazon SQS) queue.
A solutions architect needs to design a secure solution to establish a connection between the EC2 instances and the SQS queue.
Which solution will meet these requirements?

**A.** Implement an interface VPC endpoint for Amazon SQS. Configure the endpoint to use the private subnets. Add to the endpoint a security
group that has an inbound access rule that allows traffic from the EC2 instances that are in the private subnets.

**B.** Implement an interface VPC endpoint for Amazon SQS. Configure the endpoint to use the public subnets. Attach to the interface endpoint a
VPC endpoint policy that allows access from the EC2 instances that are in the private subnets.

**C.** Implement an interface VPC endpoint for Amazon SQS. Configure the endpoint to use the public subnets. Attach an Amazon SQS access
policy to the interface VPC endpoint that allows requests from only a specified VPC endpoint.

**D.** Implement a gateway endpoint for Amazon SQS. Add a NAT gateway to the private subnets. Attach an IAM role to the EC2 instances that
allows access to the SQS queue.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs an application in a VPC with public and private subnets. The VPC extends across multiple Availability Zones. The application runs on Amazon EC2 instances in private subnets. The application uses an Amazon Simple Queue Service (Amazon SQS) queue.

A solutions architect needs to design a secure solution to establish a connection between the EC2 instances and the SQS queue.

Which solution will meet these requirements?


**A.** Implement an interface VPC endpoint for Amazon SQS. Configure the endpoint to use the private subnets. Add to the endpoint a security group that has an inbound access rule that allows traffic from the EC2 instances that are in the private subnets.

Interface VPC endpoints are used for services that are accessed over the Internet, and in this case, it's Amazon SQS. By implementing an interface VPC endpoint for SQS, you can ensure that the traffic stays within the Amazon network.

</details>

---

## Question 556

[Review topic](../sections/ec2.md) · Source PDF page 204

A solutions architect is using an AWS CloudFormation template to deploy a three-tier web application. The web application consists of a web tier
and an application tier that stores and retrieves user data in Amazon DynamoDB tables. The web and application tiers are hosted on Amazon EC2
instances, and the database tier is not publicly accessible. The application EC2 instances need to access the DynamoDB tables without exposing
API credentials in the template.
What should the solutions architect do to meet these requirements?

**A.** Create an IAM role to read the DynamoDB tables. Associate the role with the application instances by referencing an instance profile.

**B.** Create an IAM role that has the required permissions to read and write from the DynamoDB tables. Add the role to the EC2 instance profile,
and associate the instance profile with the application instances.

**C.** Use the parameter section in the AWS CloudFormation template to have the user input access and secret keys from an already-created IAM
user that has the required permissions to read and write from the DynamoDB tables.

**D.** Create an IAM user in the AWS CloudFormation template that has the required permissions to read and write from the DynamoDB tables.
Use the GetAtt function to retrieve the access and secret keys, and pass them to the application instances through the user data.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is using an AWS CloudFormation template to deploy a three-tier web application. The web application consists of a web tier and an application tier that stores and retrieves user data in Amazon DynamoDB tables. The web and application tiers are hosted on Amazon EC2 instances, and the database tier is not publicly accessible. The application EC2 instances need to access the DynamoDB tables without exposing API credentials in the template.

What should the solutions architect do to meet these requirements?


**B.** Create an IAM role that has the required permissions to read and write from the DynamoDB tables. Add the role to the EC2 instance profile, and associate the instance profile with the application instances.

Option B is the correct choice because it leverages IAM roles and instance profiles for EC2 instances. By creating an IAM role with the necessary permissions to access DynamoDB and associating it with the EC2 instance profile, you can securely grant permissions to the EC2 instances without exposing API credentials in the CloudFormation template.

</details>

---

## Question 557

[Review topic](../sections/s3.md) · Source PDF page 205

A solutions architect manages an analytics application. The application stores large amounts of semistructured data in an Amazon S3 bucket.
The solutions architect wants to use parallel data processing to process the data more quickly. The solutions architect also wants to use
information that is stored in an Amazon Redshift database to enrich the data.
Which solution will meet these requirements?

**A.** Use Amazon Athena to process the S3 data. Use AWS Glue with the Amazon Redshift data to enrich the S3 data.

**B.** Use Amazon EMR to process the S3 data. Use Amazon EMR with the Amazon Redshift data to enrich the S3 data.

**C.** Use Amazon EMR to process the S3 data. Use Amazon Kinesis Data Streams to move the S3 data into Amazon Redshift so that the data
can be enriched.

**D.** Use AWS Glue to process the S3 data. Use AWS Lake Formation with the Amazon Redshift data to enrich the S3 data.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect manages an analytics application. The application stores large amounts of semistructured data in an Amazon S3 bucket. The solutions architect wants to use parallel data processing to process the data more quickly. The solutions architect also wants to use information that is stored in an Amazon Redshift database to enrich the data.

Which solution will meet these requirements?


**B.** Use Amazon EMR to process the S3 data. Use Amazon EMR with the Amazon Redshift data to enrich the S3 data.


**B.** Amazon EMR is a cloud-based big data platform that uses Apache Hadoop and other open-source frameworks to process and analyze large datasets. EMR supports parallel data processing, making it a good fit for the requirement. Additionally, using EMR with the Amazon Redshift data allows for efficient enrichment of the S3 data.

</details>

---

## Question 558

[Review topic](../sections/exam-revision.md) · Source PDF page 205

A company has two VPCs that are located in the us-west-2 Region within the same AWS account. The company needs to allow network traffic
between these VPCs. Approximately 500 GB of data transfer will occur between the VPCs each month.
What is the MOST cost-effective solution to connect these VPCs?

**A.** Implement AWS Transit Gateway to connect the VPCs. Update the route tables of each VPC to use the transit gateway for inter-VPC
communication.

**B.** Implement an AWS Site-to-Site VPN tunnel between the VPCs. Update the route tables of each VPC to use the VPN tunnel for inter-VPC
communication.

**C.** Set up a VPC peering connection between the VPCs. Update the route tables of each VPC to use the VPC peering connection for inter-VPC
communication.

**D.** Set up a 1 GB AWS Direct Connect connection between the VPCs. Update the route tables of each VPC to use the Direct Connect
connection for inter-VPC communication.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has two VPCs that are located in the us-west-2 Region within the same AWS account. The company needs to allow network traffic between these VPCs. Approximately 500 GB of data transfer will occur between the VPCs each month.

What is the MOST cost-effective solution to connect these VPCs?


**C.** Set up a VPC peering connection between the VPCs. Update the route tables of each VPC to use the VPC peering connection for inter-VPC communication.

 VPC peering allows communication between VPCs within the same AWS account. It is a cost-effective solution, especially when the VPCs are located in the same region. In this case, both VPCs are in the us-west-2 region.

</details>

---

## Question 559

[Review topic](../sections/cost-governance.md) · Source PDF page 205

A company hosts multiple applications on AWS for different product lines. The applications use different compute resources, including Amazon
EC2 instances and Application Load Balancers. The applications run in different AWS accounts under the same organization in AWS Organizations
across multiple AWS Regions. Teams for each product line have tagged each compute resource in the individual accounts.
The company wants more details about the cost for each product line from the consolidated billing feature in Organizations.
Which combination of steps will meet these requirements? (Choose two.)

**A.** Select a specific AWS generated tag in the AWS Billing console.

**B.** Select a specific user-defined tag in the AWS Billing console.

**C.** Select a specific user-defined tag in the AWS Resource Groups console.

**D.** Activate the selected tag from each AWS account.

**E.** Activate the selected tag from the Organizations management account.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

559Topic 1
A company hosts multiple applications on AWS for different product lines. The applications use different compute resources, including Amazon EC2 instances and Application Load Balancers. The applications run in different AWS accounts under the same organization in AWS Organizations across multiple AWS Regions. Teams for each product line have tagged each compute resource in the individual accounts.

The company wants more details about the cost for each product line from the consolidated billing feature in Organizations.

Which combination of steps will meet these requirements? (Choose two.)


**B.** Select a specific user-defined tag in the AWS Billing console.


**E.** Activate the selected tag from the Organizations management account.

User-defined tags are tags that you create and attach to your AWS resources. In this case, since teams for each product line have tagged each compute resource with user-defined tags, selecting a specific user-defined tag in the AWS Billing console allows you to filter costs based on those tags.

The consolidated billing feature in AWS Organizations allows you to view and manage costs across multiple AWS accounts. By activating the selected tag from the Organizations management account, you ensure that the tagged resources from all linked accounts are included in the consolidated billing report. This enables you to get detailed cost information for each product line.

</details>

---

## Question 560

[Review topic](../sections/exam-revision.md) · Source PDF page 206

A company's solutions architect is designing an AWS multi-account solution that uses AWS Organizations. The solutions architect has organized
the company's accounts into organizational units (OUs).
The solutions architect needs a solution that will identify any changes to the OU hierarchy. The solution also needs to notify the company's
operations team of any changes.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Provision the AWS accounts by using AWS Control Tower. Use account drift notifications to identify the changes to the OU hierarchy.

**B.** Provision the AWS accounts by using AWS Control Tower. Use AWS Config aggregated rules to identify the changes to the OU hierarchy.

**C.** Use AWS Service Catalog to create accounts in Organizations. Use an AWS CloudTrail organization trail to identify the changes to the OU
hierarchy.

**D.** Use AWS CloudFormation templates to create accounts in Organizations. Use the drift detection operation on a stack to identify the
changes to the OU hierarchy.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company's solutions architect is designing an AWS multi-account solution that uses AWS Organizations. The solutions architect has organized the company's accounts into organizational units (OUs).

The solutions architect needs a solution that will identify any changes to the OU hierarchy. The solution also needs to notify the company's operations team of any changes.

Which solution will meet these requirements with the LEAST operational overhead?


**A.** Provision the AWS accounts by using AWS Control Tower. Use account drift notifications to identify the changes to the OU hierarchy.

AWS Control Tower is a service that simplifies the process of setting up and governing a secure, multi-account AWS environment based on AWS best practices. It provides a pre-defined landing zone with an organizational structure, OUs, and guardrails to enforce security and compliance.
 the organizational units (OUs) are established as part of the AWS Control Tower landing zone. If there are any changes to the OU hierarchy (such as moving accounts between OUs), these changes are considered drift, and AWS Control Tower can generate account drift notifications.

</details>

---

## Question 561

[Review topic](../sections/exam-revision.md) · Source PDF page 206

A company's website handles millions of requests each day, and the number of requests continues to increase. A solutions architect needs to
improve the response time of the web application. The solutions architect determines that the application needs to decrease latency when
retrieving product details from the Amazon DynamoDB table.
Which solution will meet these requirements with the LEAST amount of operational overhead?

**A.** Set up a DynamoDB Accelerator (DAX) cluster. Route all read requests through DAX.

**B.** Set up Amazon ElastiCache for Redis between the DynamoDB table and the web application. Route all read requests through Redis.

**C.** Set up Amazon ElastiCache for Memcached between the DynamoDB table and the web application. Route all read requests through
Memcached.

**D.** Set up Amazon DynamoDB Streams on the table, and have AWS Lambda read from the table and populate Amazon ElastiCache. Route all
read requests through ElastiCache.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company's website handles millions of requests each day, and the number of requests continues to increase. A solutions architect needs to improve the response time of the web application. The solutions architect determines that the application needs to decrease latency when retrieving product details from the Amazon DynamoDB table.

Which solution will meet these requirements with the LEAST amount of operational overhead?


**A.** Set up a DynamoDB Accelerator (DAX) cluster. Route all read requests through DAX.

DynamoDB Accelerator (DAX) is a fully managed, highly available, and in-memory cache for DynamoDB. It is designed to improve the response time of read-intensive DynamoDB workloads by caching frequently accessed data. Using DAX helps reduce the read latency as it retrieves data from an in-memory cache instead of the DynamoDB table.

</details>

---

## Question 562

[Review topic](../sections/ec2.md) · Source PDF page 206

A solutions architect needs to ensure that API calls to Amazon DynamoDB from Amazon EC2 instances in a VPC do not travel across the internet.
Which combination of steps should the solutions architect take to meet this requirement? (Choose two.)

**A.** Create a route table entry for the endpoint.

**B.** Create a gateway endpoint for DynamoDB.

**C.** Create an interface endpoint for Amazon EC2.

**D.** Create an elastic network interface for the endpoint in each of the subnets of the VPC.

**E.** Create a security group entry in the endpoint's security group to provide access.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect needs to ensure that API calls to Amazon DynamoDB from Amazon EC2 instances in a VPC do not travel across the internet.

Which combination of steps should the solutions architect take to meet this requirement? (Choose two.)


**A.** Create a route table entry for the endpoint.

**B.** Create a gateway endpoint for DynamoDB.

</details>

---

## Question 563

[Review topic](../sections/containers.md) · Source PDF page 207

A company runs its applications on both Amazon Elastic Kubernetes Service (Amazon EKS) clusters and on-premises Kubernetes clusters. The
company wants to view all clusters and workloads from a central location.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use Amazon CloudWatch Container Insights to collect and group the cluster information.

**B.** Use Amazon EKS Connector to register and connect all Kubernetes clusters.

**C.** Use AWS Systems Manager to collect and view the cluster information.

**D.** Use Amazon EKS Anywhere as the primary cluster to view the other clusters with native Kubernetes commands.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

clusters and workloads from a central location.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Use Amazon EKS Connector to register and connect all Kubernetes clusters.

Amazon EKS Connector is designed to help centralize the management of multiple Amazon Elastic Kubernetes Service (EKS) clusters. It allows you to register and connect multiple EKS clusters, providing a unified view of the clusters from the AWS Management Console. This solution aligns well with the requirement of managing clusters and workloads from a central location with the least operational overhead.

</details>

---

## Question 564

[Review topic](../sections/exam-revision.md) · Source PDF page 207

A company is building an ecommerce application and needs to store sensitive customer information. The company needs to give customers the
ability to complete purchase transactions on the website. The company also needs to ensure that sensitive customer data is protected, even from
database administrators.
Which solution meets these requirements?

**A.** Store sensitive data in an Amazon Elastic Block Store (Amazon EBS) volume. Use EBS encryption to encrypt the data. Use an IAM instance
role to restrict access.

**B.** Store sensitive data in Amazon RDS for MySQL. Use AWS Key Management Service (AWS KMS) client-side encryption to encrypt the data.

**C.** Store sensitive data in Amazon S3. Use AWS Key Management Service (AWS KMS) server-side encryption to encrypt the data. Use S3
bucket policies to restrict access.

**D.** Store sensitive data in Amazon FSx for Windows Server. Mount the file share on application servers. Use Windows file permissions to
restrict access.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is building an ecommerce application and needs to store sensitive customer information. The company needs to give customers the ability to complete purchase transactions on the website. The company also needs to ensure that sensitive customer data is protected, even from database administrators.

Which solution meets these requirements?


**B.** Store sensitive data in Amazon RDS for MySQL. Use AWS Key Management Service (AWS KMS) client-side encryption to encrypt the data.

Amazon RDS (Relational Database Service) for MySQL is a managed relational database service that makes it easy to set up, operate, and scale a MySQL database in the cloud.
AWS Key Management Service (KMS) provides a way to create and control encryption keys. In the context of client-side encryption, the application (in this case, the ecommerce application) handles the encryption and decryption of data before it is stored in or retrieved from the database.

</details>

---

## Question 565

[Review topic](../sections/rds-aurora.md) · Source PDF page 207

A company has an on-premises MySQL database that handles transactional data. The company is migrating the database to the AWS Cloud. The
migrated database must maintain compatibility with the company's applications that use the database. The migrated database also must scale
automatically during periods of increased demand.
Which migration solution will meet these requirements?

**A.** Use native MySQL tools to migrate the database to Amazon RDS for MySQL. Configure elastic storage scaling.

**B.** Migrate the database to Amazon Redshift by using the mysqldump utility. Turn on Auto Scaling for the Amazon Redshift cluster.

**C.** Use AWS Database Migration Service (AWS DMS) to migrate the database to Amazon Aurora. Turn on Aurora Auto Scaling.

**D.** Use AWS Database Migration Service (AWS DMS) to migrate the database to Amazon DynamoDB. Configure an Auto Scaling policy.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an on-premises MySQL database that handles transactional data. The company is migrating the database to the AWS Cloud. The migrated database must maintain compatibility with the company's applications that use the database. The migrated database also must scale automatically during periods of increased demand.

Which migration solution will meet these requirements?


**C.** Use AWS Database Migration Service (AWS DMS) to migrate the database to Amazon Aurora. Turn on Aurora Auto Scaling.

AWS DMS is a fully managed service that helps you migrate databases to AWS easily and securely. It supports homogeneous and heterogeneous database migrations.
Amazon Aurora is a fully managed relational database service that is compatible with MySQL and PostgreSQL. It provides high performance and availability with compatibility for MySQL, making it a seamless choice for migrating MySQL databases.

</details>

---

## Question 566

[Review topic](../sections/ec2.md) · Source PDF page 208

A company runs multiple Amazon EC2 Linux instances in a VPC across two Availability Zones. The instances host applications that use a
hierarchical directory structure. The applications need to read and write rapidly and concurrently to shared storage.
What should a solutions architect do to meet these requirements?

**A.** Create an Amazon S3 bucket. Allow access from all the EC2 instances in the VPC.

**B.** Create an Amazon Elastic File System (Amazon EFS) file system. Mount the EFS file system from each EC2 instance.

**C.** Create a file system on a Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volume. Attach the EBS volume to all the
EC2 instances.

**D.** Create file systems on Amazon Elastic Block Store (Amazon EBS) volumes that are attached to each EC2 instance. Synchronize the EBS
volumes across the different EC2 instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs multiple Amazon EC2 Linux instances in a VPC across two Availability Zones. The instances host applications that use a hierarchical directory structure. The applications need to read and write rapidly and concurrently to shared storage.

What should a solutions architect do to meet these requirements?


**B.** Create an Amazon Elastic File System (Amazon EFS) file system. Mount the EFS file system from each EC2 instance.

Amazon EFS is a fully managed, scalable file storage service designed to provide shared access to files across multiple Amazon EC2 instances. It is particularly well-suited for use cases that require concurrent access from multiple instances.

</details>

---

## Question 567

[Review topic](../sections/exam-revision.md) · Source PDF page 208

A solutions architect is designing a workload that will store hourly energy consumption by business tenants in a building. The sensors will feed a
database through HTTP requests that will add up usage for each tenant. The solutions architect must use managed services when possible. The
workload will receive more features in the future as the solutions architect adds independent components.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use Amazon API Gateway with AWS Lambda functions to receive the data from the sensors, process the data, and store the data in an
Amazon DynamoDB table.

**B.** Use an Elastic Load Balancer that is supported by an Auto Scaling group of Amazon EC2 instances to receive and process the data from the
sensors. Use an Amazon S3 bucket to store the processed data.

**C.** Use Amazon API Gateway with AWS Lambda functions to receive the data from the sensors, process the data, and store the data in a
Microsoft SQL Server Express database on an Amazon EC2 instance.

**D.** Use an Elastic Load Balancer that is supported by an Auto Scaling group of Amazon EC2 instances to receive and process the data from the
sensors. Use an Amazon Elastic File System (Amazon EFS) shared file system to store the processed data.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing a workload that will store hourly energy consumption by business tenants in a building. The sensors will feed a database through HTTP requests that will add up usage for each tenant. The solutions architect must use managed services when possible. The workload will receive more features in the future as the solutions architect adds independent components.

Which solution will meet these requirements with the LEAST operational overhead?


**A.** Use Amazon API Gateway with AWS Lambda functions to receive the data from the sensors, process the data, and store the data in an Amazon DynamoDB table.

Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. It acts as an entry point for HTTP requests and can handle the communication with the sensors.
In this scenario, you can use Lambda functions to process the data received from the sensors. 
Amazon DynamoDB is a fully managed NoSQL database that can handle the storage of the hourly energy consumption data.

</details>

---

## Question 568

[Review topic](../sections/exam-revision.md) · Source PDF page 208

A solutions architect is designing the storage architecture for a new web application used for storing and viewing engineering drawings. All
application components will be deployed on the AWS infrastructure.
The application design must support caching to minimize the amount of time that users wait for the engineering drawings to load. The application
must be able to store petabytes of data.
Which combination of storage and caching should the solutions architect use?

**A.** Amazon S3 with Amazon CloudFront

**B.** Amazon S3 Glacier with Amazon ElastiCache

**C.** Amazon Elastic Block Store (Amazon EBS) volumes with Amazon CloudFront

**D.** AWS Storage Gateway with Amazon ElastiCache

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing the storage architecture for a new web application used for storing and viewing engineering drawings. All application components will be deployed on the AWS infrastructure.

The application design must support caching to minimize the amount of time that users wait for the engineering drawings to load. The application must be able to store petabytes of data.

Which combination of storage and caching should the solutions architect use?


**A.** Amazon S3 with Amazon CloudFront

It is suitable for storing petabytes of data and is designed to provide low-latency access.
Amazon CloudFront is a content delivery network (CDN) service that securely delivers data, videos, applications, and APIs to customers globally with low latency and high transfer speeds. By integrating CloudFront with S3, you can distribute the engineering drawings to edge locations worldwide, reducing the latency for users and improving load times.

</details>

---

## Question 569

[Review topic](../sections/serverless.md) · Source PDF page 209

An Amazon EventBridge rule targets a third-party API. The third-party API has not received any incoming traffic. A solutions architect needs to
determine whether the rule conditions are being met and if the rule's target is being invoked.
Which solution will meet these requirements?

**A.** Check for metrics in Amazon CloudWatch in the namespace for AWS/Events.

**B.** Review events in the Amazon Simple Queue Service (Amazon SQS) dead-letter queue.

**C.** Check for the events in Amazon CloudWatch Logs.

**D.** Check the trails in AWS CloudTrail for the EventBridge events.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An Amazon EventBridge rule targets a third-party API. The third-party API has not received any incoming traffic. A solutions architect needs to determine whether the rule conditions are being met and if the rule's target is being invoked.

Which solution will meet these requirements?

s

</details>

---

## Question 570

[Review topic](../sections/exam-revision.md) · Source PDF page 209

A company has a large workload that runs every Friday evening. The workload runs on Amazon EC2 instances that are in two Availability Zones in
the us-east-1 Region. Normally, the company must run no more than two instances at all times. However, the company wants to scale up to six
instances each Friday to handle a regularly repeating increased workload.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create a reminder in Amazon EventBridge to scale the instances.

**B.** Create an Auto Scaling group that has a scheduled action.

**C.** Create an Auto Scaling group that uses manual scaling.

**D.** Create an Auto Scaling group that uses automatic scaling.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a large workload that runs every Friday evening. The workload runs on Amazon EC2 instances that are in two Availability Zones in the us-east-1 Region. Normally, the company must run no more than two instances at all times. However, the company wants to scale up to six instances each Friday to handle a regularly repeating increased workload.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Create an Auto Scaling group that has a scheduled action.

By creating an Auto Scaling group with a scheduled action, you can configure the group to automatically adjust the desired capacity based on a specified schedule. In this case, you can set up a scheduled action to increase the desired capacity to six instances every Friday evening.

</details>

---

## Question 571

[Review topic](../sections/security.md) · Source PDF page 209

A company is creating a REST API. The company has strict requirements for the use of TLS. The company requires TLSv1.3 on the API endpoints.
The company also requires a specific public third-party certificate authority (CA) to sign the TLS certificate.
Which solution will meet these requirements?

**A.** Use a local machine to create a certificate that is signed by the third-party CImport the certificate into AWS Certificate Manager (ACM).
Create an HTTP API in Amazon API Gateway with a custom domain. Configure the custom domain to use the certificate.

**B.** Create a certificate in AWS Certificate Manager (ACM) that is signed by the third-party CA. Create an HTTP API in Amazon API Gateway with
a custom domain. Configure the custom domain to use the certificate.

**C.** Use AWS Certificate Manager (ACM) to create a certificate that is signed by the third-party CA. Import the certificate into AWS Certificate
Manager (ACM). Create an AWS Lambda function with a Lambda function URL. Configure the Lambda function URL to use the certificate.

**D.** Create a certificate in AWS Certificate Manager (ACM) that is signed by the third-party CA. Create an AWS Lambda function with a Lambda
function URL. Configure the Lambda function URL to use the certificate.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is creating a REST API. The company has strict requirements for the use of TLS. The company requires TLSv1.3 on the API endpoints. The company also requires a specific public third-party certificate authority (CA) to sign the TLS certificate.

Which solution will meet these requirements?


**A.** Use a local machine to create a certificate that is signed by the third-party CImport the certificate into AWS Certificate Manager (ACM). Create an HTTP API in Amazon API Gateway with a custom domain. Configure the custom domain to use the certificate.

</details>

---

## Question 572

[Review topic](../sections/elb-asg.md) · Source PDF page 210

A company runs an application on AWS. The application receives inconsistent amounts of usage. The application uses AWS Direct Connect to
connect to an on-premises MySQL-compatible database. The on-premises database consistently uses a minimum of 2 GiB of memory.
The company wants to migrate the on-premises database to a managed AWS service. The company wants to use auto scaling capabilities to
manage unexpected workload increases.
Which solution will meet these requirements with the LEAST administrative overhead?

**A.** Provision an Amazon DynamoDB database with default read and write capacity settings.

**B.** Provision an Amazon Aurora database with a minimum capacity of 1 Aurora capacity unit (ACU).

**C.** Provision an Amazon Aurora Serverless v2 database with a minimum capacity of 1 Aurora capacity unit (ACU).

**D.** Provision an Amazon RDS for MySQL database with 2 GiB of memory.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs an application on AWS. The application receives inconsistent amounts of usage. The application uses AWS Direct Connect to connect to an on-premises MySQL-compatible database. The on-premises database consistently uses a minimum of 2 GiB of memory.

The company wants to migrate the on-premises database to a managed AWS service. The company wants to use auto scaling capabilities to manage unexpected workload increases.

Which solution will meet these requirements with the LEAST administrative overhead?


**C.** Provision an Amazon Aurora Serverless v2 database with a minimum capacity of 1 Aurora capacity unit (ACU).

Aurora Serverless is designed for applications with variable or unpredictable workloads. With Aurora Serverless v2, you can set the minimum capacity to 1 Aurora capacity unit (ACU), and it will automatically scale based on the actual workload.

</details>

---

## Question 573

[Review topic](../sections/serverless.md) · Source PDF page 210

A company wants to use an event-driven programming model with AWS Lambda. The company wants to reduce startup latency for Lambda
functions that run on Java 11. The company does not have strict latency requirements for the applications. The company wants to reduce cold
starts and outlier latencies when a function scales up.
Which solution will meet these requirements MOST cost-effectively?

**A.** Configure Lambda provisioned concurrency.

**B.** Increase the timeout of the Lambda functions.

**C.** Increase the memory of the Lambda functions.

**D.** Configure Lambda SnapStart.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to use an event-driven programming model with AWS Lambda. The company wants to reduce startup latency for Lambda functions that run on Java 11. The company does not have strict latency requirements for the applications. The company wants to reduce cold starts and outlier latencies when a function scales up.

Which solution will meet these requirements MOST cost-effectively?


**D.** Configure Lambda SnapStart.

Lambda Cold Start:
When a Lambda function is invoked, it may take a bit of time for the system to set up everything needed to run the function. This initial setup time is called a "cold start." Cold starts can add some delay, especially if the function hasn't been used recently.
Lambda SnapStart:
SnapStart is a feature in AWS Lambda designed to make these cold starts faster, specifically for functions written in Java. Instead of starting from scratch every time a function is called, SnapStart pre-warms the environment. It's like getting things ready in advance so that when your function is called, it can start quickly without much delay.

</details>

---

## Question 574

[Review topic](../sections/rds-aurora.md) · Source PDF page 210

A financial services company launched a new application that uses an Amazon RDS for MySQL database. The company uses the application to
track stock market trends. The company needs to operate the application for only 2 hours at the end of each week. The company needs to
optimize the cost of running the database.
Which solution will meet these requirements MOST cost-effectively?

**A.** Migrate the existing RDS for MySQL database to an Aurora Serverless v2 MySQL database cluster.

**B.** Migrate the existing RDS for MySQL database to an Aurora MySQL database cluster.

**C.** Migrate the existing RDS for MySQL database to an Amazon EC2 instance that runs MySQL. Purchase an instance reservation for the EC2
instance.

**D.** Migrate the existing RDS for MySQL database to an Amazon Elastic Container Service (Amazon ECS) cluster that uses MySQL container
images to run tasks.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A financial services company launched a new application that uses an Amazon RDS for MySQL database. The company uses the application to track stock market trends. The company needs to operate the application for only 2 hours at the end of each week. The company needs to optimize the cost of running the database.

Which solution will meet these requirements MOST cost-effectively?


**A.** Migrate the existing RDS for MySQL database to an Aurora Serverless v2 MySQL database cluster.

Aurora Serverless allows the database to automatically start up, shut down, and scale capacity based on actual usage. With Aurora Serverless v2, you can set a minimum and maximum capacity for the cluster. This is suitable for intermittent workloads, such as the application that is only operated for 2 hours at the end of each week.

</details>

---

## Question 575

[Review topic](../sections/elb-asg.md) · Source PDF page 211

A company deploys its applications on Amazon Elastic Kubernetes Service (Amazon EKS) behind an Application Load Balancer in an AWS Region.
The application needs to store data in a PostgreSQL database engine. The company wants the data in the database to be highly available. The
company also needs increased capacity for read workloads.
Which solution will meet these requirements with the MOST operational efficiency?

**A.** Create an Amazon DynamoDB database table configured with global tables.

**B.** Create an Amazon RDS database with Multi-AZ deployments.

**C.** Create an Amazon RDS database with Multi-AZ DB cluster deployment.

**D.** Create an Amazon RDS database configured with cross-Region read replicas.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company deploys its applications on Amazon Elastic Kubernetes Service (Amazon EKS) behind an Application Load Balancer in an AWS Region. The application needs to store data in a PostgreSQL database engine. The company wants the data in the database to be highly available. The company also needs increased capacity for read workloads.

Which solution will meet these requirements with the MOST operational efficiency?


**C.** Create an Amazon RDS database with Multi-AZ DB cluster deployment.

Amazon RDS with Multi-AZ (Availability Zone) DB cluster deployment provides high availability by automatically replicating the primary database to a standby instance in a different Availability Zone. This helps ensure database availability in the event of a failure in the primary Availability Zone.

</details>

---

## Question 576

[Review topic](../sections/serverless.md) · Source PDF page 211

A company is building a RESTful serverless web application on AWS by using Amazon API Gateway and AWS Lambda. The users of this web
application will be geographically distributed, and the company wants to reduce the latency of API requests to these users.
Which type of endpoint should a solutions architect use to meet these requirements?

**A.** Private endpoint

**B.** Regional endpoint

**C.** Interface VPC endpoint

**D.** Edge-optimized endpoint

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is building a RESTful serverless web application on AWS by using Amazon API Gateway and AWS Lambda. The users of this web application will be geographically distributed, and the company wants to reduce the latency of API requests to these users.

Which type of endpoint should a solutions architect use to meet these requirements?


**D.** Edge-optimized endpoint

Edge-optimized endpoints use the global CloudFront network to distribute API traffic across multiple edge locations. This reduces latency for users by serving API requests from the edge locations closest to the users. It leverages the AWS Global Accelerator and CloudFront to automatically route requests to the nearest AWS endpoint.

</details>

---

## Question 577

[Review topic](../sections/global-delivery.md) · Source PDF page 211

A company uses an Amazon CloudFront distribution to serve content pages for its website. The company needs to ensure that clients use a TLS
certificate when accessing the company's website. The company wants to automate the creation and renewal of the TLS certificates.
Which solution will meet these requirements with the MOST operational efficiency?

**A.** Use a CloudFront security policy to create a certificate.

**B.** Use a CloudFront origin access control (OAC) to create a certificate.

**C.** Use AWS Certificate Manager (ACM) to create a certificate. Use DNS validation for the domain.

**D.** Use AWS Certificate Manager (ACM) to create a certificate. Use email validation for the domain.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses an Amazon CloudFront distribution to serve content pages for its website. The company needs to ensure that clients use a TLS certificate when accessing the company's website. The company wants to automate the creation and renewal of the TLS certificates.

Which solution will meet these requirements with the MOST operational efficiency?


**C.** Use AWS Certificate Manager (ACM) to create a certificate. Use DNS validation for the domain.

AWS Certificate Manager (ACM): ACM is a fully managed service that allows you to easily provision, manage, and deploy public and private Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for use with AWS services and your internal connected resources. It is designed for automation and ease of use.

DNS Validation: DNS validation involves adding a DNS record to your domain's DNS configuration. This method is more suitable for automation as it does not require manual intervention, and it can be easily integrated into automated certificate issuance and renewal processes.

</details>

---

## Question 578

[Review topic](../sections/dynamodb-caching.md) · Source PDF page 212

A company deployed a serverless application that uses Amazon DynamoDB as a database layer. The application has experienced a large increase
in users. The company wants to improve database response time from milliseconds to microseconds and to cache requests to the database.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use DynamoDB Accelerator (DAX).

**B.** Migrate the database to Amazon Redshift.

**C.** Migrate the database to Amazon RDS.

**D.** Use Amazon ElastiCache for Redis.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company deployed a serverless application that uses Amazon DynamoDB as a database layer. The application has experienced a large increase in users. The company wants to improve database response time from milliseconds to microseconds and to cache requests to the database.

Which solution will meet these requirements with the LEAST operational overhead?


**A.** Use DynamoDB Accelerator (DAX).

DAX is a fully managed, highly available, in-memory cache for DynamoDB that delivers fast response times for DynamoDB queries. It can be seamlessly integrated with existing DynamoDB applications, requiring minimal code changes. DAX allows you to cache frequently accessed data, reducing the need to read from the DynamoDB table and improving response times.

</details>

---

## Question 579

[Review topic](../sections/rds-aurora.md) · Source PDF page 212

A company runs an application that uses Amazon RDS for PostgreSQL. The application receives traffic only on weekdays during business hours.
The company wants to optimize costs and reduce operational overhead based on this usage.
Which solution will meet these requirements?

**A.** Use the Instance Scheduler on AWS to configure start and stop schedules.

**B.** Turn off automatic backups. Create weekly manual snapshots of the database.

**C.** Create a custom AWS Lambda function to start and stop the database based on minimum CPU utilization.

**D.** Purchase All Upfront reserved DB instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs an application that uses Amazon RDS for PostgreSQL. The application receives traffic only on weekdays during business hours. The company wants to optimize costs and reduce operational overhead based on this usage.

Which solution will meet these requirements?


**A.** Use the Instance Scheduler on AWS to configure start and stop schedules.

Instance Scheduler: The AWS Instance Scheduler is a solution that allows you to schedule the start and stop times of your Amazon EC2 and RDS instances. By configuring start and stop schedules, you can ensure that resources are only running during the required business hours, thereby optimizing costs.

</details>

---

## Question 580

[Review topic](../sections/cost-governance.md) · Source PDF page 212

A company uses locally attached storage to run a latency-sensitive application on premises. The company is using a lift and shift method to move
the application to the AWS Cloud. The company does not want to change the application architecture.
Which solution will meet these requirements MOST cost-effectively?

**A.** Configure an Auto Scaling group with an Amazon EC2 instance. Use an Amazon FSx for Lustre file system to run the application.

**B.** Host the application on an Amazon EC2 instance. Use an Amazon Elastic Block Store (Amazon EBS) GP2 volume to run the application.

**C.** Configure an Auto Scaling group with an Amazon EC2 instance. Use an Amazon FSx for OpenZFS file system to run the application.

**D.** Host the application on an Amazon EC2 instance. Use an Amazon Elastic Block Store (Amazon EBS) GP3 volume to run the application.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses locally attached storage to run a latency-sensitive application on premises. The company is using a lift and shift method to move the application to the AWS Cloud. The company does not want to change the application architecture.

Which solution will meet these requirements MOST cost-effectively?


**D.** Host the application on an Amazon EC2 instance. Use an Amazon Elastic Block Store (Amazon EBS) GP3 volume to run the application.

Amazon EC2 Instance with GP3 Volume (Option D): Amazon EBS GP3 volumes are designed to provide cost savings compared to GP2 volumes while still offering good performance for a broad range of workloads. GP3 volumes allow you to provision the IOPS (input/output operations per second) and throughput that your application needs, giving you flexibility and cost-effectiveness.

</details>

---

## Question 581

[Review topic](../sections/ec2.md) · Source PDF page 213

A company runs a stateful production application on Amazon EC2 instances. The application requires at least two EC2 instances to always be
running.
A solutions architect needs to design a highly available and fault-tolerant architecture for the application. The solutions architect creates an Auto
Scaling group of EC2 instances.
Which set of additional steps should the solutions architect take to meet these requirements?

**A.** Set the Auto Scaling group's minimum capacity to two. Deploy one On-Demand Instance in one Availability Zone and one On-Demand
Instance in a second Availability Zone.

**B.** Set the Auto Scaling group's minimum capacity to four. Deploy two On-Demand Instances in one Availability Zone and two On-Demand
Instances in a second Availability Zone.

**C.** Set the Auto Scaling group's minimum capacity to two. Deploy four Spot Instances in one Availability Zone.

**D.** Set the Auto Scaling group's minimum capacity to four. Deploy two On-Demand Instances in one Availability Zone and two Spot Instances in
a second Availability Zone.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: B**

Four On-Demand instances, two in each AZ, leave the required two running after one AZ fails. Spot capacity does not guarantee the baseline.

**Original companion notes (not independently verified):**

A company runs a stateful production application on Amazon EC2 instances. The application requires at least two EC2 instances to always be running.

A solutions architect needs to design a highly available and fault-tolerant architecture for the application. The solutions architect creates an Auto Scaling group of EC2 instances.

Which set of additional steps should the solutions architect take to meet these requirements?

</details>

---

## Question 582

[Review topic](../sections/global-delivery.md) · Source PDF page 213

An ecommerce company uses Amazon Route 53 as its DNS provider. The company hosts its website on premises and in the AWS Cloud. The
company's on-premises data center is near the us-west-1 Region. The company uses the eu-central-1 Region to host the website. The company
wants to minimize load time for the website as much as possible.
Which solution will meet these requirements?

**A.** Set up a geolocation routing policy. Send the traffic that is near us-west-1 to the on-premises data center. Send the traffic that is near eu-
central-1 to eu-central-1.

**B.** Set up a simple routing policy that routes all traffic that is near eu-central-1 to eu-central-1 and routes all traffic that is near the on-premises
datacenter to the on-premises data center.

**C.** Set up a latency routing policy. Associate the policy with us-west-1.

**D.** Set up a weighted routing policy. Split the traffic evenly between eu-central-1 and the on-premises data center.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An ecommerce company uses Amazon Route 53 as its DNS provider. The company hosts its website on premises and in the AWS Cloud. The company's on-premises data center is near the us-west-1 Region. The company uses the eu-central-1 Region to host the website. The company wants to minimize load time for the website as much as possible.

Which solution will meet these requirements?


**A.** Set up a geolocation routing policy. Send the traffic that is near us-west-1 to the on-premises data center. Send the traffic that is near eu-central-1 to eu-central-1.

Geolocation routing directs traffic based on the geographic location of the user. This option would send users near us-west-1 to the on-premises data center and users near eu-central-1 to eu-central-1. While this approach considers geographic location, it might not always result in the lowest latency.

</details>

---

## Question 583

[Review topic](../sections/cost-governance.md) · Source PDF page 213

A company has 5 PB of archived data on physical tapes. The company needs to preserve the data on the tapes for another 10 years for
compliance purposes. The company wants to migrate to AWS in the next 6 months. The data center that stores the tapes has a 1 Gbps uplink
internet connectivity.
Which solution will meet these requirements MOST cost-effectively?

**A.** Read the data from the tapes on premises. Stage the data in a local NFS storage. Use AWS DataSync to migrate the data to Amazon S3
Glacier Flexible Retrieval.

**B.** Use an on-premises backup application to read the data from the tapes and to write directly to Amazon S3 Glacier Deep Archive.

**C.** Order multiple AWS Snowball devices that have Tape Gateway. Copy the physical tapes to virtual tapes in Snowball. Ship the Snowball
devices to AWS. Create a lifecycle policy to move the tapes to Amazon S3 Glacier Deep Archive.

**D.** Configure an on-premises Tape Gateway. Create virtual tapes in the AWS Cloud. Use backup software to copy the physical tape to the virtual
tape.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has 5 PB of archived data on physical tapes. The company needs to preserve the data on the tapes for another 10 years for compliance purposes. The company wants to migrate to AWS in the next 6 months. The data center that stores the tapes has a 1 Gbps uplink internet connectivity.

Which solution will meet these requirements MOST cost-effectively?


**C.** Order multiple AWS Snowball devices that have Tape Gateway. Copy the physical tapes to virtual tapes in Snowball. Ship the Snowball devices to AWS. Create a lifecycle policy to move the tapes to Amazon S3 Glacier Deep Archive.

AWS Snowball devices can be more cost-effective than transferring large amounts of data over a 1 Gbps internet connection, especially when dealing with petabytes of data. 
AWS, a lifecycle policy can be configured to move the data to Amazon S3 Glacier Deep Archive, which is a cost-effective storage class designed for long-term archival.

</details>

---

## Question 584

[Review topic](../sections/ec2.md) · Source PDF page 214

A company is deploying an application that processes large quantities of data in parallel. The company plans to use Amazon EC2 instances for
the workload. The network architecture must be configurable to prevent groups of nodes from sharing the same underlying hardware.
Which networking solution meets these requirements?

**A.** Run the EC2 instances in a spread placement group.

**B.** Group the EC2 instances in separate accounts.

**C.** Configure the EC2 instances with dedicated tenancy.

**D.** Configure the EC2 instances with shared tenancy.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is deploying an application that processes large quantities of data in parallel. The company plans to use Amazon EC2 instances for the workload. The network architecture must be configurable to prevent groups of nodes from sharing the same underlying hardware.

Which networking solution meets these requirements?


**A.** Run the EC2 instances in a spread placement group.

A spread placement group is a logical grouping of instances that are placed on distinct underlying hardware. This ensures that instances within the group are physically separated, reducing the risk of correlated failures. This option is suitable for applications that need to maximize the level of isolation.

</details>

---

## Question 585

[Review topic](../sections/disaster-recovery.md) · Source PDF page 214

A solutions architect is designing a disaster recovery (DR) strategy to provide Amazon EC2 capacity in a failover AWS Region. Business
requirements state that the DR strategy must meet capacity in the failover Region.
Which solution will meet these requirements?

**A.** Purchase On-Demand Instances in the failover Region.

**B.** Purchase an EC2 Savings Plan in the failover Region.

**C.** Purchase regional Reserved Instances in the failover Region.

**D.** Purchase a Capacity Reservation in the failover Region.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing a disaster recovery (DR) strategy to provide Amazon EC2 capacity in a failover AWS Region. Business requirements state that the DR strategy must meet capacity in the failover Region.

Which solution will meet these requirements?


**D.** Purchase a Capacity Reservation in the failover Region.

A Capacity Reservation allows you to reserve a specific amount of EC2 instance capacity in a given region without purchasing specific instances. This reserved capacity is dedicated to your account and can be utilized for launching instances when needed. Capacity Reservations offer flexibility, allowing you to launch different instance types and sizes within the reserved capacity.

</details>

---

## Question 586

[Review topic](../sections/cost-governance.md) · Source PDF page 214

A company has five organizational units (OUs) as part of its organization in AWS Organizations. Each OU correlates to the five businesses that the
company owns. The company's research and development (R&D) business is separating from the company and will need its own organization. A
solutions architect creates a separate new management account for this purpose.
What should the solutions architect do next in the new management account?

**A.** Have the R&D AWS account be part of both organizations during the transition.

**B.** Invite the R&D AWS account to be part of the new organization after the R&D AWS account has left the prior organization.

**C.** Create a new R&D AWS account in the new organization. Migrate resources from the prior R&D AWS account to the new R&D AWS account.

**D.** Have the R&D AWS account join the new organization. Make the new management account a member of the prior organization.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has five organizational units (OUs) as part of its organization in AWS Organizations. Each OU correlates to the five businesses that the company owns. The company's research and development (R&D) business is separating from the company and will need its own organization. A solutions architect creates a separate new management account for this purpose.

What should the solutions architect do next in the new management account?


**B.** Invite the R&D AWS account to be part of the new organization after the R&D AWS account has left the prior organization.

</details>

---

## Question 587

[Review topic](../sections/analytics.md) · Source PDF page 215

A company is designing a solution to capture customer activity in different web applications to process analytics and make predictions. Customer
activity in the web applications is unpredictable and can increase suddenly. The company requires a solution that integrates with other web
applications. The solution must include an authorization step for security purposes.
Which solution will meet these requirements?

**A.** Configure a Gateway Load Balancer (GWLB) in front of an Amazon Elastic Container Service (Amazon ECS) container instance that stores
the information that the company receives in an Amazon Elastic File System (Amazon EFS) file system. Authorization is resolved at the GWLB.

**B.** Configure an Amazon API Gateway endpoint in front of an Amazon Kinesis data stream that stores the information that the company
receives in an Amazon S3 bucket. Use an AWS Lambda function to resolve authorization.

**C.** Configure an Amazon API Gateway endpoint in front of an Amazon Kinesis Data Firehose that stores the information that the company
receives in an Amazon S3 bucket. Use an API Gateway Lambda authorizer to resolve authorization.

**D.** Configure a Gateway Load Balancer (GWLB) in front of an Amazon Elastic Container Service (Amazon ECS) container instance that stores
the information that the company receives on an Amazon Elastic File System (Amazon EFS) file system. Use an AWS Lambda function to
resolve authorization.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is designing a solution to capture customer activity in different web applications to process analytics and make predictions. Customer activity in the web applications is unpredictable and can increase suddenly. The company requires a solution that integrates with other web applications. The solution must include an authorization step for security purposes.

Which solution will meet these requirements?


**C.** Configure an Amazon API Gateway endpoint in front of an Amazon Kinesis Data Firehose that stores the information that the company receives in an Amazon S3 bucket. Use an API Gateway Lambda authorizer to resolve authorization.

Amazon API Gateway: It provides a fully managed service for creating, publishing, maintaining, monitoring, and securing APIs at any scale. It allows you to expose the capabilities of your backend services as APIs.
Amazon Kinesis Data Firehose: It can capture and load streaming data into storage services such as Amazon S3. It is well-suited for scenarios where you need to ingest and store large volumes of streaming data.
API Gateway Lambda Authorizer: It allows you to control access to your APIs using Lambda functions. It's used to resolve authorization before allowing access to the API.

</details>

---

## Question 588

[Review topic](../sections/disaster-recovery.md) · Source PDF page 215

An ecommerce company wants a disaster recovery solution for its Amazon RDS DB instances that run Microsoft SQL Server Enterprise Edition.
The company's current recovery point objective (RPO) and recovery time objective (RTO) are 24 hours.
Which solution will meet these requirements MOST cost-effectively?

**A.** Create a cross-Region read replica and promote the read replica to the primary instance.

**B.** Use AWS Database Migration Service (AWS DMS) to create RDS cross-Region replication.

**C.** Use cross-Region replication every 24 hours to copy native backups to an Amazon S3 bucket.

**D.** Copy automatic snapshots to another Region every 24 hours.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An ecommerce company wants a disaster recovery solution for its Amazon RDS DB instances that run Microsoft SQL Server Enterprise Edition. The company's current recovery point objective (RPO) and recovery time objective (RTO) are 24 hours.

Which solution will meet these requirements MOST cost-effectively?


**D.** Copy automatic snapshots to another Region every 24 hours.

RDS automatically takes snapshots of your database instances. These snapshots capture the entire DB instance, including the data and the DB instance's metadata.

</details>

---

## Question 589

[Review topic](../sections/elb-asg.md) · Source PDF page 215

A company runs a web application on Amazon EC2 instances in an Auto Scaling group behind an Application Load Balancer that has sticky
sessions enabled. The web server currently hosts the user session state. The company wants to ensure high availability and avoid user session
state loss in the event of a web server outage.
Which solution will meet these requirements?

**A.** Use an Amazon ElastiCache for Memcached instance to store the session data. Update the application to use ElastiCache for Memcached
to store the session state.

**B.** Use Amazon ElastiCache for Redis to store the session state. Update the application to use ElastiCache for Redis to store the session
state.

**C.** Use an AWS Storage Gateway cached volume to store session data. Update the application to use AWS Storage Gateway cached volume to
store the session state.

**D.** Use Amazon RDS to store the session state. Update the application to use Amazon RDS to store the session state.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a web application on Amazon EC2 instances in an Auto Scaling group behind an Application Load Balancer that has sticky sessions enabled. The web server currently hosts the user session state. The company wants to ensure high availability and avoid user session state loss in the event of a web server outage.

Which solution will meet these requirements?


**B.** Use Amazon ElastiCache for Redis to store the session state. Update the application to use ElastiCache for Redis to store the session state.

ElastiCache for Redis is an in-memory data store service that is well-suited for storing session data. It provides high availability and durability. Using Redis allows the application to offload the session state from individual EC2 instances to a centralized and highly available Redis cluster.

</details>

---

## Question 590

[Review topic](../sections/rds-aurora.md) · Source PDF page 216

A company migrated a MySQL database from the company's on-premises data center to an Amazon RDS for MySQL DB instance. The company
sized the RDS DB instance to meet the company's average daily workload. Once a month, the database performs slowly when the company runs
queries for a report. The company wants to have the ability to run reports and maintain the performance of the daily workloads.
Which solution will meet these requirements?

**A.** Create a read replica of the database. Direct the queries to the read replica.

**B.** Create a backup of the database. Restore the backup to another DB instance. Direct the queries to the new database.

**C.** Export the data to Amazon S3. Use Amazon Athena to query the S3 bucket.

**D.** Resize the DB instance to accommodate the additional workload.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company migrated a MySQL database from the company's on-premises data center to an Amazon RDS for MySQL DB instance. The company sized the RDS DB instance to meet the company's average daily workload. Once a month, the database performs slowly when the company runs queries for a report. The company wants to have the ability to run reports and maintain the performance of the daily workloads.

Which solution will meet these requirements?


**A.** Create a read replica of the database. Direct the queries to the read replica.

Read Replica: Creating a read replica of the database allows you to offload read queries to a replica instance. This helps in distributing the workload and prevents the additional load from impacting the performance of the primary database.

Direct Queries to the Read Replica: By directing the queries for the monthly reports to the read replica, you ensure that the heavy reporting workload doesn't affect the performance of the primary database handling daily workloads. Read replicas are designed to handle read-intensive workloads, providing a scalable solution.

</details>

---

## Question 591

[Review topic](../sections/containers.md) · Source PDF page 216

A company runs a container application by using Amazon Elastic Kubernetes Service (Amazon EKS). The application includes microservices that
manage customers and place orders. The company needs to route incoming requests to the appropriate microservices.
Which solution will meet this requirement MOST cost-effectively?

**A.** Use the AWS Load Balancer Controller to provision a Network Load Balancer.

**B.** Use the AWS Load Balancer Controller to provision an Application Load Balancer.

**C.** Use an AWS Lambda function to connect the requests to Amazon EKS.

**D.** Use Amazon API Gateway to connect the requests to Amazon EKS.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a container application by using Amazon Elastic Kubernetes Service (Amazon EKS). The application includes microservices that manage customers and place orders. The company needs to route incoming requests to the appropriate microservices.

Which solution will meet this requirement MOST cost-effectively?


**B.** Use the AWS Load Balancer Controller to provision an Application Load Balancer.

This is a Kubernetes-native controller that allows you to define and manage Application Load Balancers and Network Load Balancers to route traffic to services in your Amazon EKS cluster.
ALBs are designed for routing HTTP/HTTPS traffic and provide more advanced routing features compared to Network Load Balancers.

</details>

---

## Question 592

[Review topic](../sections/exam-revision.md) · Source PDF page 216

A company uses AWS and sells access to copyrighted images. The company’s global customer base needs to be able to access these images
quickly. The company must deny access to users from specific countries. The company wants to minimize costs as much as possible.
Which solution will meet these requirements?

**A.** Use Amazon S3 to store the images. Turn on multi-factor authentication (MFA) and public bucket access. Provide customers with a link to
the S3 bucket.

**B.** Use Amazon S3 to store the images. Create an IAM user for each customer. Add the users to a group that has permission to access the S3
bucket.

**C.** Use Amazon EC2 instances that are behind Application Load Balancers (ALBs) to store the images. Deploy the instances only in the
countries the company services. Provide customers with links to the ALBs for their specific country's instances.

**D.** Use Amazon S3 to store the images. Use Amazon CloudFront to distribute the images with geographic restrictions. Provide a signed URL
for each customer to access the data in CloudFront.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses AWS and sells access to copyrighted images. The company’s global customer base needs to be able to access these images quickly. The company must deny access to users from specific countries. The company wants to minimize costs as much as possible.

Which solution will meet these requirements?


**D.** Use Amazon S3 to store the images. Use Amazon CloudFront to distribute the images with geographic restrictions. Provide a signed URL for each customer to access the data in CloudFront.

By using CloudFront, you can cache and serve the images from edge locations around the world, improving access speed for global customers.
Geographic Restrictions in CloudFront: CloudFront allows you to set up geographic restrictions to deny access to users from specific countries.

</details>

---

## Question 593

[Review topic](../sections/cloud-foundations.md) · Source PDF page 217

A solutions architect is designing a highly available Amazon ElastiCache for Redis based solution. The solutions architect needs to ensure that
failures do not result in performance degradation or loss of data locally and within an AWS Region. The solution needs to provide high availability
at the node level and at the Region level.
Which solution will meet these requirements?

**A.** Use Multi-AZ Redis replication groups with shards that contain multiple nodes.

**B.** Use Redis shards that contain multiple nodes with Redis append only files (AOF) turned on.

**C.** Use a Multi-AZ Redis cluster with more than one read replica in the replication group.

**D.** Use Redis shards that contain multiple nodes with Auto Scaling turned on.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing a highly available Amazon ElastiCache for Redis based solution. The solutions architect needs to ensure that failures do not result in performance degradation or loss of data locally and within an AWS Region. The solution needs to provide high availability at the node level and at the Region level.

Which solution will meet these requirements?


**A.** Use Multi-AZ Redis replication groups with shards that contain multiple nodes.

 Multi-AZ (Availability Zone) replication groups provide high availability at the node level. In a Multi-AZ setup, your data is replicated asynchronously to a standby replica in a different Availability Zone.
Using shards with multiple nodes within each Availability Zone further enhances availability and provides scalability.

</details>

---

## Question 594

[Review topic](../sections/ec2.md) · Source PDF page 217

A company plans to migrate to AWS and use Amazon EC2 On-Demand Instances for its application. During the migration testing phase, a
technical team observes that the application takes a long time to launch and load memory to become fully productive.
Which solution will reduce the launch time of the application during the next testing phase?

**A.** Launch two or more EC2 On-Demand Instances. Turn on auto scaling features and make the EC2 On-Demand Instances available during the
next testing phase.

**B.** Launch EC2 Spot Instances to support the application and to scale the application so it is available during the next testing phase.

**C.** Launch the EC2 On-Demand Instances with hibernation turned on. Configure EC2 Auto Scaling warm pools during the next testing phase.

**D.** Launch EC2 On-Demand Instances with Capacity Reservations. Start additional EC2 instances during the next testing phase.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company plans to migrate to AWS and use Amazon EC2 On-Demand Instances for its application. During the migration testing phase, a technical team observes that the application takes a long time to launch and load memory to become fully productive.

Which solution will reduce the launch time of the application during the next testing phase?


**C.** Launch the EC2 On-Demand Instances with hibernation turned on. Configure EC2 Auto Scaling warm pools during the next testing phase.

When you launch EC2 On-Demand Instances with hibernation turned on, the instances can be hibernated and resumed rather than terminated and launched.

</details>

---

## Question 595

[Review topic](../sections/elb-asg.md) · Source PDF page 217

A company's applications run on Amazon EC2 instances in Auto Scaling groups. The company notices that its applications experience sudden
traffic increases on random days of the week. The company wants to maintain application performance during sudden traffic increases.
Which solution will meet these requirements MOST cost-effectively?

**A.** Use manual scaling to change the size of the Auto Scaling group.

**B.** Use predictive scaling to change the size of the Auto Scaling group.

**C.** Use dynamic scaling to change the size of the Auto Scaling group.

**D.** Use schedule scaling to change the size of the Auto Scaling group.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company's applications run on Amazon EC2 instances in Auto Scaling groups. The company notices that its applications experience sudden traffic increases on random days of the week. The company wants to maintain application performance during sudden traffic increases.

Which solution will meet these requirements MOST cost-effectively?


**C.** Use dynamic scaling to change the size of the Auto Scaling group.

Dynamic Scaling: With dynamic scaling, the Auto Scaling group automatically adjusts its capacity based on real-time demand. It scales out during traffic spikes and scales in during periods of lower demand. This ensures that your application can handle sudden increases in traffic without manual intervention.

</details>

---

## Question 596

[Review topic](../sections/exam-revision.md) · Source PDF page 218

An ecommerce application uses a PostgreSQL database that runs on an Amazon EC2 instance. During a monthly sales event, database usage
increases and causes database connection issues for the application. The traffic is unpredictable for subsequent monthly sales events, which
impacts the sales forecast. The company needs to maintain performance when there is an unpredictable increase in traffic.
Which solution resolves this issue in the MOST cost-effective way?

**A.** Migrate the PostgreSQL database to Amazon Aurora Serverless v2.

**B.** Enable auto scaling for the PostgreSQL database on the EC2 instance to accommodate increased usage.

**C.** Migrate the PostgreSQL database to Amazon RDS for PostgreSQL with a larger instance type.

**D.** Migrate the PostgreSQL database to Amazon Redshift to accommodate increased usage.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An ecommerce application uses a PostgreSQL database that runs on an Amazon EC2 instance. During a monthly sales event, database usage increases and causes database connection issues for the application. The traffic is unpredictable for subsequent monthly sales events, which impacts the sales forecast. The company needs to maintain performance when there is an unpredictable increase in traffic.

Which solution resolves this issue in the MOST cost-effective way?


**A.** Migrate the PostgreSQL database to Amazon Aurora Serverless v2.

Aurora Serverless is a serverless relational database engine provided by Amazon. It automatically adjusts its capacity based on actual usage, allowing it to scale up or down as needed. Aurora Serverless v2 builds upon the original Aurora Serverless model with additional features for even more efficient scaling.

</details>

---

## Question 597

[Review topic](../sections/serverless.md) · Source PDF page 218

A company hosts an internal serverless application on AWS by using Amazon API Gateway and AWS Lambda. The company’s employees report
issues with high latency when they begin using the application each day. The company wants to reduce latency.
Which solution will meet these requirements?

**A.** Increase the API Gateway throttling limit.

**B.** Set up a scheduled scaling to increase Lambda provisioned concurrency before employees begin to use the application each day.

**C.** Create an Amazon CloudWatch alarm to initiate a Lambda function as a target for the alarm at the beginning of each day.

**D.** Increase the Lambda function memory.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company hosts an internal serverless application on AWS by using Amazon API Gateway and AWS Lambda. The company’s employees report issues with high latency when they begin using the application each day. The company wants to reduce latency.

Which solution will meet these requirements?


**B.** Set up a scheduled scaling to increase Lambda provisioned concurrency before employees begin to use the application each day.

Lambda Provisioned Concurrency: Provisioned concurrency is the number of simultaneous executions that your function can handle. By setting up a scheduled scaling to increase Lambda provisioned concurrency before employees begin using the application, you are proactively ensuring that there are enough resources available to handle the expected load.

</details>

---

## Question 598

[Review topic](../sections/ec2-storage.md) · Source PDF page 218

A research company uses on-premises devices to generate data for analysis. The company wants to use the AWS Cloud to analyze the data. The
devices generate .csv files and support writing the data to an SMB file share. Company analysts must be able to use SQL commands to query the
data. The analysts will run queries periodically throughout the day.
Which combination of steps will meet these requirements MOST cost-effectively? (Choose three.)

**A.** Deploy an AWS Storage Gateway on premises in Amazon S3 File Gateway mode.

**B.** Deploy an AWS Storage Gateway on premises in Amazon FSx File Gateway made.

**C.** Set up an AWS Glue crawler to create a table based on the data that is in Amazon S3.

**D.** Set up an Amazon EMR cluster with EMR File System (EMRFS) to query the data that is in Amazon S3. Provide access to analysts.

**E.** Set up an Amazon Redshift cluster to query the data that is in Amazon S3. Provide access to analysts.

**F.** Setup Amazon Athena to query the data that is in Amazon S3. Provide access to analysts.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A research company uses on-premises devices to generate data for analysis. The company wants to use the AWS Cloud to analyze the data. The devices generate .csv files and support writing the data to an SMB file share. Company analysts must be able to use SQL commands to query the data. The analysts will run queries periodically throughout the day.

Which combination of steps will meet these requirements MOST cost-effectively? (Choose three.)


**A.** Deploy an AWS Storage Gateway on premises in Amazon S3 File Gateway mode.


**C.** Set up an AWS Glue crawler to create a table based on the data that is in Amazon S3.


**F.** Setup Amazon Athena to query the data that is in Amazon S3. Provide access to analysts.

This step allows you to seamlessly integrate on-premises devices with AWS S3, providing a scalable and cost-effective storage solution. The AWS Storage Gateway in S3 File Gateway mode enables you to write data from on-premises devices to S3.

AWS Glue can discover, catalog, and transform data from S3. By setting up a Glue crawler, you create a table schema based on the .csv files in S3. This step prepares the data for analysis.

Amazon Athena allows you to run SQL queries directly on the data stored in S3 without the need for a dedicated database. You can create databases and tables in Athena based on the cataloged data using Glue.

</details>

---

## Question 599

[Review topic](../sections/containers.md) · Source PDF page 219

A company wants to use Amazon Elastic Container Service (Amazon ECS) clusters and Amazon RDS DB instances to build and run a payment
processing application. The company will run the application in its on-premises data center for compliance purposes.
A solutions architect wants to use AWS Outposts as part of the solution. The solutions architect is working with the company's operational team
to build the application.
Which activities are the responsibility of the company's operational team? (Choose three.)

**A.** Providing resilient power and network connectivity to the Outposts racks

**B.** Managing the virtualization hypervisor, storage systems, and the AWS services that run on Outposts

**C.** Physical security and access controls of the data center environment

**D.** Availability of the Outposts infrastructure including the power supplies, servers, and networking equipment within the Outposts racks

**E.** Physical maintenance of Outposts components

**F.** Providing extra capacity for Amazon ECS clusters to mitigate server failures and maintenance events

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: A, C, F**

The customer supplies site power/networking, physical access security, and application capacity planning. AWS maintains Outposts hardware and its virtualization/service infrastructure.

**Original companion notes (not independently verified):**

A company wants to use Amazon Elastic Container Service (Amazon ECS) clusters and Amazon RDS DB instances to build and run a payment processing application. The company will run the application in its on-premises data center for compliance purposes.

A solutions architect wants to use AWS Outposts as part of the solution. The solutions architect is working with the company's operational team to build the application.

Which activities are the responsibility of the company's operational team? (Choose three.)

</details>

---

## Question 600

[Review topic](../sections/vpc.md) · Source PDF page 219

A company is planning to migrate a TCP-based application into the company's VPC. The application is publicly accessible on a nonstandard TCP
port through a hardware appliance in the company's data center. This public endpoint can process up to 3 million requests per second with low
latency. The company requires the same level of performance for the new public endpoint in AWS.
What should a solutions architect recommend to meet this requirement?

**A.** Deploy a Network Load Balancer (NLB). Configure the NLB to be publicly accessible over the TCP port that the application requires.

**B.** Deploy an Application Load Balancer (ALB). Configure the ALB to be publicly accessible over the TCP port that the application requires.

**C.** Deploy an Amazon CloudFront distribution that listens on the TCP port that the application requires. Use an Application Load Balancer as
the origin.

**D.** Deploy an Amazon API Gateway API that is configured with the TCP port that the application requires. Configure AWS Lambda functions
with provisioned concurrency to process the requests.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is planning to migrate a TCP-based application into the company's VPC. The application is publicly accessible on a nonstandard TCP port through a hardware appliance in the company's data center. This public endpoint can process up to 3 million requests per second with low latency. The company requires the same level of performance for the new public endpoint in AWS.

What should a solutions architect recommend to meet this requirement?


**A.** Deploy a Network Load Balancer (NLB). Configure the NLB to be publicly accessible over the TCP port that the application requires.

Network Load Balancer (NLB): It operates at the connection level (Layer 4) and is well-suited for TCP traffic. It can handle millions of requests per second with minimal latency.
NLB allows you to configure the listener for the specific TCP port that the application requires, ensuring compatibility with the nonstandard TCP port used by the application.

</details>

---

