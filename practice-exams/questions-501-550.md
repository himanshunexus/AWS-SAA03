# Practice questions 501-550

[Home](../README.md) · [All sets](README.md)

Answer notes are source-provided unless labeled suggested. These sets preserve the supplied PDF; they are not official AWS exams.

## Question 501

[Review topic](../sections/s3.md) · Source PDF page 184

A company wants to ingest customer payment data into the company's data lake in Amazon S3. The company receives payment data every minute
on average. The company wants to analyze the payment data in real time. Then the company wants to ingest the data into the data lake.
Which solution will meet these requirements with the MOST operational efficiency?

**A.** Use Amazon Kinesis Data Streams to ingest data. Use AWS Lambda to analyze the data in real time.

**B.** Use AWS Glue to ingest data. Use Amazon Kinesis Data Analytics to analyze the data in real time.

**C.** Use Amazon Kinesis Data Firehose to ingest data. Use Amazon Kinesis Data Analytics to analyze the data in real time.

**D.** Use Amazon API Gateway to ingest data. Use AWS Lambda to analyze the data in real time.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to ingest customer payment data into the company's data lake in Amazon S3. The company receives payment data every minute on average. The company wants to analyze the payment data in real time. Then the company wants to ingest the data into the data lake.

Which solution will meet these requirements with the MOST operational efficiency?


**C.** Use Amazon Kinesis Data Firehose to ingest data. Use Amazon Kinesis Data Analytics to analyze the data in real time.

Amazon Kinesis Data Firehose:

It is a fully managed service that can reliably load streaming data into data lakes, data stores, and analytics tools.
It can automatically scale to handle varying data throughput.
It simplifies the data delivery process, making it easy to ingest data into Amazon S3.

Amazon Kinesis Data Analytics:

It enables you to analyze streaming data in real-time with SQL queries.
It integrates seamlessly with other AWS services, including Kinesis Data Firehose.
It provides the capability to perform real-time analytics on the streaming data before storing it in Amazon S3.

</details>

---

## Question 502

[Review topic](../sections/ec2.md) · Source PDF page 185

A company runs a website that uses a content management system (CMS) on Amazon EC2. The CMS runs on a single EC2 instance and uses an
Amazon Aurora MySQL Multi-AZ DB instance for the data tier. Website images are stored on an Amazon Elastic Block Store (Amazon EBS) volume
that is mounted inside the EC2 instance.
Which combination of actions should a solutions architect take to improve the performance and resilience of the website? (Choose two.)

**A.** Move the website images into an Amazon S3 bucket that is mounted on every EC2 instance

**B.** Share the website images by using an NFS share from the primary EC2 instance. Mount this share on the other EC2 instances.

**C.** Move the website images onto an Amazon Elastic File System (Amazon EFS) file system that is mounted on every EC2 instance.

**D.** Create an Amazon Machine Image (AMI) from the existing EC2 instance. Use the AMI to provision new instances behind an Application
Load Balancer as part of an Auto Scaling group. Configure the Auto Scaling group to maintain a minimum of two instances. Configure an
accelerator in AWS Global Accelerator for the website

**E.** Create an Amazon Machine Image (AMI) from the existing EC2 instance. Use the AMI to provision new instances behind an Application
Load Balancer as part of an Auto Scaling group. Configure the Auto Scaling group to maintain a minimum of two instances. Configure an
Amazon CloudFront distribution for the website.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a website that uses a content management system (CMS) on Amazon EC2. The CMS runs on a single EC2 instance and uses an Amazon Aurora MySQL Multi-AZ DB instance for the data tier. Website images are stored on an Amazon Elastic Block Store (Amazon EBS) volume that is mounted inside the EC2 instance.

Which combination of actions should a solutions architect take to improve the performance and resilience of the website? (Choose two.)


**C.** Move the website images onto an Amazon Elastic File System (Amazon EFS) file system that is mounted on every EC2 instance.


**E.** Create an Amazon Machine Image (AMI) from the existing EC2 instance. Use the AMI to provision new instances behind an Application Load Balancer as part of an Auto Scaling group. Configure the Auto Scaling group to maintain a minimum of two instances. Configure an Amazon CloudFront distribution for the website.

Option C provides moving the website images onto an Amazon EFS file system that is mounted on every EC2 instance. Amazon EFS provides a scalable and fully managed file storage solution that can be accessed concurrently from multiple EC2 instances. This ensures that the website images can be accessed efficiently and consistently by all instances, improving performance.

In Option E The Auto Scaling group maintains a minimum of two instances, ensuring resilience by automatically replacing any unhealthy instances. Additionally, configuring an Amazon CloudFront distribution for the website further improves performance by caching content at edge locations closer to the end-users, reducing latency and improving content delivery.
Hence combining these actions, the website's performance is improved through efficient image storage and content delivery

</details>

---

## Question 503

[Review topic](../sections/operations.md) · Source PDF page 185

A company runs an infrastructure monitoring service. The company is building a new feature that will enable the service to monitor data in
customer AWS accounts. The new feature will call AWS APIs in customer accounts to describe Amazon EC2 instances and read Amazon
CloudWatch metrics.
What should the company do to obtain access to customer accounts in the MOST secure way?

**A.** Ensure that the customers create an IAM role in their account with read-only EC2 and CloudWatch permissions and a trust policy to the
company’s account.

**B.** Create a serverless API that implements a token vending machine to provide temporary AWS credentials for a role with read-only EC2 and
CloudWatch permissions.

**C.** Ensure that the customers create an IAM user in their account with read-only EC2 and CloudWatch permissions. Encrypt and store
customer access and secret keys in a secrets management system.

**D.** Ensure that the customers create an Amazon Cognito user in their account to use an IAM role with read-only EC2 and CloudWatch
permissions. Encrypt and store the Amazon Cognito user and password in a secrets management system.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs an infrastructure monitoring service. The company is building a new feature that will enable the service to monitor data in customer AWS accounts. The new feature will call AWS APIs in customer accounts to describe Amazon EC2 instances and read Amazon CloudWatch metrics.

What should the company do to obtain access to customer accounts in the MOST secure way?


**A.** Ensure that the customers create an IAM role in their account with read-only EC2 and CloudWatch permissions and a trust policy to the company’s account.

</details>

---

## Question 504

[Review topic](../sections/cloud-foundations.md) · Source PDF page 185

A company needs to connect several VPCs in the us-east-1 Region that span hundreds of AWS accounts. The company's networking team has its
own AWS account to manage the cloud network.
What is the MOST operationally efficient solution to connect the VPCs?

**A.** Set up VPC peering connections between each VPC. Update each associated subnet’s route table

**B.** Configure a NAT gateway and an internet gateway in each VPC to connect each VPC through the internet

**C.** Create an AWS Transit Gateway in the networking team’s AWS account. Configure static routes from each VPC.

**D.** Deploy VPN gateways in each VPC. Create a transit VPC in the networking team’s AWS account to connect to each VPC.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs to connect several VPCs in the us-east-1 Region that span hundreds of AWS accounts. The company's networking team has its own AWS account to manage the cloud network.

What is the MOST operationally efficient solution to connect the VPCs?


**C.** Create an AWS Transit Gateway in the networking team’s AWS account. Configure static routes from each VPC.

AWS Transit Gateway: It is designed to simplify the connectivity between multiple VPCs. It acts as a central hub that allows you to connect multiple VPCs and on-premises networks. This approach reduces the complexity of managing peering connections individually.

</details>

---

## Question 505

[Review topic](../sections/ec2.md) · Source PDF page 186

A company has Amazon EC2 instances that run nightly batch jobs to process data. The EC2 instances run in an Auto Scaling group that uses On-
Demand billing. If a job fails on one instance, another instance will reprocess the job. The batch jobs run between 12:00 AM and 06:00 AM local
time every day.
Which solution will provide EC2 instances to meet these requirements MOST cost-effectively?

**A.** Purchase a 1-year Savings Plan for Amazon EC2 that covers the instance family of the Auto Scaling group that the batch job uses.

**B.** Purchase a 1-year Reserved Instance for the specific instance type and operating system of the instances in the Auto Scaling group that the
batch job uses.

**C.** Create a new launch template for the Auto Scaling group. Set the instances to Spot Instances. Set a policy to scale out based on CPU
usage.

**D.** Create a new launch template for the Auto Scaling group. Increase the instance size. Set a policy to scale out based on CPU usage.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has Amazon EC2 instances that run nightly batch jobs to process data. The EC2 instances run in an Auto Scaling group that uses On-Demand billing. If a job fails on one instance, another instance will reprocess the job. The batch jobs run between 12:00 AM and 06:00 AM local time every day.

Which solution will provide EC2 instances to meet these requirements MOST cost-effectively?


**C.** Create a new launch template for the Auto Scaling group. Set the instances to Spot Instances. Set a policy to scale out based on CPU usage.

Spot Instances: Spot Instances allow you to bid for unused EC2 capacity at a potentially lower cost than On-Demand pricing. This can result in significant cost savings for batch jobs that are fault-tolerant and can be interrupted or retried.

Scaling Policy: Setting a policy to scale out based on CPU usage ensures that additional Spot Instances are launched when the demand for processing power increases during batch job execution. This helps in handling varying workloads efficiently.

</details>

---

## Question 506

[Review topic](../sections/exam-revision.md) · Source PDF page 186

A social media company is building a feature for its website. The feature will give users the ability to upload photos. The company expects
significant increases in demand during large events and must ensure that the website can handle the upload traffic from users.
Which solution meets these requirements with the MOST scalability?

**A.** Upload files from the user's browser to the application servers. Transfer the files to an Amazon S3 bucket.

**B.** Provision an AWS Storage Gateway file gateway. Upload files directly from the user's browser to the file gateway.

**C.** Generate Amazon S3 presigned URLs in the application. Upload files directly from the user's browser into an S3 bucket.

**D.** Provision an Amazon Elastic File System (Amazon EFS) file system. Upload files directly from the user's browser to the file system.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A social media company is building a feature for its website. The feature will give users the ability to upload photos. The company expects significant increases in demand during large events and must ensure that the website can handle the upload traffic from users.

Which solution meets these requirements with the MOST scalability?


**C.** Generate Amazon S3 presigned URLs in the application. Upload files directly from the user's browser into an S3 bucket.

