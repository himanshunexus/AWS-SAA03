# Practice questions 251-300

[Home](../README.md) · [All sets](README.md)

Answer notes are source-provided unless labeled suggested. These sets preserve the supplied PDF; they are not official AWS exams.

## Question 251

[Review topic](../sections/vpc.md) · Source PDF page 91

An Amazon EC2 instance is located in a private subnet in a new VPC. This subnet does not have outbound internet access, but the EC2 instance
needs the ability to download monthly security updates from an outside vendor.
What should a solutions architect do to meet these requirements?

**A.** Create an internet gateway, and attach it to the VPC. Configure the private subnet route table to use the internet gateway as the default
route.

**B.** Create a NAT gateway, and place it in a public subnet. Configure the private subnet route table to use the NAT gateway as the default route.

**C.** Create a NAT instance, and place it in the same subnet where the EC2 instance is located. Configure the private subnet route table to use
the NAT instance as the default route.

**D.** Create an internet gateway, and attach it to the VPC. Create a NAT instance, and place it in the same subnet where the EC2 instance is
located. Configure the private subnet route table to use the internet gateway as the default route.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An Amazon EC2 instance is located in a private subnet in a new VPC. This subnet does not have outbound internet access, but the EC2 instance needs the ability to download monthly security updates from an outside vendor.

What should a solutions architect do to meet these requirements?


**B.** Create a NAT gateway, and place it in a public subnet. Configure the private subnet route table to use the NAT gateway as the default route.

NAT gateways are designed to provide outbound internet access for instances in private subnets. Placing a NAT gateway in a public subnet and configuring the private subnet's route table to use the NAT gateway as the default route allows the EC2 instance to download security updates while maintaining security.

</details>

---

## Question 252

[Review topic](../sections/ec2.md) · Source PDF page 91

A solutions architect needs to design a system to store client case files. The files are core company assets and are important. The number of files
will grow over time.
The files must be simultaneously accessible from multiple application servers that run on Amazon EC2 instances. The solution must have built-in
redundancy.
Which solution meets these requirements?

**A.** Amazon Elastic File System (Amazon EFS)

**B.** Amazon Elastic Block Store (Amazon EBS)

**C.** Amazon S3 Glacier Deep Archive

**D.** AWS Backup

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect needs to design a system to store client case files. The files are core company assets and are important. The number of files will grow over time.

The files must be simultaneously accessible from multiple application servers that run on Amazon EC2 instances. The solution must have built-in redundancy.

Which solution meets these requirements?


**A.** Amazon Elastic File System (Amazon EFS)

</details>

---

## Question 253

[Review topic](../sections/iam.md) · Source PDF page 92

A solutions architect has created two IAM policies: Policy1 and Policy2. Both policies are attached to an IAM group.
A cloud engineer is added as an IAM user to the IAM group. Which action will the cloud engineer be able to perform?

**A.** Deleting IAM users

**B.** Deleting directories

**C.** Deleting Amazon EC2 instances

**D.** Deleting logs from Amazon CloudWatch Logs

**Policy / option transcription**

Policy 1 allows iam:Get*, iam:List*, kms:List*, ec2:*, rds:*, logs:Get* and logs:Describe* on *. Policy 2 denies ds:Delete* on *. These are two distinct service prefixes: iam is IAM; ds is Directory Service.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

policy que. 


**C.** Deleting Amazon EC2 instances.

</details>

---

## Question 254

[Review topic](../sections/vpc.md) · Source PDF page 92

A company is reviewing a recent migration of a three-tier application to a VPC. The security team discovers that the principle of least privilege is
not being applied to Amazon EC2 security group ingress and egress rules between the application tiers.
What should a solutions architect do to correct this issue?

**A.** Create security group rules using the instance ID as the source or destination.

**B.** Create security group rules using the security group ID as the source or destination.

**C.** Create security group rules using the VPC CIDR blocks as the source or destination.

**D.** Create security group rules using the subnet CIDR blocks as the source or destination.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is reviewing a recent migration of a three-tier application to a VPC. The security team discovers that the principle of least privilege is not being applied to Amazon EC2 security group ingress and egress rules between the application tiers.

What should a solutions architect do to correct this issue?


**B.** Create security group rules using the security group ID as the source or destination.

Using security group IDs allows for dynamic and flexible configuration. Referencing security groups directly in rules ensures that instances associated with those security groups, regardless of their individual IDs, are included. This approach aligns with the principle of least privilege and simplifies rule management.

</details>

---

## Question 255

[Review topic](../sections/exam-revision.md) · Source PDF page 93

A company has an ecommerce checkout workflow that writes an order to a database and calls a service to process the payment. Users are
experiencing timeouts during the checkout process. When users resubmit the checkout form, multiple unique orders are created for the same
desired transaction.
How should a solutions architect refactor this workflow to prevent the creation of multiple orders?

**A.** Configure the web application to send an order message to Amazon Kinesis Data Firehose. Set the payment service to retrieve the message
from Kinesis Data Firehose and process the order.

**B.** Create a rule in AWS CloudTrail to invoke an AWS Lambda function based on the logged application path request. Use Lambda to query the
database, call the payment service, and pass in the order information.

**C.** Store the order in the database. Send a message that includes the order number to Amazon Simple Notification Service (Amazon SNS). Set
the payment service to poll Amazon SNS, retrieve the message, and process the order.

**D.** Store the order in the database. Send a message that includes the order number to an Amazon Simple Queue Service (Amazon SQS) FIFO
queue. Set the payment service to retrieve the message and process the order. Delete the message from the queue.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an ecommerce checkout workflow that writes an order to a database and calls a service to process the payment. Users are experiencing timeouts during the checkout process. When users resubmit the checkout form, multiple unique orders are created for the same desired transaction.

How should a solutions architect refactor this workflow to prevent the creation of multiple orders?


**D.** Store the order in the database. Send a message that includes the order number to an Amazon Simple Queue Service (Amazon SQS) FIFO queue. Set the payment service to retrieve the message and process the order. Delete the message from the queue.
Storing the order in the database first ensures that the order information is saved, even if the payment processing is delayed or fails.
Sending a message to an SQS FIFO queue with the order number ensures that the processing is idempotent. If the same order number is sent multiple times, SQS guarantees that the messages are processed in order and only once.

</details>

---

## Question 256

[Review topic](../sections/s3.md) · Source PDF page 93

A solutions architect is implementing a document review application using an Amazon S3 bucket for storage. The solution must prevent
accidental deletion of the documents and ensure that all versions of the documents are available. Users must be able to download, modify, and
upload documents.
Which combination of actions should be taken to meet these requirements? (Choose two.)

**A.** Enable a read-only bucket ACL.

**B.** Enable versioning on the bucket.

**C.** Attach an IAM policy to the bucket.

**D.** Enable MFA Delete on the bucket.

**E.** Encrypt the bucket using AWS KMS.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is implementing a document review application using an Amazon S3 bucket for storage. The solution must prevent accidental deletion of the documents and ensure that all versions of the documents are available. Users must be able to download, modify, and upload documents.

Which combination of actions should be taken to meet these requirements? (Choose two.)


**B.** Enable versioning on the bucket.


**D.** Enable MFA Delete on the bucket.

**B.** allows multiple versions of objects in the S3 bucket to be stored. This ensures that all versions of the documents are available, even if they are accidentally overwritten or deleted.


**D.** adds an extra layer of protection against accidental deletion of objects in the bucket. With MFA Delete enabled, a user would need to provide an additional authentication factor to successfully delete objects from the bucket. This helps prevent accidental or unauthorized deletions and provides an extra level of security for critical documents.

</details>

---

## Question 257

[Review topic](../sections/elb-asg.md) · Source PDF page 93

A company is building a solution that will report Amazon EC2 Auto Scaling events across all the applications in an AWS account. The company
needs to use a serverless solution to store the EC2 Auto Scaling status data in Amazon S3. The company then will use the data in Amazon S3 to
provide near-real-time updates in a dashboard. The solution must not affect the speed of EC2 instance launches.
How should the company move the data to Amazon S3 to meet these requirements?

**A.** Use an Amazon CloudWatch metric stream to send the EC2 Auto Scaling status data to Amazon Kinesis Data Firehose. Store the data in
Amazon S3.

**B.** Launch an Amazon EMR cluster to collect the EC2 Auto Scaling status data and send the data to Amazon Kinesis Data Firehose. Store the
data in Amazon S3.

**C.** Create an Amazon EventBridge rule to invoke an AWS Lambda function on a schedule. Configure the Lambda function to send the EC2 Auto
Scaling status data directly to Amazon S3.

**D.** Use a bootstrap script during the launch of an EC2 instance to install Amazon Kinesis Agent. Configure Kinesis Agent to collect the EC2
Auto Scaling status data and send the data to Amazon Kinesis Data Firehose. Store the data in Amazon S3.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: A**

CloudWatch metric streams through Firehose provide managed, near-real-time delivery of enabled Auto Scaling metrics to S3. Metrics are not individual lifecycle events; use EventBridge event rules when actual event records are required.

</details>

---

## Question 258

[Review topic](../sections/s3.md) · Source PDF page 94

A company has an application that places hundreds of .csv files into an Amazon S3 bucket every hour. The files are 1 GB in size. Each time a file is
uploaded, the company needs to convert the file to Apache Parquet format and place the output file into an S3 bucket.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create an AWS Lambda function to download the .csv files, convert the files to Parquet format, and place the output files in an S3 bucket.
Invoke the Lambda function for each S3 PUT event.

**B.** Create an Apache Spark job to read the .csv files, convert the files to Parquet format, and place the output files in an S3 bucket. Create an
AWS Lambda function for each S3 PUT event to invoke the Spark job.

**C.** Create an AWS Glue table and an AWS Glue crawler for the S3 bucket where the application places the .csv files. Schedule an AWS Lambda
function to periodically use Amazon Athena to query the AWS Glue table, convert the query results into Parquet format, and place the output
files into an S3 bucket.

