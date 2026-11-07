# Practice questions 401-450

[Home](../README.md) · [All sets](README.md)

Answer notes are source-provided unless labeled suggested. These sets preserve the supplied PDF; they are not official AWS exams.

## Question 401

[Review topic](../sections/exam-revision.md) · Source PDF page 146

A company wants to use the AWS Cloud to make an existing application highly available and resilient. The current version of the application
resides in the company's data center. The application recently experienced data loss after a database server crashed because of an unexpected
power outage.
The company needs a solution that avoids any single points of failure. The solution must give the application the ability to scale to meet user
demand.
Which solution will meet these requirements?

**A.** Deploy the application servers by using Amazon EC2 instances in an Auto Scaling group across multiple Availability Zones. Use an Amazon
RDS DB instance in a Multi-AZ configuration.

**B.** Deploy the application servers by using Amazon EC2 instances in an Auto Scaling group in a single Availability Zone. Deploy the database
on an EC2 instance. Enable EC2 Auto Recovery.

**C.** Deploy the application servers by using Amazon EC2 instances in an Auto Scaling group across multiple Availability Zones. Use an Amazon
RDS DB instance with a read replica in a single Availability Zone. Promote the read replica to replace the primary DB instance if the primary DB
instance fails.

**D.** Deploy the application servers by using Amazon EC2 instances in an Auto Scaling group across multiple Availability Zones. Deploy the
primary and secondary database servers on EC2 instances across multiple Availability Zones. Use Amazon Elastic Block Store (Amazon EBS)
Multi-Attach to create shared storage between the instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to use the AWS Cloud to make an existing application highly available and resilient. The current version of the application resides in the company's data center. The application recently experienced data loss after a database server crashed because of an unexpected power outage.

The company needs a solution that avoids any single points of failure. The solution must give the application the ability to scale to meet user demand.

Which solution will meet these requirements?


**A.** Deploy the application servers by using Amazon EC2 instances in an Auto Scaling group across multiple Availability Zones. Use an Amazon RDS DB instance in a Multi-AZ configuration.

Auto Scaling Across Multiple Availability Zones: Deploying application servers using EC2 instances in an Auto Scaling group across multiple Availability Zones (AZs) helps avoid a single point of failure. If one AZ experiences an issue, the application can continue to operate in another AZ.

</details>

---

## Question 402

[Review topic](../sections/s3.md) · Source PDF page 147

A company needs to ingest and handle large amounts of streaming data that its application generates. The application runs on Amazon EC2
instances and sends data to Amazon Kinesis Data Streams, which is configured with default settings. Every other day, the application consumes
the data and writes the data to an Amazon S3 bucket for business intelligence (BI) processing. The company observes that Amazon S3 is not
receiving all the data that the application sends to Kinesis Data Streams.
What should a solutions architect do to resolve this issue?

**A.** Update the Kinesis Data Streams default settings by modifying the data retention period.

**B.** Update the application to use the Kinesis Producer Library (KPL) to send the data to Kinesis Data Streams.

**C.** Update the number of Kinesis shards to handle the throughput of the data that is sent to Kinesis Data Streams.

**D.** Turn on S3 Versioning within the S3 bucket to preserve every version of every object that is ingested in the S3 bucket.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: A**

The default stream retention is 24 hours, shorter than the two-day consumer interval. Increase retention beyond the processing interval and recovery margin.

**Original companion notes (not independently verified):**

A company needs to ingest and handle large amounts of streaming data that its application generates. The application runs on Amazon EC2 instances and sends data to Amazon Kinesis Data Streams, which is configured with default settings. Every other day, the application consumes the data and writes the data to an Amazon S3 bucket for business intelligence (BI) processing. The company observes that Amazon S3 is not receiving all the data that the application sends to Kinesis Data Streams.

What should a solutions architect do to resolve this issue?

</details>

---

## Question 403

[Review topic](../sections/iam.md) · Source PDF page 147

A developer has an application that uses an AWS Lambda function to upload files to Amazon S3 and needs the required permissions to perform
the task. The developer already has an IAM user with valid IAM credentials required for Amazon S3.
What should a solutions architect do to grant the permissions?

**A.** Add required IAM permissions in the resource policy of the Lambda function.

**B.** Create a signed request using the existing IAM credentials in the Lambda function.

**C.** Create a new IAM user and use the existing IAM credentials in the Lambda function.

**D.** Create an IAM execution role with the required permissions and attach the IAM role to the Lambda function.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A developer has an application that uses an AWS Lambda function to upload files to Amazon S3 and needs the required permissions to perform the task. The developer already has an IAM user with valid IAM credentials required for Amazon S3.

What should a solutions architect do to grant the permissions?


**D.** Create an IAM execution role with the required permissions and attach the IAM role to the Lambda function.

o grant the necessary permissions to an AWS Lambda function to upload files to Amazon S3, a solutions architect should create an IAM execution role with the required permissions and attach the IAM role to the Lambda function. This approach follows the principle of least privilege and ensures that the Lambda function can only access the resources it needs to perform its specific task.

</details>

---

## Question 404

[Review topic](../sections/serverless.md) · Source PDF page 147

A company has deployed a serverless application that invokes an AWS Lambda function when new documents are uploaded to an Amazon S3
bucket. The application uses the Lambda function to process the documents. After a recent marketing campaign, the company noticed that the
application did not process many of the documents.
What should a solutions architect do to improve the architecture of this application?

**A.** Set the Lambda function's runtime timeout value to 15 minutes.

**B.** Configure an S3 bucket replication policy. Stage the documents in the S3 bucket for later processing.

**C.** Deploy an additional Lambda function. Load balance the processing of the documents across the two Lambda functions.

**D.** Create an Amazon Simple Queue Service (Amazon SQS) queue. Send the requests to the queue. Configure the queue as an event source for
Lambda.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has deployed a serverless application that invokes an AWS Lambda function when new documents are uploaded to an Amazon S3 bucket. The application uses the Lambda function to process the documents. After a recent marketing campaign, the company noticed that the application did not process many of the documents.

What should a solutions architect do to improve the architecture of this application?


**D.** Create an Amazon Simple Queue Service (Amazon SQS) queue. Send the requests to the queue. Configure the queue as an event source for Lambda.

Introducing Amazon SQS as a queue allows for better decoupling between the S3 events and the document processing. This ensures that the Lambda function is not overwhelmed with spikes in incoming events, leading to missed document processing.

</details>

---

## Question 405

[Review topic](../sections/elb-asg.md) · Source PDF page 148

A solutions architect is designing the architecture for a software demonstration environment. The environment will run on Amazon EC2 instances
in an Auto Scaling group behind an Application Load Balancer (ALB). The system will experience significant increases in traffic during working
hours but is not required to operate on weekends.
Which combination of actions should the solutions architect take to ensure that the system can scale to meet demand? (Choose two.)

**A.** Use AWS Auto Scaling to adjust the ALB capacity based on request rate.

**B.** Use AWS Auto Scaling to scale the capacity of the VPC internet gateway.

**C.** Launch the EC2 instances in multiple AWS Regions to distribute the load across Regions.

**D.** Use a target tracking scaling policy to scale the Auto Scaling group based on instance CPU utilization.

**E.** Use scheduled scaling to change the Auto Scaling group minimum, maximum, and desired capacity to zero for weekends. Revert to the
default values at the start of the week.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing the architecture for a software demonstration environment. The environment will run on Amazon EC2 instances in an Auto Scaling group behind an Application Load Balancer (ALB). The system will experience significant increases in traffic during working hours but is not required to operate on weekends.

Which combination of actions should the solutions architect take to ensure that the system can scale to meet demand? (Choose two.)


**D.** Configure a target tracking policy that adjusts the number of EC2 instances in the Auto Scaling group based on demand.


**E.** Use scheduled scaling to change the Auto Scaling group minimum, maximum, and desired capacity to zero for weekends. Revert to the default values at the start of the week.

Explanation: An Application Load Balancer scales its own capacity automatically — you don't (and can't) attach an Auto Scaling policy to the ALB itself, so the old option A isn't a real configuration. The EC2 Auto Scaling group behind it is what needs a scaling policy (D), alongside scheduled scaling (E) to scale to zero on weekends.

This allows you to save costs and resources during weekends when the system is not required to operate. Scaling down the Auto Scaling group to zero instances during weekends and reverting to the default values at the start of the week ensures that you only incur costs when the system is actively in use.

</details>

---

## Question 406

[Review topic](../sections/vpc.md) · Source PDF page 148

A solutions architect is designing a two-tiered architecture that includes a public subnet and a database subnet. The web servers in the public
subnet must be open to the internet on port 443. The Amazon RDS for MySQL DB instance in the database subnet must be accessible only to the
web servers on port 3306.
Which combination of steps should the solutions architect take to meet these requirements? (Choose two.)

**A.** Create a network ACL for the public subnet. Add a rule to deny outbound traffic to 0.0.0.0/0 on port 3306.

**B.** Create a security group for the DB instance. Add a rule to allow traffic from the public subnet CIDR block on port 3306.

**C.** Create a security group for the web servers in the public subnet. Add a rule to allow traffic from 0.0.0.0/0 on port 443.

**D.** Create a security group for the DB instance. Add a rule to allow traffic from the web servers’ security group on port 3306.

**E.** Create a security group for the DB instance. Add a rule to deny all traffic except traffic from the web servers’ security group on port 3306.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is designing a two-tiered architecture that includes a public subnet and a database subnet. The web servers in the public subnet must be open to the internet on port 443. The Amazon RDS for MySQL DB instance in the database subnet must be accessible only to the web servers on port 3306.

Which combination of steps should the solutions architect take to meet these requirements? (Choose two.)


**C.** Create a security group for the web servers in the public subnet. Add a rule to allow traffic from 0.0.0.0/0 on port 443.


**D.** Create a security group for the DB instance. Add a rule to allow traffic from the web servers’ security group on port 3306.

This allows inbound traffic from the internet on port 443 to the web servers.

This ensures that the RDS instance is accessible only from the web servers in the public subnet.

</details>

---

## Question 407

[Review topic](../sections/ec2-storage.md) · Source PDF page 148

A company is implementing a shared storage solution for a gaming application that is hosted in the AWS Cloud. The company needs the ability to
use Lustre clients to access data. The solution must be fully managed.
Which solution meets these requirements?

**A.** Create an AWS DataSync task that shares the data as a mountable file system. Mount the file system to the application server.