Amazon S3 Presigned URLs: This approach allows the client (user's browser) to directly upload files to Amazon S3 using a presigned URL generated by the server. This offloads the file transfer process from the application servers and enables a direct upload to S3 from the client side.

</details>

---

## Question 507

[Review topic](../sections/exam-revision.md) · Source PDF page 186

A company has a web application for travel ticketing. The application is based on a database that runs in a single data center in North America.
The company wants to expand the application to serve a global user base. The company needs to deploy the application to multiple AWS Regions.
Average latency must be less than 1 second on updates to the reservation database.
The company wants to have separate deployments of its web platform across multiple Regions. However, the company must maintain a single
primary reservation database that is globally consistent.
Which solution should a solutions architect recommend to meet these requirements?

**A.** Convert the application to use Amazon DynamoDB. Use a global table for the center reservation table. Use the correct Regional endpoint in
each Regional deployment.

**B.** Migrate the database to an Amazon Aurora MySQL database. Deploy Aurora Read Replicas in each Region. Use the correct Regional
endpoint in each Regional deployment for access to the database.

**C.** Migrate the database to an Amazon RDS for MySQL database. Deploy MySQL read replicas in each Region. Use the correct Regional
endpoint in each Regional deployment for access to the database.

**D.** Migrate the application to an Amazon Aurora Serverless database. Deploy instances of the database to each Region. Use the correct
Regional endpoint in each Regional deployment to access the database. Use AWS Lambda functions to process event streams in each Region
to synchronize the databases.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a web application for travel ticketing. The application is based on a database that runs in a single data center in North America. The company wants to expand the application to serve a global user base. The company needs to deploy the application to multiple AWS Regions. Average latency must be less than 1 second on updates to the reservation database.

The company wants to have separate deployments of its web platform across multiple Regions. However, the company must maintain a single primary reservation database that is globally consistent.

Which solution should a solutions architect recommend to meet these requirements?


**A.** Convert the application to use Amazon DynamoDB. Use a global table for the center reservation table. Use the correct Regional endpoint in each Regional deployment.

Using DynamoDB's global tables feature, you can achieve a globally consistent reservation database with low latency on updates, making it suitable for serving a global user base. The automatic replication provided by DynamoDB eliminates the need for manual synchronization between Regions.

</details>

---

## Question 508

[Review topic](../sections/cloud-foundations.md) · Source PDF page 187

A company has migrated multiple Microsoft Windows Server workloads to Amazon EC2 instances that run in the us-west-1 Region. The company
manually backs up the workloads to create an image as needed.
In the event of a natural disaster in the us-west-1 Region, the company wants to recover workloads quickly in the us-west-2 Region. The company
wants no more than 24 hours of data loss on the EC2 instances. The company also wants to automate any backups of the EC2 instances.
Which solutions will meet these requirements with the LEAST administrative effort? (Choose two.)

**A.** Create an Amazon EC2-backed Amazon Machine Image (AMI) lifecycle policy to create a backup based on tags. Schedule the backup to run
twice daily. Copy the image on demand.

**B.** Create an Amazon EC2-backed Amazon Machine Image (AMI) lifecycle policy to create a backup based on tags. Schedule the backup to run
twice daily. Configure the copy to the us-west-2 Region.

**C.** Create backup vaults in us-west-1 and in us-west-2 by using AWS Backup. Create a backup plan for the EC2 instances based on tag values.
Create an AWS Lambda function to run as a scheduled job to copy the backup data to us-west-2.

**D.** Create a backup vault by using AWS Backup. Use AWS Backup to create a backup plan for the EC2 instances based on tag values. Define
the destination for the copy as us-west-2. Specify the backup schedule to run twice daily.

**E.** Create a backup vault by using AWS Backup. Use AWS Backup to create a backup plan for the EC2 instances based on tag values. Specify
the backup schedule to run twice daily. Copy on demand to us-west-2.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

Topic 1
A company has migrated multiple Microsoft Windows Server workloads to Amazon EC2 instances that run in the us-west-1 Region. The company manually backs up the workloads to create an image as needed.

In the event of a natural disaster in the us-west-1 Region, the company wants to recover workloads quickly in the us-west-2 Region. The company wants no more than 24 hours of data loss on the EC2 instances. The company also wants to automate any backups of the EC2 instances.

Which solutions will meet these requirements with the LEAST administrative effort? (Choose two.)


**B.** Create an Amazon EC2-backed Amazon Machine Image (AMI) lifecycle policy to create a backup based on tags. Schedule the backup to run twice daily. Configure the copy to the us-west-2 Region.


**D.** Create a backup vault by using AWS Backup. Use AWS Backup to create a backup plan for the EC2 instances based on tag values. Define the destination for the copy as us-west-2. Specify the backup schedule to run twice daily.

</details>

---

## Question 509

[Review topic](../sections/elb-asg.md) · Source PDF page 187

A company operates a two-tier application for image processing. The application uses two Availability Zones, each with one public subnet and one
private subnet. An Application Load Balancer (ALB) for the web tier uses the public subnets. Amazon EC2 instances for the application tier use
the private subnets.
Users report that the application is running more slowly than expected. A security audit of the web server log files shows that the application is
receiving millions of illegitimate requests from a small number of IP addresses. A solutions architect needs to resolve the immediate performance
problem while the company investigates a more permanent solution.
What should the solutions architect recommend to meet this requirement?

**A.** Modify the inbound security group for the web tier. Add a deny rule for the IP addresses that are consuming resources.

**B.** Modify the network ACL for the web tier subnets. Add an inbound deny rule for the IP addresses that are consuming resources.

**C.** Modify the inbound security group for the application tier. Add a deny rule for the IP addresses that are consuming resources.

**D.** Modify the network ACL for the application tier subnets. Add an inbound deny rule for the IP addresses that are consuming resources.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company operates a two-tier application for image processing. The application uses two Availability Zones, each with one public subnet and one private subnet. An Application Load Balancer (ALB) for the web tier uses the public subnets. Amazon EC2 instances for the application tier use the private subnets.

Users report that the application is running more slowly than expected. A security audit of the web server log files shows that the application is receiving millions of illegitimate requests from a small number of IP addresses. A solutions architect needs to resolve the immediate performance problem while the company investigates a more permanent solution.

What should the solutions architect recommend to meet this requirement?


**B.** Modify the network ACL for the web tier subnets. Add an inbound deny rule for the IP addresses that are consuming resources.

</details>

---

## Question 510

[Review topic](../sections/cloud-foundations.md) · Source PDF page 188

A global marketing company has applications that run in the ap-southeast-2 Region and the eu-west-1 Region. Applications that run in a VPC in eu-
west-1 need to communicate securely with databases that run in a VPC in ap-southeast-2.
Which network design will meet these requirements?

**A.** Create a VPC peering connection between the eu-west-1 VPC and the ap-southeast-2 VPC. Create an inbound rule in the eu-west-1
application security group that allows traffic from the database server IP addresses in the ap-southeast-2 security group.

**B.** Configure a VPC peering connection between the ap-southeast-2 VPC and the eu-west-1 VPC. Update the subnet route tables. Create an
inbound rule in the ap-southeast-2 database security group that references the security group ID of the application servers in eu-west-1.

**C.** Configure a VPC peering connection between the ap-southeast-2 VPC and the eu-west-1 VPUpdate the subnet route tables. Create an
inbound rule in the ap-southeast-2 database security group that allows traffic from the eu-west-1 application server IP addresses.

**D.** Create a transit gateway with a peering attachment between the eu-west-1 VPC and the ap-southeast-2 VPC. After the transit gateways are
properly peered and routing is configured, create an inbound rule in the database security group that references the security group ID of the
application servers in eu-west-1.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A global marketing company has applications that run in the ap-southeast-2 Region and the eu-west-1 Region. Applications that run in a VPC in eu-west-1 need to communicate securely with databases that run in a VPC in ap-southeast-2.

Which network design will meet these requirements?


**C.** Configure a VPC peering connection between the ap-southeast-2 VPC and the eu-west-1 VPUpdate the subnet route tables. Create an inbound rule in the ap-southeast-2 database security group that allows traffic from the eu-west-1 application server IP addresses.

VPC peering connections can be established between VPCs in different AWS Regions.
In this case, a VPC peering connection is set up between the VPC in ap-southeast-2 and the VPC in eu-west-1.

</details>

---

## Question 511

[Review topic](../sections/rds-aurora.md) · Source PDF page 188

A company is developing software that uses a PostgreSQL database schema. The company needs to configure multiple development
environments and databases for the company's developers. On average, each development environment is used for half of the 8-hour workday.
Which solution will meet these requirements MOST cost-effectively?

**A.** Configure each development environment with its own Amazon Aurora PostgreSQL database

**B.** Configure each development environment with its own Amazon RDS for PostgreSQL Single-AZ DB instances

**C.** Configure each development environment with its own Amazon Aurora On-Demand PostgreSQL-Compatible database

**D.** Configure each development environment with its own Amazon S3 bucket by using Amazon S3 Object Select

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is developing software that uses a PostgreSQL database schema. The company needs to configure multiple development environments and databases for the company's developers. On average, each development environment is used for half of the 8-hour workday.

Which solution will meet these requirements MOST cost-effectively?


**B.** Configure each development environment with its own Amazon RDS for PostgreSQL database. Stop the RDS instance outside of the 8-hour workday.

Explanation: Since each environment is only used for half of the workday, a standard RDS for PostgreSQL instance that gets stopped when not in use is cheaper than running Aurora continuously — Aurora costs more than standard RDS and this workload doesn't need Aurora's extra performance/availability features.

</details>

---

## Question 512

[Review topic](../sections/exam-revision.md) · Source PDF page 188

A company uses AWS Organizations with resources tagged by account. The company also uses AWS Backup to back up its AWS infrastructure
resources. The company needs to back up all AWS resources.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use AWS Config to identify all untagged resources. Tag the identified resources programmatically. Use tags in the backup plan.

**B.** Use AWS Config to identify all resources that are not running. Add those resources to the backup vault.

**C.** Require all AWS account owners to review their resources to identify the resources that need to be backed up.

**D.** Use Amazon Inspector to identify all noncompliant resources.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses AWS Organizations with resources tagged by account. The company also uses AWS Backup to back up its AWS infrastructure resources. The company needs to back up all AWS resources.

Which solution will meet these requirements with the LEAST operational overhead?


**A.** Use AWS Config to identify all untagged resources. Tag the identified resources programmatically. Use tags in the backup plan.

AWS Config can be used to identify untagged resources, and it can provide a comprehensive view of the resource inventory across your AWS Organization. 
AWS Backup supports the use of tags in backup plans. By utilizing tags, you can create a backup plan that automatically includes resources based on their tags.

</details>

---

## Question 513

[Review topic](../sections/exam-revision.md) · Source PDF page 189

A social media company wants to allow its users to upload images in an application that is hosted in the AWS Cloud. The company needs a
solution that automatically resizes the images so that the images can be displayed on multiple device types. The application experiences
unpredictable traffic patterns throughout the day. The company is seeking a highly available solution that maximizes scalability.
What should a solutions architect do to meet these requirements?

**A.** Create a static website hosted in Amazon S3 that invokes AWS Lambda functions to resize the images and store the images in an Amazon
S3 bucket.

**B.** Create a static website hosted in Amazon CloudFront that invokes AWS Step Functions to resize the images and store the images in an
Amazon RDS database.

**C.** Create a dynamic website hosted on a web server that runs on an Amazon EC2 instance. Configure a process that runs on the EC2 instance
to resize the images and store the images in an Amazon S3 bucket.

**D.** Create a dynamic website hosted on an automatically scaling Amazon Elastic Container Service (Amazon ECS) cluster that creates a resize
job in Amazon Simple Queue Service (Amazon SQS). Set up an image-resizing program that runs on an Amazon EC2 instance to process the
resize jobs.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A social media company wants to allow its users to upload images in an application that is hosted in the AWS Cloud. The company needs a solution that automatically resizes the images so that the images can be displayed on multiple device types. The application experiences unpredictable traffic patterns throughout the day. The company is seeking a highly available solution that maximizes scalability.

What should a solutions architect do to meet these requirements?


**A.** Create a static website hosted in Amazon S3 that invokes AWS Lambda functions to resize the images and store the images in an Amazon S3 bucket.

Hosting a static website in Amazon S3 is a cost-effective and highly available solution. Amazon S3 provides scalable and durable object storage.
A static website in S3 can serve as the front end for user interactions.
In this option, Lambda functions can be triggered by events (e.g., new image uploads to an S3 bucket) to perform image resizing. Lambda can efficiently handle sporadic and unpredictable workloads.

</details>

---

## Question 514

[Review topic](../sections/containers.md) · Source PDF page 189

A company is running a microservices application on Amazon EC2 instances. The company wants to migrate the application to an Amazon Elastic
Kubernetes Service (Amazon EKS) cluster for scalability. The company must configure the Amazon EKS control plane with endpoint private access
set to true and endpoint public access set to false to maintain security compliance. The company must also put the data plane in private subnets.
However, the company has received error notifications because the node cannot join the cluster.
Which solution will allow the node to join the cluster?

**A.** Grant the required permission in AWS Identity and Access Management (IAM) to the AmazonEKSNodeRole IAM role.

**B.** Create interface VPC endpoints to allow nodes to access the control plane.

**C.** Recreate nodes in the public subnet. Restrict security groups for EC2 nodes.

**D.** Allow outbound traffic in the security group of the nodes.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is running a microservices application on Amazon EC2 instances. The company wants to migrate the application to an Amazon Elastic Kubernetes Service (Amazon EKS) cluster for scalability. The company must configure the Amazon EKS control plane with endpoint private access set to true and endpoint public access set to false to maintain security compliance. The company must also put the data plane in private subnets. However, the company has received error notifications because the node cannot join the cluster.

Which solution will allow the node to join the cluster?


**B.** Create interface VPC endpoints to allow nodes to access the control plane.

When the Amazon EKS control plane has private access, nodes need to communicate with the control plane through interface VPC endpoints.
Creating interface VPC endpoints ensures that the nodes in private subnets can securely communicate with the EKS control plane without the need for public IP addresses.

</details>

---

## Question 515

[Review topic](../sections/analytics.md) · Source PDF page 189

A company is migrating an on-premises application to AWS. The company wants to use Amazon Redshift as a solution.
Which use cases are suitable for Amazon Redshift in this scenario? (Choose three.)

**A.** Supporting data APIs to access data with traditional, containerized, and event-driven applications

**B.** Supporting client-side and server-side encryption

**C.** Building analytics workloads during specified hours and when the application is not active

**D.** Caching data to reduce the pressure on the backend database

**E.** Scaling globally to support petabytes of data and tens of millions of requests per minute

**F.** Creating a secondary replica of the cluster by using the AWS Management Console

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is migrating an on-premises application to AWS. The company wants to use Amazon Redshift as a solution.

Which use cases are suitable for Amazon Redshift in this scenario? (Choose three.)


**B.** Supporting client-side and server-side encryption


**C.** Building analytics workloads during specified hours and when the application is not active


**E.** Scaling globally to support petabytes of data and tens of millions of requests per minute
Amazon Redshift supports encryption for data at rest and in transit, providing security features for sensitive data. This makes it suitable for scenarios where encryption is a requirement.
Amazon Redshift is a fully managed data warehouse service optimized for analytical queries. Running analytics workloads during specified hours aligns with Redshift's strengths, allowing for efficient query processing and analysis.

</details>

---

## Question 516

[Review topic](../sections/exam-revision.md) · Source PDF page 190

A company provides an API interface to customers so the customers can retrieve their financial information. Еhe company expects a larger
number of requests during peak usage times of the year.
The company requires the API to respond consistently with low latency to ensure customer satisfaction. The company needs to provide a
compute host for the API.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use an Application Load Balancer and Amazon Elastic Container Service (Amazon ECS).

**B.** Use Amazon API Gateway and AWS Lambda functions with provisioned concurrency.

**C.** Use an Application Load Balancer and an Amazon Elastic Kubernetes Service (Amazon EKS) cluster.

**D.** Use Amazon API Gateway and AWS Lambda functions with reserved concurrency.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company provides an API interface to customers so the customers can retrieve their financial information. Еhe company expects a larger number of requests during peak usage times of the year.

The company requires the API to respond consistently with low latency to ensure customer satisfaction. The company needs to provide a compute host for the API.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Use Amazon API Gateway and AWS Lambda functions with provisioned concurrency.

Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale.
AWS Lambda is a serverless computing service that automatically scales based on demand.
Provisioned concurrency in AWS Lambda allows you to set a specific number of concurrent executions to ensure that the function is ready to respond quickly to incoming requests.

</details>

---

## Question 517

[Review topic](../sections/s3.md) · Source PDF page 190

A company wants to send all AWS Systems Manager Session Manager logs to an Amazon S3 bucket for archival purposes.
Which solution will meet this requirement with the MOST operational efficiency?

**A.** Enable S3 logging in the Systems Manager console. Choose an S3 bucket to send the session data to.

**B.** Install the Amazon CloudWatch agent. Push all logs to a CloudWatch log group. Export the logs to an S3 bucket from the group for archival
purposes.

**C.** Create a Systems Manager document to upload all server logs to a central S3 bucket. Use Amazon EventBridge to run the Systems Manager
document against all servers that are in the account daily.

**D.** Install an Amazon CloudWatch agent. Push all logs to a CloudWatch log group. Create a CloudWatch logs subscription that pushes any
incoming log events to an Amazon Kinesis Data Firehose delivery stream. Set Amazon S3 as the destination.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to send all AWS Systems Manager Session Manager logs to an Amazon S3 bucket for archival purposes.

Which solution will meet this requirement with the MOST operational efficiency?


**A.** Enable S3 logging in the Systems Manager console. Choose an S3 bucket to send the session data to.

While AWS Systems Manager supports logging command output to an S3 bucket, this is primarily for storing the output of commands executed through Systems Manager, not specifically for Session Manager logs.
It may not capture all the detailed session logs, including interactive session input/output and other session-specific details.

</details>

---

## Question 518

[Review topic](../sections/rds-aurora.md) · Source PDF page 190

An application uses an Amazon RDS MySQL DB instance. The RDS database is becoming low on disk space. A solutions architect wants to
increase the disk space without downtime.
Which solution meets these requirements with the LEAST amount of effort?

**A.** Enable storage autoscaling in RDS

**B.** Increase the RDS database instance size

**C.** Change the RDS database instance storage type to Provisioned IOPS

**D.** Back up the RDS database, increase the storage capacity, restore the database, and stop the previous instance

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An application uses an Amazon RDS MySQL DB instance. The RDS database is becoming low on disk space. A solutions architect wants to increase the disk space without downtime.

Which solution meets these requirements with the LEAST amount of effort?


**A.** Enable storage autoscaling in RDS

Enabling storage autoscaling allows Amazon RDS to automatically adjust the storage capacity of the database without requiring manual intervention.
With autoscaling, the storage capacity can increase dynamically based on the actual usage, preventing the need for manual adjustments.

</details>

---

## Question 519

[Review topic](../sections/exam-revision.md) · Source PDF page 191

A consulting company provides professional services to customers worldwide. The company provides solutions and tools for customers to
expedite gathering and analyzing data on AWS. The company needs to centrally manage and deploy a common set of solutions and tools for
customers to use for self-service purposes.
Which solution will meet these requirements?

**A.** Create AWS CloudFormation templates for the customers.

**B.** Create AWS Service Catalog products for the customers.

**C.** Create AWS Systems Manager templates for the customers.

**D.** Create AWS Config items for the customers.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A consulting company provides professional services to customers worldwide. The company provides solutions and tools for customers to expedite gathering and analyzing data on AWS. The company needs to centrally manage and deploy a common set of solutions and tools for customers to use for self-service purposes.

Which solution will meet these requirements?


**B.** Create AWS Service Catalog products for the customers.

AWS Service Catalog allows you to create and manage catalogs of IT services that are approved for use on AWS. It enables you to centrally manage and distribute standardized product portfolios.

</details>

---

## Question 520

[Review topic](../sections/dynamodb-caching.md) · Source PDF page 191

A company is designing a new web application that will run on Amazon EC2 Instances. The application will use Amazon DynamoDB for backend
data storage. The application traffic will be unpredictable. The company expects that the application read and write throughput to the database
will be moderate to high. The company needs to scale in response to application traffic.
Which DynamoDB table configuration will meet these requirements MOST cost-effectively?

**A.** Configure DynamoDB with provisioned read and write by using the DynamoDB Standard table class. Set DynamoDB auto scaling to a
maximum defined capacity.

**B.** Configure DynamoDB in on-demand mode by using the DynamoDB Standard table class.

**C.** Configure DynamoDB with provisioned read and write by using the DynamoDB Standard Infrequent Access (DynamoDB Standard-IA) table
class. Set DynamoDB auto scaling to a maximum defined capacity.

**D.** Configure DynamoDB in on-demand mode by using the DynamoDB Standard Infrequent Access (DynamoDB Standard-IA) table class.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is designing a new web application that will run on Amazon EC2 Instances. The application will use Amazon DynamoDB for backend data storage. The application traffic will be unpredictable. The company expects that the application read and write throughput to the database will be moderate to high. The company needs to scale in response to application traffic.

Which DynamoDB table configuration will meet these requirements MOST cost-effectively?


**B.** Configure DynamoDB in on-demand mode by using the DynamoDB Standard table class.

On-demand capacity mode allows DynamoDB to automatically scale read and write capacity based on actual application traffic.
It eliminates the need for manual provisioning of read and write capacity, making it well-suited for unpredictable workloads.
DynamoDB Standard Table Class:

The DynamoDB Standard table class provides general-purpose storage with consistent, single-digit millisecond latency. It's suitable for a wide range of applications, including those with unpredictable traffic

</details>

---

## Question 521

[Review topic](../sections/dynamodb-caching.md) · Source PDF page 192

A retail company has several businesses. The IT team for each business manages its own AWS account. Each team account is part of an
organization in AWS Organizations. Each team monitors its product inventory levels in an Amazon DynamoDB table in the team's own AWS
account.
The company is deploying a central inventory reporting application into a shared AWS account. The application must be able to read items from all
the teams' DynamoDB tables.
Which authentication option will meet these requirements MOST securely?

**A.** Integrate DynamoDB with AWS Secrets Manager in the inventory application account. Configure the application to use the correct secret
from Secrets Manager to authenticate and read the DynamoDB table. Schedule secret rotation for every 30 days.

**B.** In every business account, create an IAM user that has programmatic access. Configure the application to use the correct IAM user access
key ID and secret access key to authenticate and read the DynamoDB table. Manually rotate IAM access keys every 30 days.

**C.** In every business account, create an IAM role named BU_ROLE with a policy that gives the role access to the DynamoDB table and a trust
policy to trust a specific role in the inventory application account. In the inventory account, create a role named APP_ROLE that allows access
to the STS AssumeRole API operation. Configure the application to use APP_ROLE and assume the crossaccount role BU_ROLE to read the
DynamoDB table.

**D.** Integrate DynamoDB with AWS Certificate Manager (ACM). Generate identity certificates to authenticate DynamoDB. Configure the
application to use the correct certificate to authenticate and read the DynamoDB table.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A retail company has several businesses. The IT team for each business manages its own AWS account. Each team account is part of an organization in AWS Organizations. Each team monitors its product inventory levels in an Amazon DynamoDB table in the team's own AWS account.

The company is deploying a central inventory reporting application into a shared AWS account. The application must be able to read items from all the teams' DynamoDB tables.

Which authentication option will meet these requirements MOST securely?


**C.** In every business account, create an IAM role named BU_ROLE with a policy that gives the role access to the DynamoDB table and a trust policy to trust a specific role in the inventory application account. In the inventory account, create a role named APP_ROLE that allows access to the STS AssumeRole API operation. Configure the application to use APP_ROLE and assume the crossaccount role BU_ROLE to read the DynamoDB table.

</details>

---

## Question 522

[Review topic](../sections/containers.md) · Source PDF page 192

A company runs container applications by using Amazon Elastic Kubernetes Service (Amazon EKS). The company's workload is not consistent
throughout the day. The company wants Amazon EKS to scale in and out according to the workload.
Which combination of steps will meet these requirements with the LEAST operational overhead? (Choose two.)

**A.** Use an AWS Lambda function to resize the EKS cluster.

**B.** Use the Kubernetes Metrics Server to activate horizontal pod autoscaling.

**C.** Use the Kubernetes Cluster Autoscaler to manage the number of nodes in the cluster.

**D.** Use Amazon API Gateway and connect it to Amazon EKS.

**E.** Use AWS App Mesh to observe network activity.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs container applications by using Amazon Elastic Kubernetes Service (Amazon EKS). The company's workload is not consistent throughout the day. The company wants Amazon EKS to scale in and out according to the workload.

Which combination of steps will meet these requirements with the LEAST operational overhead? (Choose two.)


**B.** Use the Kubernetes Metrics Server for Horizontal Pod Autoscaling:

Kubernetes supports Horizontal Pod Autoscaling (HPA) based on custom metrics or resource metrics.
By using the Kubernetes Metrics Server, you can enable HPA to automatically adjust the number of pods in a deployment based on observed custom metrics (such as application-specific metrics) or resource metrics (such as CPU or memory usage).


**C.** Use the Kubernetes Cluster Autoscaler:

The Kubernetes Cluster Autoscaler automatically adjusts the size of the cluster by adding or removing nodes based on the resource utilization and pod scheduling requirements.
This helps in scaling the cluster itself based on the overall demand.

</details>

---

## Question 523

[Review topic](../sections/dynamodb-caching.md) · Source PDF page 192

A company runs a microservice-based serverless web application. The application must be able to retrieve data from multiple Amazon DynamoDB
tables A solutions architect needs to give the application the ability to retrieve the data with no impact on the baseline performance of the
application.
Which solution will meet these requirements in the MOST operationally efficient way?

**A.** AWS AppSync pipeline resolvers

**B.** Amazon CloudFront with Lambda@Edge functions

**C.** Edge-optimized Amazon API Gateway with AWS Lambda functions

**D.** Amazon Athena Federated Query with a DynamoDB connector

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a microservice-based serverless web application. The application must be able to retrieve data from multiple Amazon DynamoDB tables A solutions architect needs to give the application the ability to retrieve the data with no impact on the baseline performance of the application.

Which solution will meet these requirements in the MOST operationally efficient way?


**B.** Amazon CloudFront with Lambda@Edge functions

Amazon CloudFront is a content delivery network (CDN) service that can distribute content globally with low latency.
Lambda@Edge allows you to run custom code in response to CloudFront events, such as viewer requests, origin requests, and more.
By using Lambda@Edge functions, you can customize and augment the behavior of CloudFront.

</details>

---

## Question 524

[Review topic](../sections/iam.md) · Source PDF page 193

A company wants to analyze and troubleshoot Access Denied errors and Unauthorized errors that are related to IAM permissions. The company
has AWS CloudTrail turned on.
Which solution will meet these requirements with the LEAST effort?

**A.** Use AWS Glue and write custom scripts to query CloudTrail logs for the errors.

**B.** Use AWS Batch and write custom scripts to query CloudTrail logs for the errors.

**C.** Search CloudTrail logs with Amazon Athena queries to identify the errors.

**D.** Search CloudTrail logs with Amazon QuickSight. Create a dashboard to identify the errors.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to analyze and troubleshoot Access Denied errors and Unauthorized errors that are related to IAM permissions. The company has AWS CloudTrail turned on.

Which solution will meet these requirements with the LEAST effort?


**C.** Search CloudTrail logs with Amazon Athena queries to identify the errors.

Amazon Athena allows you to query data directly from S3 using standard SQL queries.
CloudTrail logs can be stored in Amazon S3, and Athena makes it easy to analyze the logs using SQL queries.

</details>

---

## Question 525

[Review topic](../sections/cost-governance.md) · Source PDF page 193

A company wants to add its existing AWS usage cost to its operation cost dashboard. A solutions architect needs to recommend a solution that
will give the company access to its usage cost programmatically. The company must be able to access cost data for the current year and forecast
costs for the next 12 months.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Access usage cost-related data by using the AWS Cost Explorer API with pagination.

**B.** Access usage cost-related data by using downloadable AWS Cost Explorer report .csv files.

**C.** Configure AWS Budgets actions to send usage cost data to the company through FTP.

**D.** Create AWS Budgets reports for usage cost data. Send the data to the company through SMTP.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to add its existing AWS usage cost to its operation cost dashboard. A solutions architect needs to recommend a solution that will give the company access to its usage cost programmatically. The company must be able to access cost data for the current year and forecast costs for the next 12 months.

Which solution will meet these requirements with the LEAST operational overhead?


**A.** Access usage cost-related data by using the AWS Cost Explorer API with pagination.

AWS Cost Explorer is a tool provided by Amazon Web Services (AWS) that allows users to visualize, understand, and manage their AWS costs and usage.

</details>

---

## Question 526

[Review topic](../sections/rds-aurora.md) · Source PDF page 193

A solutions architect is reviewing the resilience of an application. The solutions architect notices that a database administrator recently failed
over the application's Amazon Aurora PostgreSQL database writer instance as part of a scaling exercise. The failover resulted in 3 minutes of
downtime for the application.
Which solution will reduce the downtime for scaling exercises with the LEAST operational overhead?

**A.** Create more Aurora PostgreSQL read replicas in the cluster to handle the load during failover.

**B.** Set up a secondary Aurora PostgreSQL cluster in the same AWS Region. During failover, update the application to use the secondary
cluster's writer endpoint.

**C.** Create an Amazon ElastiCache for Memcached cluster to handle the load during failover.

**D.** Set up an Amazon RDS proxy for the database. Update the application to use the proxy endpoint.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is reviewing the resilience of an application. The solutions architect notices that a database administrator recently failed over the application's Amazon Aurora PostgreSQL database writer instance as part of a scaling exercise. The failover resulted in 3 minutes of downtime for the application.

Which solution will reduce the downtime for scaling exercises with the LEAST operational overhead?


**D.** Set up an Amazon RDS proxy for the database. Update the application to use the proxy endpoint.

Amazon RDS Proxy is a fully managed, highly available database proxy for Amazon RDS (Relational Database Service). It provides connection pooling, read/write splitting, and automatic failover, helping to improve the availability and scalability of database workloads.

</details>

---

## Question 527

[Review topic](../sections/ec2.md) · Source PDF page 194

A company has a regional subscription-based streaming service that runs in a single AWS Region. The architecture consists of web servers and
application servers on Amazon EC2 instances. The EC2 instances are in Auto Scaling groups behind Elastic Load Balancers. The architecture
includes an Amazon Aurora global database cluster that extends across multiple Availability Zones.
The company wants to expand globally and to ensure that its application has minimal downtime.
Which solution will provide the MOST fault tolerance?

**A.** Extend the Auto Scaling groups for the web tier and the application tier to deploy instances in Availability Zones in a second Region. Use an
Aurora global database to deploy the database in the primary Region and the second Region. Use Amazon Route 53 health checks with a
failover routing policy to the second Region.

**B.** Deploy the web tier and the application tier to a second Region. Add an Aurora PostgreSQL cross-Region Aurora Replica in the second
Region. Use Amazon Route 53 health checks with a failover routing policy to the second Region. Promote the secondary to primary as needed.

**C.** Deploy the web tier and the application tier to a second Region. Create an Aurora PostgreSQL database in the second Region. Use AWS
Database Migration Service (AWS DMS) to replicate the primary database to the second Region. Use Amazon Route 53 health checks with a
failover routing policy to the second Region.

**D.** Deploy the web tier and the application tier to a second Region. Use an Amazon Aurora global database to deploy the database in the
primary Region and the second Region. Use Amazon Route 53 health checks with a failover routing policy to the second Region. Promote the
secondary to primary as needed.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a regional subscription-based streaming service that runs in a single AWS Region. The architecture consists of web servers and application servers on Amazon EC2 instances. The EC2 instances are in Auto Scaling groups behind Elastic Load Balancers. The architecture includes an Amazon Aurora global database cluster that extends across multiple Availability Zones.

The company wants to expand globally and to ensure that its application has minimal downtime.

Which solution will provide the MOST fault tolerance?


**D.** Deploy the web tier and the application tier to a second Region. Use an Amazon Aurora global database to deploy the database in the primary Region and the second Region. Use Amazon Route 53 health checks with a failover routing policy to the second Region. Promote the secondary to primary as needed.

An Aurora global database allows you to replicate your database across multiple AWS Regions. This ensures that you have a read-capable secondary database in the second Region, providing low-latency access to the database.
Amazon Route 53 can be configured with health checks to monitor the health of the web and application tiers in both Regions. In the event of a failure in the primary Region, Route 53 can automatically route traffic to the healthy resources in the second Region.

</details>

---

## Question 528

[Review topic](../sections/analytics.md) · Source PDF page 194

A data analytics company wants to migrate its batch processing system to AWS. The company receives thousands of small data files periodically
during the day through FTP. An on-premises batch job processes the data files overnight. However, the batch job takes hours to finish running.
The company wants the AWS solution to process incoming data files as soon as possible with minimal changes to the FTP clients that send the
files. The solution must delete the incoming data files after the files have been processed successfully. Processing for each file needs to take 3-8
minutes.
Which solution will meet these requirements in the MOST operationally efficient way?

**A.** Use an Amazon EC2 instance that runs an FTP server to store incoming files as objects in Amazon S3 Glacier Flexible Retrieval. Configure a
job queue in AWS Batch. Use Amazon EventBridge rules to invoke the job to process the objects nightly from S3 Glacier Flexible Retrieval.
Delete the objects after the job has processed the objects.

**B.** Use an Amazon EC2 instance that runs an FTP server to store incoming files on an Amazon Elastic Block Store (Amazon EBS) volume.
Configure a job queue in AWS Batch. Use Amazon EventBridge rules to invoke the job to process the files nightly from the EBS volume. Delete
the files after the job has processed the files.

**C.** Use AWS Transfer Family to create an FTP server to store incoming files on an Amazon Elastic Block Store (Amazon EBS) volume.
Configure a job queue in AWS Batch. Use an Amazon S3 event notification when each file arrives to invoke the job in AWS Batch. Delete the
files after the job has processed the files.

**D.** Use AWS Transfer Family to create an FTP server to store incoming files in Amazon S3 Standard. Create an AWS Lambda function to
process the files and to delete the files after they are processed. Use an S3 event notification to invoke the Lambda function when the files
arrive.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: D**

Transfer Family writes incoming FTP files to S3; object events trigger Lambda. Three-to-eight-minute processing fits the 15-minute limit. Delete only after success and handle duplicate events.

</details>

---

## Question 529

[Review topic](../sections/exam-revision.md) · Source PDF page 195

A company is migrating its workloads to AWS. The company has transactional and sensitive data in its databases. The company wants to use
AWS Cloud solutions to increase security and reduce operational overhead for the databases.
Which solution will meet these requirements?

**A.** Migrate the databases to Amazon EC2. Use an AWS Key Management Service (AWS KMS) AWS managed key for encryption.

**B.** Migrate the databases to Amazon RDS Configure encryption at rest.

**C.** Migrate the data to Amazon S3 Use Amazon Macie for data security and protection

**D.** Migrate the database to Amazon RDS. Use Amazon CloudWatch Logs for data security and protection.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is migrating its workloads to AWS. The company has transactional and sensitive data in its databases. The company wants to use AWS Cloud solutions to increase security and reduce operational overhead for the databases.

Which solution will meet these requirements?


**B.** Migrate the databases to Amazon RDS Configure encryption at rest.

Amazon RDS (Relational Database Service) is a fully managed database service that simplifies database management tasks, such as hardware provisioning, patching, and backups.

Encryption at Rest
Amazon RDS supports encryption at rest, which means data stored in the database is automatically encrypted. This provides an additional layer of security for sensitive data.
Managed Service:
Amazon RDS is a managed service, meaning AWS takes care of operational aspects such as hardware maintenance, software patching, and backups. This reduces operational overhead for the company.

</details>

---

## Question 530

[Review topic](../sections/global-delivery.md) · Source PDF page 195

A company has an online gaming application that has TCP and UDP multiplayer gaming capabilities. The company uses Amazon Route 53 to point
the application traffic to multiple Network Load Balancers (NLBs) in different AWS Regions. The company needs to improve application
performance and decrease latency for the online game in preparation for user growth.
Which solution will meet these requirements?

**A.** Add an Amazon CloudFront distribution in front of the NLBs. Increase the Cache-Control max-age parameter.

**B.** Replace the NLBs with Application Load Balancers (ALBs). Configure Route 53 to use latency-based routing.

**C.** Add AWS Global Accelerator in front of the NLBs. Configure a Global Accelerator endpoint to use the correct listener ports.

**D.** Add an Amazon API Gateway endpoint behind the NLBs. Enable API caching. Override method caching for the different stages.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an online gaming application that has TCP and UDP multiplayer gaming capabilities. The company uses Amazon Route 53 to point the application traffic to multiple Network Load Balancers (NLBs) in different AWS Regions. The company needs to improve application performance and decrease latency for the online game in preparation for user growth.

Which solution will meet these requirements?


**C.** Add AWS Global Accelerator in front of the NLBs. Configure a Global Accelerator endpoint to use the correct listener ports.

AWS Global Accelerator is a service that uses anycast IP addresses to route traffic over the AWS global network to optimal endpoints based on health, geography, and routing policies.

</details>

---

## Question 531

[Review topic](../sections/serverless.md) · Source PDF page 195

A company needs to integrate with a third-party data feed. The data feed sends a webhook to notify an external service when new data is ready for
consumption. A developer wrote an AWS Lambda function to retrieve data when the company receives a webhook callback. The developer must
make the Lambda function available for the third party to call.
Which solution will meet these requirements with the MOST operational efficiency?

**A.** Create a function URL for the Lambda function. Provide the Lambda function URL to the third party for the webhook.

**B.** Deploy an Application Load Balancer (ALB) in front of the Lambda function. Provide the ALB URL to the third party for the webhook.

**C.** Create an Amazon Simple Notification Service (Amazon SNS) topic. Attach the topic to the Lambda function. Provide the public hostname
of the SNS topic to the third party for the webhook.

**D.** Create an Amazon Simple Queue Service (Amazon SQS) queue. Attach the queue to the Lambda function. Provide the public hostname of
the SQS queue to the third party for the webhook.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs to integrate with a third-party data feed. The data feed sends a webhook to notify an external service when new data is ready for consumption. A developer wrote an AWS Lambda function to retrieve data when the company receives a webhook callback. The developer must make the Lambda function available for the third party to call.

Which solution will meet these requirements with the MOST operational efficiency?


**A.** Create a function URL for the Lambda function. Provide the Lambda function URL to the third party for the webhook.

AWS Lambda supports API Gateway integration, which allows you to create an HTTP endpoint (URL) for your Lambda function.
Operational Efficiency:
Directly exposing the Lambda function through a URL eliminates the need for additional services, such as load balancers or message queues, for simple webhook integration.
Simplicity:
This approach is straightforward and easy to implement. It provides a direct URL that the third party can use to invoke the Lambda function when the webhook is triggered.

</details>

---

## Question 532

[Review topic](../sections/global-delivery.md) · Source PDF page 196

A company has a workload in an AWS Region. Customers connect to and access the workload by using an Amazon API Gateway REST API. The
company uses Amazon Route 53 as its DNS provider. The company wants to provide individual and secure URLs for all customers.
Which combination of steps will meet these requirements with the MOST operational efficiency? (Choose three.)

**A.** Register the required domain in a registrar. Create a wildcard custom domain name in a Route 53 hosted zone and record in the zone that
points to the API Gateway endpoint.

**B.** Request a wildcard certificate that matches the domains in AWS Certificate Manager (ACM) in a different Region.

**C.** Create hosted zones for each customer as required in Route 53. Create zone records that point to the API Gateway endpoint.

**D.** Request a wildcard certificate that matches the custom domain name in AWS Certificate Manager (ACM) in the same Region.

**E.** Create multiple API endpoints for each customer in API Gateway.

**F.** Create a custom domain name in API Gateway for the REST API. Import the certificate from AWS Certificate Manager (ACM).

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a workload in an AWS Region. Customers connect to and access the workload by using an Amazon API Gateway REST API. The company uses Amazon Route 53 as its DNS provider. The company wants to provide individual and secure URLs for all customers.

Which combination of steps will meet these requirements with the MOST operational efficiency? (Choose three.)


**A.** Register the required domain in a registrar. Create a wildcard custom domain name in a Route 53 hosted zone and record in the zone that points to the API Gateway endpoint.


**D.** Request a wildcard certificate that matches the custom domain name in AWS Certificate Manager (ACM) in the same Region.


**F.** Create a custom domain name in API Gateway for the REST API. Import the certificate from AWS Certificate Manager (ACM).

Registering the domain in a registrar and creating a wildcard custom domain name in Route 53 allows you to manage the DNS records efficiently. The DNS records can point to the API Gateway endpoint.

ACM provides a simple way to request and manage SSL/TLS certificates. Requesting a wildcard certificate for the custom domain ensures that it covers all subdomains, allowing for individual and secure URLs.

API Gateway allows you to create a custom domain name and associate it with your REST API. By importing a wildcard certificate from AWS Certificate Manager (ACM), you can secure the custom domain.

</details>

---

## Question 533

[Review topic](../sections/s3.md) · Source PDF page 196

A company stores data in Amazon S3. According to regulations, the data must not contain personally identifiable information (PII). The company
recently discovered that S3 buckets have some objects that contain PII. The company needs to automatically detect PII in S3 buckets and to notify
the company’s security team.
Which solution will meet these requirements?

**A.** Use Amazon Macie. Create an Amazon EventBridge rule to filter the SensitiveData event type from Macie findings and to send an Amazon
Simple Notification Service (Amazon SNS) notification to the security team.

**B.** Use Amazon GuardDuty. Create an Amazon EventBridge rule to filter the CRITICAL event type from GuardDuty findings and to send an
Amazon Simple Notification Service (Amazon SNS) notification to the security team.

**C.** Use Amazon Macie. Create an Amazon EventBridge rule to filter the SensitiveData:S3Object/Personal event type from Macie findings and to
send an Amazon Simple Queue Service (Amazon SQS) notification to the security team.

**D.** Use Amazon GuardDuty. Create an Amazon EventBridge rule to filter the CRITICAL event type from GuardDuty findings and to send an
Amazon Simple Queue Service (Amazon SQS) notification to the security team.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company stores data in Amazon S3. According to regulations, the data must not contain personally identifiable information (PII). The company recently discovered that S3 buckets have some objects that contain PII. The company needs to automatically detect PII in S3 buckets and to notify the company’s security team.

Which solution will meet these requirements?


**A.** Use Amazon Macie. Create an Amazon EventBridge rule to filter the SensitiveData event type from Macie findings and to send an Amazon Simple Notification Service (Amazon SNS) notification to the security team.

Amazon Macie is a service designed for data discovery and classification. It can identify sensitive data, including personally identifiable information (PII). By creating an EventBridge rule to filter the SensitiveData event type, you can specifically target PII-related findings and notify the security team using Amazon SNS.

</details>

---

## Question 534

[Review topic](../sections/s3.md) · Source PDF page 197

A company wants to build a logging solution for its multiple AWS accounts. The company currently stores the logs from all accounts in a
centralized account. The company has created an Amazon S3 bucket in the centralized account to store the VPC flow logs and AWS CloudTrail
logs. All logs must be highly available for 30 days for frequent analysis, retained for an additional 60 days for backup purposes, and deleted 90
days after creation.
Which solution will meet these requirements MOST cost-effectively?

**A.** Transition objects to the S3 Standard storage class 30 days after creation. Write an expiration action that directs Amazon S3 to delete
objects after 90 days.

**B.** Transition objects to the S3 Standard-Infrequent Access (S3 Standard-IA) storage class 30 days after creation. Move all objects to the S3
Glacier Flexible Retrieval storage class after 90 days. Write an expiration action that directs Amazon S3 to delete objects after 90 days.

**C.** Transition objects to the S3 Glacier Flexible Retrieval storage class 30 days after creation. Write an expiration action that directs Amazon
S3 to delete objects after 90 days.

**D.** Transition objects to the S3 One Zone-Infrequent Access (S3 One Zone-IA) storage class 30 days after creation. Move all objects to the S3
Glacier Flexible Retrieval storage class after 90 days. Write an expiration action that directs Amazon S3 to delete objects after 90 days.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to build a logging solution for its multiple AWS accounts. The company currently stores the logs from all accounts in a centralized account. The company has created an Amazon S3 bucket in the centralized account to store the VPC flow logs and AWS CloudTrail logs. All logs must be highly available for 30 days for frequent analysis, retained for an additional 60 days for backup purposes, and deleted 90 days after creation.

Which solution will meet these requirements MOST cost-effectively?


**B.** Transition objects to the S3 Standard-Infrequent Access (S3 Standard-IA) storage class 30 days after creation. Move all objects to the S3 Glacier Flexible Retrieval storage class after 90 days. Write an expiration action that directs Amazon S3 to delete objects after 90 days.

</details>

---

## Question 535

[Review topic](../sections/containers.md) · Source PDF page 197

A company is building an Amazon Elastic Kubernetes Service (Amazon EKS) cluster for its workloads. All secrets that are stored in Amazon EKS
must be encrypted in the Kubernetes etcd key-value store.
Which solution will meet these requirements?

**A.** Create a new AWS Key Management Service (AWS KMS) key. Use AWS Secrets Manager to manage, rotate, and store all secrets in Amazon
EKS.

**B.** Create a new AWS Key Management Service (AWS KMS) key. Enable Amazon EKS KMS secrets encryption on the Amazon EKS cluster.

**C.** Create the Amazon EKS cluster with default options. Use the Amazon Elastic Block Store (Amazon EBS) Container Storage Interface (CSI)
driver as an add-on.

**D.** Create a new AWS Key Management Service (AWS KMS) key with the alias/aws/ebs alias. Enable default Amazon Elastic Block Store
(Amazon EBS) volume encryption for the account.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is building an Amazon Elastic Kubernetes Service (Amazon EKS) cluster for its workloads. All secrets that are stored in Amazon EKS must be encrypted in the Kubernetes etcd key-value store.

Which solution will meet these requirements?


**B.** Create a new AWS Key Management Service (AWS KMS) key. Enable Amazon EKS KMS secrets encryption on the Amazon EKS cluster.


**B.** This option is the most appropriate for encrypting secrets stored in the Kubernetes etcd key-value store within Amazon EKS. Amazon EKS KMS secrets encryption allows you to encrypt secrets in etcd using an AWS Key Management Service (KMS) key. This enhances security by ensuring that the secrets are encrypted at rest.

</details>

---

## Question 536

[Review topic](../sections/rds-aurora.md) · Source PDF page 197

A company wants to provide data scientists with near real-time read-only access to the company's production Amazon RDS for PostgreSQL
database. The database is currently configured as a Single-AZ database. The data scientists use complex queries that will not affect the
production database. The company needs a solution that is highly available.
Which solution will meet these requirements MOST cost-effectively?

**A.** Scale the existing production database in a maintenance window to provide enough power for the data scientists.

**B.** Change the setup from a Single-AZ to a Multi-AZ instance deployment with a larger secondary standby instance. Provide the data scientists
access to the secondary instance.

**C.** Change the setup from a Single-AZ to a Multi-AZ instance deployment. Provide two additional read replicas for the data scientists.

**D.** Change the setup from a Single-AZ to a Multi-AZ cluster deployment with two readable standby instances. Provide read endpoints to the
data scientists.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to provide data scientists with near real-time read-only access to the company's production Amazon RDS for PostgreSQL database. The database is currently configured as a Single-AZ database. The data scientists use complex queries that will not affect the production database. The company needs a solution that is highly available.

Which solution will meet these requirements MOST cost-effectively?


**C.** Change the setup from a Single-AZ to a Multi-AZ instance deployment. Provide two additional read replicas for the data scientists.


**C.** Changing to a Multi-AZ instance deployment and providing two additional read replicas for the data scientists is a good solution. Multi-AZ provides high availability, and read replicas can be used to offload read-only queries from the production database, allowing data scientists to run their complex queries without impacting the production environment.

</details>

---

## Question 537

[Review topic](../sections/ec2.md) · Source PDF page 198

A company runs a three-tier web application in the AWS Cloud that operates across three Availability Zones. The application architecture has an
Application Load Balancer, an Amazon EC2 web server that hosts user session states, and a MySQL database that runs on an EC2 instance. The
company expects sudden increases in application traffic. The company wants to be able to scale to meet future application capacity demands and
to ensure high availability across all three Availability Zones.
Which solution will meet these requirements?

**A.** Migrate the MySQL database to Amazon RDS for MySQL with a Multi-AZ DB cluster deployment. Use Amazon ElastiCache for Redis with
high availability to store session data and to cache reads. Migrate the web server to an Auto Scaling group that is in three Availability Zones.

**B.** Migrate the MySQL database to Amazon RDS for MySQL with a Multi-AZ DB cluster deployment. Use Amazon ElastiCache for Memcached
with high availability to store session data and to cache reads. Migrate the web server to an Auto Scaling group that is in three Availability
Zones.

**C.** Migrate the MySQL database to Amazon DynamoDB Use DynamoDB Accelerator (DAX) to cache reads. Store the session data in
DynamoDB. Migrate the web server to an Auto Scaling group that is in three Availability Zones.

**D.** Migrate the MySQL database to Amazon RDS for MySQL in a single Availability Zone. Use Amazon ElastiCache for Redis with high
availability to store session data and to cache reads. Migrate the web server to an Auto Scaling group that is in three Availability Zones.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a three-tier web application in the AWS Cloud that operates across three Availability Zones. The application architecture has an Application Load Balancer, an Amazon EC2 web server that hosts user session states, and a MySQL database that runs on an EC2 instance. The company expects sudden increases in application traffic. The company wants to be able to scale to meet future application capacity demands and to ensure high availability across all three Availability Zones.

Which solution will meet these requirements?


**A.** Migrate the MySQL database to Amazon RDS for MySQL with a Multi-AZ DB cluster deployment. Use Amazon ElastiCache for Redis with high availability to store session data and to cache reads. Migrate the web server to an Auto Scaling group that is in three Availability Zones.

Migrating the MySQL database to Amazon RDS for MySQL with a Multi-AZ DB cluster deployment provides high availability by replicating the database across multiple Availability Zones.
Using Amazon ElastiCache for Redis with high availability ensures that session data and reads are cached effectively, improving performance

</details>

---

## Question 538

[Review topic](../sections/global-delivery.md) · Source PDF page 198

A global video streaming company uses Amazon CloudFront as a content distribution network (CDN). The company wants to roll out content in a
phased manner across multiple countries. The company needs to ensure that viewers who are outside the countries to which the company rolls
out content are not able to view the content.
Which solution will meet these requirements?

**A.** Add geographic restrictions to the content in CloudFront by using an allow list. Set up a custom error message.

**B.** Set up a new URL tor restricted content. Authorize access by using a signed URL and cookies. Set up a custom error message.

**C.** Encrypt the data for the content that the company distributes. Set up a custom error message.

**D.** Create a new URL for restricted content. Set up a time-restricted access policy for signed URLs.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A global video streaming company uses Amazon CloudFront as a content distribution network (CDN). The company wants to roll out content in a phased manner across multiple countries. The company needs to ensure that viewers who are outside the countries to which the company rolls out content are not able to view the content.

Which solution will meet these requirements?


**A.** Add geographic restrictions to the content in CloudFront by using an allow list. Set up a custom error message.

CloudFront allows you to set up geographic restrictions by creating an allow list. This allows you to specify the countries from which viewers are allowed to access your content. Viewers from countries not in the allow list will be restricted from accessing the content.

</details>

---

## Question 539

[Review topic](../sections/disaster-recovery.md) · Source PDF page 198

A company wants to use the AWS Cloud to improve its on-premises disaster recovery (DR) configuration. The company's core production business
application uses Microsoft SQL Server Standard, which runs on a virtual machine (VM). The application has a recovery point objective (RPO) of 30
seconds or fewer and a recovery time objective (RTO) of 60 minutes. The DR solution needs to minimize costs wherever possible.
Which solution will meet these requirements?

**A.** Configure a multi-site active/active setup between the on-premises server and AWS by using Microsoft SQL Server Enterprise with Always
On availability groups.

**B.** Configure a warm standby Amazon RDS for SQL Server database on AWS. Configure AWS Database Migration Service (AWS DMS) to use
change data capture (CDC).

**C.** Use AWS Elastic Disaster Recovery configured to replicate disk changes to AWS as a pilot light.

**D.** Use third-party backup software to capture backups every night. Store a secondary set of backups in Amazon S3.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: C**

Elastic Disaster Recovery continuously replicates blocks into a low-cost staging area and launches recovery instances when needed. Test the workload to verify the stated RPO and RTO.

**Original companion notes (not independently verified):**

A company wants to use the AWS Cloud to improve its on-premises disaster recovery (DR) configuration. The company's core production business application uses Microsoft SQL Server Standard, which runs on a virtual machine (VM). The application has a recovery point objective (RPO) of 30 seconds or fewer and a recovery time objective (RTO) of 60 minutes. The DR solution needs to minimize costs wherever possible.

Which solution will meet these requirements?

</details>

---

## Question 540

[Review topic](../sections/rds-aurora.md) · Source PDF page 199

A company has an on-premises server that uses an Oracle database to process and store customer information. The company wants to use an
AWS database service to achieve higher availability and to improve application performance. The company also wants to offload reporting from its
primary database system.
Which solution will meet these requirements in the MOST operationally efficient way?

**A.** Use AWS Database Migration Service (AWS DMS) to create an Amazon RDS DB instance in multiple AWS Regions. Point the reporting
functions toward a separate DB instance from the primary DB instance.

**B.** Use Amazon RDS in a Single-AZ deployment to create an Oracle database. Create a read replica in the same zone as the primary DB
instance. Direct the reporting functions to the read replica.

**C.** Use Amazon RDS deployed in a Multi-AZ cluster deployment to create an Oracle database. Direct the reporting functions to use the reader
instance in the cluster deployment.

**D.** Use Amazon RDS deployed in a Multi-AZ instance deployment to create an Amazon Aurora database. Direct the reporting functions to the
reader instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an on-premises server that uses an Oracle database to process and store customer information. The company wants to use an AWS database service to achieve higher availability and to improve application performance. The company also wants to offload reporting from its primary database system.

Which solution will meet these requirements in the MOST operationally efficient way?


**D.** Use Amazon RDS deployed in a Multi-AZ instance deployment to create an Amazon Aurora database. Direct the reporting functions to the reader instances.

Deploying Amazon RDS in a Multi-AZ instance deployment ensures high availability by replicating the primary database instance in a different Availability Zone (AZ). This provides automatic failover in case of a hardware failure or maintenance event.

</details>

---

## Question 541

[Review topic](../sections/cost-governance.md) · Source PDF page 199

A company wants to build a web application on AWS. Client access requests to the website are not predictable and can be idle for a long time.
Only customers who have paid a subscription fee can have the ability to sign in and use the web application.
Which combination of steps will meet these requirements MOST cost-effectively? (Choose three.)

**A.** Create an AWS Lambda function to retrieve user information from Amazon DynamoDB. Create an Amazon API Gateway endpoint to accept
RESTful APIs. Send the API calls to the Lambda function.

**B.** Create an Amazon Elastic Container Service (Amazon ECS) service behind an Application Load Balancer to retrieve user information from
Amazon RDS. Create an Amazon API Gateway endpoint to accept RESTful APIs. Send the API calls to the Lambda function.

**C.** Create an Amazon Cognito user pool to authenticate users.

**D.** Create an Amazon Cognito identity pool to authenticate users.

**E.** Use AWS Amplify to serve the frontend web content with HTML, CSS, and JS. Use an integrated Amazon CloudFront configuration.

**F.** Use Amazon S3 static web hosting with PHP, CSS, and JS. Use Amazon CloudFront to serve the frontend web content.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to build a web application on AWS. Client access requests to the website are not predictable and can be idle for a long time. Only customers who have paid a subscription fee can have the ability to sign in and use the web application.

Which combination of steps will meet these requirements MOST cost-effectively? (Choose three.)


**A.** Create an AWS Lambda function to retrieve user information from Amazon DynamoDB. Create an Amazon API Gateway endpoint to accept RESTful APIs. Send the API calls to the Lambda function.


**C.** Create an Amazon Cognito user pool to authenticate users.


**E.** Use AWS Amplify to serve the frontend web content with HTML, CSS, and JS. Use an integrated Amazon CloudFront configuration.

AWS Lambda is a serverless computing service, and its pay-per-use pricing model can be cost-effective for sporadic and unpredictable workloads. DynamoDB is a NoSQL database that can scale with demand.

Amazon Cognito provides a scalable and secure user directory for your web application. It allows you to manage user identities and authentication in a cost-effective manner. User pools can be used to handle user registration, authentication, and account recovery.

AWS Amplify simplifies the development of scalable and secure cloud-powered web and mobile apps. CloudFront is a content delivery network (CDN) that can efficiently distribute your web content globally, improving performance.

</details>

---

## Question 542

[Review topic](../sections/s3.md) · Source PDF page 199

A media company uses an Amazon CloudFront distribution to deliver content over the internet. The company wants only premium customers to
have access to the media streams and file content. The company stores all content in an Amazon S3 bucket. The company also delivers content
on demand to customers for a specific purpose, such as movie rentals or music downloads.
Which solution will meet these requirements?

**A.** Generate and provide S3 signed cookies to premium customers.

**B.** Generate and provide CloudFront signed URLs to premium customers.

**C.** Use origin access control (OAC) to limit the access of non-premium customers.

**D.** Generate and activate field-level encryption to block non-premium customers.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A media company uses an Amazon CloudFront distribution to deliver content over the internet. The company wants only premium customers to have access to the media streams and file content. The company stores all content in an Amazon S3 bucket. The company also delivers content on demand to customers for a specific purpose, such as movie rentals or music downloads.

Which solution will meet these requirements?


**B.** Generate and provide CloudFront signed URLs to premium customers.

This solution involves generating signed URLs for the content, which allows access only to those who have the appropriate permissions. Signed URLs can be time-limited, and you can define custom policies specifying who can access the content and for how long.

</details>

---

## Question 543

[Review topic](../sections/ec2.md) · Source PDF page 200

A company runs Amazon EC2 instances in multiple AWS accounts that are individually bled. The company recently purchased a Savings Pian.
Because of changes in the company’s business requirements, the company has decommissioned a large number of EC2 instances. The company
wants to use its Savings Plan discounts on its other AWS accounts.
Which combination of steps will meet these requirements? (Choose two.)

**A.** From the AWS Account Management Console of the management account, turn on discount sharing from the billing preferences section.

**B.** From the AWS Account Management Console of the account that purchased the existing Savings Plan, turn on discount sharing from the
billing preferences section. Include all accounts.

**C.** From the AWS Organizations management account, use AWS Resource Access Manager (AWS RAM) to share the Savings Plan with other
accounts.

**D.** Create an organization in AWS Organizations in a new payer account. Invite the other AWS accounts to join the organization from the
management account.

**E.** Create an organization in AWS Organizations in the existing AWS account with the existing EC2 instances and Savings Plan. Invite the other
AWS accounts to join the organization from the management account.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: A, E (intended pair; question is ambiguous)**

Use consolidated billing in Organizations and enable discount sharing from the management account. E makes the existing purchaser the management account. A new management account as in D can also work when the purchaser joins, so the listed choices are not uniquely exclusive.

**Original companion notes (not independently verified):**

A company runs Amazon EC2 instances in multiple AWS accounts that are individually bled. The company recently purchased a Savings Pian. Because of changes in the company’s business requirements, the company has decommissioned a large number of EC2 instances. The company wants to use its Savings Plan discounts on its other AWS accounts.

Which combination of steps will meet these requirements? (Choose two.)

</details>

---

## Question 544

[Review topic](../sections/serverless.md) · Source PDF page 200

A retail company uses a regional Amazon API Gateway API for its public REST APIs. The API Gateway endpoint is a custom domain name that
points to an Amazon Route 53 alias record. A solutions architect needs to create a solution that has minimal effects on customers and minimal
data loss to release the new version of APIs.
Which solution will meet these requirements?

**A.** Create a canary release deployment stage for API Gateway. Deploy the latest API version. Point an appropriate percentage of traffic to the
canary stage. After API verification, promote the canary stage to the production stage.

**B.** Create a new API Gateway endpoint with a new version of the API in OpenAPI YAML file format. Use the import-to-update operation in
merge mode into the API in API Gateway. Deploy the new version of the API to the production stage.

**C.** Create a new API Gateway endpoint with a new version of the API in OpenAPI JSON file format. Use the import-to-update operation in
overwrite mode into the API in API Gateway. Deploy the new version of the API to the production stage.

**D.** Create a new API Gateway endpoint with new versions of the API definitions. Create a custom domain name for the new API Gateway API.
Point the Route 53 alias record to the new API Gateway API custom domain name.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A retail company uses a regional Amazon API Gateway API for its public REST APIs. The API Gateway endpoint is a custom domain name that points to an Amazon Route 53 alias record. A solutions architect needs to create a solution that has minimal effects on customers and minimal data loss to release the new version of APIs.

Which solution will meet these requirements?


**A.** Create a canary release deployment stage for API Gateway. Deploy the latest API version. Point an appropriate percentage of traffic to the canary stage. After API verification, promote the canary stage to the production stage.

A canary release deployment is a strategy in software development and release management where a new version of a software application or service is gradually rolled out to a small subset of users before making it available to the entire user base.

</details>

---

## Question 545

[Review topic](../sections/elb-asg.md) · Source PDF page 201

A company wants to direct its users to a backup static error page if the company's primary website is unavailable. The primary website's DNS
records are hosted in Amazon Route 53. The domain is pointing to an Application Load Balancer (ALB). The company needs a solution that
minimizes changes and infrastructure overhead.
Which solution will meet these requirements?

**A.** Update the Route 53 records to use a latency routing policy. Add a static error page that is hosted in an Amazon S3 bucket to the records so
that the traffic is sent to the most responsive endpoints.

**B.** Set up a Route 53 active-passive failover configuration. Direct traffic to a static error page that is hosted in an Amazon S3 bucket when
Route 53 health checks determine that the ALB endpoint is unhealthy.

**C.** Set up a Route 53 active-active configuration with the ALB and an Amazon EC2 instance that hosts a static error page as endpoints.
Configure Route 53 to send requests to the instance only if the health checks fail for the ALB.

**D.** Update the Route 53 records to use a multivalue answer routing policy. Create a health check. Direct traffic to the website if the health
check passes. Direct traffic to a static error page that is hosted in Amazon S3 if the health check does not pass.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to direct its users to a backup static error page if the company's primary website is unavailable. The primary website's DNS records are hosted in Amazon Route 53. The domain is pointing to an Application Load Balancer (ALB). The company needs a solution that minimizes changes and infrastructure overhead.

Which solution will meet these requirements?


**B.** Set up a Route 53 active-passive failover configuration. Direct traffic to a static error page that is hosted in an Amazon S3 bucket when Route 53 health checks determine that the ALB endpoint is unhealthy.

An active-passive failover configuration in Route 53 involves designating one endpoint (primary, in this case, the ALB) as active and another endpoint (S3 bucket hosting a static error page) as passive.
Route 53 health checks can be configured to monitor the health of the ALB endpoint. If the health checks determine that the ALB endpoint is unhealthy (i.e., the primary website is unavailable), Route 53 automatically directs traffic to the passive endpoint (S3 bucket with the static error page).

</details>

---

## Question 546

[Review topic](../sections/disaster-recovery.md) · Source PDF page 201

A recent analysis of a company's IT expenses highlights the need to reduce backup costs. The company's chief information officer wants to
simplify the on-premises backup infrastructure and reduce costs by eliminating the use of physical backup tapes. The company must preserve the
existing investment in the on-premises backup applications and workflows.
What should a solutions architect recommend?

**A.** Set up AWS Storage Gateway to connect with the backup applications using the NFS interface.

**B.** Set up an Amazon EFS file system that connects with the backup applications using the NFS interface.

**C.** Set up an Amazon EFS file system that connects with the backup applications using the iSCSI interface.

**D.** Set up AWS Storage Gateway to connect with the backup applications using the iSCSI-virtual tape library (VTL) interface.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A recent analysis of a company's IT expenses highlights the need to reduce backup costs. The company's chief information officer wants to simplify the on-premises backup infrastructure and reduce costs by eliminating the use of physical backup tapes. The company must preserve the existing investment in the on-premises backup applications and workflows.

What should a solutions architect recommend?


**D.** Set up AWS Storage Gateway to connect with the backup applications using the iSCSI-virtual tape library (VTL) interface.

AWS Storage Gateway provides a hybrid cloud storage service that enables on-premises applications to seamlessly use cloud storage.
The iSCSI-virtual tape library (VTL) interface of AWS Storage Gateway is designed to integrate with existing backup applications that use tape-based workflows. It emulates a tape library, allowing you to store virtual tapes in Amazon S3 or Glacier, providing a cost-effective and scalable alternative to physical tapes.

</details>

---

## Question 547

[Review topic](../sections/exam-revision.md) · Source PDF page 201

A company has data collection sensors at different locations. The data collection sensors stream a high volume of data to the company. The
company wants to design a platform on AWS to ingest and process high-volume streaming data. The solution must be scalable and support data
collection in near real time. The company must store the data in Amazon S3 for future reporting.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use Amazon Kinesis Data Firehose to deliver streaming data to Amazon S3.

**B.** Use AWS Glue to deliver streaming data to Amazon S3.

**C.** Use AWS Lambda to deliver streaming data and store the data to Amazon S3.

**D.** Use AWS Database Migration Service (AWS DMS) to deliver streaming data to Amazon S3.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has data collection sensors at different locations. The data collection sensors stream a high volume of data to the company. The company wants to design a platform on AWS to ingest and process high-volume streaming data. The solution must be scalable and support data collection in near real time. The company must store the data in Amazon S3 for future reporting.

Which solution will meet these requirements with the LEAST operational overhead?


**A.** Use Amazon Kinesis Data Firehose to deliver streaming data to Amazon S3.

Amazon Kinesis Data Firehose: It is a fully managed service for ingesting, transforming, and delivering streaming data to various destinations, including Amazon S3. Kinesis Data Firehose can scale automatically based on the volume of incoming data, and it simplifies the process of delivering data to S3 without the need for manual intervention.

</details>

---

## Question 548

[Review topic](../sections/exam-revision.md) · Source PDF page 202

A company has separate AWS accounts for its finance, data analytics, and development departments. Because of costs and security concerns,
the company wants to control which services each AWS account can use.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use AWS Systems Manager templates to control which AWS services each department can use.

**B.** Create organization units (OUs) for each department in AWS Organizations. Attach service control policies (SCPs) to the OUs.

**C.** Use AWS CloudFormation to automatically provision only the AWS services that each department can use.

**D.** Set up a list of products in AWS Service Catalog in the AWS accounts to manage and control the usage of specific AWS services.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has separate AWS accounts for its finance, data analytics, and development departments. Because of costs and security concerns, the company wants to control which services each AWS account can use.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Create organization units (OUs) for each department in AWS Organizations. Attach service control policies (SCPs) to the OUs.

AWS Organizations and Service Control Policies (SCPs): AWS Organizations provides a way to centrally manage and organize multiple AWS accounts. By creating separate organizational units (OUs) for each department, you can apply Service Control Policies (SCPs) to control which AWS services each department's accounts can access.

</details>

---

## Question 549

[Review topic](../sections/elb-asg.md) · Source PDF page 202

A company has created a multi-tier application for its ecommerce website. The website uses an Application Load Balancer that resides in the
public subnets, a web tier in the public subnets, and a MySQL cluster hosted on Amazon EC2 instances in the private subnets. The MySQL
database needs to retrieve product catalog and pricing information that is hosted on the internet by a third-party provider. A solutions architect
must devise a strategy that maximizes security without increasing operational overhead.
What should the solutions architect do to meet these requirements?

**A.** Deploy a NAT instance in the VPC. Route all the internet-based traffic through the NAT instance.

**B.** Deploy a NAT gateway in the public subnets. Modify the private subnet route table to direct all internet-bound traffic to the NAT gateway.

**C.** Configure an internet gateway and attach it to the VPModify the private subnet route table to direct internet-bound traffic to the internet
gateway.

**D.** Configure a virtual private gateway and attach it to the VPC. Modify the private subnet route table to direct internet-bound traffic to the
virtual private gateway.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has created a multi-tier application for its ecommerce website. The website uses an Application Load Balancer that resides in the public subnets, a web tier in the public subnets, and a MySQL cluster hosted on Amazon EC2 instances in the private subnets. The MySQL database needs to retrieve product catalog and pricing information that is hosted on the internet by a third-party provider. A solutions architect must devise a strategy that maximizes security without increasing operational overhead.

What should the solutions architect do to meet these requirements?


**B.** Deploy a NAT gateway in the public subnets. Modify the private subnet route table to direct all internet-bound traffic to the NAT gateway.

A NAT gateway is a fully managed service provided by AWS that allows instances in a private subnet to initiate outbound traffic to the internet while preventing inbound traffic from reaching those instances. It simplifies the process of enabling internet access for instances in private subnets without the need for managing a separate NAT instance.

</details>

---

## Question 550

[Review topic](../sections/iam.md) · Source PDF page 202

A company is using AWS Key Management Service (AWS KMS) keys to encrypt AWS Lambda environment variables. A solutions architect needs to
ensure that the required permissions are in place to decrypt and use the environment variables.
Which steps must the solutions architect take to implement the correct permissions? (Choose two.)

**A.** Add AWS KMS permissions in the Lambda resource policy.

**B.** Add AWS KMS permissions in the Lambda execution role.

**C.** Add AWS KMS permissions in the Lambda function policy.

**D.** Allow the Lambda execution role in the AWS KMS key policy.

**E.** Allow the Lambda resource policy in the AWS KMS key policy.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is using AWS Key Management Service (AWS KMS) keys to encrypt AWS Lambda environment variables. A solutions architect needs to ensure that the required permissions are in place to decrypt and use the environment variables.

Which steps must the solutions architect take to implement the correct permissions? (Choose two.)


**B.** Add AWS KMS permissions in the Lambda execution role.


**D.** Allow the Lambda execution role in the AWS KMS key policy.

The Lambda execution role is the role assumed by the Lambda function when it runs. It needs permissions to use the KMS key to decrypt the environment variables.
Grant the kms:Decrypt permission on the specific KMS key used for encryption to the Lambda execution role.

The AWS KMS key policy controls who can use the KMS key. To grant the Lambda execution role permission to decrypt using the KMS key, modify the key policy to include a statement allowing the Lambda execution role to perform kms:Decrypt on the key.

</details>

---