**D.** Create an AWS Glue extract, transform, and load (ETL) job to convert the .csv files to Parquet format and place the output files into an S3
bucket. Create an AWS Lambda function for each S3 PUT event to invoke the ETL job.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an application that places hundreds of .csv files into an Amazon S3 bucket every hour. The files are 1 GB in size. Each time a file is uploaded, the company needs to convert the file to Apache Parquet format and place the output file into an S3 bucket.

Which solution will meet these requirements with the LEAST operational overhead?


**D.** Create an AWS Glue extract, transform, and load (ETL) job to convert the .csv files to Parquet format and place the output files into an S3 bucket. Create an AWS Lambda function for each S3 PUT event to invoke the ETL job.

AWS Glue ETL Job:

AWS Glue is a fully managed extract, transform, and load (ETL) service that can be used to convert data formats.
By creating an AWS Glue ETL job, you can offload the conversion process to a fully managed service, reducing operational overhead.
AWS Lambda for S3 PUT Events:
AWS Lambda can be configured to trigger on S3 PUT events. This ensures that the ETL job is invoked automatically each time a new .csv file is uploaded to the S3 bucket.
The Lambda function acts as a glue between the S3 events and the Glue ETL job.

</details>

---

## Question 259

[Review topic](../sections/iam.md) · Source PDF page 94

A company is implementing new data retention policies for all databases that run on Amazon RDS DB instances. The company must retain daily
backups for a minimum period of 2 years. The backups must be consistent and restorable.
Which solution should a solutions architect recommend to meet these requirements?

**A.** Create a backup vault in AWS Backup to retain RDS backups. Create a new backup plan with a daily schedule and an expiration period of 2
years after creation. Assign the RDS DB instances to the backup plan.

**B.** Configure a backup window for the RDS DB instances for daily snapshots. Assign a snapshot retention policy of 2 years to each RDS DB
instance. Use Amazon Data Lifecycle Manager (Amazon DLM) to schedule snapshot deletions.

**C.** Configure database transaction logs to be automatically backed up to Amazon CloudWatch Logs with an expiration period of 2 years.

**D.** Configure an AWS Database Migration Service (AWS DMS) replication task. Deploy a replication instance, and configure a change data
capture (CDC) task to stream database changes to Amazon S3 as the target. Configure S3 Lifecycle policies to delete the snapshots after 2
years.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is implementing new data retention policies for all databases that run on Amazon RDS DB instances. The company must retain daily backups for a minimum period of 2 years. The backups must be consistent and restorable.

Which solution should a solutions architect recommend to meet these requirements?


**A.** Create a backup vault in AWS Backup to retain RDS backups. Create a new backup plan with a daily schedule and an expiration period of 2 years after creation. Assign the RDS DB instances to the backup plan.

</details>

---

## Question 260

[Review topic](../sections/ec2-storage.md) · Source PDF page 94

A company’s compliance team needs to move its file shares to AWS. The shares run on a Windows Server SMB file share. A self-managed on-
premises Active Directory controls access to the files and folders.
The company wants to use Amazon FSx for Windows File Server as part of the solution. The company must ensure that the on-premises Active
Directory groups restrict access to the FSx for Windows File Server SMB compliance shares, folders, and files after the move to AWS. The
company has created an FSx for Windows File Server file system.
Which solution will meet these requirements?

**A.** Create an Active Directory Connector to connect to the Active Directory. Map the Active Directory groups to IAM groups to restrict access.

**B.** Assign a tag with a Restrict tag key and a Compliance tag value. Map the Active Directory groups to IAM groups to restrict access.

**C.** Create an IAM service-linked role that is linked directly to FSx for Windows File Server to restrict access.

**D.** Join the file system to the Active Directory to restrict access.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company’s compliance team needs to move its file shares to AWS. The shares run on a Windows Server SMB file share. A self-managed on-premises Active Directory controls access to the files and folders.

The company wants to use Amazon FSx for Windows File Server as part of the solution. The company must ensure that the on-premises Active Directory groups restrict access to the FSx for Windows File Server SMB compliance shares, folders, and files after the move to AWS. The company has created an FSx for Windows File Server file system.

Which solution will meet these requirements?


**D.** Join the file system to the Active Directory to restrict access.

Join the File System to Active Directory:

By joining the FSx for Windows File Server file system to the on-premises Active Directory, you extend the trust relationship to AWS.
This ensures that access control is based on the on-premises Active Directory groups, allowing you to continue using the existing groups to restrict access to shares, folders, and files.
After joining the file system to Active Directory, you can manage access controls using the existing Active Directory groups.
Users and groups from the on-premises Active Directory can be granted appropriate permissions on the FSx file system.

</details>

---

## Question 261

[Review topic](../sections/elb-asg.md) · Source PDF page 95

A company recently announced the deployment of its retail website to a global audience. The website runs on multiple Amazon EC2 instances
behind an Elastic Load Balancer. The instances run in an Auto Scaling group across multiple Availability Zones.
The company wants to provide its customers with different versions of content based on the devices that the customers use to access the
website.
Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)

**A.** Configure Amazon CloudFront to cache multiple versions of the content.

**B.** Configure a host header in a Network Load Balancer to forward traffic to different instances.

**C.** Configure a Lambda@Edge function to send specific objects to users based on the User-Agent header.

**D.** Configure AWS Global Accelerator. Forward requests to a Network Load Balancer (NLB). Configure the NLB to set up host-based routing to
different EC2 instances.

**E.** Configure AWS Global Accelerator. Forward requests to a Network Load Balancer (NLB). Configure the NLB to set up path-based routing to
different EC2 instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company recently announced the deployment of its retail website to a global audience. The website runs on multiple Amazon EC2 instances behind an Elastic Load Balancer. The instances run in an Auto Scaling group across multiple Availability Zones.

The company wants to provide its customers with different versions of content based on the devices that the customers use to access the website.

Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)


**A.** Configure Amazon CloudFront to cache multiple versions of the content.


**C.** Configure a Lambda@Edge function to send specific objects to users based on the User-Agent header.

Amazon CloudFront is a content delivery network (CDN) service that can cache and deliver content globally.
Configure CloudFront to cache different versions of content based on the device type or other criteria.

Lambda@Edge allows you to run code in response to CloudFront events globally.
Use a Lambda@Edge function to inspect the User-Agent header and dynamically serve different versions of content based on the device type.

</details>

---

## Question 262

[Review topic](../sections/dynamodb-caching.md) · Source PDF page 95

A company plans to use Amazon ElastiCache for its multi-tier web application. A solutions architect creates a Cache VPC for the ElastiCache
cluster and an App VPC for the application’s Amazon EC2 instances. Both VPCs are in the us-east-1 Region.
The solutions architect must implement a solution to provide the application’s EC2 instances with access to the ElastiCache cluster.
Which solution will meet these requirements MOST cost-effectively?

**A.** Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule
for the ElastiCache cluster’s security group to allow inbound connection from the application’s security group.

**B.** Create a Transit VPC. Update the VPC route tables in the Cache VPC and the App VPC to route traffic through the Transit VPC. Configure an
inbound rule for the ElastiCache cluster's security group to allow inbound connection from the application’s security group.

**C.** Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule
for the peering connection’s security group to allow inbound connection from the application’s security group.

**D.** Create a Transit VPC. Update the VPC route tables in the Cache VPC and the App VPC to route traffic through the Transit VPC. Configure an
inbound rule for the Transit VPC’s security group to allow inbound connection from the application’s security group.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company plans to use Amazon ElastiCache for its multi-tier web application. A solutions architect creates a Cache VPC for the ElastiCache cluster and an App VPC for the application’s Amazon EC2 instances. Both VPCs are in the us-east-1 Region.

The solutions architect must implement a solution to provide the application’s EC2 instances with access to the ElastiCache cluster.

Which solution will meet these requirements MOST cost-effectively?


**A.** Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule for the ElastiCache cluster’s security group to allow inbound connection from the application’s security groups.

Creating a peering connection allows communication between the Cache VPC and the App VPC.

Adding a route table entry in both VPCs for the peering connection ensures that traffic can flow between them.
Inbound Rule in ElastiCache Security Group:

Configuring an inbound rule in the ElastiCache cluster's security group to allow connections from the application's security group enables the EC2 instances in the App VPC to access the ElastiCache cluster.

</details>

---

## Question 263

[Review topic](../sections/containers.md) · Source PDF page 96

A company is building an application that consists of several microservices. The company has decided to use container technologies to deploy its
software on AWS. The company needs a solution that minimizes the amount of ongoing effort for maintenance and scaling. The company cannot
manage additional infrastructure.
Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)

**A.** Deploy an Amazon Elastic Container Service (Amazon ECS) cluster.

**B.** Deploy the Kubernetes control plane on Amazon EC2 instances that span multiple Availability Zones.

**C.** Deploy an Amazon Elastic Container Service (Amazon ECS) service with an Amazon EC2 launch type. Specify a desired task number level of
greater than or equal to 2.

**D.** Deploy an Amazon Elastic Container Service (Amazon ECS) service with a Fargate launch type. Specify a desired task number level of
greater than or equal to 2.

**E.** Deploy Kubernetes worker nodes on Amazon EC2 instances that span multiple Availability Zones. Create a deployment that specifies two or
more replicas for each microservice.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is building an application that consists of several microservices. The company has decided to use container technologies to deploy its software on AWS. The company needs a solution that minimizes the amount of ongoing effort for maintenance and scaling. The company cannot manage additional infrastructure.

Which combination of actions should a solutions architect take to meet these requirements? (Choose two.)


**A.** Deploy an Amazon Elastic Container Service (Amazon ECS) cluster.


**D.** Deploy an Amazon Elastic Container Service (Amazon ECS) service with a Fargate launch type. Specify a desired task number level of greater than or equal to 2.