**B.** Create an AWS Storage Gateway file gateway. Create a file share that uses the required client protocol. Connect the application server to the
file share.

**C.** Create an Amazon Elastic File System (Amazon EFS) file system, and configure it to support Lustre. Attach the file system to the origin
server. Connect the application server to the file system.

**D.** Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is implementing a shared storage solution for a gaming application that is hosted in the AWS Cloud. The company needs the ability to use Lustre clients to access data. The solution must be fully managed.

Which solution meets these requirements?


**D.** Create an Amazon FSx for Lustre file system. Attach the file system to the origin server. Connect the application server to the file system.

Amazon FSx for Lustre: Amazon FSx for Lustre is a fully managed service that provides high-performance shared storage. It is specifically designed to be used with Lustre, making it a suitable solution for Lustre clients.

Fully Managed: Amazon FSx for Lustre is a fully managed service, meaning that AWS takes care of maintenance, updates, and other operational tasks, reducing the management overhead for the company.

</details>

---

## Question 408

[Review topic](../sections/cloud-foundations.md) · Source PDF page 149

A company runs an application that receives data from thousands of geographically dispersed remote devices that use UDP. The application
processes the data immediately and sends a message back to the device if necessary. No data is stored.
The company needs a solution that minimizes latency for the data transmission from the devices. The solution also must provide rapid failover to
another AWS Region.
Which solution will meet these requirements?

**A.** Configure an Amazon Route 53 failover routing policy. Create a Network Load Balancer (NLB) in each of the two Regions. Configure the NLB
to invoke an AWS Lambda function to process the data.

**B.** Use AWS Global Accelerator. Create a Network Load Balancer (NLB) in each of the two Regions as an endpoint. Create an Amazon Elastic
Container Service (Amazon ECS) cluster with the Fargate launch type. Create an ECS service on the cluster. Set the ECS service as the target
for the NLProcess the data in Amazon ECS.

**C.** Use AWS Global Accelerator. Create an Application Load Balancer (ALB) in each of the two Regions as an endpoint. Create an Amazon
Elastic Container Service (Amazon ECS) cluster with the Fargate launch type. Create an ECS service on the cluster. Set the ECS service as the
target for the ALB. Process the data in Amazon ECS.

**D.** Configure an Amazon Route 53 failover routing policy. Create an Application Load Balancer (ALB) in each of the two Regions. Create an
Amazon Elastic Container Service (Amazon ECS) cluster with the Fargate launch type. Create an ECS service on the cluster. Set the ECS
service as the target for the ALB. Process the data in Amazon ECS.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs an application that receives data from thousands of geographically dispersed remote devices that use UDP. The application processes the data immediately and sends a message back to the device if necessary. No data is stored.

The company needs a solution that minimizes latency for the data transmission from the devices. The solution also must provide rapid failover to another AWS Region.

Which solution will meet these requirements?


**B.** Use AWS Global Accelerator. Create a Network Load Balancer (NLB) in each of the two Regions as an endpoint. Create an Amazon Elastic Container Service (Amazon ECS) cluster with the Fargate launch type. Create an ECS service on the cluster. Set the ECS service as the target for the NLProcess the data in Amazon ECS.

AWS Global Accelerator: AWS Global Accelerator provides static IP addresses that act as a fixed entry point to your application. It routes traffic over the AWS global network to the optimal AWS endpoint based on health, geography, and routing policies.

Network Load Balancer (NLB): NLB is well-suited for UDP-based traffic, and it's designed for high-performance, low-latency applications. In this case, it can efficiently handle the thousands of geographically dispersed remote devices sending UDP traffic.

Amazon ECS with Fargate Launch Type: Using ECS with Fargate allows you to deploy and run containers without managing the underlying infrastructure. This setup can efficiently handle the immediate processing of data without the need to manage the underlying servers.

</details>

---

## Question 409

[Review topic](../sections/elb-asg.md) · Source PDF page 149

A solutions architect must migrate a Windows Internet Information Services (IIS) web application to AWS. The application currently relies on a file
share hosted in the user's on-premises network-attached storage (NAS). The solutions architect has proposed migrating the IIS web servers to
Amazon EC2 instances in multiple Availability Zones that are connected to the storage solution, and configuring an Elastic Load Balancer attached
to the instances.
Which replacement to the on-premises file share is MOST resilient and durable?

**A.** Migrate the file share to Amazon RDS.

**B.** Migrate the file share to AWS Storage Gateway.

**C.** Migrate the file share to Amazon FSx for Windows File Server.

**D.** Migrate the file share to Amazon Elastic File System (Amazon EFS).

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect must migrate a Windows Internet Information Services (IIS) web application to AWS. The application currently relies on a file share hosted in the user's on-premises network-attached storage (NAS). The solutions architect has proposed migrating the IIS web servers to Amazon EC2 instances in multiple Availability Zones that are connected to the storage solution, and configuring an Elastic Load Balancer attached to the instances.

Which replacement to the on-premises file share is MOST resilient and durable?


**C.** Migrate the file share to Amazon FSx for Windows File Server.

Amazon FSx for Windows File Server: Amazon FSx is a fully managed file storage service that is compatible with Windows file systems. Amazon FSx for Windows File Server is specifically designed for Windows workloads, including IIS web applications. It provides a highly available and durable file system that can be accessed by multiple EC2 instances in different Availability Zones.

</details>

---

## Question 410

[Review topic](../sections/ec2-storage.md) · Source PDF page 149

A company is deploying a new application on Amazon EC2 instances. The application writes data to Amazon Elastic Block Store (Amazon EBS)
volumes. The company needs to ensure that all data that is written to the EBS volumes is encrypted at rest.
Which solution will meet this requirement?

**A.** Create an IAM role that specifies EBS encryption. Attach the role to the EC2 instances.

**B.** Create the EBS volumes as encrypted volumes. Attach the EBS volumes to the EC2 instances.

**C.** Create an EC2 instance tag that has a key of Encrypt and a value of True. Tag all instances that require encryption at the EBS level.

**D.** Create an AWS Key Management Service (AWS KMS) key policy that enforces EBS encryption in the account. Ensure that the key policy is
active.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is deploying a new application on Amazon EC2 instances. The application writes data to Amazon Elastic Block Store (Amazon EBS) volumes. The company needs to ensure that all data that is written to the EBS volumes is encrypted at rest.

Which solution will meet this requirement?


**B.** Create the EBS volumes as encrypted volumes. Attach the EBS volumes to the EC2 instances.

By creating the EBS volumes as encrypted volumes, you ensure that all data written to those volumes is automatically encrypted. This provides a straightforward and effective solution for meeting the encryption-at-rest requirement.

</details>

---

## Question 411

[Review topic](../sections/rds-aurora.md) · Source PDF page 150

A company has a web application with sporadic usage patterns. There is heavy usage at the beginning of each month, moderate usage at the start
of each week, and unpredictable usage during the week. The application consists of a web server and a MySQL database server running inside the
data center. The company would like to move the application to the AWS Cloud, and needs to select a cost-effective database platform that will
not require database modifications.
Which solution will meet these requirements?

**A.** Amazon DynamoDB

**B.** Amazon RDS for MySQL

**C.** MySQL-compatible Amazon Aurora Serverless

**D.** MySQL deployed on Amazon EC2 in an Auto Scaling group

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a web application with sporadic usage patterns. There is heavy usage at the beginning of each month, moderate usage at the start of each week, and unpredictable usage during the week. The application consists of a web server and a MySQL database server running inside the data center. The company would like to move the application to the AWS Cloud, and needs to select a cost-effective database platform that will not require database modifications.

Which solution will meet these requirements?


**C.** MySQL-compatible Amazon Aurora Serverless

Aurora Serverless is a serverless option for MySQL-compatible databases.
It automatically adjusts the database capacity based on actual usage, making it suitable for sporadic usage patterns.
It is MySQL-compatible, so it won't require significant database modifications.

</details>

---

## Question 412

[Review topic](../sections/s3.md) · Source PDF page 150

An image-hosting company stores its objects in Amazon S3 buckets. The company wants to avoid accidental exposure of the objects in the S3
buckets to the public. All S3 objects in the entire AWS account need to remain private.
Which solution will meet these requirements?

**A.** Use Amazon GuardDuty to monitor S3 bucket policies. Create an automatic remediation action rule that uses an AWS Lambda function to
remediate any change that makes the objects public.

**B.** Use AWS Trusted Advisor to find publicly accessible S3 buckets. Configure email notifications in Trusted Advisor when a change is
detected. Manually change the S3 bucket policy if it allows public access.

**C.** Use AWS Resource Access Manager to find publicly accessible S3 buckets. Use Amazon Simple Notification Service (Amazon SNS) to
invoke an AWS Lambda function when a change is detected. Deploy a Lambda function that programmatically remediates the change.

**D.** Use the S3 Block Public Access feature on the account level. Use AWS Organizations to create a service control policy (SCP) that prevents
IAM users from changing the setting. Apply the SCP to the account.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An image-hosting company stores its objects in Amazon S3 buckets. The company wants to avoid accidental exposure of the objects in the S3 buckets to the public. All S3 objects in the entire AWS account need to remain private.

Which solution will meet these requirements?


**D.** Use the S3 Block Public Access feature on the account level. Use AWS Organizations to create a service control policy (SCP) that prevents IAM users from changing the setting. Apply the SCP to the account.

AWS Organizations allows you to create service control policies (SCPs) that set fine-grained permissions for member accounts. In this case, you can create an SCP that prevents IAM users from changing the S3 Block Public Access settings. Applying this SCP to the account ensures that the configured public access settings remain in place and cannot be altered by IAM users.

</details>

---

## Question 413

[Review topic](../sections/exam-revision.md) · Source PDF page 150

An ecommerce company is experiencing an increase in user traffic. The company’s store is deployed on Amazon EC2 instances as a two-tier web
application consisting of a web tier and a separate database tier. As traffic increases, the company notices that the architecture is causing
significant delays in sending timely marketing and order confirmation email to users. The company wants to reduce the time it spends resolving
complex email delivery issues and minimize operational overhead.
What should a solutions architect do to meet these requirements?

**A.** Create a separate application tier using EC2 instances dedicated to email processing.

**B.** Configure the web instance to send email through Amazon Simple Email Service (Amazon SES).

**C.** Configure the web instance to send email through Amazon Simple Notification Service (Amazon SNS).