An ECS cluster is necessary to organize and manage your Fargate tasks and services. It provides a logical grouping of tasks and services.
When using Fargate, you don't need to manage the underlying EC2 instances; the cluster helps manage the Fargate tasks.

Fargate is a serverless compute engine for containers that eliminates the need to manage underlying infrastructure.
With Fargate, you do not need to provision or manage EC2 instances; AWS takes care of the infrastructure, allowing you to focus solely on your containers.

</details>

---

## Question 264

[Review topic](../sections/global-delivery.md) · Source PDF page 96

A company has a web application hosted over 10 Amazon EC2 instances with traffic directed by Amazon Route 53. The company occasionally
experiences a timeout error when attempting to browse the application. The networking team finds that some DNS queries return IP addresses of
unhealthy instances, resulting in the timeout error.
What should a solutions architect implement to overcome these timeout errors?

**A.** Create a Route 53 simple routing policy record for each EC2 instance. Associate a health check with each record.

**B.** Create a Route 53 failover routing policy record for each EC2 instance. Associate a health check with each record.

**C.** Create an Amazon CloudFront distribution with EC2 instances as its origin. Associate a health check with the EC2 instances.

**D.** Create an Application Load Balancer (ALB) with a health check in front of the EC2 instances. Route to the ALB from Route 53.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a web application hosted over 10 Amazon EC2 instances with traffic directed by Amazon Route 53. The company occasionally experiences a timeout error when attempting to browse the application. The networking team finds that some DNS queries return IP addresses of unhealthy instances, resulting in the timeout error.

What should a solutions architect implement to overcome these timeout errors?


**D.** Create an Application Load Balancer (ALB) with a health check in front of the EC2 instances. Route to the ALB from Route 53.

By creating an ALB and configuring health checks, the architect ensures that only healthy instances receive traffic. The ALB periodically checks the health of the EC2 instances based on the configured health check settings.

Routing traffic to the ALB from Route 53 ensures that DNS queries return the IP address of the ALB instead of individual instances. This allows the ALB to distribute traffic only to healthy instances, avoiding timeouts caused by unhealthy instances.

</details>

---

## Question 265

[Review topic](../sections/exam-revision.md) · Source PDF page 96

A solutions architect needs to design a highly available application consisting of web, application, and database tiers. HTTPS content delivery
should be as close to the edge as possible, with the least delivery time.
Which solution meets these requirements and is MOST secure?

**A.** Configure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in public subnets. Configure Amazon
CloudFront to deliver HTTPS content using the public ALB as the origin.

**B.** Configure a public Application Load Balancer with multiple redundant Amazon EC2 instances in private subnets. Configure Amazon
CloudFront to deliver HTTPS content using the EC2 instances as the origin.

**C.** Configure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in private subnets. Configure Amazon
CloudFront to deliver HTTPS content using the public ALB as the origin.

**D.** Configure a public Application Load Balancer with multiple redundant Amazon EC2 instances in public subnets. Configure Amazon
CloudFront to deliver HTTPS content using the EC2 instances as the origin.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect needs to design a highly available application consisting of web, application, and database tiers. HTTPS content delivery should be as close to the edge as possible, with the least delivery time.

Which solution meets these requirements and is MOST secure?


**C.** Configure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in private subnets. Configure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.

Public ALB in Private Subnets:

Deploy a public Application Load Balancer (ALB) in private subnets. This ensures that the ALB is not directly accessible from the internet, providing an additional layer of security.

Deploy multiple redundant Amazon EC2 instances in private subnets behind the ALB. The instances host the application and database tiers.

Configure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin. CloudFront provides content delivery close to the edge, reducing latency and improving the delivery time for end-users.

</details>

---

## Question 266

[Review topic](../sections/elb-asg.md) · Source PDF page 97

A company has a popular gaming platform running on AWS. The application is sensitive to latency because latency can impact the user
experience and introduce unfair advantages to some players. The application is deployed in every AWS Region. It runs on Amazon EC2 instances
that are part of Auto Scaling groups configured behind Application Load Balancers (ALBs). A solutions architect needs to implement a mechanism
to monitor the health of the application and redirect traffic to healthy endpoints.
Which solution meets these requirements?

**A.** Configure an accelerator in AWS Global Accelerator. Add a listener for the port that the application listens on, and attach it to a Regional
endpoint in each Region. Add the ALB as the endpoint.

**B.** Create an Amazon CloudFront distribution and specify the ALB as the origin server. Configure the cache behavior to use origin cache
headers. Use AWS Lambda functions to optimize the traffic.

**C.** Create an Amazon CloudFront distribution and specify Amazon S3 as the origin server. Configure the cache behavior to use origin cache
headers. Use AWS Lambda functions to optimize the traffic.

**D.** Configure an Amazon DynamoDB database to serve as the data store for the application. Create a DynamoDB Accelerator (DAX) cluster to
act as the in-memory cache for DynamoDB hosting the application data.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a popular gaming platform running on AWS. The application is sensitive to latency because latency can impact the user experience and introduce unfair advantages to some players. The application is deployed in every AWS Region. It runs on Amazon EC2 instances that are part of Auto Scaling groups configured behind Application Load Balancers (ALBs). A solutions architect needs to implement a mechanism to monitor the health of the application and redirect traffic to healthy endpoints.

Which solution meets these requirements?


**A.** Configure an accelerator in AWS Global Accelerator. Add a listener for the port that the application listens on, and attach it to a Regional endpoint in each Region. Add the ALB as the endpoint.

AWS Global Accelerator is designed to provide static IP addresses for global applications and direct traffic over the AWS global network to optimal AWS endpoints based on health, geography, and routing policies.
Configure an accelerator with a listener for the port that the application listens on.
Attach the listener to a Regional endpoint in each AWS Region where the application is deployed.

</details>

---

## Question 267

[Review topic](../sections/exam-revision.md) · Source PDF page 97

A company has one million users that use its mobile app. The company must analyze the data usage in near-real time. The company also must
encrypt the data in near-real time and must store the data in a centralized location in Apache Parquet format for further processing.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create an Amazon Kinesis data stream to store the data in Amazon S3. Create an Amazon Kinesis Data Analytics application to analyze the
data. Invoke an AWS Lambda function to send the data to the Kinesis Data Analytics application.

**B.** Create an Amazon Kinesis data stream to store the data in Amazon S3. Create an Amazon EMR cluster to analyze the data. Invoke an AWS
Lambda function to send the data to the EMR cluster.

**C.** Create an Amazon Kinesis Data Firehose delivery stream to store the data in Amazon S3. Create an Amazon EMR cluster to analyze the
data.

**D.** Create an Amazon Kinesis Data Firehose delivery stream to store the data in Amazon S3. Create an Amazon Kinesis Data Analytics
application to analyze the data.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has one million users that use its mobile app. The company must analyze the data usage in near-real time. The company also must encrypt the data in near-real time and must store the data in a centralized location in Apache Parquet format for further processing.

Which solution will meet these requirements with the LEAST operational overhead?


**D.** Create an Amazon Kinesis Data Firehose delivery stream to store the data in Amazon S3. Create an Amazon Kinesis Data Analytics application to analyze the data.

</details>

---

## Question 268

[Review topic](../sections/rds-aurora.md) · Source PDF page 97

A gaming company has a web application that displays scores. The application runs on Amazon EC2 instances behind an Application Load
Balancer. The application stores data in an Amazon RDS for MySQL database. Users are starting to experience long delays and interruptions that
are caused by database read performance. The company wants to improve the user experience while minimizing changes to the application’s
architecture.
What should a solutions architect do to meet these requirements?

**A.** Use Amazon ElastiCache in front of the database.

**B.** Use RDS Proxy between the application and the database.

**C.** Migrate the application from EC2 instances to AWS Lambda.

**D.** Migrate the database from Amazon RDS for MySQL to Amazon DynamoDB.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A gaming company has a web application that displays scores. The application runs on Amazon EC2 instances behind an Application Load Balancer. The application stores data in an Amazon RDS for MySQL database. Users are starting to experience long delays and interruptions that are caused by database read performance. The company wants to improve the user experience while minimizing changes to the application’s architecture.

What should a solutions architect do to meet these requirements?


**B.** Use RDS Proxy between the application and the database.

RDS Proxy is a fully managed database proxy for Amazon RDS databases, including MySQL.
It helps improve scalability and availability for database connections, reducing the impact of database connection management on the application.

</details>

---

## Question 269

[Review topic](../sections/rds-aurora.md) · Source PDF page 98

An ecommerce company has noticed performance degradation of its Amazon RDS based web application. The performance degradation is
attributed to an increase in the number of read-only SQL queries triggered by business analysts. A solutions architect needs to solve the problem
with minimal changes to the existing web application.
What should the solutions architect recommend?

**A.** Export the data to Amazon DynamoDB and have the business analysts run their queries.

**B.** Load the data into Amazon ElastiCache and have the business analysts run their queries.

**C.** Create a read replica of the primary database and have the business analysts run their queries.

**D.** Copy the data into an Amazon Redshift cluster and have the business analysts run their queries.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An ecommerce company has noticed performance degradation of its Amazon RDS based web application. The performance degradation is attributed to an increase in the number of read-only SQL queries triggered by business analysts. A solutions architect needs to solve the problem with minimal changes to the existing web application.

What should the solutions architect recommend?


**C.** Create a read replica of the primary database and have the business analysts run their queries.
Creating a read replica is a common approach to offload read-only queries from the primary database, improving overall performance.
A read replica is an asynchronous copy of the primary database that allows for read-only operations.

Read replicas can be transparently used by the web application without requiring changes to the application logic.
Business analysts can direct their read-only queries to the read replica, reducing the load on the primary database.

</details>

---

## Question 270

[Review topic](../sections/s3.md) · Source PDF page 98

A company is using a centralized AWS account to store log data in various Amazon S3 buckets. A solutions architect needs to ensure that the
data is encrypted at rest before the data is uploaded to the S3 buckets. The data also must be encrypted in transit.
Which solution meets these requirements?

**A.** Use client-side encryption to encrypt the data that is being uploaded to the S3 buckets.

**B.** Use server-side encryption to encrypt the data that is being uploaded to the S3 buckets.

**C.** Create bucket policies that require the use of server-side encryption with S3 managed encryption keys (SSE-S3) for S3 uploads.

**D.** Enable the security option to encrypt the S3 buckets through the use of a default AWS Key Management Service (AWS KMS) key.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is using a centralized AWS account to store log data in various Amazon S3 buckets. A solutions architect needs to ensure that the data is encrypted at rest before the data is uploaded to the S3 buckets. The data also must be encrypted in transit.

Which solution meets these requirements?


**A.** Use client-side encryption to encrypt the data that is being uploaded to the S3 buckets.

</details>

---

## Question 271

[Review topic](../sections/ec2.md) · Source PDF page 98

A solutions architect observes that a nightly batch processing job is automatically scaled up for 1 hour before the desired Amazon EC2 capacity is
reached. The peak capacity is the ‘same every night and the batch jobs always start at 1 AM. The solutions architect needs to find a cost-effective
solution that will allow for the desired EC2 capacity to be reached quickly and allow the Auto Scaling group to scale down after the batch jobs are
complete.
What should the solutions architect do to meet these requirements?

**A.** Increase the minimum capacity for the Auto Scaling group.

**B.** Increase the maximum capacity for the Auto Scaling group.

**C.** Configure scheduled scaling to scale up to the desired compute level.

**D.** Change the scaling policy to add more EC2 instances during each scaling operation.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect observes that a nightly batch processing job is automatically scaled up for 1 hour before the desired Amazon EC2 capacity is reached. The peak capacity is the ‘same every night and the batch jobs always start at 1 AM. The solutions architect needs to find a cost-effective solution that will allow for the desired EC2 capacity to be reached quickly and allow the Auto Scaling group to scale down after the batch jobs are complete.

What should the solutions architect do to meet these requirements?


**C.** Configure scheduled scaling to scale up to the desired compute level.

Scheduled scaling allows you to define specific times when your Auto Scaling group's desired capacity should be increased or decreased.
In this case, you can schedule the scaling action to increase the capacity just before the nightly batch processing job starts at 1 AM and then scale it down after the job completes.

</details>

---

## Question 272

[Review topic](../sections/elb-asg.md) · Source PDF page 99

A company serves a dynamic website from a fleet of Amazon EC2 instances behind an Application Load Balancer (ALB). The website needs to
support multiple languages to serve customers around the world. The website’s architecture is running in the us-west-1 Region and is exhibiting
high request latency for users that are located in other parts of the world.
The website needs to serve requests quickly and efficiently regardless of a user’s location. However, the company does not want to recreate the
existing architecture across multiple Regions.
What should a solutions architect do to meet these requirements?

**A.** Replace the existing architecture with a website that is served from an Amazon S3 bucket. Configure an Amazon CloudFront distribution
with the S3 bucket as the origin. Set the cache behavior settings to cache based on the Accept-Language request header.

**B.** Configure an Amazon CloudFront distribution with the ALB as the origin. Set the cache behavior settings to cache based on the Accept-
Language request header.

**C.** Create an Amazon API Gateway API that is integrated with the ALB. Configure the API to use the HTTP integration type. Set up an API
Gateway stage to enable the API cache based on the Accept-Language request header.

**D.** Launch an EC2 instance in each additional Region and configure NGINX to act as a cache server for that Region. Put all the EC2 instances
and the ALB behind an Amazon Route 53 record set with a geolocation routing policy.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company serves a dynamic website from a fleet of Amazon EC2 instances behind an Application Load Balancer (ALB). The website needs to support multiple languages to serve customers around the world. The website’s architecture is running in the us-west-1 Region and is exhibiting high request latency for users that are located in other parts of the world.

The website needs to serve requests quickly and efficiently regardless of a user’s location. However, the company does not want to recreate the existing architecture across multiple Regions.

What should a solutions architect do to meet these requirements?


**B.** Configure an Amazon CloudFront distribution with the ALB as the origin. Set the cache behavior settings to cache based on the Accept-Language request header.

</details>

---

## Question 273

[Review topic](../sections/cloud-foundations.md) · Source PDF page 99

A rapidly growing ecommerce company is running its workloads in a single AWS Region. A solutions architect must create a disaster recovery
(DR) strategy that includes a different AWS Region. The company wants its database to be up to date in the DR Region with the least possible
latency. The remaining infrastructure in the DR Region needs to run at reduced capacity and must be able to scale up if necessary.
Which solution will meet these requirements with the LOWEST recovery time objective (RTO)?

**A.** Use an Amazon Aurora global database with a pilot light deployment.

**B.** Use an Amazon Aurora global database with a warm standby deployment.

**C.** Use an Amazon RDS Multi-AZ DB instance with a pilot light deployment.

**D.** Use an Amazon RDS Multi-AZ DB instance with a warm standby deployment.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

273Topic 1
A rapidly growing ecommerce company is running its workloads in a single AWS Region. A solutions architect must create a disaster recovery (DR) strategy that includes a different AWS Region. The company wants its database to be up to date in the DR Region with the least possible latency. The remaining infrastructure in the DR Region needs to run at reduced capacity and must be able to scale up if necessary.

Which solution will meet these requirements with the LOWEST recovery time objective (RTO)?


**B.** Use an Amazon Aurora global database with a warm standby deployment.

Amazon Aurora supports a global database feature that allows you to create read replicas in multiple AWS Regions.
In a warm standby deployment, you can have a read replica in the DR Region that stays warm, meaning it is ready to take over in case of a failover.

</details>

---

## Question 274

[Review topic](../sections/disaster-recovery.md) · Source PDF page 99

A company runs an application on Amazon EC2 instances. The company needs to implement a disaster recovery (DR) solution for the application.
The DR solution needs to have a recovery time objective (RTO) of less than 4 hours. The DR solution also needs to use the fewest possible AWS
resources during normal operations.
Which solution will meet these requirements in the MOST operationally efficient way?

**A.** Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure
deployment in the secondary Region by using AWS Lambda and custom scripts.

**B.** Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure
deployment in the secondary Region by using AWS CloudFormation.

**C.** Launch EC2 instances in a secondary AWS Region. Keep the EC2 instances in the secondary Region active at all times.

**D.** Launch EC2 instances in a secondary Availability Zone. Keep the EC2 instances in the secondary Availability Zone active at all times.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs an application on Amazon EC2 instances. The company needs to implement a disaster recovery (DR) solution for the application. The DR solution needs to have a recovery time objective (RTO) of less than 4 hours. The DR solution also needs to use the fewest possible AWS resources during normal operations.

Which solution will meet these requirements in the MOST operationally efficient way?


**B.** Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure deployment in the secondary Region by using AWS CloudFormation.

By creating Amazon Machine Images (AMIs) to back up the EC2 instances and copying them to a secondary AWS Region, the company can ensure that they have a reliable backup in the event of a disaster. By using AWS CloudFormation to automate infrastructure deployment in the secondary Region, the company can minimize the amount of time and effort required to set up the DR solution.

</details>

---

## Question 275

[Review topic](../sections/elb-asg.md) · Source PDF page 100

A company runs an internal browser-based application. The application runs on Amazon EC2 instances behind an Application Load Balancer. The
instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. The Auto Scaling group scales up to 20 instances during
work hours, but scales down to 2 instances overnight. Staff are complaining that the application is very slow when the day begins, although it runs
well by mid-morning.
How should the scaling be changed to address the staff complaints and keep costs to a minimum?

**A.** Implement a scheduled action that sets the desired capacity to 20 shortly before the office opens.

**B.** Implement a step scaling action triggered at a lower CPU threshold, and decrease the cooldown period.

**C.** Implement a target tracking action triggered at a lower CPU threshold, and decrease the cooldown period.

**D.** Implement a scheduled action that sets the minimum and maximum capacity to 20 shortly before the office opens.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs an internal browser-based application. The application runs on Amazon EC2 instances behind an Application Load Balancer. The instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. The Auto Scaling group scales up to 20 instances during work hours, but scales down to 2 instances overnight. Staff are complaining that the application is very slow when the day begins, although it runs well by mid-morning.

How should the scaling be changed to address the staff complaints and keep costs to a minimum?


**C.** Implement a target tracking action triggered at a lower CPU threshold, and decrease the cooldown period.

</details>

---

## Question 276

[Review topic](../sections/elb-asg.md) · Source PDF page 100

A company has a multi-tier application deployed on several Amazon EC2 instances in an Auto Scaling group. An Amazon RDS for Oracle instance
is the application’ s data layer that uses Oracle-specific PL/SQL functions. Traffic to the application has been steadily increasing. This is causing
the EC2 instances to become overloaded and the RDS instance to run out of storage. The Auto Scaling group does not have any scaling metrics
and defines the minimum healthy instance count only. The company predicts that traffic will continue to increase at a steady but unpredictable
rate before leveling off.
What should a solutions architect do to ensure the system can automatically scale for the increased traffic? (Choose two.)

**A.** Configure storage Auto Scaling on the RDS for Oracle instance.

**B.** Migrate the database to Amazon Aurora to use Auto Scaling storage.

**C.** Configure an alarm on the RDS for Oracle instance for low free storage space.

**D.** Configure the Auto Scaling group to use the average CPU as the scaling metric.

**E.** Configure the Auto Scaling group to use the average free memory as the scaling metric.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a multi-tier application deployed on several Amazon EC2 instances in an Auto Scaling group. An Amazon RDS for Oracle instance is the application’ s data layer that uses Oracle-specific PL/SQL functions. Traffic to the application has been steadily increasing. This is causing the EC2 instances to become overloaded and the RDS instance to run out of storage. The Auto Scaling group does not have any scaling metrics and defines the minimum healthy instance count only. The company predicts that traffic will continue to increase at a steady but unpredictable rate before leveling off.