**D.** Create a separate application tier using EC2 instances dedicated to email processing. Place the instances in an Auto Scaling group.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An ecommerce company is experiencing an increase in user traffic. The company’s store is deployed on Amazon EC2 instances as a two-tier web application consisting of a web tier and a separate database tier. As traffic increases, the company notices that the architecture is causing significant delays in sending timely marketing and order confirmation email to users. The company wants to reduce the time it spends resolving complex email delivery issues and minimize operational overhead.

What should a solutions architect do to meet these requirements?


**B.** Configure the web instance to send email through Amazon Simple Email Service (Amazon SES).

Amazon Simple Email Service (Amazon SES) is a fully managed email sending service. By configuring the web instances to send emails through Amazon SES, the ecommerce company can offload the complexity of email delivery to a reliable and scalable service.

</details>

---

## Question 414

[Review topic](../sections/exam-revision.md) · Source PDF page 151

A company has a business system that generates hundreds of reports each day. The business system saves the reports to a network share in CSV
format. The company needs to store this data in the AWS Cloud in near-real time for analysis.
Which solution will meet these requirements with the LEAST administrative overhead?

**A.** Use AWS DataSync to transfer the files to Amazon S3. Create a scheduled task that runs at the end of each day.

**B.** Create an Amazon S3 File Gateway. Update the business system to use a new network share from the S3 File Gateway.

**C.** Use AWS DataSync to transfer the files to Amazon S3. Create an application that uses the DataSync API in the automation workflow.

**D.** Deploy an AWS Transfer for SFTP endpoint. Create a script that checks for new files on the network share and uploads the new files by
using SFTP.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: B**

S3 File Gateway exposes a network file share and asynchronously uploads files to S3 with little application change.

**Original companion notes (not independently verified):**

A company has a business system that generates hundreds of reports each day. The business system saves the reports to a network share in CSV format. The company needs to store this data in the AWS Cloud in near-real time for analysis.

Which solution will meet these requirements with the LEAST administrative overhead?

</details>

---

## Question 415

[Review topic](../sections/s3.md) · Source PDF page 151

A company is storing petabytes of data in Amazon S3 Standard. The data is stored in multiple S3 buckets and is accessed with varying frequency.
The company does not know access patterns for all the data. The company needs to implement a solution for each S3 bucket to optimize the cost
of S3 usage.
Which solution will meet these requirements with the MOST operational efficiency?

**A.** Create an S3 Lifecycle configuration with a rule to transition the objects in the S3 bucket to S3 Intelligent-Tiering.

**B.** Use the S3 storage class analysis tool to determine the correct tier for each object in the S3 bucket. Move each object to the identified
storage tier.

**C.** Create an S3 Lifecycle configuration with a rule to transition the objects in the S3 bucket to S3 Glacier Instant Retrieval.

**D.** Create an S3 Lifecycle configuration with a rule to transition the objects in the S3 bucket to S3 One Zone-Infrequent Access (S3 One Zone-
IA).

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is storing petabytes of data in Amazon S3 Standard. The data is stored in multiple S3 buckets and is accessed with varying frequency. The company does not know access patterns for all the data. The company needs to implement a solution for each S3 bucket to optimize the cost of S3 usage.

Which solution will meet these requirements with the MOST operational efficiency?


**A.** Create an S3 Lifecycle configuration with a rule to transition the objects in the S3 bucket to S3 Intelligent-Tiering.

S3 Intelligent-Tiering: This storage class is designed to automatically and dynamically move objects between two access tiers – frequent and infrequent access – based on changing access patterns. It is a good fit for data with unknown or changing access patterns. It provides cost savings compared to S3 Standard while maintaining low-latency access to frequently accessed objects.

</details>

---

## Question 416

[Review topic](../sections/rds-aurora.md) · Source PDF page 151

A rapidly growing global ecommerce company is hosting its web application on AWS. The web application includes static content and dynamic
content. The website stores online transaction processing (OLTP) data in an Amazon RDS database The website’s users are experiencing slow
page loads.
Which combination of actions should a solutions architect take to resolve this issue? (Choose two.)

**A.** Configure an Amazon Redshift cluster.

**B.** Set up an Amazon CloudFront distribution.

**C.** Host the dynamic web content in Amazon S3.

**D.** Create a read replica for the RDS DB instance.

**E.** Configure a Multi-AZ deployment for the RDS DB instance.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A rapidly growing global ecommerce company is hosting its web application on AWS. The web application includes static content and dynamic content. The website stores online transaction processing (OLTP) data in an Amazon RDS database The website’s users are experiencing slow page loads.

Which combination of actions should a solutions architect take to resolve this issue? (Choose two.)


**B.** Set up an Amazon CloudFront distribution.


**D.** Create a read replica for the RDS DB instance.

Amazon CloudFront is a content delivery network (CDN) that can improve the performance of a website by caching static content closer to the users. This reduces latency and improves page load times.
Configure CloudFront to distribute static content such as images, stylesheets, and JavaScript files. This will offload the serving of static assets from the web servers, improving overall website performance.

Creating a read replica for the Amazon RDS database allows you to offload read traffic from the primary database, improving the overall database performance.

</details>

---

## Question 417

[Review topic](../sections/ec2.md) · Source PDF page 152

A company uses Amazon EC2 instances and AWS Lambda functions to run its application. The company has VPCs with public subnets and private
subnets in its AWS account. The EC2 instances run in a private subnet in one of the VPCs. The Lambda functions need direct network access to
the EC2 instances for the application to work.
The application will run for at least 1 year. The company expects the number of Lambda functions that the application uses to increase during that
time. The company wants to maximize its savings on all application resources and to keep network latency between the services low.
Which solution will meet these requirements?

**A.** Purchase an EC2 Instance Savings Plan Optimize the Lambda functions’ duration and memory usage and the number of invocations.
Connect the Lambda functions to the private subnet that contains the EC2 instances.

**B.** Purchase an EC2 Instance Savings Plan Optimize the Lambda functions' duration and memory usage, the number of invocations, and the
amount of data that is transferred. Connect the Lambda functions to a public subnet in the same VPC where the EC2 instances run.

**C.** Purchase a Compute Savings Plan. Optimize the Lambda functions’ duration and memory usage, the number of invocations, and the
amount of data that is transferred. Connect the Lambda functions to the private subnet that contains the EC2 instances.

**D.** Purchase a Compute Savings Plan. Optimize the Lambda functions’ duration and memory usage, the number of invocations, and the
amount of data that is transferred. Keep the Lambda functions in the Lambda service VPC.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: C**

Compute Savings Plans cover eligible EC2 and Lambda usage. Connect Lambda to the VPC private subnets for direct access and optimize execution and transfer costs.

**Original companion notes (not independently verified):**

A company uses Amazon EC2 instances and AWS Lambda functions to run its application. The company has VPCs with public subnets and private subnets in its AWS account. The EC2 instances run in a private subnet in one of the VPCs. The Lambda functions need direct network access to the EC2 instances for the application to work.

The application will run for at least 1 year. The company expects the number of Lambda functions that the application uses to increase during that time. The company wants to maximize its savings on all application resources and to keep network latency between the services low.

Which solution will meet these requirements?

</details>

---

## Question 418

[Review topic](../sections/iam.md) · Source PDF page 152

A solutions architect needs to allow team members to access Amazon S3 buckets in two different AWS accounts: a development account and a
production account. The team currently has access to S3 buckets in the development account by using unique IAM users that are assigned to an
IAM group that has appropriate permissions in the account.
The solutions architect has created an IAM role in the production account. The role has a policy that grants access to an S3 bucket in the
production account.
Which solution will meet these requirements while complying with the principle of least privilege?

**A.** Attach the Administrator Access policy to the development account users.

**B.** Add the development account as a principal in the trust policy of the role in the production account.

**C.** Turn off the S3 Block Public Access feature on the S3 bucket in the production account.

**D.** Create a user in the production account with unique credentials for each team member.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect needs to allow team members to access Amazon S3 buckets in two different AWS accounts: a development account and a production account. The team currently has access to S3 buckets in the development account by using unique IAM users that are assigned to an IAM group that has appropriate permissions in the account.

The solutions architect has created an IAM role in the production account. The role has a policy that grants access to an S3 bucket in the production account.

Which solution will meet these requirements while complying with the principle of least privilege?


**B.** Add the development account as a principal in the trust policy of the role in the production account.

By adding the development account as a principal in the trust policy of the IAM role in the production account, you enable IAM users in the development account to assume the role and gain temporary permissions to access the S3 bucket in the production account.

This approach follows the principle of least privilege because it allows users in the development account to access only the specific resources (S3 bucket) defined in the trust policy of the IAM role.

</details>

---

## Question 419

[Review topic](../sections/iam.md) · Source PDF page 153

A company uses AWS Organizations with all features enabled and runs multiple Amazon EC2 workloads in the ap-southeast-2 Region. The
company has a service control policy (SCP) that prevents any resources from being created in any other Region. A security policy requires the
company to encrypt all data at rest.
An audit discovers that employees have created Amazon Elastic Block Store (Amazon EBS) volumes for EC2 instances without encrypting the
volumes. The company wants any new EC2 instances that any IAM user or root user launches in ap-southeast-2 to use encrypted EBS volumes.
The company wants a solution that will have minimal effect on employees who create EBS volumes.
Which combination of steps will meet these requirements? (Choose two.)

**A.** In the Amazon EC2 console, select the EBS encryption account attribute and define a default encryption key.

**B.** Create an IAM permission boundary. Attach the permission boundary to the root organizational unit (OU). Define the boundary to deny the
ec2:CreateVolume action when the ec2:Encrypted condition equals false.

**C.** Create an SCP. Attach the SCP to the root organizational unit (OU). Define the SCP to deny the ec2:CreateVolume action whenthe
ec2:Encrypted condition equals false.

**D.** Update the IAM policies for each account to deny the ec2:CreateVolume action when the ec2:Encrypted condition equals false.

**E.** In the Organizations management account, specify the Default EBS volume encryption setting.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses AWS Organizations with all features enabled and runs multiple Amazon EC2 workloads in the ap-southeast-2 Region. The company has a service control policy (SCP) that prevents any resources from being created in any other Region. A security policy requires the company to encrypt all data at rest.