What should a solutions architect do to ensure the system can automatically scale for the increased traffic? (Choose two.)


**A.** Configure storage Auto Scaling on the RDS for Oracle instance.

This option allows the RDS instance to automatically scale its storage based on the actual storage usage, ensuring that you don't run out of storage.


**D.** Configure the Auto Scaling group to use the average CPU as the scaling metric.

By using CPU utilization as a scaling metric, the Auto Scaling group can dynamically adjust the number of EC2 instances based on the application's demand. This helps in handling increased traffic and preventing overload on existing instances.

</details>

---

## Question 277

[Review topic](../sections/ec2-storage.md) · Source PDF page 100

A company provides an online service for posting video content and transcoding it for use by any mobile platform. The application architecture
uses Amazon Elastic File System (Amazon EFS) Standard to collect and store the videos so that multiple Amazon EC2 Linux instances can access
the video content for processing. As the popularity of the service has grown over time, the storage costs have become too expensive.
Which storage solution is MOST cost-effective?

**A.** Use AWS Storage Gateway for files to store and process the video content.

**B.** Use AWS Storage Gateway for volumes to store and process the video content.

**C.** Use Amazon EFS for storing the video content. Once processing is complete, transfer the files to Amazon Elastic Block Store (Amazon
EBS).

**D.** Use Amazon S3 for storing the video content. Move the files temporarily over to an Amazon Elastic Block Store (Amazon EBS) volume
attached to the server for processing.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company provides an online service for posting video content and transcoding it for use by any mobile platform. The application architecture uses Amazon Elastic File System (Amazon EFS) Standard to collect and store the videos so that multiple Amazon EC2 Linux instances can access the video content for processing. As the popularity of the service has grown over time, the storage costs have become too expensive.

Which storage solution is MOST cost-effective?


**D.** Use Amazon S3 for storing the video content. Move the files temporarily over to an Amazon Elastic Block Store (Amazon EBS) volume attached to the server for processing.

Amazon S3 is a highly durable, scalable, and cost-effective object storage service.
It is well-suited for storing large amounts of video content at a lower cost compared to Amazon EFS.

</details>

---

## Question 278

[Review topic](../sections/exam-revision.md) · Source PDF page 101

A company wants to create an application to store employee data in a hierarchical structured relationship. The company needs a minimum-latency
response to high-traffic queries for the employee data and must protect any sensitive data. The company also needs to receive monthly email
messages if any financial information is present in the employee data.
Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)

**A.** Use Amazon Redshift to store the employee data in hierarchies. Unload the data to Amazon S3 every month.

**B.** Use Amazon DynamoDB to store the employee data in hierarchies. Export the data to Amazon S3 every month.

**C.** Configure Amazon Macie for the AWS account. Integrate Macie with Amazon EventBridge to send monthly events to AWS Lambda.

**D.** Use Amazon Athena to analyze the employee data in Amazon S3. Integrate Athena with Amazon QuickSight to publish analysis dashboards
and share the dashboards with users.

**E.** Configure Amazon Macie for the AWS account. Integrate Macie with Amazon EventBridge to send monthly notifications through an Amazon
Simple Notification Service (Amazon SNS) subscription.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to create an application to store employee data in a hierarchical structured relationship. The company needs a minimum-latency response to high-traffic queries for the employee data and must protect any sensitive data. The company also needs to receive monthly email messages if any financial information is present in the employee data.

Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)


**B.** Use Amazon DynamoDB to store the employee data in hierarchies. Export the data to Amazon S3 every month.


**E.** Configure Amazon Macie for the AWS account. Integrate Macie with Amazon EventBridge to send monthly notifications through an Amazon Simple Notification Service (Amazon SNS) subscription.

Amazon DynamoDB is a highly scalable, low-latency NoSQL database that can efficiently store hierarchical data.
Exporting the data to Amazon S3 every month allows further analysis and integration with other AWS services.

Amazon Macie is a security service that automatically discovers, classifies, and protects sensitive data.
Integrating Macie with EventBridge allows you to set up monthly events and send notifications through Amazon SNS if financial information is detected.

</details>

---

## Question 279

[Review topic](../sections/dynamodb-caching.md) · Source PDF page 101

A company has an application that is backed by an Amazon DynamoDB table. The company’s compliance requirements specify that database
backups must be taken every month, must be available for 6 months, and must be retained for 7 years.
Which solution will meet these requirements?

**A.** Create an AWS Backup plan to back up the DynamoDB table on the first day of each month. Specify a lifecycle policy that transitions the
backup to cold storage after 6 months. Set the retention period for each backup to 7 years.

**B.** Create a DynamoDB on-demand backup of the DynamoDB table on the first day of each month. Transition the backup to Amazon S3 Glacier
Flexible Retrieval after 6 months. Create an S3 Lifecycle policy to delete backups that are older than 7 years.

**C.** Use the AWS SDK to develop a script that creates an on-demand backup of the DynamoDB table. Set up an Amazon EventBridge rule that
runs the script on the first day of each month. Create a second script that will run on the second day of each month to transition DynamoDB
backups that are older than 6 months to cold storage and to delete backups that are older than 7 years.

**D.** Use the AWS CLI to create an on-demand backup of the DynamoDB table. Set up an Amazon EventBridge rule that runs the command on the
first day of each month with a cron expression. Specify in the command to transition the backups to cold storage after 6 months and to delete
the backups after 7 years.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an application that is backed by an Amazon DynamoDB table. The company’s compliance requirements specify that database backups must be taken every month, must be available for 6 months, and must be retained for 7 years.

Which solution will meet these requirements?


**A.** Create an AWS Backup plan to back up the DynamoDB table on the first day of each month. Specify a lifecycle policy that transitions the backup to cold storage after 6 months. Set the retention period for each backup to 7 years.

 AWS Backup will automatically take full backups of the DynamoDB table on the schedule defined in the backup plan (the first of each month).
The lifecycle policy can transition backups to cold storage after 6 months, meeting that requirement.
Setting a 7-year retention period in the backup plan will ensure each backup is retained for 7 years as required.
AWS Backup manages the backup jobs and lifecycle policies, requiring no custom scripting or management.

</details>

---

## Question 280

[Review topic](../sections/global-delivery.md) · Source PDF page 101

A company is using Amazon CloudFront with its website. The company has enabled logging on the CloudFront distribution, and logs are saved in
one of the company’s Amazon S3 buckets. The company needs to perform advanced analyses on the logs and build visualizations.
What should a solutions architect do to meet these requirements?

**A.** Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with AWS Glue.

**B.** Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.

**C.** Use standard SQL queries in Amazon DynamoDB to analyze the CloudFront logs in the S3 bucket. Visualize the results with AWS Glue.

**D.** Use standard SQL queries in Amazon DynamoDB to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon
QuickSight.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is using Amazon CloudFront with its website. The company has enabled logging on the CloudFront distribution, and logs are saved in one of the company’s Amazon S3 buckets. The company needs to perform advanced analyses on the logs and build visualizations.

What should a solutions architect do to meet these requirements? 


**B.** Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.

Amazon Athena allows you to run standard SQL queries directly on the CloudFront logs stored in the S3 bucket. This enables you to perform advanced analyses on the log data.

Once you have queried and processed the CloudFront log data using Athena, you can use Amazon QuickSight for data visualization and building visualizations.

Amazon QuickSight is a business intelligence (BI) tool that allows you to create interactive dashboards and visualizations from various data sources, including the results of Athena queries.

</details>

---

## Question 281

[Review topic](../sections/rds-aurora.md) · Source PDF page 102

A company runs a fleet of web servers using an Amazon RDS for PostgreSQL DB instance. After a routine compliance check, the company sets a
standard that requires a recovery point objective (RPO) of less than 1 second for all its production databases.
Which solution meets these requirements?

**A.** Enable a Multi-AZ deployment for the DB instance.

**B.** Enable auto scaling for the DB instance in one Availability Zone.

**C.** Configure the DB instance in one Availability Zone, and create multiple read replicas in a separate Availability Zone.

**D.** Configure the DB instance in one Availability Zone, and configure AWS Database Migration Service (AWS DMS) change data capture (CDC)
tasks.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a fleet of web servers using an Amazon RDS for PostgreSQL DB instance. After a routine compliance check, the company sets a standard that requires a recovery point objective (RPO) of less than 1 second for all its production databases.

Which solution meets these requirements?


**A.** Enable a Multi-AZ deployment for the DB instance.

A Multi-AZ (Availability Zone) deployment for Amazon RDS provides high availability and failover support for DB instances. In a Multi-AZ deployment, Amazon RDS automatically provisions and maintains a synchronous standby replica in a different Availability Zone.

</details>

---

## Question 282

[Review topic](../sections/ec2.md) · Source PDF page 102

A company runs a web application that is deployed on Amazon EC2 instances in the private subnet of a VPC. An Application Load Balancer (ALB)
that extends across the public subnets directs web traffic to the EC2 instances. The company wants to implement new security measures to
restrict inbound traffic from the ALB to the EC2 instances while preventing access from any other source inside or outside the private subnet of
the EC2 instances.
Which solution will meet these requirements?

**A.** Configure a route in a route table to direct traffic from the internet to the private IP addresses of the EC2 instances.

**B.** Configure the security group for the EC2 instances to only allow traffic that comes from the security group for the ALB.

**C.** Move the EC2 instances into the public subnet. Give the EC2 instances a set of Elastic IP addresses.

**D.** Configure the security group for the ALB to allow any TCP traffic on any port.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a web application that is deployed on Amazon EC2 instances in the private subnet of a VPC. An Application Load Balancer (ALB) that extends across the public subnets directs web traffic to the EC2 instances. The company wants to implement new security measures to restrict inbound traffic from the ALB to the EC2 instances while preventing access from any other source inside or outside the private subnet of the EC2 instances.

Which solution will meet these requirements?