An audit discovers that employees have created Amazon Elastic Block Store (Amazon EBS) volumes for EC2 instances without encrypting the volumes. The company wants any new EC2 instances that any IAM user or root user launches in ap-southeast-2 to use encrypted EBS volumes. The company wants a solution that will have minimal effect on employees who create EBS volumes.

Which combination of steps will meet these requirements? (Choose two.)


**A.** In each AWS account that contains EC2 instances in ap-southeast-2, specify the Default EBS volume encryption setting.


**C.** Create an SCP. Attach the SCP to the root organizational unit (OU). Define the SCP to deny the ec2:CreateVolume action whenthe ec2:Encrypted condition equals false.

Explanation: "Default EBS encryption" is a per-account, per-Region setting — it cannot be configured centrally from the Organizations management account (ruling out the old option E). It has to be set in each member account instead, paired with the SCP (C) as a guardrail that blocks anyone who creates a volume without encryption regardless.

</details>

---

## Question 420

[Review topic](../sections/rds-aurora.md) · Source PDF page 153

A company wants to use an Amazon RDS for PostgreSQL DB cluster to simplify time-consuming database administrative tasks for production
database workloads. The company wants to ensure that its database is highly available and will provide automatic failover support in most
scenarios in less than 40 seconds. The company wants to offload reads off of the primary instance and keep costs as low as possible.
Which solution will meet these requirements?

**A.** Use an Amazon RDS Multi-AZ DB instance deployment. Create one read replica and point the read workload to the read replica.

**B.** Use an Amazon RDS Multi-AZ DB duster deployment Create two read replicas and point the read workload to the read replicas.

**C.** Use an Amazon RDS Multi-AZ DB instance deployment. Point the read workload to the secondary instances in the Multi-AZ pair.

**D.** Use an Amazon RDS Multi-AZ DB cluster deployment Point the read workload to the reader endpoint.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to use an Amazon RDS for PostgreSQL DB cluster to simplify time-consuming database administrative tasks for production database workloads. The company wants to ensure that its database is highly available and will provide automatic failover support in most scenarios in less than 40 seconds. The company wants to offload reads off of the primary instance and keep costs as low as possible.

Which solution will meet these requirements?


**D.** Use an Amazon RDS Multi-AZ DB cluster deployment Point the read workload to the reader endpoint.

Amazon RDS Multi-AZ DB Cluster Deployment: This provides high availability by automatically replicating data to a standby instance in a different Availability Zone. In case of a failure, Amazon RDS automatically fails over to the standby instance.

</details>

---

## Question 421

[Review topic](../sections/iam.md) · Source PDF page 154

A company runs a highly available SFTP service. The SFTP service uses two Amazon EC2 Linux instances that run with elastic IP addresses to
accept traffic from trusted IP sources on the internet. The SFTP service is backed by shared storage that is attached to the instances. User
accounts are created and managed as Linux users in the SFTP servers.
The company wants a serverless option that provides high IOPS performance and highly configurable security. The company also wants to
maintain control over user permissions.
Which solution will meet these requirements?

**A.** Create an encrypted Amazon Elastic Block Store (Amazon EBS) volume. Create an AWS Transfer Family SFTP service with a public endpoint
that allows only trusted IP addresses. Attach the EBS volume to the SFTP service endpoint. Grant users access to the SFTP service.

**B.** Create an encrypted Amazon Elastic File System (Amazon EFS) volume. Create an AWS Transfer Family SFTP service with elastic IP
addresses and a VPC endpoint that has internet-facing access. Attach a security group to the endpoint that allows only trusted IP addresses.
Attach the EFS volume to the SFTP service endpoint. Grant users access to the SFTP service.

**C.** Create an Amazon S3 bucket with default encryption enabled. Create an AWS Transfer Family SFTP service with a public endpoint that
allows only trusted IP addresses. Attach the S3 bucket to the SFTP service endpoint. Grant users access to the SFTP service.

**D.** Create an Amazon S3 bucket with default encryption enabled. Create an AWS Transfer Family SFTP service with a VPC endpoint that has
internal access in a private subnet. Attach a security group that allows only trusted IP addresses. Attach the S3 bucket to the SFTP service
endpoint. Grant users access to the SFTP service.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a highly available SFTP service. The SFTP service uses two Amazon EC2 Linux instances that run with elastic IP addresses to accept traffic from trusted IP sources on the internet. The SFTP service is backed by shared storage that is attached to the instances. User accounts are created and managed as Linux users in the SFTP servers.

The company wants a serverless option that provides high IOPS performance and highly configurable security. The company also wants to maintain control over user permissions.

Which solution will meet these requirements?


**B.** Create an encrypted Amazon Elastic File System (Amazon EFS) volume. Create an AWS Transfer Family SFTP service with elastic IP addresses and a VPC endpoint that has internet-facing access. Attach a security group to the endpoint that allows only trusted IP addresses. Attach the EFS volume to the SFTP service endpoint. Grant users access to the SFTP service.

</details>

---

## Question 422

[Review topic](../sections/s3.md) · Source PDF page 154

A company is developing a new machine learning (ML) model solution on AWS. The models are developed as independent microservices that
fetch approximately 1 GB of model data from Amazon S3 at startup and load the data into memory. Users access the models through an
asynchronous API. Users can send a request or a batch of requests and specify where the results should be sent.
The company provides models to hundreds of users. The usage patterns for the models are irregular. Some models could be unused for days or
weeks. Other models could receive batches of thousands of requests at a time.
Which design should a solutions architect recommend to meet these requirements?

**A.** Direct the requests from the API to a Network Load Balancer (NLB). Deploy the models as AWS Lambda functions that are invoked by the
NLB.

**B.** Direct the requests from the API to an Application Load Balancer (ALB). Deploy the models as Amazon Elastic Container Service (Amazon
ECS) services that read from an Amazon Simple Queue Service (Amazon SQS) queue. Use AWS App Mesh to scale the instances of the ECS
cluster based on the SQS queue size.

**C.** Direct the requests from the API into an Amazon Simple Queue Service (Amazon SQS) queue. Deploy the models as AWS Lambda functions
that are invoked by SQS events. Use AWS Auto Scaling to increase the number of vCPUs for the Lambda functions based on the SQS queue
size.

**D.** Direct the requests from the API into an Amazon Simple Queue Service (Amazon SQS) queue. Deploy the models as Amazon Elastic
Container Service (Amazon ECS) services that read from the queue. Enable AWS Auto Scaling on Amazon ECS for both the cluster and copies
of the service based on the queue size.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is developing a new machine learning (ML) model solution on AWS. The models are developed as independent microservices that fetch approximately 1 GB of model data from Amazon S3 at startup and load the data into memory. Users access the models through an asynchronous API. Users can send a request or a batch of requests and specify where the results should be sent.

The company provides models to hundreds of users. The usage patterns for the models are irregular. Some models could be unused for days or weeks. Other models could receive batches of thousands of requests at a time.

Which design should a solutions architect recommend to meet these requirements?


**D.** Direct the requests from the API into an Amazon Simple Queue Service (Amazon SQS) queue. Deploy the models as Amazon Elastic Container Service (Amazon ECS) services that read from the queue. Enable AWS Auto Scaling on Amazon ECS for both the cluster and copies of the service based on the queue size.

Amazon ECS Services: Deploying the models as Amazon ECS services allows for flexibility in managing the containerized applications. ECS services can efficiently handle the startup process of fetching model data from Amazon S3 and loading it into memory.

Application Load Balancer (ALB): The ALB is used to direct requests from the API to the ECS services. ALB provides advanced routing capabilities and can handle the asynchronous API requirements.

AWS App Mesh: AWS App Mesh can be used to scale the instances of the ECS cluster based on the SQS queue size. This allows for dynamic scaling based on demand, helping to efficiently use resources.

</details>

---

## Question 423

[Review topic](../sections/iam.md) · Source PDF page 155

A solutions architect wants to use the following JSON text as an identity-based policy to grant specific permissions:
Which IAM principals can the solutions architect attach this policy to? (Choose two.)

**A.** Role

**B.** Group

**C.** Organization

**D.** Amazon Elastic Container Service (Amazon ECS) resource

**E.** Amazon EC2 resource

**Policy / option transcription**

Identity policy: Effect Allow; Action [ssm:ListDocuments, ssm:GetDocument]; Resource *; Sid is an empty string; Version 2012-10-17.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: A, B**

Identity-based policies attach to IAM roles, groups or users; organizations and compute resources are not identity-policy attachment targets.

**Original companion notes (not independently verified):**

Josn format

</details>

---

## Question 424

[Review topic](../sections/ec2.md) · Source PDF page 155

A company is running a custom application on Amazon EC2 On-Demand Instances. The application has frontend nodes that need to run 24 hours
a day, 7 days a week and backend nodes that need to run only for a short time based on workload. The number of backend nodes varies during the
day.
The company needs to scale out and scale in more instances based on workload.
Which solution will meet these requirements MOST cost-effectively?

**A.** Use Reserved Instances for the frontend nodes. Use AWS Fargate for the backend nodes.

**B.** Use Reserved Instances for the frontend nodes. Use Spot Instances for the backend nodes.

**C.** Use Spot Instances for the frontend nodes. Use Reserved Instances for the backend nodes.

**D.** Use Spot Instances for the frontend nodes. Use AWS Fargate for the backend nodes.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is running a custom application on Amazon EC2 On-Demand Instances. The application has frontend nodes that need to run 24 hours a day, 7 days a week and backend nodes that need to run only for a short time based on workload. The number of backend nodes varies during the day.

The company needs to scale out and scale in more instances based on workload.

Which solution will meet these requirements MOST cost-effectively?


**B.** Use Reserved Instances for the frontend nodes. Use Spot Instances for the backend nodes.

Reserved Instances (RIs) for Frontend Nodes: Since the frontend nodes need to run 24/7, Reserved Instances provide a significant cost savings compared to On-Demand pricing. RIs are a commitment to a consistent usage pattern, making them suitable for instances that need to run continuously.

Spot Instances for Backend Nodes: Spot Instances are a cost-effective option for workloads that can be interrupted or are flexible regarding availability. As the number of backend nodes varies during the day, using Spot Instances allows you to take advantage of spare capacity at a lower cost. Spot Instances are suitable for short-lived, scalable, and flexible workloads.

</details>

---

## Question 425

[Review topic](../sections/ec2.md) · Source PDF page 156