**B.** Configure the security group for the EC2 instances to only allow traffic that comes from the security group for the ALB.

Security groups act as virtual firewalls for EC2 instances. By configuring the security group for the EC2 instances to only allow traffic from the security group associated with the ALB, you can control and restrict inbound traffic effectively.

When you specify a security group as the source in the inbound rules of another security group, you allow traffic only from instances that are members of that source security group. In this case, you can allow traffic only from the ALB, ensuring that traffic is restricted to the necessary source.

</details>

---

## Question 283

[Review topic](../sections/ec2-storage.md) · Source PDF page 102

A research company runs experiments that are powered by a simulation application and a visualization application. The simulation application
runs on Linux and outputs intermediate data to an NFS share every 5 minutes. The visualization application is a Windows desktop application that
displays the simulation output and requires an SMB file system.
The company maintains two synchronized file systems. This strategy is causing data duplication and inefficient resource usage. The company
needs to migrate the applications to AWS without making code changes to either application.
Which solution will meet these requirements?

**A.** Migrate both applications to AWS Lambda. Create an Amazon S3 bucket to exchange data between the applications.

**B.** Migrate both applications to Amazon Elastic Container Service (Amazon ECS). Configure Amazon FSx File Gateway for storage.

**C.** Migrate the simulation application to Linux Amazon EC2 instances. Migrate the visualization application to Windows EC2 instances.
Configure Amazon Simple Queue Service (Amazon SQS) to exchange data between the applications.

**D.** Migrate the simulation application to Linux Amazon EC2 instances. Migrate the visualization application to Windows EC2 instances.
Configure Amazon FSx for NetApp ONTAP for storage.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: D**

FSx for NetApp ONTAP supports NFS and SMB access, avoiding duplicate file systems. Configure multiprotocol permissions appropriately.

</details>

---

## Question 284

[Review topic](../sections/exam-revision.md) · Source PDF page 103

As part of budget planning, management wants a report of AWS billed items listed by user. The data will be used to create department budgets. A
solutions architect needs to determine the most efficient way to obtain this report information.
Which solution meets these requirements?

**A.** Run a query with Amazon Athena to generate the report.

**B.** Create a report in Cost Explorer and download the report.

**C.** Access the bill details from the billing dashboard and download the bill.

**D.** Modify a cost budget in AWS Budgets to alert with Amazon Simple Email Service (Amazon SES).

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

As part of budget planning, management wants a report of AWS billed items listed by user. The data will be used to create department budgets. A solutions architect needs to determine the most efficient way to obtain this report information.

Which solution meets these requirements?


**B.** Create a report in Cost Explorer and download the report.

AWS Cost Explorer is a tool that allows you to visualize, understand, and manage your AWS costs and usage over time. It provides various pre-built reports and the ability to customize and filter reports based on different dimensions.

Option B, creating a report in Cost Explorer and downloading the report, is a suitable solution for obtaining detailed billed items listed by user. The report can be customized to include data relevant to user costs, and the downloadable report can be used for budget planning.

</details>

---

## Question 285

[Review topic](../sections/s3.md) · Source PDF page 103

A company hosts its static website by using Amazon S3. The company wants to add a contact form to its webpage. The contact form will have
dynamic server-side components for users to input their name, email address, phone number, and user message. The company anticipates that
there will be fewer than 100 site visits each month.
Which solution will meet these requirements MOST cost-effectively?

**A.** Host a dynamic contact form page in Amazon Elastic Container Service (Amazon ECS). Set up Amazon Simple Email Service (Amazon SES)
to connect to any third-party email provider.

**B.** Create an Amazon API Gateway endpoint with an AWS Lambda backend that makes a call to Amazon Simple Email Service (Amazon SES).

**C.** Convert the static webpage to dynamic by deploying Amazon Lightsail. Use client-side scripting to build the contact form. Integrate the
form with Amazon WorkMail.

**D.** Create a t2.micro Amazon EC2 instance. Deploy a LAMP (Linux, Apache, MySQL, PHP/Perl/Python) stack to host the webpage. Use client-
side scripting to build the contact form. Integrate the form with Amazon WorkMail.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company hosts its static website by using Amazon S3. The company wants to add a contact form to its webpage. The contact form will have dynamic server-side components for users to input their name, email address, phone number, and user message. The company anticipates that there will be fewer than 100 site visits each month.

Which solution will meet these requirements MOST cost-effectively?



**B.** Create an Amazon API Gateway endpoint with an AWS Lambda backend that makes a call to Amazon Simple Email Service (Amazon SES).

Amazon API Gateway: Acts as the endpoint for the contact form. It enables you to create, publish, maintain, monitor, and secure APIs at any scale.
AWS Lambda: Serves as the backend for handling the dynamic components of the contact form. Lambda allows you to run code without provisioning or managing servers.
Amazon Simple Email Service (Amazon SES): Can be used to send emails, making it suitable for handling the form submissions.
This serverless architecture eliminates the need for managing and maintaining infrastructure, and costs are based on actual usage, making it cost-effective for low-traffic scenarios.

</details>

---

## Question 286

[Review topic](../sections/s3.md) · Source PDF page 103

A company has a static website that is hosted on Amazon CloudFront in front of Amazon S3. The static website uses a database backend. The
company notices that the website does not reflect updates that have been made in the website’s Git repository. The company checks the
continuous integration and continuous delivery (CI/CD) pipeline between the Git repository and Amazon S3. The company verifies that the
webhooks are configured properly and that the CI/CD pipeline is sending messages that indicate successful deployments.
A solutions architect needs to implement a solution that displays the updates on the website.
Which solution will meet these requirements?

**A.** Add an Application Load Balancer.

**B.** Add Amazon ElastiCache for Redis or Memcached to the database layer of the web application.

**C.** Invalidate the CloudFront cache.

**D.** Use AWS Certificate Manager (ACM) to validate the website’s SSL certificate.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a static website that is hosted on Amazon CloudFront in front of Amazon S3. The static website uses a database backend. The company notices that the website does not reflect updates that have been made in the website’s Git repository. The company checks the continuous integration and continuous delivery (CI/CD) pipeline between the Git repository and Amazon S3. The company verifies that the webhooks are configured properly and that the CI/CD pipeline is sending messages that indicate successful deployments.

A solutions architect needs to implement a solution that displays the updates on the website.

Which solution will meet these requirements?


**C.** Invalidate the CloudFront cache.

When the website does not reflect updates that have been made in the Git repository, and the CI/CD pipeline is sending messages indicating successful deployments, it's likely that the issue is related to caching. Amazon CloudFront caches content to improve performance and reduce latency, and if the cache is not updated, it may serve stale content.

By invalidating the CloudFront cache, you ensure that the next request to CloudFront fetches the latest content from the origin (in this case, Amazon S3). This process forces CloudFront to re-fetch the content and update its cache.

</details>

---

## Question 287

[Review topic](../sections/exam-revision.md) · Source PDF page 104

A company wants to migrate a Windows-based application from on premises to the AWS Cloud. The application has three tiers: an application tier,
a business tier, and a database tier with Microsoft SQL Server. The company wants to use specific features of SQL Server such as native backups
and Data Quality Services. The company also needs to share files for processing between the tiers.
How should a solutions architect design the architecture to meet these requirements?

**A.** Host all three tiers on Amazon EC2 instances. Use Amazon FSx File Gateway for file sharing between the tiers.

**B.** Host all three tiers on Amazon EC2 instances. Use Amazon FSx for Windows File Server for file sharing between the tiers.

**C.** Host the application tier and the business tier on Amazon EC2 instances. Host the database tier on Amazon RDS. Use Amazon Elastic File
System (Amazon EFS) for file sharing between the tiers.

**D.** Host the application tier and the business tier on Amazon EC2 instances. Host the database tier on Amazon RDS. Use a Provisioned IOPS
SSD (io2) Amazon Elastic Block Store (Amazon EBS) volume for file sharing between the tiers.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to migrate a Windows-based application from on premises to the AWS Cloud. The application has three tiers: an application tier, a business tier, and a database tier with Microsoft SQL Server. The company wants to use specific features of SQL Server such as native backups and Data Quality Services. The company also needs to share files for processing between the tiers.

How should a solutions architect design the architecture to meet these requirements?


**B.** Host all three tiers on Amazon EC2 instances. Use Amazon FSx for Windows File Server for file sharing between the tiers.

 hosting all three tiers on Amazon EC2 instances allows you to have flexibility and control over the entire application architecture. To address the file-sharing requirement between the tiers, you can use Amazon FSx for Windows File Server.

Amazon FSx for Windows File Server is a fully managed Windows file system that is accessible from Windows-based instances over the Server Message Block (SMB) protocol. It supports the specific features of Windows File Server, including features like native backups and access to Windows-specific services.

</details>

---

## Question 288

[Review topic](../sections/exam-revision.md) · Source PDF page 104

A company is migrating a Linux-based web server group to AWS. The web servers must access files in a shared file store for some content. The
company must not make any changes to the application.
What should a solutions architect do to meet these requirements?

**A.** Create an Amazon S3 Standard bucket with access to the web servers.

**B.** Configure an Amazon CloudFront distribution with an Amazon S3 bucket as the origin.

**C.** Create an Amazon Elastic File System (Amazon EFS) file system. Mount the EFS file system on all web servers.

**D.** Configure a General Purpose SSD (gp3) Amazon Elastic Block Store (Amazon EBS) volume. Mount the EBS volume to all web servers.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is migrating a Linux-based web server group to AWS. The web servers must access files in a shared file store for some content. The company must not make any changes to the application.

What should a solutions architect do to meet these requirements?


**C.** Create an Amazon Elastic File System (Amazon EFS) file system. Mount the EFS file system on all web servers.

To meet the requirement of providing a shared file store for Linux-based web servers without making changes to the application, you can use Amazon Elastic File System (Amazon EFS). Amazon EFS is a scalable and fully managed file storage service that can be easily mounted on multiple EC2 instances.