A company uses high block storage capacity to runs its workloads on premises. The company's daily peak input and output transactions per
second are not more than 15,000 IOPS. The company wants to migrate the workloads to Amazon EC2 and to provision disk performance
independent of storage capacity.
Which Amazon Elastic Block Store (Amazon EBS) volume type will meet these requirements MOST cost-effectively?

**A.** GP2 volume type

**B.** io2 volume type

**C.** GP3 volume type

**D.** io1 volume type

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses high block storage capacity to runs its workloads on premises. The company's daily peak input and output transactions per second are not more than 15,000 IOPS. The company wants to migrate the workloads to Amazon EC2 and to provision disk performance independent of storage capacity.

Which Amazon Elastic Block Store (Amazon EBS) volume type will meet these requirements MOST cost-effectively?


**C.** GP3 volume type

General Purpose SSD (gp3) volumes are designed to provide a balance of price and performance. They allow you to provision IOPS independently of storage capacity, making them suitable for workloads with varying performance requirements. GP3 volumes offer a lower price per IOPS compared to io1 volumes and are a good fit for general-purpose workloads.

</details>

---

## Question 426

[Review topic](../sections/exam-revision.md) · Source PDF page 156

A company needs to store data from its healthcare application. The application’s data frequently changes. A new regulation requires audit access
at all levels of the stored data.
The company hosts the application on an on-premises infrastructure that is running out of storage capacity. A solutions architect must securely
migrate the existing data to AWS while satisfying the new regulation.
Which solution will meet these requirements?

**A.** Use AWS DataSync to move the existing data to Amazon S3. Use AWS CloudTrail to log data events.

**B.** Use AWS Snowcone to move the existing data to Amazon S3. Use AWS CloudTrail to log management events.

**C.** Use Amazon S3 Transfer Acceleration to move the existing data to Amazon S3. Use AWS CloudTrail to log data events.

**D.** Use AWS Storage Gateway to move the existing data to Amazon S3. Use AWS CloudTrail to log management events.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs to store data from its healthcare application. The application’s data frequently changes. A new regulation requires audit access at all levels of the stored data.

The company hosts the application on an on-premises infrastructure that is running out of storage capacity. A solutions architect must securely migrate the existing data to AWS while satisfying the new regulation.

Which solution will meet these requirements?


**A.** Use AWS Storage Gateway to move the existing data to Amazon S3. Use AWS CloudTrail to log data events for the S3 bucket.

Explanation: CloudTrail management events don't capture object-level (data) access, so they can't satisfy "audit access at all levels of the stored data." CloudTrail data events, which log individual object-level API activity on the S3 bucket, are needed instead.

</details>

---

## Question 427

[Review topic](../sections/rds-aurora.md) · Source PDF page 156

A solutions architect is implementing a complex Java application with a MySQL database. The Java application must be deployed on Apache
Tomcat and must be highly available.
What should the solutions architect do to meet these requirements?

**A.** Deploy the application in AWS Lambda. Configure an Amazon API Gateway API to connect with the Lambda functions.

**B.** Deploy the application by using AWS Elastic Beanstalk. Configure a load-balanced environment and a rolling deployment policy.

**C.** Migrate the database to Amazon ElastiCache. Configure the ElastiCache security group to allow access from the application.

**D.** Launch an Amazon EC2 instance. Install a MySQL server on the EC2 instance. Configure the application on the server. Create an AMI. Use
the AMI to create a launch template with an Auto Scaling group.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is implementing a complex Java application with a MySQL database. The Java application must be deployed on Apache Tomcat and must be highly available.

What should the solutions architect do to meet these requirements?


**B.** Deploy the application by using AWS Elastic Beanstalk. Configure a load-balanced environment and a rolling deployment policy.

AWS Elastic Beanstalk: It is a fully managed service that simplifies the deployment and operation of applications, including web applications running Apache Tomcat. Elastic Beanstalk handles the deployment details, capacity provisioning, load balancing, auto-scaling, and application health monitoring, making it easier to deploy and manage your applications.

</details>

---

## Question 428

[Review topic](../sections/serverless.md) · Source PDF page 157

A serverless application uses Amazon API Gateway, AWS Lambda, and Amazon DynamoDB. The Lambda function needs permissions to read and
write to the DynamoDB table.
Which solution will give the Lambda function access to the DynamoDB table MOST securely?

**A.** Create an IAM user with programmatic access to the Lambda function. Attach a policy to the user that allows read and write access to the
DynamoDB table. Store the access_key_id and secret_access_key parameters as part of the Lambda environment variables. Ensure that other
AWS users do not have read and write access to the Lambda function configuration.

**B.** Create an IAM role that includes Lambda as a trusted service. Attach a policy to the role that allows read and write access to the
DynamoDB table. Update the configuration of the Lambda function to use the new role as the execution role.

**C.** Create an IAM user with programmatic access to the Lambda function. Attach a policy to the user that allows read and write access to the
DynamoDB table. Store the access_key_id and secret_access_key parameters in AWS Systems Manager Parameter Store as secure string
parameters. Update the Lambda function code to retrieve the secure string parameters before connecting to the DynamoDB table.

**D.** Create an IAM role that includes DynamoDB as a trusted service. Attach a policy to the role that allows read and write access from the
Lambda function. Update the code of the Lambda function to attach to the new role as an execution role.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A serverless application uses Amazon API Gateway, AWS Lambda, and Amazon DynamoDB. The Lambda function needs permissions to read and write to the DynamoDB table.

Which solution will give the Lambda function access to the DynamoDB table MOST securely?


**B.** Create an IAM role that includes Lambda as a trusted service. Attach a policy to the role that allows read and write access to the DynamoDB table. Update the configuration of the Lambda function to use the new role as the execution role.

IAM Role with Lambda as a Trusted Service: This approach follows the principle of least privilege. You create an IAM role that specifically grants the required permissions to access DynamoDB and makes Lambda a trusted service. This ensures that only Lambda functions associated with this role can assume it.

</details>

---

## Question 429

[Review topic](../sections/iam.md) · Source PDF page 158

The following IAM policy is attached to an IAM group. This is the only policy applied to the group.
What are the effective IAM permissions of this policy for group members?

**A.** Group members are permitted any Amazon EC2 action within the us-east-1 Region. Statements after the Allow permission are not applied.

**B.** Group members are denied any Amazon EC2 permissions in the us-east-1 Region unless they are logged in with multi-factor authentication
(MFA).

**C.** Group members are allowed the ec2:StopInstances and ec2:TerminateInstances permissions for all Regions when logged in with multi-
factor authentication (MFA). Group members are permitted any other Amazon EC2 action.

**D.** Group members are allowed the ec2:StopInstances and ec2:TerminateInstances permissions for the us-east-1 Region only when logged in
with multi-factor authentication (MFA). Group members are permitted any other Amazon EC2 action within the us-east-1 Region.

**Policy / option transcription**

Statement 1 allows ec2:* on * only when StringEquals ec2:Region = us-east-1. Statement 2 denies ec2:StopInstances and ec2:TerminateInstances on * when BoolIfExists aws:MultiFactorAuthPresent = false. Version 2012-10-17.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: D**

The Allow is limited to us-east-1. An explicit Deny blocks StopInstances and TerminateInstances without MFA; MFA does not extend the regional Allow.

**Original companion notes (not independently verified):**

Json format

</details>

---

## Question 430

[Review topic](../sections/s3.md) · Source PDF page 159

A manufacturing company has machine sensors that upload .csv files to an Amazon S3 bucket. These .csv files must be converted into images
and must be made available as soon as possible for the automatic generation of graphical reports.
The images become irrelevant after 1 month, but the .csv files must be kept to train machine learning (ML) models twice a year. The ML trainings
and audits are planned weeks in advance.
Which combination of steps will meet these requirements MOST cost-effectively? (Choose two.)

**A.** Launch an Amazon EC2 Spot Instance that downloads the .csv files every hour, generates the image files, and uploads the images to the S3
bucket.

**B.** Design an AWS Lambda function that converts the .csv files into images and stores the images in the S3 bucket. Invoke the Lambda
function when a .csv file is uploaded.

**C.** Create S3 Lifecycle rules for .csv files and image files in the S3 bucket. Transition the .csv files from S3 Standard to S3 Glacier 1 day after
they are uploaded. Expire the image files after 30 days.

**D.** Create S3 Lifecycle rules for .csv files and image files in the S3 bucket. Transition the .csv files from S3 Standard to S3 One Zone-Infrequent
Access (S3 One Zone-IA) 1 day after they are uploaded. Expire the image files after 30 days.

**E.** Create S3 Lifecycle rules for .csv files and image files in the S3 bucket. Transition the .csv files from S3 Standard to S3 Standard-Infrequent
Access (S3 Standard-IA) 1 day after they are uploaded. Keep the image files in Reduced Redundancy Storage (RRS).

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A manufacturing company has machine sensors that upload .csv files to an Amazon S3 bucket. These .csv files must be converted into images and must be made available as soon as possible for the automatic generation of graphical reports.

The images become irrelevant after 1 month, but the .csv files must be kept to train machine learning (ML) models twice a year. The ML trainings and audits are planned weeks in advance.

Which combination of steps will meet these requirements MOST cost-effectively? (Choose two.)


**B.** Design an AWS Lambda function that converts the .csv files into images and stores the images in the S3 bucket. Invoke the Lambda function when a .csv file is uploaded. Most Voted

**C.** Create S3 Lifecycle rules for .csv files and image files in the S3 bucket. Transition the .csv files from S3 Standard to S3 Glacier 1 day after they are uploaded. Expire the image files after 30 days.

</details>

---

## Question 431

[Review topic](../sections/rds-aurora.md) · Source PDF page 159

A company has developed a new video game as a web application. The application is in a three-tier architecture in a VPC with Amazon RDS for
MySQL in the database layer. Several players will compete concurrently online. The game’s developers want to display a top-10 scoreboard in near-
real time and offer the ability to stop and restore the game while preserving the current scores.
What should a solutions architect do to meet these requirements?

**A.** Set up an Amazon ElastiCache for Memcached cluster to cache the scores for the web application to display.

**B.** Set up an Amazon ElastiCache for Redis cluster to compute and cache the scores for the web application to display.

**C.** Place an Amazon CloudFront distribution in front of the web application to cache the scoreboard in a section of the application.

**D.** Create a read replica on Amazon RDS for MySQL to run queries to compute the scoreboard and serve the read traffic to the web application.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has developed a new video game as a web application. The application is in a three-tier architecture in a VPC with Amazon RDS for MySQL in the database layer. Several players will compete concurrently online. The game’s developers want to display a top-10 scoreboard in near-real time and offer the ability to stop and restore the game while preserving the current scores.