</details>

---

## Question 289

[Review topic](../sections/s3.md) · Source PDF page 104

A company has an AWS Lambda function that needs read access to an Amazon S3 bucket that is located in the same AWS account.
Which solution will meet these requirements in the MOST secure manner?

**A.** Apply an S3 bucket policy that grants read access to the S3 bucket.

**B.** Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to the S3 bucket.

**C.** Embed an access key and a secret key in the Lambda function’s code to grant the required IAM permissions for read access to the S3
bucket.

**D.** Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to all S3 buckets in the account.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an AWS Lambda function that needs read access to an Amazon S3 bucket that is located in the same AWS account.

Which solution will meet these requirements in the MOST secure manner?


**B.** Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to the S3 bucket.

An IAM role provides temporary credentials to the Lambda function to access AWS resources. The function does not have persistent credentials.
The IAM policy grants least privilege access by specifying read access only to the specific S3 bucket needed. Access is not granted to all S3 buckets.
If the Lambda function is compromised, the attacker would only gain access to the one specified S3 bucket. They would not receive broad access to resources.

</details>

---

## Question 290

[Review topic](../sections/ec2.md) · Source PDF page 105

A company hosts a web application on multiple Amazon EC2 instances. The EC2 instances are in an Auto Scaling group that scales in response to
user demand. The company wants to optimize cost savings without making a long-term commitment.
Which EC2 instance purchasing option should a solutions architect recommend to meet these requirements?

**A.** Dedicated Instances only

**B.** On-Demand Instances only

**C.** A mix of On-Demand Instances and Spot Instances

**D.** A mix of On-Demand Instances and Reserved Instances

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company hosts a web application on multiple Amazon EC2 instances. The EC2 instances are in an Auto Scaling group that scales in response to user demand. The company wants to optimize cost savings without making a long-term commitment.

Which EC2 instance purchasing option should a solutions architect recommend to meet these requirements?


**C.** A mix of On-Demand Instances and Spot Instances

On-Demand Instances: These instances are charged per hour or per second of usage, without any upfront payment or long-term commitment. While they offer flexibility, they are usually more expensive compared to other purchasing options.

Spot Instances: These are spare compute capacity in the AWS cloud available at a lower price compared to On-Demand Instances. However, they can be terminated by AWS with little notice if the capacity is needed elsewhere. Spot Instances are suitable for workloads that are fault-tolerant and can handle interruptions.

</details>

---

## Question 291

[Review topic](../sections/s3.md) · Source PDF page 105

A media company uses Amazon CloudFront for its publicly available streaming video content. The company wants to secure the video content
that is hosted in Amazon S3 by controlling who has access. Some of the company’s users are using a custom HTTP client that does not support
cookies. Some of the company’s users are unable to change the hardcoded URLs that they are using for access.
Which services or methods will meet these requirements with the LEAST impact to the users? (Choose two.)

**A.** Signed cookies

**B.** Signed URLs

**C.** AWS AppSync

**D.** JSON Web Token (JWT)

**E.** AWS Secrets Manager

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A media company uses Amazon CloudFront for its publicly available streaming video content. The company wants to secure the video content that is hosted in Amazon S3 by controlling who has access. Some of the company’s users are using a custom HTTP client that does not support cookies. Some of the company’s users are unable to change the hardcoded URLs that they are using for access.

Which services or methods will meet these requirements with the LEAST impact to the users? (Choose two.)


**A.** Signed cookies

**B.** Signed URLs

</details>

---

## Question 292

[Review topic](../sections/s3.md) · Source PDF page 105

A company is preparing a new data platform that will ingest real-time streaming data from multiple sources. The company needs to transform the
data before writing the data to Amazon S3. The company needs the ability to use SQL to query the transformed data.
Which solutions will meet these requirements? (Choose two.)

**A.** Use Amazon Kinesis Data Streams to stream the data. Use Amazon Kinesis Data Analytics to transform the data. Use Amazon Kinesis Data
Firehose to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.

**B.** Use Amazon Managed Streaming for Apache Kafka (Amazon MSK) to stream the data. Use AWS Glue to transform the data and to write the
data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.

**C.** Use AWS Database Migration Service (AWS DMS) to ingest the data. Use Amazon EMR to transform the data and to write the data to
Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.

**D.** Use Amazon Managed Streaming for Apache Kafka (Amazon MSK) to stream the data. Use Amazon Kinesis Data Analytics to transform the
data and to write the data to Amazon S3. Use the Amazon RDS query editor to query the transformed data from Amazon S3.

**E.** Use Amazon Kinesis Data Streams to stream the data. Use AWS Glue to transform the data. Use Amazon Kinesis Data Firehose to write the
data to Amazon S3. Use the Amazon RDS query editor to query the transformed data from Amazon S3.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is preparing a new data platform that will ingest real-time streaming data from multiple sources. The company needs to transform the data before writing the data to Amazon S3. The company needs the ability to use SQL to query the transformed data.

Which solutions will meet these requirements? (Choose two.)


**A.** Use Amazon Kinesis Data Streams to stream the data. Use Amazon Kinesis Data Analytics to transform the data. Use Amazon Kinesis Data Firehose to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.

**B.** Use Amazon Managed Streaming for Apache Kafka (Amazon MSK) to stream the data. Use AWS Glue to transform the data and to write the data to Amazon S3. Use Amazon Athena to query the transformed data from Amazon S3.

Use Amazon Kinesis Data Streams to stream the data.
Use Amazon Kinesis Data Analytics to transform the data.
Use Amazon Kinesis Data Firehose to write the data to Amazon S3.
Use Amazon Athena to query the transformed data from Amazon S3.
This option uses the Kinesis suite for streaming, analytics, and Firehose for writing to S3, with Athena for querying.

Use Amazon Managed Streaming for Apache Kafka (Amazon MSK) to stream the data.
Use AWS Glue to transform the data and write the data to Amazon S3.
Use Amazon Athena to query the transformed data from Amazon S3.
This option leverages Amazon MSK for streaming, AWS Glue for transformation, and Athena for querying, providing a comprehensive solution.

</details>

---

## Question 293

[Review topic](../sections/disaster-recovery.md) · Source PDF page 106

A company has an on-premises volume backup solution that has reached its end of life. The company wants to use AWS as part of a new backup
solution and wants to maintain local access to all the data while it is backed up on AWS. The company wants to ensure that the data backed up on
AWS is automatically and securely transferred.
Which solution meets these requirements?

**A.** Use AWS Snowball to migrate data out of the on-premises solution to Amazon S3. Configure on-premises systems to mount the Snowball
S3 endpoint to provide local access to the data.

**B.** Use AWS Snowball Edge to migrate data out of the on-premises solution to Amazon S3. Use the Snowball Edge file interface to provide on-
premises systems with local access to the data.

**C.** Use AWS Storage Gateway and configure a cached volume gateway. Run the Storage Gateway software appliance on premises and
configure a percentage of data to cache locally. Mount the gateway storage volumes to provide local access to the data.

**D.** Use AWS Storage Gateway and configure a stored volume gateway. Run the Storage Gateway software appliance on premises and map the
gateway storage volumes to on-premises storage. Mount the gateway storage volumes to provide local access to the data.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an on-premises volume backup solution that has reached its end of life. The company wants to use AWS as part of a new backup solution and wants to maintain local access to all the data while it is backed up on AWS. The company wants to ensure that the data backed up on AWS is automatically and securely transferred.

Which solution meets these requirements?


**D.** Use AWS Storage Gateway and configure a stored volume gateway. Run the Storage Gateway software appliance on premises and map the gateway storage volumes to on-premises storage. Mount the gateway storage volumes to provide local access to the data.

</details>

---

## Question 294

[Review topic](../sections/s3.md) · Source PDF page 106

An application that is hosted on Amazon EC2 instances needs to access an Amazon S3 bucket. Traffic must not traverse the internet.
How should a solutions architect configure access to meet these requirements?

**A.** Create a private hosted zone by using Amazon Route 53.

**B.** Set up a gateway VPC endpoint for Amazon S3 in the VPC.

**C.** Configure the EC2 instances to use a NAT gateway to access the S3 bucket.

**D.** Establish an AWS Site-to-Site VPN connection between the VPC and the S3 bucket.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An application that is hosted on Amazon EC2 instances needs to access an Amazon S3 bucket. Traffic must not traverse the internet.

How should a solutions architect configure access to meet these requirements?


**B.** Set up a gateway VPC endpoint for Amazon S3 in the VPC.

A VPC endpoint for Amazon S3 allows you to connect your VPC directly to S3 without traversing the internet. This ensures that traffic between your EC2 instances and the S3 bucket stays within the AWS network.

</details>

---

## Question 295

[Review topic](../sections/exam-revision.md) · Source PDF page 106

An ecommerce company stores terabytes of customer data in the AWS Cloud. The data contains personally identifiable information (PII). The
company wants to use the data in three applications. Only one of the applications needs to process the PII. The PII must be removed before the
other two applications process the data.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Store the data in an Amazon DynamoDB table. Create a proxy application layer to intercept and process the data that each application
requests.

**B.** Store the data in an Amazon S3 bucket. Process and transform the data by using S3 Object Lambda before returning the data to the
requesting application.

**C.** Process the data and store the transformed data in three separate Amazon S3 buckets so that each application has its own custom
dataset. Point each application to its respective S3 bucket.

**D.** Process the data and store the transformed data in three separate Amazon DynamoDB tables so that each application has its own custom
dataset. Point each application to its respective DynamoDB table.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An ecommerce company stores terabytes of customer data in the AWS Cloud. The data contains personally identifiable information (PII). The company wants to use the data in three applications. Only one of the applications needs to process the PII. The PII must be removed before the other two applications process the data.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Store the data in an Amazon S3 bucket. Process and transform the data by using S3 Object Lambda before returning the data to the requesting application.

S3 Object Lambda allows you to add custom code to process and transform data as it is requested by applications, without having to modify the original data stored in S3.
By using S3 Object Lambda, you can process and remove the personally identifiable information (PII) on-the-fly before returning the data to the applications.
This approach minimizes operational overhead because you don't need to create separate storage (buckets or tables) for each application, and you can apply the PII removal logic dynamically as the data is requested.

</details>

---

## Question 296

[Review topic](../sections/vpc.md) · Source PDF page 107

A development team has launched a new application that is hosted on Amazon EC2 instances inside a development VPC. A solutions architect
needs to create a new VPC in the same account. The new VPC will be peered with the development VPC. The VPC CIDR block for the development
VPC is 192.168.0.0/24. The solutions architect needs to create a CIDR block for the new VPC. The CIDR block must be valid for a VPC peering
connection to the development VPC.
What is the SMALLEST CIDR block that meets these requirements?

**A.** 10.0.1.0/32

**B.** 192.168.0.0/24

**C.** 192.168.1.0/32

**D.** 10.0.1.0/24

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A development team has launched a new application that is hosted on Amazon EC2 instances inside a development VPC. A solutions architect needs to create a new VPC in the same account. The new VPC will be peered with the development VPC. The VPC CIDR block for the development VPC is 192.168.0.0/24. The solutions architect needs to create a CIDR block for the new VPC. The CIDR block must be valid for a VPC peering connection to the development VPC.

What is the SMALLEST CIDR block that meets these requirements?


**D.** 10.0.1.0/24

This is a valid CIDR block that does not overlap with the existing development VPC (192.168.0.0/24).

Therefore, this is the SMALLEST CIDR block that meets the requirements.

</details>

---

## Question 297

[Review topic](../sections/elb-asg.md) · Source PDF page 107

A company deploys an application on five Amazon EC2 instances. An Application Load Balancer (ALB) distributes traffic to the instances by using
a target group. The average CPU usage on each of the instances is below 10% most of the time, with occasional surges to 65%.
A solutions architect needs to implement a solution to automate the scalability of the application. The solution must optimize the cost of the
architecture and must ensure that the application has enough CPU resources when surges occur.
Which solution will meet these requirements?

**A.** Create an Amazon CloudWatch alarm that enters the ALARM state when the CPUUtilization metric is less than 20%. Create an AWS Lambda
function that the CloudWatch alarm invokes to terminate one of the EC2 instances in the ALB target group.

**B.** Create an EC2 Auto Scaling group. Select the existing ALB as the load balancer and the existing target group as the target group. Set a
target tracking scaling policy that is based on the ASGAverageCPUUtilization metric. Set the minimum instances to 2, the desired capacity to
3, the maximum instances to 6, and the target value to 50%. Add the EC2 instances to the Auto Scaling group.

**C.** Create an EC2 Auto Scaling group. Select the existing ALB as the load balancer and the existing target group as the target group. Set the
minimum instances to 2, the desired capacity to 3, and the maximum instances to 6. Add the EC2 instances to the Auto Scaling group.

**D.** Create two Amazon CloudWatch alarms. Configure the first CloudWatch alarm to enter the ALARM state when the average CPUUtilization
metric is below 20%. Configure the second CloudWatch alarm to enter the ALARM state when the average CPUUtilization matric is above 50%.
Configure the alarms to publish to an Amazon Simple Notification Service (Amazon SNS) topic to send an email message. After receiving the
message, log in to decrease or increase the number of EC2 instances that are running.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect needs to implement a solution to automate the scalability of the application. The solution must optimize the cost of the architecture and must ensure that the application has enough CPU resources when surges occur.

Which solution will meet these requirements?


**B.** Create an EC2 Auto Scaling group. Select the existing ALB as the load balancer and the existing target group as the target group. Set a target tracking scaling policy that is based on the ASGAverageCPUUtilization metric. Set the minimum instances to 2, the desired capacity to 3, the maximum instances to 6, and the target value to 50%. Add the EC2 instances to the Auto Scaling group.

Option B utilizes EC2 Auto Scaling, which automatically adjusts the number of EC2 instances in the Auto Scaling group based on the specified target tracking scaling policy.
By setting a target tracking scaling policy based on the ASGAverageCPUUtilization metric with a target value of 50%, the Auto Scaling group will dynamically adjust the number of instances to maintain an average CPU utilization close to the target value.
This solution provides scalability when needed, ensures that there are enough CPU resources during surges, and optimizes costs by automatically adjusting the capacity based on demand.

</details>

---

## Question 298

[Review topic](../sections/cloud-foundations.md) · Source PDF page 108

A company is running a critical business application on Amazon EC2 instances behind an Application Load Balancer. The EC2 instances run in an
Auto Scaling group and access an Amazon RDS DB instance.
The design did not pass an operational review because the EC2 instances and the DB instance are all located in a single Availability Zone. A
solutions architect must update the design to use a second Availability Zone.
Which solution will make the application highly available?

**A.** Provision a subnet in each Availability Zone. Configure the Auto Scaling group to distribute the EC2 instances across both Availability
Zones. Configure the DB instance with connections to each network.

**B.** Provision two subnets that extend across both Availability Zones. Configure the Auto Scaling group to distribute the EC2 instances across
both Availability Zones. Configure the DB instance with connections to each network.

**C.** Provision a subnet in each Availability Zone. Configure the Auto Scaling group to distribute the EC2 instances across both Availability
Zones. Configure the DB instance for Multi-AZ deployment.

**D.** Provision a subnet that extends across both Availability Zones. Configure the Auto Scaling group to distribute the EC2 instances across
both Availability Zones. Configure the DB instance for Multi-AZ deployment.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: C**

Subnets belong to one Availability Zone. Spread application instances across AZs and enable RDS Multi-AZ for database failover.

**Original companion notes (not independently verified):**

A company is running a critical business application on Amazon EC2 instances behind an Application Load Balancer. The EC2 instances run in an Auto Scaling group and access an Amazon RDS DB instance.

The design did not pass an operational review because the EC2 instances and the DB instance are all located in a single Availability Zone. A solutions architect must update the design to use a second Availability Zone.

Which solution will make the application highly available?

</details>

---

## Question 299

[Review topic](../sections/ec2.md) · Source PDF page 108

A research laboratory needs to process approximately 8 TB of data. The laboratory requires sub-millisecond latencies and a minimum throughput
of 6 GBps for the storage subsystem. Hundreds of Amazon EC2 instances that run Amazon Linux will distribute and process the data.
Which solution will meet the performance requirements?

**A.** Create an Amazon FSx for NetApp ONTAP file system. Sat each volume’ tiering policy to ALL. Import the raw data into the file system.
Mount the fila system on the EC2 instances.

**B.** Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre file system that uses persistent SSD storage. Select
the option to import data from and export data to Amazon S3. Mount the file system on the EC2 instances.

**C.** Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre file system that uses persistent HDD storage. Select
the option to import data from and export data to Amazon S3. Mount the file system on the EC2 instances.

**D.** Create an Amazon FSx for NetApp ONTAP file system. Set each volume’s tiering policy to NONE. Import the raw data into the file system.
Mount the file system on the EC2 instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A research laboratory needs to process approximately 8 TB of data. The laboratory requires sub-millisecond latencies and a minimum throughput of 6 GBps for the storage subsystem. Hundreds of Amazon EC2 instances that run Amazon Linux will distribute and process the data.

Which solution will meet the performance requirements?


**B.** Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre file system that uses persistent SSD storage. Select the option to import data from and export data to Amazon S3. Mount the file system on the EC2 instances.
Amazon FSx for Lustre is a high-performance file system designed for use with compute-intensive workloads. It provides sub-millisecond latencies and is well-suited for scenarios where high throughput is required.
Using persistent SSD storage for the Amazon FSx for Lustre file system ensures that it meets the minimum throughput requirement of 6 GBps.
Storing the raw data in an Amazon S3 bucket allows for scalable and durable storage, and the integration with FSx for Lustre allows seamless importing and exporting of data to and from S3.
This solution is designed to provide the required performance characteristics for processing large amounts of data with hundreds of EC2 instances.

</details>

---

## Question 300

[Review topic](../sections/cost-governance.md) · Source PDF page 108

A company needs to migrate a legacy application from an on-premises data center to the AWS Cloud because of hardware capacity constraints.
The application runs 24 hours a day, 7 days a week. The application’s database storage continues to grow over time.
What should a solutions architect do to meet these requirements MOST cost-effectively?

**A.** Migrate the application layer to Amazon EC2 Spot Instances. Migrate the data storage layer to Amazon S3.

**B.** Migrate the application layer to Amazon EC2 Reserved Instances. Migrate the data storage layer to Amazon RDS On-Demand Instances.

**C.** Migrate the application layer to Amazon EC2 Reserved Instances. Migrate the data storage layer to Amazon Aurora Reserved Instances.

**D.** Migrate the application layer to Amazon EC2 On-Demand Instances. Migrate the data storage layer to Amazon RDS Reserved Instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs to migrate a legacy application from an on-premises data center to the AWS Cloud because of hardware capacity constraints. The application runs 24 hours a day, 7 days a week. The application’s database storage continues to grow over time.

What should a solutions architect do to meet these requirements MOST cost-effectively?


**C.** Migrate the application layer to Amazon EC2 Reserved Instances. Migrate the data storage layer to Amazon Aurora Reserved Instances.

Using Amazon EC2 Reserved Instances for the application layer provides cost savings compared to On-Demand Instances while ensuring availability for the 24/7 runtime.
Migrating the data storage layer to Amazon Aurora Reserved Instances provides a fully managed relational database service with automatic scaling capabilities. Amazon Aurora is designed for high performance and cost efficiency.
Reserved Instances provide cost savings compared to On-Demand Instances over an extended period, making them suitable for applications with continuous operation.
Amazon Aurora, being a fully managed service, offloads much of the operational overhead associated with managing a traditional database, making it a cost-effective choice for growing database storage.

=====================================================================================================

</details>

---