What should a solutions architect do to meet these requirements?


**B.** Set up an Amazon ElastiCache for Redis cluster to compute and cache the scores for the web application to display.

Redis is an in-memory data store that is well-suited for caching and real-time data processing. By setting up an ElastiCache for Redis cluster, you can compute and cache the scores in-memory, allowing for fast retrieval and updates.

</details>

---

## Question 432

[Review topic](../sections/exam-revision.md) · Source PDF page 159

An ecommerce company wants to use machine learning (ML) algorithms to build and train models. The company will use the models to visualize
complex scenarios and to detect trends in customer data. The architecture team wants to integrate its ML models with a reporting platform to
analyze the augmented data and use the data directly in its business intelligence dashboards.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use AWS Glue to create an ML transform to build and train models. Use Amazon OpenSearch Service to visualize the data.

**B.** Use Amazon SageMaker to build and train models. Use Amazon QuickSight to visualize the data.

**C.** Use a pre-built ML Amazon Machine Image (AMI) from the AWS Marketplace to build and train models. Use Amazon OpenSearch Service to
visualize the data.

**D.** Use Amazon QuickSight to build and train models by using calculated fields. Use Amazon QuickSight to visualize the data.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An ecommerce company wants to use machine learning (ML) algorithms to build and train models. The company will use the models to visualize complex scenarios and to detect trends in customer data. The architecture team wants to integrate its ML models with a reporting platform to analyze the augmented data and use the data directly in its business intelligence dashboards.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Use Amazon SageMaker to build and train models. Use Amazon QuickSight to visualize the data.

Amazon SageMaker: It is a fully managed service for building, training, and deploying machine learning models. SageMaker simplifies the ML workflow and reduces operational overhead. It provides a fully managed Jupyter Notebook instance for model development and training, and it can seamlessly integrate with other AWS services.
QuickSight can directly connect to Amazon SageMaker models and use the results for visualization without the need for extensive data movement or transformation.

</details>

---

## Question 433

[Review topic](../sections/cost-governance.md) · Source PDF page 160

A company is running its production and nonproduction environment workloads in multiple AWS accounts. The accounts are in an organization in
AWS Organizations. The company needs to design a solution that will prevent the modification of cost usage tags.
Which solution will meet these requirements?

**A.** Create a custom AWS Config rule to prevent tag modification except by authorized principals.

**B.** Create a custom trail in AWS CloudTrail to prevent tag modification.

**C.** Create a service control policy (SCP) to prevent tag modification except by authorized principals.

**D.** Create custom Amazon CloudWatch logs to prevent tag modification.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is running its production and nonproduction environment workloads in multiple AWS accounts. The accounts are in an organization in AWS Organizations. The company needs to design a solution that will prevent the modification of cost usage tags.

Which solution will meet these requirements?


**C.** Create a service control policy (SCP) to prevent tag modification except by authorized principals.

SCPs in AWS Organizations are used to set fine-grained permissions on what actions AWS accounts within the organization can perform. You can create a custom SCP to specifically control access to tag modification.

</details>

---

## Question 434

[Review topic](../sections/elb-asg.md) · Source PDF page 160

A company hosts its application in the AWS Cloud. The application runs on Amazon EC2 instances behind an Elastic Load Balancer in an Auto
Scaling group and with an Amazon DynamoDB table. The company wants to ensure the application can be made available in anotherAWS Region
with minimal downtime.
What should a solutions architect do to meet these requirements with the LEAST amount of downtime?

**A.** Create an Auto Scaling group and a load balancer in the disaster recovery Region. Configure the DynamoDB table as a global table.
Configure DNS failover to point to the new disaster recovery Region's load balancer.

**B.** Create an AWS CloudFormation template to create EC2 instances, load balancers, and DynamoDB tables to be launched when needed
Configure DNS failover to point to the new disaster recovery Region's load balancer.

**C.** Create an AWS CloudFormation template to create EC2 instances and a load balancer to be launched when needed. Configure the
DynamoDB table as a global table. Configure DNS failover to point to the new disaster recovery Region's load balancer.

**D.** Create an Auto Scaling group and load balancer in the disaster recovery Region. Configure the DynamoDB table as a global table. Create an
Amazon CloudWatch alarm to trigger an AWS Lambda function that updates Amazon Route 53 pointing to the disaster recovery load balancer.

<details>
<summary>Show answer and explanation</summary>

**Suggested answer: A**

Pre-provision the recovery application, replicate data using global tables, and configure health-based DNS failover to minimize provisioning delays.

**Original companion notes (not independently verified):**

A company hosts its application in the AWS Cloud. The application runs on Amazon EC2 instances behind an Elastic Load Balancer in an Auto Scaling group and with an Amazon DynamoDB table. The company wants to ensure the application can be made available in anotherAWS Region with minimal downtime.

What should a solutions architect do to meet these requirements with the LEAST amount of downtime?

</details>

---

## Question 435

[Review topic](../sections/rds-aurora.md) · Source PDF page 160

A company needs to migrate a MySQL database from its on-premises data center to AWS within 2 weeks. The database is 20 TB in size. The
company wants to complete the migration with minimal downtime.
Which solution will migrate the database MOST cost-effectively?

**A.** Order an AWS Snowball Edge Storage Optimized device. Use AWS Database Migration Service (AWS DMS) with AWS Schema Conversion
Tool (AWS SCT) to migrate the database with replication of ongoing changes. Send the Snowball Edge device to AWS to finish the migration
and continue the ongoing replication.

**B.** Order an AWS Snowmobile vehicle. Use AWS Database Migration Service (AWS DMS) with AWS Schema Conversion Tool (AWS SCT) to
migrate the database with ongoing changes. Send the Snowmobile vehicle back to AWS to finish the migration and continue the ongoing
replication.

**C.** Order an AWS Snowball Edge Compute Optimized with GPU device. Use AWS Database Migration Service (AWS DMS) with AWS Schema
Conversion Tool (AWS SCT) to migrate the database with ongoing changes. Send the Snowball device to AWS to finish the migration and
continue the ongoing replication

**D.** Order a 1 GB dedicated AWS Direct Connect connection to establish a connection with the data center. Use AWS Database Migration
Service (AWS DMS) with AWS Schema Conversion Tool (AWS SCT) to migrate the database with replication of ongoing changes.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs to migrate a MySQL database from its on-premises data center to AWS within 2 weeks. The database is 20 TB in size. The company wants to complete the migration with minimal downtime.

Which solution will migrate the database MOST cost-effectively?


**A.** Order an AWS Snowball Edge Storage Optimized device. Use AWS Database Migration Service (AWS DMS) with AWS Schema Conversion Tool (AWS SCT) to migrate the database with replication of ongoing changes. Send the Snowball Edge device to AWS to finish the migration and continue the ongoing replication.

This is a cost-effective solution for shipping large amounts of data to AWS. Snowball Edge devices are designed for efficient data transfer, and they can handle the 20 TB database.

AWS DMS is a managed service for migrating databases to AWS, and AWS SCT can assist in converting the database schema. Using these tools in combination allows for a smooth migration process.

</details>

---

## Question 436

[Review topic](../sections/rds-aurora.md) · Source PDF page 161

A company moved its on-premises PostgreSQL database to an Amazon RDS for PostgreSQL DB instance. The company successfully launched a
new product. The workload on the database has increased. The company wants to accommodate the larger workload without adding
infrastructure.
Which solution will meet these requirements MOST cost-effectively?

**A.** Buy reserved DB instances for the total workload. Make the Amazon RDS for PostgreSQL DB instance larger.

**B.** Make the Amazon RDS for PostgreSQL DB instance a Multi-AZ DB instance.

**C.** Buy reserved DB instances for the total workload. Add another Amazon RDS for PostgreSQL DB instance.

**D.** Make the Amazon RDS for PostgreSQL DB instance an on-demand DB instance.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company moved its on-premises PostgreSQL database to an Amazon RDS for PostgreSQL DB instance. The company successfully launched a new product. The workload on the database has increased. The company wants to accommodate the larger workload without adding infrastructure.

Which solution will meet these requirements MOST cost-effectively?


**A.** Buy reserved DB instances for the total workload. Make the Amazon RDS for PostgreSQL DB instance larger.

When you commit to using a database instance for a longer time (with reserved instances), AWS gives you a discount compared to paying on a month-to-month basis.

Imagine you have a computer, and you want to make it more powerful because you have more things to do on it. Making the instance larger means upgrading the power of your virtual computer.

</details>

---

## Question 437

[Review topic](../sections/elb-asg.md) · Source PDF page 161

A company operates an ecommerce website on Amazon EC2 instances behind an Application Load Balancer (ALB) in an Auto Scaling group. The
site is experiencing performance issues related to a high request rate from illegitimate external systems with changing IP addresses. The security
team is worried about potential DDoS attacks against the website. The company must block the illegitimate incoming requests in a way that has a
minimal impact on legitimate users.
What should a solutions architect recommend?

**A.** Deploy Amazon Inspector and associate it with the ALB.

**B.** Deploy AWS WAF, associate it with the ALB, and configure a rate-limiting rule.

**C.** Deploy rules to the network ACLs associated with the ALB to block the incomingtraffic.

**D.** Deploy Amazon GuardDuty and enable rate-limiting protection when configuring GuardDuty.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company operates an ecommerce website on Amazon EC2 instances behind an Application Load Balancer (ALB) in an Auto Scaling group. The site is experiencing performance issues related to a high request rate from illegitimate external systems with changing IP addresses. The security team is worried about potential DDoS attacks against the website. The company must block the illegitimate incoming requests in a way that has a minimal impact on legitimate users.

What should a solutions architect recommend?


**B.** Deploy AWS WAF, associate it with the ALB, and configure a rate-limiting rule.

AWS WAF is a web application firewall service that helps protect your web applications from common web exploits. It allows you to create rules to filter and monitor HTTP and HTTPS traffic based on conditions that you define.
By associating AWS WAF with the ALB, you can inspect and filter incoming traffic before it reaches your instances, providing a layer of protection against DDoS attacks and other malicious activities.

</details>

---

## Question 438

[Review topic](../sections/vpc.md) · Source PDF page 161

A company wants to share accounting data with an external auditor. The data is stored in an Amazon RDS DB instance that resides in a private
subnet. The auditor has its own AWS account and requires its own copy of the database.
What is the MOST secure way for the company to share the database with the auditor?

**A.** Create a read replica of the database. Configure IAM standard database authentication to grant the auditor access.

**B.** Export the database contents to text files. Store the files in an Amazon S3 bucket. Create a new IAM user for the auditor. Grant the user
access to the S3 bucket.

**C.** Copy a snapshot of the database to an Amazon S3 bucket. Create an IAM user. Share the user's keys with the auditor to grant access to the
object in the S3 bucket.

**D.** Create an encrypted snapshot of the database. Share the snapshot with the auditor. Allow access to the AWS Key Management Service
(AWS KMS) encryption key.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to share accounting data with an external auditor. The data is stored in an Amazon RDS DB instance that resides in a private subnet. The auditor has its own AWS account and requires its own copy of the database.

What is the MOST secure way for the company to share the database with the auditor?


**D.** Create an encrypted snapshot of the database. Share the snapshot with the auditor. Allow access to the AWS Key Management Service (AWS KMS) encryption key.

Creating an encrypted snapshot ensures that the database data is protected during the transfer and storage process.
Sharing the encrypted snapshot with the auditor allows them to create their own copy of the database securely.
By allowing access to the AWS KMS encryption key, the auditor can decrypt the snapshot and restore it to their own environment.

</details>

---

## Question 439

[Review topic](../sections/vpc.md) · Source PDF page 162

A solutions architect configured a VPC that has a small range of IP addresses. The number of Amazon EC2 instances that are in the VPC is
increasing, and there is an insufficient number of IP addresses for future workloads.
Which solution resolves this issue with the LEAST operational overhead?

**A.** Add an additional IPv4 CIDR block to increase the number of IP addresses and create additional subnets in the VPC. Create new resources
in the new subnets by using the new CIDR.

**B.** Create a second VPC with additional subnets. Use a peering connection to connect the second VPC with the first VPC Update the routes
and create new resources in the subnets of the second VPC.

**C.** Use AWS Transit Gateway to add a transit gateway and connect a second VPC with the first VPUpdate the routes of the transit gateway and
VPCs. Create new resources in the subnets of the second VPC.

**D.** Create a second VPC. Create a Site-to-Site VPN connection between the first VPC and the second VPC by using a VPN-hosted solution on
Amazon EC2 and a virtual private gateway. Update the route between VPCs to the traffic through the VPN. Create new resources in the
subnets of the second VPC.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect configured a VPC that has a small range of IP addresses. The number of Amazon EC2 instances that are in the VPC is increasing, and there is an insufficient number of IP addresses for future workloads.

Which solution resolves this issue with the LEAST operational overhead?


**A.** Add an additional IPv4 CIDR block to increase the number of IP addresses and create additional subnets in the VPC. Create new resources in the new subnets by using the new CIDR.

By adding an additional IPv4 CIDR block to the existing VPC, you can effectively increase the number of available IP addresses within the same VPC.
Creating additional subnets using the new CIDR block allows you to organize your resources and maintain segmentation within the VPC.

</details>

---

## Question 440

[Review topic](../sections/rds-aurora.md) · Source PDF page 162

A company used an Amazon RDS for MySQL DB instance during application testing. Before terminating the DB instance at the end of the test
cycle, a solutions architect created two backups. The solutions architect created the first backup by using the mysqldump utility to create a
database dump. The solutions architect created the second backup by enabling the final DB snapshot option on RDS termination.
The company is now planning for a new test cycle and wants to create a new DB instance from the most recent backup. The company has chosen
a MySQL-compatible edition ofAmazon Aurora to host the DB instance.
Which solutions will create the new DB instance? (Choose two.)

**A.** Import the RDS snapshot directly into Aurora.

**B.** Upload the RDS snapshot to Amazon S3. Then import the RDS snapshot into Aurora.

**C.** Upload the database dump to Amazon S3. Then import the database dump into Aurora.

**D.** Use AWS Database Migration Service (AWS DMS) to import the RDS snapshot into Aurora.

**E.** Upload the database dump to Amazon S3. Then use AWS Database Migration Service (AWS DMS) to import the database dump into Aurora.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company used an Amazon RDS for MySQL DB instance during application testing. Before terminating the DB instance at the end of the test cycle, a solutions architect created two backups. The solutions architect created the first backup by using the mysqldump utility to create a database dump. The solutions architect created the second backup by enabling the final DB snapshot option on RDS termination.

The company is now planning for a new test cycle and wants to create a new DB instance from the most recent backup. The company has chosen a MySQL-compatible edition ofAmazon Aurora to host the DB instance.

Which solutions will create the new DB instance? (Choose two.)


**A.** Import the RDS snapshot directly into Aurora.


**C.** Upload the database dump to Amazon S3. Then import the database dump into Aurora.


**A.** Amazon Aurora allows you to directly import an Amazon RDS snapshot into Aurora. This is a straightforward process for migrating data from RDS to Aurora.


**C.** Uploading the database dump to Amazon S3 and then importing the database dump into Aurora is a common method. You can use the MySQL-compatible version of Aurora to restore the data from a database dump stored in Amazon S3.

</details>

---

## Question 441

[Review topic](../sections/elb-asg.md) · Source PDF page 162

A company hosts a multi-tier web application on Amazon Linux Amazon EC2 instances behind an Application Load Balancer. The instances run in
an Auto Scaling group across multiple Availability Zones. The company observes that the Auto Scaling group launches more On-Demand
Instances when the application's end users access high volumes of static web content. The company wants to optimize cost.
What should a solutions architect do to redesign the application MOST cost-effectively?

**A.** Update the Auto Scaling group to use Reserved Instances instead of On-Demand Instances.

**B.** Update the Auto Scaling group to scale by launching Spot Instances instead of On-Demand Instances.

**C.** Create an Amazon CloudFront distribution to host the static web contents from an Amazon S3 bucket.

**D.** Create an AWS Lambda function behind an Amazon API Gateway API to host the static website contents.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company hosts a multi-tier web application on Amazon Linux Amazon EC2 instances behind an Application Load Balancer. The instances run in an Auto Scaling group across multiple Availability Zones. The company observes that the Auto Scaling group launches more On-Demand Instances when the application's end users access high volumes of static web content. The company wants to optimize cost.

What should a solutions architect do to redesign the application MOST cost-effectively?


**C.** Create an Amazon CloudFront distribution to host the static web contents from an Amazon S3 bucket.

Amazon CloudFront is a content delivery network (CDN) service that delivers static and dynamic web content, including images, videos, CSS, and JavaScript, with low latency and high transfer speeds. It can be used to cache and distribute static content globally, reducing the load on your web servers.

By creating a CloudFront distribution and hosting static web content in an Amazon S3 bucket, you offload the serving of static content to the CDN, which can significantly reduce the load on your EC2 instances.

</details>

---

## Question 442

[Review topic](../sections/analytics.md) · Source PDF page 163

A company stores several petabytes of data across multiple AWS accounts. The company uses AWS Lake Formation to manage its data lake. The
company's data science team wants to securely share selective data from its accounts with the company's engineering team for analytical
purposes.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Copy the required data to a common account. Create an IAM access role in that account. Grant access by specifying a permission policy
that includes users from the engineering team accounts as trusted entities.

**B.** Use the Lake Formation permissions Grant command in each account where the data is stored to allow the required engineering team users
to access the data.

**C.** Use AWS Data Exchange to privately publish the required data to the required engineering team accounts.

**D.** Use Lake Formation tag-based access control to authorize and grant cross-account permissions for the required data to the engineering
team accounts.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company stores several petabytes of data across multiple AWS accounts. The company uses AWS Lake Formation to manage its data lake. The company's data science team wants to securely share selective data from its accounts with the company's engineering team for analytical purposes.

Which solution will meet these requirements with the LEAST operational overhead?


**D.** Use Lake Formation tag-based access control to authorize and grant cross-account permissions for the required data to the engineering team accounts.

Lake Formation allows you to use tag-based access control to authorize and grant permissions for data in the data lake. You can apply tags to databases and tables, and then use those tags to control access to the data.

By applying tags to the relevant data and using tag-based access control, you can easily manage access to specific data sets without having to create additional IAM roles or copy data to a common account.

</details>

---

## Question 443

[Review topic](../sections/cost-governance.md) · Source PDF page 163

A company wants to host a scalable web application on AWS. The application will be accessed by users from different geographic regions of the
world. Application users will be able to download and upload unique data up to gigabytes in size. The development team wants a cost-effective
solution to minimize upload and download latency and maximize performance.
What should a solutions architect do to accomplish this?

**A.** Use Amazon S3 with Transfer Acceleration to host the application.

**B.** Use Amazon S3 with CacheControl headers to host the application.

**C.** Use Amazon EC2 with Auto Scaling and Amazon CloudFront to host the application.

**D.** Use Amazon EC2 with Auto Scaling and Amazon ElastiCache to host the application.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to host a scalable web application on AWS. The application will be accessed by users from different geographic regions of the world. Application users will be able to download and upload unique data up to gigabytes in size. The development team wants a cost-effective solution to minimize upload and download latency and maximize performance.

What should a solutions architect do to accomplish this?


**A.** Use Amazon S3 with Transfer Acceleration to host the application.

</details>

---

## Question 444

[Review topic](../sections/cloud-foundations.md) · Source PDF page 163

A company has hired a solutions architect to design a reliable architecture for its application. The application consists of one Amazon RDS DB
instance and two manually provisioned Amazon EC2 instances that run web servers. The EC2 instances are located in a single Availability Zone.
An employee recently deleted the DB instance, and the application was unavailable for 24 hours as a result. The company is concerned with the
overall reliability of its environment.
What should the solutions architect do to maximize reliability of the application's infrastructure?

**A.** Delete one EC2 instance and enable termination protection on the other EC2 instance. Update the DB instance to be Multi-AZ, and enable
deletion protection.

**B.** Update the DB instance to be Multi-AZ, and enable deletion protection. Place the EC2 instances behind an Application Load Balancer, and
run them in an EC2 Auto Scaling group across multiple Availability Zones.

**C.** Create an additional DB instance along with an Amazon API Gateway and an AWS Lambda function. Configure the application to invoke the
Lambda function through API Gateway. Have the Lambda function write the data to the two DB instances.

**D.** Place the EC2 instances in an EC2 Auto Scaling group that has multiple subnets located in multiple Availability Zones. Use Spot Instances
instead of On-Demand Instances. Set up Amazon CloudWatch alarms to monitor the health of the instances Update the DB instance to be
Multi-AZ, and enable deletion protection.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has hired a solutions architect to design a reliable architecture for its application. The application consists of one Amazon RDS DB instance and two manually provisioned Amazon EC2 instances that run web servers. The EC2 instances are located in a single Availability Zone.

An employee recently deleted the DB instance, and the application was unavailable for 24 hours as a result. The company is concerned with the overall reliability of its environment.

What should the solutions architect do to maximize reliability of the application's infrastructure?


**B.** Update the DB instance to be Multi-AZ, and enable deletion protection. Place the EC2 instances behind an Application Load Balancer, and run them in an EC2 Auto Scaling group across multiple Availability Zones.

Multi-AZ RDS Instance: By updating the DB instance to be Multi-AZ, you ensure that there is a standby replica in a different Availability Zone, providing high availability and automatic failover in case of a failure in the primary zone.

Deletion Protection: Enabling deletion protection for the DB instance helps prevent accidental deletion, reducing the risk of downtime caused by human error.

</details>

---

## Question 445

[Review topic](../sections/migration.md) · Source PDF page 164

A company is storing 700 terabytes of data on a large network-attached storage (NAS) system in its corporate data center. The company has a
hybrid environment with a 10 Gbps AWS Direct Connect connection.
After an audit from a regulator, the company has 90 days to move the data to the cloud. The company needs to move the data efficiently and
without disruption. The company still needs to be able to access and update the data during the transfer window.
Which solution will meet these requirements?

**A.** Create an AWS DataSync agent in the corporate data center. Create a data transfer task Start the transfer to an Amazon S3 bucket.

**B.** Back up the data to AWS Snowball Edge Storage Optimized devices. Ship the devices to an AWS data center. Mount a target Amazon S3
bucket on the on-premises file system.

**C.** Use rsync to copy the data directly from local storage to a designated Amazon S3 bucket over the Direct Connect connection.

**D.** Back up the data on tapes. Ship the tapes to an AWS data center. Mount a target Amazon S3 bucket on the on-premises file system.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is storing 700 terabytes of data on a large network-attached storage (NAS) system in its corporate data center. The company has a hybrid environment with a 10 Gbps AWS Direct Connect connection.

After an audit from a regulator, the company has 90 days to move the data to the cloud. The company needs to move the data efficiently and without disruption. The company still needs to be able to access and update the data during the transfer window.

Which solution will meet these requirements?


**A.** Create an AWS DataSync agent in the corporate data center. Create a data transfer task Start the transfer to an Amazon S3 bucket.

using AWS DataSync, which is designed for efficiently transferring large amounts of data between on-premises storage and Amazon S3. It allows you to create data transfer tasks and initiate the transfer to an Amazon S3 bucket.

</details>

---

## Question 446

[Review topic](../sections/s3.md) · Source PDF page 164

A company stores data in PDF format in an Amazon S3 bucket. The company must follow a legal requirement to retain all new and existing data in
Amazon S3 for 7 years.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Turn on the S3 Versioning feature for the S3 bucket. Configure S3 Lifecycle to delete the data after 7 years. Configure multi-factor
authentication (MFA) delete for all S3 objects.

**B.** Turn on S3 Object Lock with governance retention mode for the S3 bucket. Set the retention period to expire after 7 years. Recopy all
existing objects to bring the existing data into compliance.

**C.** Turn on S3 Object Lock with compliance retention mode for the S3 bucket. Set the retention period to expire after 7 years. Recopy all
existing objects to bring the existing data into compliance.

**D.** Turn on S3 Object Lock with compliance retention mode for the S3 bucket. Set the retention period to expire after 7 years. Use S3 Batch
Operations to bring the existing data into compliance.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company stores data in PDF format in an Amazon S3 bucket. The company must follow a legal requirement to retain all new and existing data in Amazon S3 for 7 years.

Which solution will meet these requirements with the LEAST operational overhead?


**D.** Turn on S3 Object Lock with compliance retention mode for the S3 bucket. Set the retention period to expire after 7 years. Use S3 Batch Operations to bring the existing data into compliance.

</details>

---

## Question 447

[Review topic](../sections/serverless.md) · Source PDF page 164

A company has a stateless web application that runs on AWS Lambda functions that are invoked by Amazon API Gateway. The company wants to
deploy the application across multiple AWS Regions to provide Regional failover capabilities.
What should a solutions architect do to route traffic to multiple Regions?

**A.** Create Amazon Route 53 health checks for each Region. Use an active-active failover configuration.

**B.** Create an Amazon CloudFront distribution with an origin for each Region. Use CloudFront health checks to route traffic.

**C.** Create a transit gateway. Attach the transit gateway to the API Gateway endpoint in each Region. Configure the transit gateway to route
requests.

**D.** Create an Application Load Balancer in the primary Region. Set the target group to point to the API Gateway endpoint hostnames in each
Region.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a stateless web application that runs on AWS Lambda functions that are invoked by Amazon API Gateway. The company wants to deploy the application across multiple AWS Regions to provide Regional failover capabilities.

What should a solutions architect do to route traffic to multiple Regions?


**A.** Create Amazon Route 53 health checks for each Region. Use an active-active failover configuration.

By creating Amazon Route 53 health checks for each Region and configuring an active-active failover configuration, Route 53 can monitor the health of the endpoints in each Region and route traffic to healthy endpoints. In the event of a failure in one Region, Route 53 automatically routes traffic to the healthy endpoints in other Regions.

</details>

---

## Question 448

[Review topic](../sections/vpc.md) · Source PDF page 165

A company has two VPCs named Management and Production. The Management VPC uses VPNs through a customer gateway to connect to a
single device in the data center. The Production VPC uses a virtual private gateway with two attached AWS Direct Connect connections. The
Management and Production VPCs both use a single VPC peering connection to allow communication between the applications.
What should a solutions architect do to mitigate any single point of failure in this architecture?

**A.** Add a set of VPNs between the Management and Production VPCs.

**B.** Add a second virtual private gateway and attach it to the Management VPC.

**C.** Add a second set of VPNs to the Management VPC from a second customer gateway device.

**D.** Add a second VPC peering connection between the Management VPC and the Production VPC.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has two VPCs named Management and Production. The Management VPC uses VPNs through a customer gateway to connect to a single device in the data center. The Production VPC uses a virtual private gateway with two attached AWS Direct Connect connections. The Management and Production VPCs both use a single VPC peering connection to allow communication between the applications.

What should a solutions architect do to mitigate any single point of failure in this architecture?


**C.** Add a second set of VPNs to the Management VPC from a second customer gateway device.

Adding a second set of VPN connections from the Management VPC to a second customer gateway device provides redundancy and eliminates this single point of failure.

</details>

---

## Question 449

[Review topic](../sections/rds-aurora.md) · Source PDF page 165

A company runs its application on an Oracle database. The company plans to quickly migrate to AWS because of limited resources for the
database, backup administration, and data center maintenance. The application uses third-party database features that require privileged access.
Which solution will help the company migrate the database to AWS MOST cost-effectively?

**A.** Migrate the database to Amazon RDS for Oracle. Replace third-party features with cloud services.

**B.** Migrate the database to Amazon RDS Custom for Oracle. Customize the database settings to support third-party features.

**C.** Migrate the database to an Amazon EC2 Amazon Machine Image (AMI) for Oracle. Customize the database settings to support third-party
features.

**D.** Migrate the database to Amazon RDS for PostgreSQL by rewriting the application code to remove dependency on Oracle APEX.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs its application on an Oracle database. The company plans to quickly migrate to AWS because of limited resources for the database, backup administration, and data center maintenance. The application uses third-party database features that require privileged access.

Which solution will help the company migrate the database to AWS MOST cost-effectively?


**B.** Migrate the database to Amazon RDS Custom for Oracle. Customize the database settings to support third-party features.

</details>

---

## Question 450

[Review topic](../sections/exam-revision.md) · Source PDF page 165

A company has a three-tier web application that is in a single server. The company wants to migrate the application to the AWS Cloud. The
company also wants the application to align with the AWS Well-Architected Framework and to be consistent with AWS recommended best
practices for security, scalability, and resiliency.
Which combination of solutions will meet these requirements? (Choose three.)

**A.** Create a VPC across two Availability Zones with the application's existing architecture. Host the application with existing architecture on an
Amazon EC2 instance in a private subnet in each Availability Zone with EC2 Auto Scaling groups. Secure the EC2 instance with security groups
and network access control lists (network ACLs).

**B.** Set up security groups and network access control lists (network ACLs) to control access to the database layer. Set up a single Amazon
RDS database in a private subnet.

**C.** Create a VPC across two Availability Zones. Refactor the application to host the web tier, application tier, and database tier. Host each tier
on its own private subnet with Auto Scaling groups for the web tier and application tier.

**D.** Use a single Amazon RDS database. Allow database access only from the application tier security group.

**E.** Use Elastic Load Balancers in front of the web tier. Control access by using security groups containing references to each layer's security
groups.

**F.** Use an Amazon RDS database Multi-AZ cluster deployment in private subnets. Allow database access only from application tier security
groups.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a three-tier web application that is in a single server. The company wants to migrate the application to the AWS Cloud. The company also wants the application to align with the AWS Well-Architected Framework and to be consistent with AWS recommended best practices for security, scalability, and resiliency.

Which combination of solutions will meet these requirements? (Choose three.)


**C.** Create a VPC across two Availability Zones. Refactor the application to host the web tier, application tier, and database tier. Host each tier on its own private subnet with Auto Scaling groups for the web tier and application tier.

This choice aligns with best practices by using separate subnets for each tier, allowing for better security and scalability. Auto Scaling groups provide elasticity and resiliency.


**E.** Use Elastic Load Balancers in front of the web tier. Control access by using security groups containing references to each layer's security groups.

This option introduces an Elastic Load Balancer (ELB) for the web tier, which enhances scalability and resiliency. Using security groups to control access adds an additional layer of security.


**F.** Use an Amazon RDS database Multi-AZ cluster deployment in private subnets. Allow database access only from application tier security groups.

This option leverages Amazon RDS for the database tier, utilizing Multi-AZ for high availability. Placing the RDS database in private subnets and restricting access to the application tier security groups enhances security.

</details>

---

