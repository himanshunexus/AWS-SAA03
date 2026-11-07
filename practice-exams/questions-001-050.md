# Practice questions 1-50

[Home](../README.md) · [All sets](README.md)

Answer notes are source-provided unless labeled suggested. These sets preserve the supplied PDF; they are not official AWS exams.

## Question 1

[Review topic](../sections/s3.md) · Source PDF page 2

A company collects data for temperature, humidity, and atmospheric pressure in cities across multiple continents. The average volume of data
that the company collects from each site daily is 500 GB. Each site has a high-speed Internet connection.
The company wants to aggregate the data from all these global sites as quickly as possible in a single Amazon S3 bucket. The solution must
minimize operational complexity.
Which solution meets these requirements?

**A.** Turn on S3 Transfer Acceleration on the destination S3 bucket. Use multipart uploads to directly upload site data to the destination S3
bucket.

**B.** Upload the data from each site to an S3 bucket in the closest Region. Use S3 Cross-Region Replication to copy objects to the destination S3
bucket. Then remove the data from the origin S3 bucket.

**C.** Schedule AWS Snowball Edge Storage Optimized device jobs daily to transfer data from each site to the closest Region. Use S3 Cross-
Region Replication to copy objects to the destination S3 bucket.

**D.** Upload the data from each site to an Amazon EC2 instance in the closest Region. Store the data in an Amazon Elastic Block Store (Amazon
EBS) volume. At regular intervals, take an EBS snapshot and copy it to the Region that contains the destination S3 bucket. Restore the EBS
volume in that Region.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company collects data for temperature, humidity, and atmospheric pressure in cities across multiple continents. The average volume of data that the company collects from each site daily is 500 GB. Each site has a high-speed Internet connection.
The company wants to aggregate the data from all these global sites as quickly as possible in a single Amazon S3 bucket. The solution must minimize operational complexity.
Which solution meets these requirements

ans- Turn on S3 Transfer Acceleration on the destination S3 bucket. Use multipart uploads to directly upload site data to the destination S3 bucket. 

General line: Collect huge amount of the files across multiple continents
Conditions: High speed Internet connectivity
Task: aggregate the data from all in a single S3 bucket
Requirements: as quick as possible, minimize operational complexity

Correct answer A: S3 Transfer Acceleration because:
- ideally works with objects for long-distance transfer (uses Edge Locations)
- can speed up content transfers to and from S3 as much as 50-500%
- use cases: mobile & web application uploads and downloads, distributed office transfers, data exchange with trusted partners. Generally for sharing of large data sets between companies, customers can set up special access to their S3 buckets with accelerated uploads to speed data exchanges and the pace of innovation.

</details>

---

## Question 2

[Review topic](../sections/s3.md) · Source PDF page 2

A company needs the ability to analyze the log files of its proprietary application. The logs are stored in JSON format in an Amazon S3 bucket.
Queries will be simple and will run on-demand. A solutions architect needs to perform the analysis with minimal changes to the existing
architecture.
What should the solutions architect do to meet these requirements with the LEAST amount of operational overhead?

**A.** Use Amazon Redshift to load all the content into one place and run the SQL queries as needed.

**B.** Use Amazon CloudWatch Logs to store the logs. Run SQL queries as needed from the Amazon CloudWatch console.

**C.** Use Amazon Athena directly with Amazon S3 to run the queries as needed.

**D.** Use AWS Glue to catalog the logs. Use a transient Apache Spark cluster on Amazon EMR to run the SQL queries as needed.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs the ability to analyze the log files of its proprietary application. The logs are stored in JSON format in an Amazon S3 bucket. Queries will be simple and will run on-demand. A solutions architect needs to perform the analysis with minimal changes to the existing architecture.
What should the solutions architect do to meet these requirements with the LEAST amount of operational overhead?

ans-Use Amazon Athena directly with Amazon S3 to run the queries as needed.

Amazon Athena is an interactive query service that makes it easy to analyze data directly in Amazon Simple Storage Service (Amazon S3) using standard SQL. With a few actions in the AWS Management Console, you can point Athena at your data stored in Amazon S3 and begin using standard SQL to run ad-hoc queries and get results in seconds.

</details>

---

## Question 3

[Review topic](../sections/s3.md) · Source PDF page 2

A company uses AWS Organizations to manage multiple AWS accounts for different departments. The management account has an Amazon S3
bucket that contains project reports. The company wants to limit access to this S3 bucket to only users of accounts within the organization in
AWS Organizations.
Which solution meets these requirements with the LEAST amount of operational overhead?

**A.** Add the aws PrincipalOrgID global condition key with a reference to the organization ID to the S3 bucket policy.

**B.** Create an organizational unit (OU) for each department. Add the aws:PrincipalOrgPaths global condition key to the S3 bucket policy.

**C.** Use AWS CloudTrail to monitor the CreateAccount, InviteAccountToOrganization, LeaveOrganization, and RemoveAccountFromOrganization
events. Update the S3 bucket policy accordingly.

**D.** Tag each user that needs access to the S3 bucket. Add the aws:PrincipalTag global condition key to the S3 bucket policy.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses AWS Organizations to manage multiple AWS accounts for different departments. The management account has an Amazon S3 bucket that contains project reports. The company wants to limit access to this S3 bucket to only users of accounts within the organization in AWS Organizations.
Which solution meets these requirements with the LEAST amount of operational overhead?

ans-. Add the aws PrincipalOrgID global condition key with a reference to the organization ID to the S3 bucket policy.

aws:PrincipalOrgID – Simplifies specifying the Principal element in a resource-based policy. This global key provides an alternative to listing all the account IDs for all AWS accounts in an organization. Instead of listing all of the accounts that are members of an organization, you can specify the organization ID in the Condition element.
proposes adding the aws PrincipalOrgID global condition key with a reference to the organization ID to the S3 bucket policy. This would limit access to the S3 bucket to only users of accounts within the organization in AWS Organizations, as the aws PrincipalOrgID condition key can check if the request is coming from within the organization.

</details>

---

## Question 4

[Review topic](../sections/s3.md) · Source PDF page 3

An application runs on an Amazon EC2 instance in a VPC. The application processes logs that are stored in an Amazon S3 bucket. The EC2
instance needs to access the S3 bucket without connectivity to the internet.
Which solution will provide private network connectivity to Amazon S3?

**A.** Create a gateway VPC endpoint to the S3 bucket.

**B.** Stream the logs to Amazon CloudWatch Logs. Export the logs to the S3 bucket.

**C.** Create an instance profile on Amazon EC2 to allow S3 access.

**D.** Create an Amazon API Gateway API with a private link to access the S3 endpoint.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An application runs on an Amazon EC2 instance in a VPC. The application processes logs that are stored in an Amazon S3 bucket. The EC2 instance needs to access the S3 bucket without connectivity to the internet.
Which solution will provide private network connectivity to Amazon S3?


**A.** Create a gateway VPC endpoint to the S3 bucket.

Keywords:
- EC2 in VPC
- EC2 instance needs to access the S3 bucket without connectivity to the internet
VPC endpoint allows you to connect to AWS services using a private network instead of using the public Internet.

With a gateway endpoint, you can access Amazon S3 from your VPC, without requiring an internet gateway or NAT device for your VPC, and with no additional cost. However, gateway endpoints do not allow access from on-premises networks, from peered VPCs in other AWS Regions, or through a transit gateway.

</details>

---

## Question 5

[Review topic](../sections/cloud-foundations.md) · Source PDF page 3

A company is hosting a web application on AWS using a single Amazon EC2 instance that stores user-uploaded documents in an Amazon EBS
volume. For better scalability and availability, the company duplicated the architecture and created a second EC2 instance and EBS volume in
another Availability Zone, placing both behind an Application Load Balancer. After completing this change, users reported that, each time they
refreshed the website, they could see one subset of their documents or the other, but never all of the documents at the same time.
What should a solutions architect propose to ensure users see all of their documents at once?

**A.** Copy the data so both EBS volumes contain all the documents

**B.** Configure the Application Load Balancer to direct a user to the server with the documents

**C.** Copy the data from both EBS volumes to Amazon EFS. Modify the application to save new documents to Amazon EFS

**D.** Configure the Application Load Balancer to send the request to both servers. Return each document from the correct server

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is hosting a web application on AWS using a single Amazon EC2 instance that stores user-uploaded documents in an Amazon EBS volume. For better scalability and availability, the company duplicated the architecture and created a second EC2 instance and EBS volume in another Availability Zone, placing both behind an Application Load Balancer. After completing this change, users reported that, each time they refreshed the website, they could see one subset of their documents or the other, but never all of the documents at the same time.
What should a solutions architect propose to ensure users see all of their documents at once?


**C.** Copy the data from both EBS volumes to Amazon EFS. Modify the application to save new documents to Amazon EFS

Option C, which involves copying the data to Amazon EFS and modifying the application to use Amazon EFS for document storage, is the most appropriate solution to ensure users can see all their documents at once in the duplicated architecture. Amazon EFS provides scalability, availability, and shared access, allowing both EC2 instances to access and synchronize the documents seamlessly. Unlike EBS volumes or snapshots, which cannot be shared in real time across multiple instances and Availability Zones, Amazon EFS allows both EC2 instances to access the same file system simultaneously, ensuring all users see the same set of documents regardless of which instance serves their request.

</details>

---

## Question 6

[Review topic](../sections/ec2-storage.md) · Source PDF page 3

A company uses NFS to store large video files in on-premises network attached storage. Each video file ranges in size from 1 MB to 500 GB. The
total storage is 70 TB and is no longer growing. The company decides to migrate the video files to Amazon S3. The company must migrate the
video files as soon as possible while using the least possible network bandwidth.
Which solution will meet these requirements?

**A.** Create an S3 bucket. Create an IAM role that has permissions to write to the S3 bucket. Use the AWS CLI to copy all files locally to the S3
bucket.

**B.** Create an AWS Snowball Edge job. Receive a Snowball Edge device on premises. Use the Snowball Edge client to transfer data to the
device. Return the device so that AWS can import the data into Amazon S3.

**C.** Deploy an S3 File Gateway on premises. Create a public service endpoint to connect to the S3 File Gateway. Create an S3 bucket. Create a
new NFS file share on the S3 File Gateway. Point the new file share to the S3 bucket. Transfer the data from the existing NFS file share to the
S3 File Gateway.

**D.** Set up an AWS Direct Connect connection between the on-premises network and AWS. Deploy an S3 File Gateway on premises. Create a
public virtual interface (VIF) to connect to the S3 File Gateway. Create an S3 bucket. Create a new NFS file share on the S3 File Gateway. Point
the new file share to the S3 bucket. Transfer the data from the existing NFS file share to the S3 File Gateway.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses NFS to store large video files in on-premises network attached storage. Each video file ranges in size from 1 MB to 500 GB. The total storage is 70 TB and is no longer growing. The company decides to migrate the video files to Amazon S3. The company must migrate the video files as soon as possible while using the least possible network bandwidth.
Which solution will meet these requirements?

  B Create an AWS Snowball Edge job. Receive a Snowball Edge device on premises. Use the Snowball Edge client to transfer data to the device. Return the device so that AWS can import the data into Amazon S3

 On a Snowball Edge device you can copy files with a speed of up to 100Gbps. 70TB will take around 5600 seconds, so very quickly, less than 2 hours. The downside is that it'll take between 4-6 working days to receive the device and then another 2-3 working days to send it back and for AWS to move the data onto S3 once it reaches them. Total time: 6-9 working days. Bandwidth used: 0.

</details>

---

## Question 7

[Review topic](../sections/exam-revision.md) · Source PDF page 4

A company has an application that ingests incoming messages. Dozens of other applications and microservices then quickly consume these
messages. The number of messages varies drastically and sometimes increases suddenly to 100,000 each second. The company wants to
decouple the solution and increase scalability.
Which solution meets these requirements?

**A.** Persist the messages to Amazon Kinesis Data Analytics. Configure the consumer applications to read and process the messages.

**B.** Deploy the ingestion application on Amazon EC2 instances in an Auto Scaling group to scale the number of EC2 instances based on CPU
metrics.

**C.** Write the messages to Amazon Kinesis Data Streams with a single shard. Use an AWS Lambda function to preprocess messages and store
them in Amazon DynamoDB. Configure the consumer applications to read from DynamoDB to process the messages.

**D.** Publish the messages to an Amazon Simple Notification Service (Amazon SNS) topic with multiple Amazon Simple Queue Service (Amazon
SOS) subscriptions. Configure the consumer applications to process the messages from the queues.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an application that ingests incoming messages. Dozens of other applications and microservices then quickly consume these messages. The number of messages varies drastically and sometimes increases suddenly to 100,000 each second. The company wants to decouple the solution and increase scalability.
Which solution meets these requirements?


**D.** Publish the messages to an Amazon Simple Notification Service (Amazon SNS) topic with multiple Amazon Simple Queue Service (Amazon SOS) subscriptions. Configure the consumer applications to process the messages from the queues. 

A good practice is to also add message attributes when publishing to SNS. Each SQS subscription can have a filter policy that matches only the messages it cares about, so that only relevant messages are delivered to each SQS queue, and consumers only see/process what they need.

an SQS queue can handle a maximum of 3,000 messages per second. However, you can request higher throughput by contacting AWS Support. AWS can increase the message throughput for your queue beyond the default limits in increments of 300 messages per second, up to a maximum of 10,000 messages per second.

It's important to note that the maximum number of messages per second that a queue can handle is not the same as the maximum number of requests per second that the SQS API can handle. The SQS API is designed to handle a high volume of requests per second, so it can be used to send messages to your queue at a rate that exceeds the maximum message throughput of the queue.

</details>

---

## Question 8

[Review topic](../sections/exam-revision.md) · Source PDF page 4

A company is migrating a distributed application to AWS. The application serves variable workloads. The legacy platform consists of a primary
server that coordinates jobs across multiple compute nodes. The company wants to modernize the application with a solution that maximizes
resiliency and scalability.
How should a solutions architect design the architecture to meet these requirements?

**A.** Configure an Amazon Simple Queue Service (Amazon SQS) queue as a destination for the jobs. Implement the compute nodes with
Amazon EC2 instances that are managed in an Auto Scaling group. Configure EC2 Auto Scaling to use scheduled scaling.

**B.** Configure an Amazon Simple Queue Service (Amazon SQS) queue as a destination for the jobs. Implement the compute nodes with Amazon
EC2 instances that are managed in an Auto Scaling group. Configure EC2 Auto Scaling based on the size of the queue.

**C.** Implement the primary server and the compute nodes with Amazon EC2 instances that are managed in an Auto Scaling group. Configure
AWS CloudTrail as a destination for the jobs. Configure EC2 Auto Scaling based on the load on the primary server.

**D.** Implement the primary server and the compute nodes with Amazon EC2 instances that are managed in an Auto Scaling group. Configure
Amazon EventBridge (Amazon CloudWatch Events) as a destination for the jobs. Configure EC2 Auto Scaling based on the load on the
compute nodes.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is migrating a distributed application to AWS. The application serves variable workloads. The legacy platform consists of a primary server that coordinates jobs across multiple compute nodes. The company wants to modernize the application with a solution that maximizes resiliency and scalability.
How should a solutions architect design the architecture to meet these requirements?


**B.** Configure an Amazon Simple Queue Service (Amazon SQS) queue as a destination for the jobs. Implement the compute nodes with Amazon EC2 instances that are managed in an Auto Scaling group. Configure EC2 Auto Scaling based on the size of the queue.

Option B: This option provides a decoupled architecture where the jobs are sent to an SQS queue. The compute nodes (EC2 instances in an Auto Scaling group) can then process these jobs. Scaling based on the size of the SQS queue (the number of messages) allows the architecture to adapt to variable workloads, scaling out when the queue depth increases and scaling in when the depth decreases.

</details>

---

## Question 9

[Review topic](../sections/ec2-storage.md) · Source PDF page 4

A company is running an SMB file server in its data center. The file server stores large files that are accessed frequently for the first few days after
the files are created. After 7 days the files are rarely accessed.
The total data size is increasing and is close to the company's total storage capacity. A solutions architect must increase the company's available
storage space without losing low-latency access to the most recently accessed files. The solutions architect must also provide file lifecycle
management to avoid future storage issues.
Which solution will meet these requirements?

**A.** Use AWS DataSync to copy data that is older than 7 days from the SMB file server to AWS.

**B.** Create an Amazon S3 File Gateway to extend the company's storage space. Create an S3 Lifecycle policy to transition the data to S3 Glacier
Deep Archive after 7 days.

**C.** Create an Amazon FSx for Windows File Server file system to extend the company's storage space.

**D.** Install a utility on each user's computer to access Amazon S3. Create an S3 Lifecycle policy to transition the data to S3 Glacier Flexible
Retrieval after 7 days.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is running an SMB file server in its data center. The file server stores large files that are accessed frequently for the first few days after the files are created. After 7 days the files are rarely accessed.
The total data size is increasing and is close to the company's total storage capacity. A solutions architect must increase the company's available storage space without losing low-latency access to the most recently accessed files. The solutions architect must also provide file lifecycle management to avoid future storage issues.
Which solution will meet these requirements?


**B.** Create an Amazon S3 File Gateway to extend the company's storage space. Create an S3 Lifecycle policy to transition the data to S3 Glacier Deep Archive after 7 days.

Option B: Amazon S3 File Gateway provides a hybrid cloud storage solution, integrating on-premises environments with cloud storage. Files written to the file share are automatically saved as S3 objects. With S3 Lifecycle policies, you can transition objects between storage classes. Transitioning to Glacier Deep Archive is suitable for rarely accessed files. This solution addresses both the storage capacity and lifecycle management requirements.

</details>

---

## Question 10

[Review topic](../sections/serverless.md) · Source PDF page 5

A company is building an ecommerce web application on AWS. The application sends information about new orders to an Amazon API Gateway
REST API to process. The company wants to ensure that orders are processed in the order that they are received.
Which solution will meet these requirements?

**A.** Use an API Gateway integration to publish a message to an Amazon Simple Notification Service (Amazon SNS) topic when the application
receives an order. Subscribe an AWS Lambda function to the topic to perform processing.

**B.** Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) FIFO queue when the application
receives an order. Configure the SQS FIFO queue to invoke an AWS Lambda function for processing.

**C.** Use an API Gateway authorizer to block any requests while the application processes an order.

**D.** Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) standard queue when the
application receives an order. Configure the SQS standard queue to invoke an AWS Lambda function for processing.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is building an ecommerce web application on AWS. The application sends information about new orders to an Amazon API Gateway REST API to process. The company wants to ensure that orders are processed in the order that they are received.
Which solution will meet these requirements?


**B.** Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) FIFO queue when the application receives an order. Configure the SQS FIFO queue to invoke an AWS Lambda function for processing

Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) FIFO queue when the application receives an order. Configure the SQS FIFO queue to invoke an AWS Lambda function for processing.

</details>

---

## Question 11

[Review topic](../sections/ec2.md) · Source PDF page 5

A company has an application that runs on Amazon EC2 instances and uses an Amazon Aurora database. The EC2 instances connect to the
database by using user names and passwords that are stored locally in a file. The company wants to minimize the operational overhead of
credential management.
What should a solutions architect do to accomplish this goal?

**A.** Use AWS Secrets Manager. Turn on automatic rotation.

**B.** Use AWS Systems Manager Parameter Store. Turn on automatic rotation.

**C.** Create an Amazon S3 bucket to store objects that are encrypted with an AWS Key Management Service (AWS KMS) encryption key. Migrate
the credential file to the S3 bucket. Point the application to the S3 bucket.

**D.** Create an encrypted Amazon Elastic Block Store (Amazon EBS) volume for each EC2 instance. Attach the new EBS volume to each EC2
instance. Migrate the credential file to the new EBS volume. Point the application to the new EBS volume.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an application that runs on Amazon EC2 instances and uses an Amazon Aurora database. The EC2 instances connect to the database by using user names and passwords that are stored locally in a file. The company wants to minimize the operational overhead of credential management.
What should a solutions architect do to accomplish this goal?


**A.** Use AWS Secrets Manager and attach an IAM role that grants access to that secret to the EC2 instances that need it. Turn on automatic rotation. 

 AWS Secrets Manager is a secrets management service that helps you protect access to your applications, services, and IT resources. This service enables you to rotate, manage, and retrieve database credentials, API keys, and other secrets throughout their lifecycle.

</details>

---

## Question 12

[Review topic](../sections/elb-asg.md) · Source PDF page 5

A global company hosts its web application on Amazon EC2 instances behind an Application Load Balancer (ALB). The web application has static
data and dynamic data. The company stores its static data in an Amazon S3 bucket. The company wants to improve performance and reduce
latency for the static data and dynamic data. The company is using its own domain name registered with Amazon Route 53.
What should a solutions architect do to meet these requirements?

**A.** Create an Amazon CloudFront distribution that has the S3 bucket and the ALB as origins. Configure Route 53 to route traffic to the
CloudFront distribution.

**B.** Create an Amazon CloudFront distribution that has the ALB as an origin. Create an AWS Global Accelerator standard accelerator that has
the S3 bucket as an endpoint Configure Route 53 to route traffic to the CloudFront distribution.

**C.** Create an Amazon CloudFront distribution that has the S3 bucket as an origin. Create an AWS Global Accelerator standard accelerator that
has the ALB and the CloudFront distribution as endpoints. Create a custom domain name that points to the accelerator DNS name. Use the
custom domain name as an endpoint for the web application.

**D.** Create an Amazon CloudFront distribution that has the ALB as an origin. Create an AWS Global Accelerator standard accelerator that has
the S3 bucket as an endpoint. Create two domain names. Point one domain name to the CloudFront DNS name for dynamic content. Point the
other domain name to the accelerator DNS name for static content. Use the domain names as endpoints for the web application.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A global company hosts its web application on Amazon EC2 instances behind an Application Load Balancer (ALB). The web application has static data and dynamic data. The company stores its static data in an Amazon S3 bucket. The company wants to improve performance and reduce latency for the static data and dynamic data. The company is using its own domain name registered with Amazon Route 53.
What should a solutions architect do to meet these requirements?


**A.** Create an Amazon CloudFront distribution that has the S3 bucket and the ALB as origins. Configure Route 53 to route traffic to the CloudFront distribution.

CloudFront with Multiple Origins: CloudFront allows you to set up multiple origins for your distribution, so you can use both the ALB (for dynamic content) and the S3 bucket (for static content) as origins. This means that both your dynamic and static content can be served through CloudFront, which will cache content at edge locations to reduce latency.
Route 53 Integration with CloudFront: Amazon Route 53 can be easily configured to route traffic for your domain to a CloudFront distribution. Users will access your domain, and Route 53 will direct them to the nearest CloudFront edge location.

</details>

---

## Question 13

[Review topic](../sections/rds-aurora.md) · Source PDF page 6

A company performs monthly maintenance on its AWS infrastructure. During these maintenance activities, the company needs to rotate the
credentials for its Amazon RDS for MySQL databases across multiple AWS Regions.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Store the credentials as secrets in AWS Secrets Manager. Use multi-Region secret replication for the required Regions. Configure Secrets
Manager to rotate the secrets on a schedule.

**B.** Store the credentials as secrets in AWS Systems Manager by creating a secure string parameter. Use multi-Region secret replication for the
required Regions. Configure Systems Manager to rotate the secrets on a schedule.

**C.** Store the credentials in an Amazon S3 bucket that has server-side encryption (SSE) enabled. Use Amazon EventBridge (Amazon
CloudWatch Events) to invoke an AWS Lambda function to rotate the credentials.

**D.** Encrypt the credentials as secrets by using AWS Key Management Service (AWS KMS) multi-Region customer managed keys. Store the
secrets in an Amazon DynamoDB global table. Use an AWS Lambda function to retrieve the secrets from DynamoDB. Use the RDS API to
rotate the secrets.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company performs monthly maintenance on its AWS infrastructure. During these maintenance activities, the company needs to rotate the credentials for its Amazon RDS for MySQL databases across multiple AWS Regions.
Which solution will meet these requirements with the LEAST operational overhead?


**A.** Store the credentials as secrets in AWS Secrets Manager. Use multi-Region secret replication for the required Regions. Configure Secrets Manager to rotate the secrets on a schedule.

AWS Secrets Manager allows you to store, manage, and rotate secrets, such as database credentials, across multiple AWS Regions. By enabling multi-Region secret replication, you can replicate the secrets across the required Regions to allow for seamless rotation of the credentials during maintenance activities. Additionally, Secrets Manager provides automatic rotation of secrets on a schedule, which would minimize the operational overhead of rotating the credentials on a monthly basis.

</details>

---

## Question 14

[Review topic](../sections/elb-asg.md) · Source PDF page 6

A company runs an ecommerce application on Amazon EC2 instances behind an Application Load Balancer. The instances run in an Amazon EC2
Auto Scaling group across multiple Availability Zones. The Auto Scaling group scales based on CPU utilization metrics. The ecommerce
application stores the transaction data in a MySQL 8.0 database that is hosted on a large EC2 instance.
The database's performance degrades quickly as application load increases. The application handles more read requests than write transactions.
The company wants a solution that will automatically scale the database to meet the demand of unpredictable read workloads while maintaining
high availability.
Which solution will meet these requirements?

**A.** Use Amazon Redshift with a single node for leader and compute functionality.

**B.** Use Amazon RDS with a Single-AZ deployment Configure Amazon RDS to add reader instances in a different Availability Zone.

**C.** Use Amazon Aurora with a Multi-AZ deployment. Configure Aurora Auto Scaling with Aurora Replicas.

**D.** Use Amazon ElastiCache for Memcached with EC2 Spot Instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs an ecommerce application on Amazon EC2 instances behind an Application Load Balancer. The instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. The Auto Scaling group scales based on CPU utilization metrics. The ecommerce application stores the transaction data in a MySQL 8.0 database that is hosted on a large EC2 instance.
The database's performance degrades quickly as application load increases. The application handles more read requests than write transactions. The company wants a solution that will automatically scale the database to meet the demand of unpredictable read workloads while maintaining high availability.
Which solution will meet these requirements?


**C.** Use Amazon Aurora with a Multi-AZ deployment. Configure Aurora Auto Scaling with Aurora Replicas.

Option C: Using Amazon Aurora with a Multi-AZ deployment and configuring Aurora Auto Scaling with Aurora Replicas is the most appropriate solution. Aurora is a MySQL-compatible relational database engine that provides high performance and scalability. With Multi-AZ deployment, the database is automatically replicated across multiple Availability Zones for high availability.
Aurora Auto Scaling allows the database to automatically add or remove Aurora Replicas based on the workload, ensuring that read requests can be distributed effectively and the database can scale to meet demand. This provides both high availability and automatic scaling to handle unpredictable read workloads.

</details>

---

## Question 15

[Review topic](../sections/vpc.md) · Source PDF page 6

A company recently migrated to AWS and wants to implement a solution to protect the traffic that flows in and out of the production VPC. The
company had an inspection server in its on-premises data center. The inspection server performed specific operations such as traffic flow
inspection and traffic filtering. The company wants to have the same functionalities in the AWS Cloud.
Which solution will meet these requirements?

**A.** Use Amazon GuardDuty for traffic inspection and traffic filtering in the production VPC.

**B.** Use Traffic Mirroring to mirror traffic from the production VPC for traffic inspection and filtering.

**C.** Use AWS Network Firewall to create the required rules for traffic inspection and traffic filtering for the production VPC.

**D.** Use AWS Firewall Manager to create the required rules for traffic inspection and traffic filtering for the production VPC.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company recently migrated to AWS and wants to implement a solution to protect the traffic that flows in and out of the production VPC. The company had an inspection server in its on-premises data center. The inspection server performed specific operations such as traffic flow inspection and traffic filtering. The company wants to have the same functionalities in the AWS Cloud.
Which solution will meet these requirements?


**C.** Use AWS Network Firewall to create the required rules for traffic inspection and traffic filtering for the production VPC.

AWS Network Firewall is a managed firewall service that provides filtering for both inbound and outbound network traffic. It allows you to create rules for traffic inspection and filtering, which can help protect your production VPC

</details>

---

## Question 16

[Review topic](../sections/rds-aurora.md) · Source PDF page 7

A company hosts a data lake on AWS. The data lake consists of data in Amazon S3 and Amazon RDS for PostgreSQL. The company needs a
reporting solution that provides data visualization and includes all the data sources within the data lake. Only the company's management team
should have full access to all the visualizations. The rest of the company should have only limited access.
Which solution will meet these requirements?

**A.** Create an analysis in Amazon QuickSight. Connect all the data sources and create new datasets. Publish dashboards to visualize the data.
Share the dashboards with the appropriate IAM roles.

**B.** Create an analysis in Amazon QuickSight. Connect all the data sources and create new datasets. Publish dashboards to visualize the data.
Share the dashboards with the appropriate users and groups.

**C.** Create an AWS Glue table and crawler for the data in Amazon S3. Create an AWS Glue extract, transform, and load (ETL) job to produce
reports. Publish the reports to Amazon S3. Use S3 bucket policies to limit access to the reports.

**D.** Create an AWS Glue table and crawler for the data in Amazon S3. Use Amazon Athena Federated Query to access data within Amazon RDS
for PostgreSQL. Generate reports by using Amazon Athena. Publish the reports to Amazon S3. Use S3 bucket policies to limit access to the
reports.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company hosts a data lake on AWS. The data lake consists of data in Amazon S3 and Amazon RDS for PostgreSQL. The company needs a reporting solution that provides data visualization and includes all the data sources within the data lake. Only the company's management team should have full access to all the visualizations. The rest of the company should have only limited access.
Which solution will meet these requirements?


**B.** Create an analysis in Amazon QuickSight. Connect all the data sources and create new datasets. Publish dashboards to visualize the data. Share the dashboards with the appropriate users and groups

using Amazon QuickSight, which is a business intelligence tool provided by AWS for data visualization and reporting. With this option, you can connect all the data sources within the data lake, including Amazon S3 and Amazon RDS for PostgreSQL. You can create datasets within QuickSight that pull data from these sources.

</details>

---

## Question 17

[Review topic](../sections/s3.md) · Source PDF page 7

A company is implementing a new business application. The application runs on two Amazon EC2 instances and uses an Amazon S3 bucket for
document storage. A solutions architect needs to ensure that the EC2 instances can access the S3 bucket.
What should the solutions architect do to meet this requirement?

**A.** Create an IAM role that grants access to the S3 bucket. Attach the role to the EC2 instances.

**B.** Create an IAM policy that grants access to the S3 bucket. Attach the policy to the EC2 instances.

**C.** Create an IAM group that grants access to the S3 bucket. Attach the group to the EC2 instances.

**D.** Create an IAM user that grants access to the S3 bucket. Attach the user account to the EC2 instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is implementing a new business application. The application runs on two Amazon EC2 instances and uses an Amazon S3 bucket for document storage. A solutions architect needs to ensure that the EC2 instances can access the S3 bucket.
What should the solutions architect do to meet this requirement?


**A.** Create an IAM role that grants access to the S3 bucket. Attach the role to the EC2 instances

An IAM role is an AWS resource that allows you to delegate access to AWS resources and services. You can create an IAM role that grants access to the S3 bucket and then attach the role to the EC2 instances. This will allow the EC2 instances to access the S3 bucket and the documents stored within it.

</details>

---

## Question 18

[Review topic](../sections/s3.md) · Source PDF page 7

An application development team is designing a microservice that will convert large images to smaller, compressed images. When a user uploads
an image through the web interface, the microservice should store the image in an Amazon S3 bucket, process and compress the image with an
AWS Lambda function, and store the image in its compressed form in a different S3 bucket.
A solutions architect needs to design a solution that uses durable, stateless components to process the images automatically.
Which combination of actions will meet these requirements? (Choose two.)

**A.** Create an Amazon Simple Queue Service (Amazon SQS) queue. Configure the S3 bucket to send a notification to the SQS queue when an
image is uploaded to the S3 bucket.

**B.** Configure the Lambda function to use the Amazon Simple Queue Service (Amazon SQS) queue as the invocation source. When the SQS
message is successfully processed, delete the message in the queue.

**C.** Configure the Lambda function to monitor the S3 bucket for new uploads. When an uploaded image is detected, write the file name to a text
file in memory and use the text file to keep track of the images that were processed.

**D.** Launch an Amazon EC2 instance to monitor an Amazon Simple Queue Service (Amazon SQS) queue. When items are added to the queue,
log the file name in a text file on the EC2 instance and invoke the Lambda function.

**E.** Configure an Amazon EventBridge (Amazon CloudWatch Events) event to monitor the S3 bucket. When an image is uploaded, send an alert
to an Amazon ample Notification Service (Amazon SNS) topic with the application owner's email address for further processing.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An application development team is designing a microservice that will convert large images to smaller, compressed images. When a user uploads an image through the web interface, the microservice should store the image in an Amazon S3 bucket, process and compress the image with an AWS Lambda function, and store the image in its compressed form in a different S3 bucket.
A solutions architect needs to design a solution that uses durable, stateless components to process the images automatically.
Which combination of actions will meet these requirements? (Choose two.)


**A.** Create an Amazon Simple Queue Service (Amazon SQS) queue. Configure the S3 bucket to send a notification to the SQS queue when an image is uploaded to the S3 bucket. 


**B.** Configure the Lambda function to use the Amazon Simple Queue Service (Amazon SQS) queue as the invocation source. When the SQS message is successfully processed, delete the message in the queue

Option A: By creating an Amazon SQS queue and configuring the S3 bucket to send a notification to the SQS queue when an image is uploaded, the system establishes a durable and scalable way to handle incoming image processing tasks.

Option B: Configuring the Lambda function to use the SQS queue as the invocation source allows it to retrieve messages from the queue and process them in a stateless manner. After successfully processing the image, the Lambda function can delete the message from the queue to avoid duplicate processing.

</details>

---

## Question 19

[Review topic](../sections/vpc.md) · Source PDF page 8

A company has a three-tier web application that is deployed on AWS. The web servers are deployed in a public subnet in a VPC. The application
servers and database servers are deployed in private subnets in the same VPC. The company has deployed a third-party virtual firewall appliance
from AWS Marketplace in an inspection VPC. The appliance is configured with an IP interface that can accept IP packets.
A solutions architect needs to integrate the web application with the appliance to inspect all traffic to the application before the traffic reaches the
web server.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create a Network Load Balancer in the public subnet of the application's VPC to route the traffic to the appliance for packet inspection.

**B.** Create an Application Load Balancer in the public subnet of the application's VPC to route the traffic to the appliance for packet inspection.

**C.** Deploy a transit gateway in the inspection VPConfigure route tables to route the incoming packets through the transit gateway.

**D.** Deploy a Gateway Load Balancer in the inspection VPC. Create a Gateway Load Balancer endpoint to receive the incoming packets and
forward the packets to the appliance.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a three-tier web application that is deployed on AWS. The web servers are deployed in a public subnet in a VPC. The application servers and database servers are deployed in private subnets in the same VPC. The company has deployed a third-party virtual firewall appliance from AWS Marketplace in an inspection VPC. The appliance is configured with an IP interface that can accept IP packets.
A solutions architect needs to integrate the web application with the appliance to inspect all traffic to the application before the traffic reaches the web server.
Which solution will meet these requirements with the LEAST operational overhead?

 Deploy a Gateway Load Balancer in the inspection VPC. Create a Gateway Load Balancer endpoint to receive the incoming packets and forward the packets to the appliance.

 Gateway Load Balancer is a new type of load balancer that operates at layer 3 of the OSI model and is built on Hyperplane, which is capable of handling several thousands of connections per second. Gateway Load Balancer endpoints are configured in spoke VPCs originating or receiving traffic from the Internet. This architecture allows you to perform inline inspection of traffic from multiple spoke VPCs in a simplified and scalable fashion while still centralizing your virtual appliances.

</details>

---

## Question 20

[Review topic](../sections/cloud-foundations.md) · Source PDF page 8

A company wants to improve its ability to clone large amounts of production data into a test environment in the same AWS Region. The data is
stored in Amazon EC2 instances on Amazon Elastic Block Store (Amazon EBS) volumes. Modifications to the cloned data must not affect the
production environment. The software that accesses this data requires consistently high I/O performance.
A solutions architect needs to minimize the time that is required to clone the production data into the test environment.
Which solution will meet these requirements?

**A.** Take EBS snapshots of the production EBS volumes. Restore the snapshots onto EC2 instance store volumes in the test environment.

**B.** Configure the production EBS volumes to use the EBS Multi-Attach feature. Take EBS snapshots of the production EBS volumes. Attach the
production EBS volumes to the EC2 instances in the test environment.

**C.** Take EBS snapshots of the production EBS volumes. Create and initialize new EBS volumes. Attach the new EBS volumes to EC2 instances
in the test environment before restoring the volumes from the production EBS snapshots.

**D.** Take EBS snapshots of the production EBS volumes. Turn on the EBS fast snapshot restore feature on the EBS snapshots. Restore the
snapshots into new EBS volumes. Attach the new EBS volumes to EC2 instances in the test environment.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to improve its ability to clone large amounts of production data into a test environment in the same AWS Region. The data is stored in Amazon EC2 instances on Amazon Elastic Block Store (Amazon EBS) volumes. Modifications to the cloned data must not affect the production environment. The software that accesses this data requires consistently high I/O performance.
A solutions architect needs to minimize the time that is required to clone the production data into the test environment.
Which solution will meet these requirements?

 Take EBS snapshots of the production EBS volumes. Turn on the EBS fast snapshot restore feature on the EBS snapshots. Restore the snapshots into new EBS volumes. Attach the new EBS volumes to EC2 instances in the test environment

Amazon EBS fast snapshot restore (FSR) enables you to create a volume from a snapshot that is fully initialized at creation. This eliminates the latency of I/O operations on a block when it is accessed for the first time. Volumes that are created using fast snapshot restore instantly deliver all of their provisioned performance

</details>

---

## Question 21

[Review topic](../sections/exam-revision.md) · Source PDF page 8

An ecommerce company wants to launch a one-deal-a-day website on AWS. Each day will feature exactly one product on sale for a period of 24
hours. The company wants to be able to handle millions of requests each hour with millisecond latency during peak hours.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use Amazon S3 to host the full website in different S3 buckets. Add Amazon CloudFront distributions. Set the S3 buckets as origins for the
distributions. Store the order data in Amazon S3.

**B.** Deploy the full website on Amazon EC2 instances that run in Auto Scaling groups across multiple Availability Zones. Add an Application
Load Balancer (ALB) to distribute the website traffic. Add another ALB for the backend APIs. Store the data in Amazon RDS for MySQL.

**C.** Migrate the full application to run in containers. Host the containers on Amazon Elastic Kubernetes Service (Amazon EKS). Use the
Kubernetes Cluster Autoscaler to increase and decrease the number of pods to process bursts in traffic. Store the data in Amazon RDS for
MySQL.

**D.** Use an Amazon S3 bucket to host the website's static content. Deploy an Amazon CloudFront distribution. Set the S3 bucket as the origin.
Use Amazon API Gateway and AWS Lambda functions for the backend APIs. Store the data in Amazon DynamoDB.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

An ecommerce company wants to launch a one-deal-a-day website on AWS. Each day will feature exactly one product on sale for a period of 24 hours. The company wants to be able to handle millions of requests each hour with millisecond latency during peak hours.
Which solution will meet these requirements with the LEAST operational overhead?


**D.** Use an Amazon S3 bucket to host the website's static content. Deploy an Amazon CloudFront distribution. Set the S3 bucket as the origin. Use Amazon API Gateway and AWS Lambda functions for the backend APIs. Store the data in Amazon DynamoDB.

 Use an Amazon S3 bucket to host the website's static content, deploy an Amazon CloudFront distribution, set the S3 bucket as the origin, and use Amazon API Gateway and AWS Lambda functions for the backend APIs. Store the data in Amazon DynamoDB.

Using Amazon S3 to host static content and Amazon CloudFront to distribute the content can provide high performance and scale for websites with millions of requests each hour. Amazon API Gateway and AWS Lambda can be used to build scalable and highly available backend APIs to support the website, and Amazon DynamoDB can be used to store the data. This solution requires minimal operational overhead as it leverages fully managed services that automatically scale to meet demand.

</details>

---

## Question 22

[Review topic](../sections/cloud-foundations.md) · Source PDF page 9

A solutions architect is using Amazon S3 to design the storage architecture of a new digital media application. The media files must be resilient to
the loss of an Availability Zone. Some files are accessed frequently while other files are rarely accessed in an unpredictable pattern. The solutions
architect must minimize the costs of storing and retrieving the media files.
Which storage option meets these requirements?

**A.** S3 Standard

**B.** S3 Intelligent-Tiering

**C.** S3 Standard-Infrequent Access (S3 Standard-IA)

**D.** S3 One Zone-Infrequent Access (S3 One Zone-IA)

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect is using Amazon S3 to design the storage architecture of a new digital media application. The media files must be resilient to the loss of an Availability Zone. Some files are accessed frequently while other files are rarely accessed in an unpredictable pattern. The solutions architect must minimize the costs of storing and retrieving the media files.
Which storage option meets these requirements? 


**B.** S3 Intelligent-Tiering

Amazon S3 Intelligent Tiering is a storage class that automatically moves data to the most cost-effective storage tier based on access patterns. It can store objects in two access tiers: the frequent access tier and the infrequent access tier. The frequent access tier is optimized for frequently accessed objects and is charged at the same rate as S3 Standard. The infrequent access tier is optimized for objects that are not accessed frequently and are charged at a lower rate than S3 Standard.

S3 Intelligent Tiering is a good choice for storing media files that are accessed frequently and infrequently in an unpredictable pattern because it automatically moves data to the most cost-effective storage tier based on access patterns, minimizing storage and retrieval costs. It is also resilient to the loss of an Availability Zone because it stores objects in multiple Availability Zones within a region.

</details>

---

## Question 23

[Review topic](../sections/s3.md) · Source PDF page 9

A company is storing backup files by using Amazon S3 Standard storage. The files are accessed frequently for 1 month. However, the files are not
accessed after 1 month. The company must keep the files indefinitely.
Which storage solution will meet these requirements MOST cost-effectively?

**A.** Configure S3 Intelligent-Tiering to automatically migrate objects.

**B.** Create an S3 Lifecycle configuration to transition objects from S3 Standard to S3 Glacier Deep Archive after 1 month.

**C.** Create an S3 Lifecycle configuration to transition objects from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-IA) after 1
month.

**D.** Create an S3 Lifecycle configuration to transition objects from S3 Standard to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 1
month.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is storing backup files by using Amazon S3 Standard storage. The files are accessed frequently for 1 month. However, the files are not accessed after 1 month. The company must keep the files indefinitely.
Which storage solution will meet these requirements MOST cost-effectively? 


**B.** Create an S3 Lifecycle configuration to transition objects from S3 Standard to S3 Glacier Deep Archive after 1 month.

Amazon S3 Glacier Deep Archive is a secure, durable, and extremely low-cost Amazon S3 storage class for long-term retention of data that is rarely accessed and for which retrieval times of several hours are acceptable. It is the lowest-cost storage option in Amazon S3, making it a cost-effective choice for storing backup files that are not accessed after 1 month.

You can use an S3 Lifecycle configuration to automatically transition objects from S3 Standard to S3 Glacier Deep Archive after 1 month. This will minimize the storage costs for the backup files that are not accessed frequently.

</details>

---

## Question 24

[Review topic](../sections/ec2.md) · Source PDF page 9

A company observes an increase in Amazon EC2 costs in its most recent bill. The billing team notices unwanted vertical scaling of instance types
for a couple of EC2 instances. A solutions architect needs to create a graph comparing the last 2 months of EC2 costs and perform an in-depth
analysis to identify the root cause of the vertical scaling.
How should the solutions architect generate the information with the LEAST operational overhead?

**A.** Use AWS Budgets to create a budget report and compare EC2 costs based on instance types.

**B.** Use Cost Explorer's granular filtering feature to perform an in-depth analysis of EC2 costs based on instance types.

**C.** Use graphs from the AWS Billing and Cost Management dashboard to compare EC2 costs based on instance types for the last 2 months.

**D.** Use AWS Cost and Usage Reports to create a report and send it to an Amazon S3 bucket. Use Amazon QuickSight with Amazon S3 as a
source to generate an interactive graph based on instance types.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company observes an increase in Amazon EC2 costs in its most recent bill. The billing team notices unwanted vertical scaling of instance types for a couple of EC2 instances. A solutions architect needs to create a graph comparing the last 2 months of EC2 costs and perform an in-depth analysis to identify the root cause of the vertical scaling.
How should the solutions architect generate the information with the LEAST operational overhead?


**B.** Use Cost Explorer's granular filtering feature to perform an in-depth analysis of EC2 costs based on instance types.

</details>

---

## Question 25

[Review topic](../sections/serverless.md) · Source PDF page 10

A company is designing an application. The application uses an AWS Lambda function to receive information through Amazon API Gateway and to
store the information in an Amazon Aurora PostgreSQL database.
During the proof-of-concept stage, the company has to increase the Lambda quotas significantly to handle the high volumes of data that the
company needs to load into the database. A solutions architect must recommend a new design to improve scalability and minimize the
configuration effort.
Which solution will meet these requirements?

**A.** Refactor the Lambda function code to Apache Tomcat code that runs on Amazon EC2 instances. Connect the database by using native
Java Database Connectivity (JDBC) drivers.

**B.** Change the platform from Aurora to Amazon DynamoDProvision a DynamoDB Accelerator (DAX) cluster. Use the DAX client SDK to point
the existing DynamoDB API calls at the DAX cluster.

**C.** Set up two Lambda functions. Configure one function to receive the information. Configure the other function to load the information into
the database. Integrate the Lambda functions by using Amazon Simple Notification Service (Amazon SNS).

**D.** Set up two Lambda functions. Configure one function to receive the information. Configure the other function to load the information into
the database. Integrate the Lambda functions by using an Amazon Simple Queue Service (Amazon SQS) queue.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is designing an application. The application uses an AWS Lambda function to receive information through Amazon API Gateway and to store the information in an Amazon Aurora PostgreSQL database.
During the proof-of-concept stage, the company has to increase the Lambda quotas significantly to handle the high volumes of data that the company needs to load into the database. A solutions architect must recommend a new design to improve scalability and minimize the configuration effort.
Which solution will meet these requirements?


**D.** Set up two Lambda functions. Configure one function to receive the information. Configure the other function to load the information into the database. Integrate the Lambda functions by using an Amazon Simple Queue Service (Amazon SQS) queue.


"By dividing the functionality into two Lambda functions, one for receiving the information and the other for loading it into the database, you can independently scale and optimize each function based on their specific requirements. This approach allows for more efficient resource allocation and reduces the potential impact of high volumes of data on the overall system.

</details>

---

## Question 26

[Review topic](../sections/s3.md) · Source PDF page 10

A company needs to review its AWS Cloud deployment to ensure that its Amazon S3 buckets do not have unauthorized configuration changes.
What should a solutions architect do to accomplish this goal?

**A.** Turn on AWS Config with the appropriate rules.

**B.** Turn on AWS Trusted Advisor with the appropriate checks.

**C.** Turn on Amazon Inspector with the appropriate assessment template.

**D.** Turn on Amazon S3 server access logging. Configure Amazon EventBridge (Amazon Cloud Watch Events).

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs to review its AWS Cloud deployment to ensure that its Amazon S3 buckets do not have unauthorized configuration changes.
What should a solutions architect do to accomplish this goal?


**A.** Turn on AWS Config with the appropriate rules.

AWS Config is a service that enables you to assess, audit, and evaluate the configurations of your AWS resources. You can use AWS Config to monitor and record changes to the configuration of your Amazon S3 buckets. By turning on AWS Config and enabling the appropriate rules, you can ensure that your S3 buckets do not have unauthorized configuration changes.

</details>

---

## Question 27

[Review topic](../sections/operations.md) · Source PDF page 10

A company is launching a new application and will display application metrics on an Amazon CloudWatch dashboard. The company's product
manager needs to access this dashboard periodically. The product manager does not have an AWS account. A solutions architect must provide
access to the product manager by following the principle of least privilege.
Which solution will meet these requirements?

**A.** Share the dashboard from the CloudWatch console. Enter the product manager's email address, and complete the sharing steps. Provide a
shareable link for the dashboard to the product manager.

**B.** Create an IAM user specifically for the product manager. Attach the CloudWatchReadOnlyAccess AWS managed policy to the user. Share
the new login credentials with the product manager. Share the browser URL of the correct dashboard with the product manager.

**C.** Create an IAM user for the company's employees. Attach the ViewOnlyAccess AWS managed policy to the IAM user. Share the new login
credentials with the product manager. Ask the product manager to navigate to the CloudWatch console and locate the dashboard by name in
the Dashboards section.

**D.** Deploy a bastion server in a public subnet. When the product manager requires access to the dashboard, start the server and share the RDP
credentials. On the bastion server, ensure that the browser is configured to open the dashboard URL with cached AWS credentials that have
appropriate permissions to view the dashboard.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is launching a new application and will display application metrics on an Amazon CloudWatch dashboard. The company's product manager needs to access this dashboard periodically. The product manager does not have an AWS account. A solutions architect must provide access to the product manager by following the principle of least privilege.
Which solution will meet these requirements?


**A.** Share the dashboard from the CloudWatch console. Enter the product manager's email address, and complete the sharing steps. Provide a shareable link for the dashboard to the product manage.


Share a single dashboard and designate specific email addresses of the people who can view the dashboard. Each of these users creates their own password that they must enter to view the dashboard.

</details>

---

## Question 28

[Review topic](../sections/iam.md) · Source PDF page 11

A company is migrating applications to AWS. The applications are deployed in different accounts. The company manages the accounts centrally
by using AWS Organizations. The company's security team needs a single sign-on (SSO) solution across all the company's accounts. The company
must continue managing the users and groups in its on-premises self-managed Microsoft Active Directory.
Which solution will meet these requirements?

**A.** Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console. Create a one-way forest trust or a one-way domain trust to connect the
company's self-managed Microsoft Active Directory with AWS SSO by using AWS Directory Service for Microsoft Active Directory.

**B.** Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console. Create a two-way forest trust to connect the company's self-managed
Microsoft Active Directory with AWS SSO by using AWS Directory Service for Microsoft Active Directory.

**C.** Use AWS Directory Service. Create a two-way trust relationship with the company's self-managed Microsoft Active Directory.

**D.** Deploy an identity provider (IdP) on premises. Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is migrating applications to AWS. The applications are deployed in different accounts. The company manages the accounts centrally by using AWS Organizations. The company's security team needs a single sign-on (SSO) solution across all the company's accounts. The company must continue managing the users and groups in its on-premises self-managed Microsoft Active Directory.

Which solution will meet these requirements?


**B.** Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console. Create a two-way forest trust to connect the company's self-managed Microsoft Active Directory with AWS SSO by using AWS Directory Service for Microsoft Active Directory.

Explanation:
AWS Single Sign-On (AWS SSO), now called AWS IAM Identity Center, provides centralized SSO access across multiple AWS accounts in AWS Organizations. To continue managing users and groups in the company's on-premises self-managed Microsoft Active Directory, the company can connect the directory to AWS Managed Microsoft AD by using a two-way forest trust. The two-way trust is required so IAM Identity Center can authenticate users and read users and groups from the self-managed Active Directory.

Option A is incorrect because a one-way trust is not enough for IAM Identity Center in this scenario. Option C is incomplete because it creates the trust but does not configure AWS SSO/IAM Identity Center for SSO across accounts. Option D adds unnecessary operational overhead by deploying a separate on-premises identity provider.

</details>

---

## Question 29

[Review topic](../sections/elb-asg.md) · Source PDF page 11

A company provides a Voice over Internet Protocol (VoIP) service that uses UDP connections. The service consists of Amazon EC2 instances that
run in an Auto Scaling group. The company has deployments across multiple AWS Regions.
The company needs to route users to the Region with the lowest latency. The company also needs automated failover between Regions.
Which solution will meet these requirements?

**A.** Deploy a Network Load Balancer (NLB) and an associated target group. Associate the target group with the Auto Scaling group. Use the
NLB as an AWS Global Accelerator endpoint in each Region.

**B.** Deploy an Application Load Balancer (ALB) and an associated target group. Associate the target group with the Auto Scaling group. Use the
ALB as an AWS Global Accelerator endpoint in each Region.

**C.** Deploy a Network Load Balancer (NLB) and an associated target group. Associate the target group with the Auto Scaling group. Create an
Amazon Route 53 latency record that points to aliases for each NLB. Create an Amazon CloudFront distribution that uses the latency record
as an origin.

**D.** Deploy an Application Load Balancer (ALB) and an associated target group. Associate the target group with the Auto Scaling group. Create
an Amazon Route 53 weighted record that points to aliases for each ALB. Deploy an Amazon CloudFront distribution that uses the weighted
record as an origin.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company provides a Voice over Internet Protocol (VoIP) service that uses UDP connections. The service consists of Amazon EC2 instances that run in an Auto Scaling group. The company has deployments across multiple AWS Regions.
The company needs to route users to the Region with the lowest latency. The company also needs automated failover between Regions.
Which solution will meet these requirements?


**A.** Deploy a Network Load Balancer (NLB) and an associated target group. Associate the target group with the Auto Scaling group. Use the NLB as an AWS Global Accelerator endpoint in each Region.

Answer A does not mention service Global Accelerator, it mentions the NLB would act like one. Not sure if the wording is wrong or not.
' Deploy a Network Load Balancer (NLB) and an associated target group. Associate the target group with the Auto Scaling group. Use the NLB as an AWS Global Accelerator endpoint in each Region.

</details>

---

## Question 30

[Review topic](../sections/rds-aurora.md) · Source PDF page 11

A development team runs monthly resource-intensive tests on its general purpose Amazon RDS for MySQL DB instance with Performance Insights
enabled. The testing lasts for 48 hours once a month and is the only process that uses the database. The team wants to reduce the cost of
running the tests without reducing the compute and memory attributes of the DB instance.
Which solution meets these requirements MOST cost-effectively?

**A.** Stop the DB instance when tests are completed. Restart the DB instance when required.

**B.** Use an Auto Scaling policy with the DB instance to automatically scale when tests are completed.

**C.** Create a snapshot when tests are completed. Terminate the DB instance and restore the snapshot when required.

**D.** Modify the DB instance to a low-capacity instance when tests are completed. Modify the DB instance again when required.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A development team runs monthly resource-intensive tests on its general purpose Amazon RDS for MySQL DB instance with Performance Insights enabled. The testing lasts for 48 hours once a month and is the only process that uses the database. The team wants to reduce the cost of running the tests without reducing the compute and memory attributes of the DB instance.
Which solution meets these requirements MOST cost-effectively?


**C.** Create a snapshot when tests are completed. Terminate the DB instance and restore the snapshot when required.

By creating a snapshot and terminating the DB instance, you effectively stop incurring costs for the running instance. When you need to run the tests again, you can restore the snapshot to create a new instance and resume testing. This approach allows you to save costs during the periods when the tests are not running.

</details>

---

## Question 31

[Review topic](../sections/ec2.md) · Source PDF page 12

A company that hosts its web application on AWS wants to ensure all Amazon EC2 instances. Amazon RDS DB instances. and Amazon Redshift
clusters are configured with tags. The company wants to minimize the effort of configuring and operating this check.
What should a solutions architect do to accomplish this?

**A.** Use AWS Config rules to define and detect resources that are not properly tagged.

**B.** Use Cost Explorer to display resources that are not properly tagged. Tag those resources manually.

**C.** Write API calls to check all resources for proper tag allocation. Periodically run the code on an EC2 instance.

**D.** Write API calls to check all resources for proper tag allocation. Schedule an AWS Lambda function through Amazon CloudWatch to
periodically run the code.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company that hosts its web application on AWS wants to ensure all Amazon EC2 instances. Amazon RDS DB instances. and Amazon Redshift clusters are configured with tags. The company wants to minimize the effort of configuring and operating this check.
What should a solutions architect do to accomplish this?


**A.** Use AWS Config rules to define and detect resources that are not properly tagged.

Yes, you can use AWS Config to create tags for your resources. AWS Config is a service that enables you to assess, audit, and evaluate the configurations of your AWS resources. You can use AWS Config to create rules that automatically tag resources when they are created or when their configurations change.

</details>

---

## Question 32

[Review topic](../sections/exam-revision.md) · Source PDF page 12

A development team needs to host a website that will be accessed by other teams. The website contents consist of HTML, CSS, client-side
JavaScript, and images.
Which method is the MOST cost-effective for hosting the website?

**A.** Containerize the website and host it in AWS Fargate.

**B.** Create an Amazon S3 bucket and host the website there.

**C.** Deploy a web server on an Amazon EC2 instance to host the website.

**D.** Configure an Application Load Balancer with an AWS Lambda target that uses the Express.js framework.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A development team needs to host a website that will be accessed by other teams. The website contents consist of HTML, CSS, client-side JavaScript, and images.

Which method is the MOST cost-effective for hosting the website?


**B.** Create an Amazon S3 bucket and host the website there.

Explanation:
The website is a static website because it consists only of HTML, CSS, client-side JavaScript, and images. The most cost-effective method is to create an Amazon S3 bucket and host the website there.

Amazon S3 is a highly scalable and cost-effective object storage service. It is suitable for hosting static websites because no web servers, containers, or backend compute resources are required.

To host the website on Amazon S3, the development team would create an S3 bucket, upload the website files to the bucket, and configure the bucket for static website hosting.

Option A is incorrect because AWS Fargate is used to run containers and is unnecessary for a static website. Option C is incorrect because an EC2 web server would add compute cost and operational overhead. Option D is incorrect because using an Application Load Balancer with Lambda and Express.js is overly complex for static content.

</details>

---

## Question 33

[Review topic](../sections/exam-revision.md) · Source PDF page 12

A company runs an online marketplace web application on AWS. The application serves hundreds of thousands of users during peak hours. The
company needs a scalable, near-real-time solution to share the details of millions of financial transactions with several other internal applications.
Transactions also need to be processed to remove sensitive data before being stored in a document database for low-latency retrieval.
What should a solutions architect recommend to meet these requirements?

**A.** Store the transactions data into Amazon DynamoDB. Set up a rule in DynamoDB to remove sensitive data from every transaction upon
write. Use DynamoDB Streams to share the transactions data with other applications.

**B.** Stream the transactions data into Amazon Kinesis Data Firehose to store data in Amazon DynamoDB and Amazon S3. Use AWS Lambda
integration with Kinesis Data Firehose to remove sensitive data. Other applications can consume the data stored in Amazon S3.

**C.** Stream the transactions data into Amazon Kinesis Data Streams. Use AWS Lambda integration to remove sensitive data from every
transaction and then store the transactions data in Amazon DynamoDB. Other applications can consume the transactions data off the Kinesis
data stream.

**D.** Store the batched transactions data in Amazon S3 as files. Use AWS Lambda to process every file and remove sensitive data before
updating the files in Amazon S3. The Lambda function then stores the data in Amazon DynamoDB. Other applications can consume
transaction files stored in Amazon S3.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs an online marketplace web application on AWS. The application serves hundreds of thousands of users during peak hours. The company needs a scalable, near-real-time solution to share the details of millions of financial transactions with several other internal applications. Transactions also need to be processed to remove sensitive data before being stored in a document database for low-latency retrieval.
What should a solutions architect recommend to meet these requirements?


**C.** Stream the transactions data into Amazon Kinesis Data Streams. Use AWS Lambda integration to remove sensitive data from every transaction and then store the transactions data in Amazon DynamoDB. Other applications can consume the transactions data off the Kinesis data stream. 

1. Real-time Data Stream: To share millions of financial transactions with other apps, you need to be able to ingest data in real-time, which is made possible by Amazon Kinesis Data Streams.

2. Data Transformation: You can cleanse and eliminate sensitive data from transactions before storing them in Amazon DynamoDB by utilizing AWS Lambda with Kinesis Data Streams. This takes care of the requirement to handle sensitive data with care.
3. Scalability: DynamoDB and Amazon Kinesis are both extremely scalable technologies that can manage enormous data volumes and adjust to the workload.

</details>

---

## Question 34

[Review topic](../sections/exam-revision.md) · Source PDF page 13

A company hosts its multi-tier applications on AWS. For compliance, governance, auditing, and security, the company must track configuration
changes on its AWS resources and record a history of API calls made to these resources.
What should a solutions architect do to meet these requirements?

**A.** Use AWS CloudTrail to track configuration changes and AWS Config to record API calls.

**B.** Use AWS Config to track configuration changes and AWS CloudTrail to record API calls.

**C.** Use AWS Config to track configuration changes and Amazon CloudWatch to record API calls.

**D.** Use AWS CloudTrail to track configuration changes and Amazon CloudWatch to record API calls.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company hosts its multi-tier applications on AWS. For compliance, governance, auditing, and security, the company must track configuration changes on its AWS resources and record a history of API calls made to these resources.
What should a solutions architect do to meet these requirements?


**B.** Use AWS Config to track configuration changes and AWS CloudTrail to record API calls.

AWS Config for Configuration Changes: AWS Config is a service that tracks changes to resource configurations over time. It provides a history of configuration changes to your AWS resources and helps with compliance and auditing by allowing you to assess how resource configurations have changed over time.

AWS CloudTrail for API Calls: AWS CloudTrail is designed specifically for recording API calls made to AWS resources. It captures detailed information about who made each API call, the actions taken, and the resources affected. This is essential for auditing and security purposes.

</details>

---

## Question 35

[Review topic](../sections/elb-asg.md) · Source PDF page 13

A company is preparing to launch a public-facing web application in the AWS Cloud. The architecture consists of Amazon EC2 instances within a
VPC behind an Elastic Load Balancer (ELB). A third-party service is used for the DNS. The company's solutions architect must recommend a
solution to detect and protect against large-scale DDoS attacks.
Which solution meets these requirements?

**A.** Enable Amazon GuardDuty on the account.

**B.** Enable Amazon Inspector on the EC2 instances.

**C.** Enable AWS Shield and assign Amazon Route 53 to it.

**D.** Enable AWS Shield Advanced and assign the ELB to it.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is preparing to launch a public-facing web application in the AWS Cloud. The architecture consists of Amazon EC2 instances within a VPC behind an Elastic Load Balancer (ELB). A third-party service is used for the DNS. The company's solutions architect must recommend a solution to detect and protect against large-scale DDoS attacks.
Which solution meets these requirements?


**D.** Enable AWS Shield Advanced and assign the ELB to it.

AWS Shield Advanced provides expanded DDoS attack protection for your Amazon EC2 instances, Elastic Load Balancing load balancers, CloudFront distributions, Route 53 hosted zones, and AWS Global Accelerator standard accelerators.

</details>

---

## Question 36

[Review topic](../sections/s3.md) · Source PDF page 13

A company is building an application in the AWS Cloud. The application will store data in Amazon S3 buckets in two AWS Regions. The company
must use an AWS Key Management Service (AWS KMS) customer managed key to encrypt all data that is stored in the S3 buckets. The data in
both S3 buckets must be encrypted and decrypted with the same KMS key. The data and the key must be stored in each of the two Regions.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create an S3 bucket in each Region. Configure the S3 buckets to use server-side encryption with Amazon S3 managed encryption keys
(SSE-S3). Configure replication between the S3 buckets.

**B.** Create a customer managed multi-Region KMS key. Create an S3 bucket in each Region. Configure replication between the S3 buckets.
Configure the application to use the KMS key with client-side encryption.

**C.** Create a customer managed KMS key and an S3 bucket in each Region. Configure the S3 buckets to use server-side encryption with
Amazon S3 managed encryption keys (SSE-S3). Configure replication between the S3 buckets.

**D.** Create a customer managed KMS key and an S3 bucket in each Region. Configure the S3 buckets to use server-side encryption with AWS
KMS keys (SSE-KMS). Configure replication between the S3 buckets.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is building an application in the AWS Cloud. The application will store data in Amazon S3 buckets in two AWS Regions. The company must use an AWS Key Management Service (AWS KMS) customer managed key to encrypt all data that is stored in the S3 buckets. The data in both S3 buckets must be encrypted and decrypted with the same KMS key. The data and the key must be stored in each of the two Regions.

Which solution will meet these requirements with the LEAST operational overhead?


**B.** Create a customer managed multi-Region KMS key. Create an S3 bucket in each Region. Configure replication between the S3 buckets. Configure the application to use the KMS key with client-side encryption.

Explanation:
The requirement says that the data in both S3 buckets must be encrypted and decrypted with the same KMS key, and that the key must exist in both AWS Regions. This points to an AWS KMS multi-Region customer managed key. A multi-Region KMS key has related keys in different Regions with the same key material, which allows data encrypted in one Region to be decrypted in another Region.

Option A is incorrect because SSE-S3 uses Amazon S3 managed keys, not AWS KMS customer managed keys. Option C is incorrect because it creates customer managed KMS keys but then uses SSE-S3. Option D is close, but it creates separate KMS keys in each Region instead of using a multi-Region KMS key with the same key material.

</details>

---

## Question 37

[Review topic](../sections/exam-revision.md) · Source PDF page 14

A company recently launched a variety of new workloads on Amazon EC2 instances in its AWS account. The company needs to create a strategy
to access and administer the instances remotely and securely. The company needs to implement a repeatable process that works with native AWS
services and follows the AWS Well-Architected Framework.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use the EC2 serial console to directly access the terminal interface of each instance for administration.

**B.** Attach the appropriate IAM role to each existing instance and new instance. Use AWS Systems Manager Session Manager to establish a
remote SSH session.

**C.** Create an administrative SSH key pair. Load the public key into each EC2 instance. Deploy a bastion host in a public subnet to provide a
tunnel for administration of each instance.

**D.** Establish an AWS Site-to-Site VPN connection. Instruct administrators to use their local on-premises machines to connect directly to the
instances by using SSH keys across the VPN tunnel.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company recently launched a variety of new workloads on Amazon EC2 instances in its AWS account. The company needs to create a strategy to access and administer the instances remotely and securely. The company needs to implement a repeatable process that works with native AWS services and follows the AWS Well-Architected Framework.
Which solution will meet these requirements with the LEAST operational overhead?


**B.** Attach the appropriate IAM role to each existing instance and new instance. Use AWS Systems Manager Session Manager to establish a remote SSH session.

With AWS Systems Manager Session Manager, you can manage your Amazon Elastic Compute Cloud (Amazon EC2) instances, edge devices, on-premises servers, and virtual machines (VMs). You can use either an interactive one-click browser-based shell or the AWS Command Line Interface (AWS CLI). It provides secure and auditable node management without the need to open inbound ports, maintain bastion hosts, or manage SSH keys.

</details>

---

## Question 38

[Review topic](../sections/global-delivery.md) · Source PDF page 14

A company is hosting a static website on Amazon S3 and is using Amazon Route 53 for DNS. The website is experiencing increased demand from
around the world. The company must decrease latency for users who access the website.
Which solution meets these requirements MOST cost-effectively?

**A.** Replicate the S3 bucket that contains the website to all AWS Regions. Add Route 53 geolocation routing entries.

**B.** Provision accelerators in AWS Global Accelerator. Associate the supplied IP addresses with the S3 bucket. Edit the Route 53 entries to
point to the IP addresses of the accelerators.

**C.** Add an Amazon CloudFront distribution in front of the S3 bucket. Edit the Route 53 entries to point to the CloudFront distribution.

**D.** Enable S3 Transfer Acceleration on the bucket. Edit the Route 53 entries to point to the new endpoint.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is hosting a static website on Amazon S3 and is using Amazon Route 53 for DNS. The website is experiencing increased demand from around the world. The company must decrease latency for users who access the website.
Which solution meets these requirements MOST cost-effectively?


**C.** Add an Amazon CloudFront distribution in front of the S3 bucket. Edit the Route 53 entries to point to the CloudFront distribution

Amazon CloudFront is a content delivery network (CDN) service that distributes content globally to reduce latency. By setting up a CloudFront distribution in front of the S3 bucket hosting the static website, you can take advantage of its edge locations around the world to deliver content from the nearest location to the users, reducing the latency they experience.

CloudFront automatically caches and replicates content to its edge locations, resulting in faster delivery and lower latency for users worldwide. This solution is highly effective in optimizing performance while keeping costs under control because CloudFront charges are based on actual data transfer and requests, and the pay-as-you-go pricing model ensures that you only pay for what you use.

</details>

---

## Question 39

[Review topic](../sections/rds-aurora.md) · Source PDF page 14

A company maintains a searchable repository of items on its website. The data is stored in an Amazon RDS for MySQL database table that
contains more than 10 million rows. The database has 2 TB of General Purpose SSD storage. There are millions of updates against this data every
day through the company's website.
The company has noticed that some insert operations are taking 10 seconds or longer. The company has determined that the database storage
performance is the problem.
Which solution addresses this performance issue?

**A.** Change the storage type to Provisioned IOPS SSD.

**B.** Change the DB instance to a memory optimized instance class.

**C.** Change the DB instance to a burstable performance instance class.

**D.** Enable Multi-AZ RDS read replicas with MySQL native asynchronous replication.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company maintains a searchable repository of items on its website. The data is stored in an Amazon RDS for MySQL database table that contains more than 10 million rows. The database has 2 TB of General Purpose SSD storage. There are millions of updates against this data every day through the company's website.
The company has noticed that some insert operations are taking 10 seconds or longer. The company has determined that the database storage performance is the problem.
Which solution addresses this performance issue?


**A.** Change the storage type to Provisioned IOPS SSD.

Using Amazon Provisioned IOPS (PIOPS) SSD storage is the best way to solve the performance issue of insert operations taking 10 seconds or longer on an Amazon RDS for MySQL database table with more than 10 million rows and 2 TB of General Purpose SSD storage.

A high-performance storage solution with reliable throughput and minimal latency is PIOPS SSD storage. Workloads like insert operations, which demand high I/O performance, are ideally suited for it.

</details>

---

## Question 40

[Review topic](../sections/exam-revision.md) · Source PDF page 15

A company has thousands of edge devices that collectively generate 1 TB of status alerts each day. Each alert is approximately 2 KB in size. A
solutions architect needs to implement a solution to ingest and store the alerts for future analysis.
The company wants a highly available solution. However, the company needs to minimize costs and does not want to manage additional
infrastructure. Additionally, the company wants to keep 14 days of data available for immediate analysis and archive any data older than 14 days.
What is the MOST operationally efficient solution that meets these requirements?

**A.** Create an Amazon Kinesis Data Firehose delivery stream to ingest the alerts. Configure the Kinesis Data Firehose stream to deliver the
alerts to an Amazon S3 bucket. Set up an S3 Lifecycle configuration to transition data to Amazon S3 Glacier after 14 days.

**B.** Launch Amazon EC2 instances across two Availability Zones and place them behind an Elastic Load Balancer to ingest the alerts. Create a
script on the EC2 instances that will store the alerts in an Amazon S3 bucket. Set up an S3 Lifecycle configuration to transition data to
Amazon S3 Glacier after 14 days.

**C.** Create an Amazon Kinesis Data Firehose delivery stream to ingest the alerts. Configure the Kinesis Data Firehose stream to deliver the
alerts to an Amazon OpenSearch Service (Amazon Elasticsearch Service) cluster. Set up the Amazon OpenSearch Service (Amazon
Elasticsearch Service) cluster to take manual snapshots every day and delete data from the cluster that is older than 14 days.

**D.** Create an Amazon Simple Queue Service (Amazon SQS) standard queue to ingest the alerts, and set the message retention period to 14
days. Configure consumers to poll the SQS queue, check the age of the message, and analyze the message data as needed. If the message is
14 days old, the consumer should copy the message to an Amazon S3 bucket and delete the message from the SQS queue.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has thousands of edge devices that collectively generate 1 TB of status alerts each day. Each alert is approximately 2 KB in size. A solutions architect needs to implement a solution to ingest and store the alerts for future analysis.
The company wants a highly available solution. However, the company needs to minimize costs and does not want to manage additional infrastructure. Additionally, the company wants to keep 14 days of data available for immediate analysis and archive any data older than 14 days.
What is the MOST operationally efficient solution that meets these requirements?


**A.** Create an Amazon Kinesis Data Firehose delivery stream to ingest the alerts. Configure the Kinesis Data Firehose stream to deliver the alerts to an Amazon S3 bucket. Set up an S3 Lifecycle configuration to transition data to Amazon S3 Glacier after 14 days.

Amazon Kinesis Data Firehose is a fully managed service that can capture, transform, and deliver streaming data into storage systems or analytics tools, making it an ideal solution for ingesting and storing status alerts. In this solution, the Kinesis Data Firehose delivery stream ingests the alerts and delivers them to an S3 bucket, which is a cost-effective storage solution. An S3 Lifecycle configuration is set up to transition the data to Amazon S3 Glacier after 14 days to minimize storage costs.

</details>

---

## Question 41

[Review topic](../sections/ec2.md) · Source PDF page 15

A company's application integrates with multiple software-as-a-service (SaaS) sources for data collection. The company runs Amazon EC2
instances to receive the data and to upload the data to an Amazon S3 bucket for analysis. The same EC2 instance that receives and uploads the
data also sends a notification to the user when an upload is complete. The company has noticed slow application performance and wants to
improve the performance as much as possible.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create an Auto Scaling group so that EC2 instances can scale out. Configure an S3 event notification to send events to an Amazon Simple
Notification Service (Amazon SNS) topic when the upload to the S3 bucket is complete.

**B.** Create an Amazon AppFlow flow to transfer data between each SaaS source and the S3 bucket. Configure an S3 event notification to send
events to an Amazon Simple Notification Service (Amazon SNS) topic when the upload to the S3 bucket is complete.

**C.** Create an Amazon EventBridge (Amazon CloudWatch Events) rule for each SaaS source to send output data. Configure the S3 bucket as the
rule's target. Create a second EventBridge (Cloud Watch Events) rule to send events when the upload to the S3 bucket is complete. Configure
an Amazon Simple Notification Service (Amazon SNS) topic as the second rule's target.

**D.** Create a Docker container to use instead of an EC2 instance. Host the containerized application on Amazon Elastic Container Service
(Amazon ECS). Configure Amazon CloudWatch Container Insights to send events to an Amazon Simple Notification Service (Amazon SNS)
topic when the upload to the S3 bucket is complete.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company's application integrates with multiple software-as-a-service (SaaS) sources for data collection. The company runs Amazon EC2 instances to receive the data and to upload the data to an Amazon S3 bucket for analysis. The same EC2 instance that receives and uploads the data also sends a notification to the user when an upload is complete. The company has noticed slow application performance and wants to improve the performance as much as possible.
Which solution will meet these requirements with the LEAST operational overhead?	


**B.** Create an Amazon AppFlow flow to transfer data between each SaaS source and the S3 bucket. Configure an S3 event notification to send events to an Amazon Simple Notification Service (Amazon SNS) topic when the upload to the S3 bucket is complete.

Amazon AppFlow is a fully-managed integration service that enables you to securely exchange data between software as a service (SaaS) applications, such as Salesforce, and AWS services, such as Amazon Simple Storage Service (Amazon S3) and Amazon Redshift.
The use of Appflow helps to remove the ec2 as the middle layer which slows down the process of data transmission and introduce an additional variable.
Appflow is also a fully managed AWS service, thus reducing the operational overhead.

</details>

---

## Question 42

[Review topic](../sections/ec2.md) · Source PDF page 16

A company runs a highly available image-processing application on Amazon EC2 instances in a single VPC. The EC2 instances run inside several
subnets across multiple Availability Zones. The EC2 instances do not communicate with each other. However, the EC2 instances download images
from Amazon S3 and upload images to Amazon S3 through a single NAT gateway. The company is concerned about data transfer charges.
What is the MOST cost-effective way for the company to avoid Regional data transfer charges?

**A.** Launch the NAT gateway in each Availability Zone.

**B.** Replace the NAT gateway with a NAT instance.

**C.** Deploy a gateway VPC endpoint for Amazon S3.

**D.** Provision an EC2 Dedicated Host to run the EC2 instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a highly available image-processing application on Amazon EC2 instances in a single VPC. The EC2 instances run inside several subnets across multiple Availability Zones. The EC2 instances do not communicate with each other. However, the EC2 instances download images from Amazon S3 and upload images to Amazon S3 through a single NAT gateway. The company is concerned about data transfer charges.
What is the MOST cost-effective way for the company to avoid Regional data transfer charges?


**C.** Deploy a gateway VPC endpoint for Amazon S3.

S3 VPC endpoint provides a way for an S3 request to be routed through to the Amazon S3 service, without having to connect a subnet to an internet gateway. The S3 VPC endpoint is what's known as a gateway endpoint.

</details>

---

## Question 43

[Review topic](../sections/s3.md) · Source PDF page 16

A company has an on-premises application that generates a large amount of time-sensitive data that is backed up to Amazon S3. The application
has grown and there are user complaints about internet bandwidth limitations. A solutions architect needs to design a long-term solution that
allows for both timely backups to Amazon S3 and with minimal impact on internet connectivity for internal users.
Which solution meets these requirements?

**A.** Establish AWS VPN connections and proxy all traffic through a VPC gateway endpoint.

**B.** Establish a new AWS Direct Connect connection and direct backup traffic through this new connection.

**C.** Order daily AWS Snowball devices. Load the data onto the Snowball devices and return the devices to AWS each day.

**D.** Submit a support ticket through the AWS Management Console. Request the removal of S3 service limits from the account.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an on-premises application that generates a large amount of time-sensitive data that is backed up to Amazon S3. The application has grown and there are user complaints about internet bandwidth limitations. A solutions architect needs to design a long-term solution that allows for both timely backups to Amazon S3 and with minimal impact on internet connectivity for internal users.
Which solution meets these requirements?


**B.** Establish a new AWS Direct Connect connection and direct backup traffic through this new connection.

AWS Direct Connect is a network service that allows you to establish a dedicated network connection from your on-premises data center to AWS. This connection bypasses the public Internet and can provide more reliable, lower-latency communication between your on-premises application and Amazon S3. By directing backup traffic through the AWS Direct Connect connection, you can minimize the impact on your internet bandwidth and ensure timely backups to S3.

</details>

---

## Question 44

[Review topic](../sections/s3.md) · Source PDF page 16

A company has an Amazon S3 bucket that contains critical data. The company must protect the data from accidental deletion.
Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)

**A.** Enable versioning on the S3 bucket.

**B.** Enable MFA Delete on the S3 bucket.

**C.** Create a bucket policy on the S3 bucket.

**D.** Enable default encryption on the S3 bucket.

**E.** Create a lifecycle policy for the objects in the S3 bucket.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an Amazon S3 bucket that contains critical data. The company must protect the data from accidental deletion.
Which combination of steps should a solutions architect take to meet these requirements? (Choose two.)


**A.** Enable versioning on the S3 bucket

**B.** Enable MFA Delete on the S3 bucket

The two most effective steps a solutions architect can take to protect an Amazon S3 bucket from accidental deletion are:


**A.** Enable versioning on the S3 bucket.

**B.** Enable MFA Delete on the S3 bucket.

Versioning keeps multiple versions of objects in the S3 bucket, even when they are overwritten or deleted. This allows you to recover objects that have been accidentally deleted.

MFA Delete requires you to enter a one-time password from a multi-factor authentication (MFA) device before you can delete an object in the S3 bucket. This helps to prevent accidental deletions.

</details>

---

## Question 45

[Review topic](../sections/serverless.md) · Source PDF page 17

A company has a data ingestion workflow that consists of the following:
• An Amazon Simple Notification Service (Amazon SNS) topic for notifications about new data deliveries
• An AWS Lambda function to process the data and record metadata
The company observes that the ingestion workflow fails occasionally because of network connectivity issues. When such a failure occurs, the
Lambda function does not ingest the corresponding data unless the company manually reruns the job.
Which combination of actions should a solutions architect take to ensure that the Lambda function ingests all data in the future? (Choose two.)

**A.** Deploy the Lambda function in multiple Availability Zones.

**B.** Create an Amazon Simple Queue Service (Amazon SQS) queue, and subscribe it to the SNS topic.

**C.** Increase the CPU and memory that are allocated to the Lambda function.

**D.** Increase provisioned throughput for the Lambda function.

**E.** Modify the Lambda function to read from an Amazon Simple Queue Service (Amazon SQS) queue.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a data ingestion workflow that consists of the following:
• An Amazon Simple Notification Service (Amazon SNS) topic for notifications about new data deliveries
• An AWS Lambda function to process the data and record metadata
The company observes that the ingestion workflow fails occasionally because of network connectivity issues. When such a failure occurs, the Lambda function does not ingest the corresponding data unless the company manually reruns the job.
Which combination of actions should a solutions architect take to ensure that the Lambda function ingests all data in the future? (Choose two.)


**B.** Create an Amazon Simple Queue Service (Amazon SQS) queue, and subscribe it to the SNS topic.

**E.** Modify the Lambda function to read from an Amazon Simple Queue Service (Amazon SQS) queue.


**B.** Create an Amazon Simple Queue Service (Amazon SQS) queue, and subscribe it to the SNS topic. This will decouple the ingestion workflow and provide a buffer to temporarily store the data in case of network connectivity issues.


**E.** Modify the Lambda function to read from an Amazon Simple Queue Service (Amazon SQS) queue. This will allow the Lambda function to process the data from the SQS queue at its own pace, decoupling the data ingestion from the data delivery and providing more flexibility and fault tolerance.

</details>

---

## Question 46

[Review topic](../sections/exam-revision.md) · Source PDF page 17

A company has an application that provides marketing services to stores. The services are based on previous purchases by store customers. The
stores upload transaction data to the company through SFTP, and the data is processed and analyzed to generate new marketing offers. Some of
the files can exceed 200 GB in size.
Recently, the company discovered that some of the stores have uploaded files that contain personally identifiable information (PII) that should not
have been included. The company wants administrators to be alerted if PII is shared again. The company also wants to automate remediation.
What should a solutions architect do to meet these requirements with the LEAST development effort?

**A.** Use an Amazon S3 bucket as a secure transfer point. Use Amazon Inspector to scan the objects in the bucket. If objects contain PII, trigger
an S3 Lifecycle policy to remove the objects that contain PII.

**B.** Use an Amazon S3 bucket as a secure transfer point. Use Amazon Macie to scan the objects in the bucket. If objects contain PII, use
Amazon Simple Notification Service (Amazon SNS) to trigger a notification to the administrators to remove the objects that contain PII.

**C.** Implement custom scanning algorithms in an AWS Lambda function. Trigger the function when objects are loaded into the bucket. If
objects contain PII, use Amazon Simple Notification Service (Amazon SNS) to trigger a notification to the administrators to remove the objects
that contain PII.

**D.** Implement custom scanning algorithms in an AWS Lambda function. Trigger the function when objects are loaded into the bucket. If
objects contain PII, use Amazon Simple Email Service (Amazon SES) to trigger a notification to the administrators and trigger an S3 Lifecycle
policy to remove the meats that contain PII.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has an application that provides marketing services to stores. The services are based on previous purchases by store customers. The stores upload transaction data to the company through SFTP, and the data is processed and analyzed to generate new marketing offers. Some of the files can exceed 200 GB in size.
Recently, the company discovered that some of the stores have uploaded files that contain personally identifiable information (PII) that should not have been included. The company wants administrators to be alerted if PII is shared again. The company also wants to automate remediation.
What should a solutions architect do to meet these requirements with the LEAST development effort?


**B.** Use an Amazon S3 bucket as a secure transfer point. Use Amazon Macie to scan the objects in the bucket. If objects contain PII, use Amazon Simple Notification Service (Amazon SNS) to trigger a notification to the administrators to remove the objects that contain PII.

Some quotas can be increased, while others cannot. To request an increase to a quota, use the Service Quotas console. To learn how to request an increase, see Requesting a quota increase in the Service Quotas User Guide. If a quota isn't available on the Service Quotas console, use the service limit increase form on the AWS Support Center Console to request an increase to the quota.

</details>

---

## Question 47

[Review topic](../sections/ec2.md) · Source PDF page 17

A company needs guaranteed Amazon EC2 capacity in three specific Availability Zones in a specific AWS Region for an upcoming event that will
last 1 week.
What should the company do to guarantee the EC2 capacity?

**A.** Purchase Reserved Instances that specify the Region needed.

**B.** Create an On-Demand Capacity Reservation that specifies the Region needed.

**C.** Purchase Reserved Instances that specify the Region and three Availability Zones needed.

**D.** Create an On-Demand Capacity Reservation that specifies the Region and three Availability Zones needed.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs guaranteed Amazon EC2 capacity in three specific Availability Zones in a specific AWS Region for an upcoming event that will last 1 week.
What should the company do to guarantee the EC2 capacity?


**D.** Create an On-Demand Capacity Reservation that specifies the Region and three Availability Zones needed.

An On-Demand Capacity Reservation is a type of Amazon EC2 reservation that enables you to create and manage reserved capacity on Amazon EC2. With an On-Demand Capacity Reservation, you can specify the Region and Availability Zones where you want to reserve capacity, and the number of EC2 instances you want to reserve. This allows you to guarantee capacity in specific Availability Zones in a specific Region.

</details>

---

## Question 48

[Review topic](../sections/ec2-storage.md) · Source PDF page 18

A company's website uses an Amazon EC2 instance store for its catalog of items. The company wants to make sure that the catalog is highly
available and that the catalog is stored in a durable location.
What should a solutions architect do to meet these requirements?

**A.** Move the catalog to Amazon ElastiCache for Redis.

**B.** Deploy a larger EC2 instance with a larger instance store.

**C.** Move the catalog from the instance store to Amazon S3 Glacier Deep Archive.

**D.** Move the catalog to an Amazon Elastic File System (Amazon EFS) file system.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company's website uses an Amazon EC2 instance store for its catalog of items. The company wants to make sure that the catalog is highly available and that the catalog is stored in a durable location.
What should a solutions architect do to meet these requirements?


**D.** Move the catalog to an Amazon Elastic File System (Amazon EFS) file system.

EFS is fully managed, durable, highly available, and shared file system.

</details>

---

## Question 49

[Review topic](../sections/cost-governance.md) · Source PDF page 18

A company stores call transcript files on a monthly basis. Users access the files randomly within 1 year of the call, but users access the files
infrequently after 1 year. The company wants to optimize its solution by giving users the ability to query and retrieve files that are less than 1-year-
old as quickly as possible. A delay in retrieving older files is acceptable.
Which solution will meet these requirements MOST cost-effectively?

**A.** Store individual files with tags in Amazon S3 Glacier Instant Retrieval. Query the tags to retrieve the files from S3 Glacier Instant Retrieval.

**B.** Store individual files in Amazon S3 Intelligent-Tiering. Use S3 Lifecycle policies to move the files to S3 Glacier Flexible Retrieval after 1 year.
Query and retrieve the files that are in Amazon S3 by using Amazon Athena. Query and retrieve the files that are in S3 Glacier by using S3
Glacier Select.

**C.** Store individual files with tags in Amazon S3 Standard storage. Store search metadata for each archive in Amazon S3 Standard storage.
Use S3 Lifecycle policies to move the files to S3 Glacier Instant Retrieval after 1 year. Query and retrieve the files by searching for metadata
from Amazon S3.

**D.** Store individual files in Amazon S3 Standard storage. Use S3 Lifecycle policies to move the files to S3 Glacier Deep Archive after 1 year.
Store search metadata in Amazon RDS. Query the files from Amazon RDS. Retrieve the files from S3 Glacier Deep Archive.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company stores call transcript files on a monthly basis. Users access the files randomly within 1 year of the call, but users access the files infrequently after 1 year. The company wants to optimize its solution by giving users the ability to query and retrieve files that are less than 1-year-old as quickly as possible. A delay in retrieving older files is acceptable.
Which solution will meet these requirements MOST cost-effectively?


**B.** Store individual files in Amazon S3 Intelligent-Tiering. Use S3 Lifecycle policies to move the files to S3 Glacier Flexible Retrieval after 1 year. Query and retrieve the files that are in Amazon S3 by using Amazon Athena. Query and retrieve the files that are in S3 Glacier by using S3 Glacier Select. 


S3 Intelligent-Tiering is the ideal storage class for data with unknown, changing, or unpredictable access patterns, independent of object size or retention period. You can use S3 Intelligent-Tiering as the default storage class for virtually any workload, especially data lakes, data analytics, new applications, and user-generated content.

</details>

---

## Question 50

[Review topic](../sections/ec2.md) · Source PDF page 18

A company has a production workload that runs on 1,000 Amazon EC2 Linux instances. The workload is powered by third-party software. The
company needs to patch the third-party software on all EC2 instances as quickly as possible to remediate a critical security vulnerability.
What should a solutions architect do to meet these requirements?

**A.** Create an AWS Lambda function to apply the patch to all EC2 instances.

**B.** Configure AWS Systems Manager Patch Manager to apply the patch to all EC2 instances.

**C.** Schedule an AWS Systems Manager maintenance window to apply the patch to all EC2 instances.

**D.** Use AWS Systems Manager Run Command to run a custom command that applies the patch to all EC2 instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a production workload that runs on 1,000 Amazon EC2 Linux instances. The workload is powered by third-party software. The company needs to patch the third-party software on all EC2 instances as quickly as possible to remediate a critical security vulnerability.
What should a solutions architect do to meet these requirements?


**D.** Use AWS Systems Manager Run Command to run a custom command that applies the patch to all EC2 instances.

AWS Systems Manager Run Command allows the company to run commands or scripts on multiple EC2 instances. By using Run Command, the company can quickly and easily apply the patch to all 1,000 EC2 instances to remediate the security vulnerability.

Creating an AWS Lambda function to apply the patch to all EC2 instances would not be a suitable solution, as Lambda functions are not designed to run on EC2 instances. Configuring AWS Systems Manager Patch Manager to apply the patch to all EC2 instances would not be a suitable solution, as Patch Manager is not designed to apply third-party software patches. Scheduling an AWS Systems Manager maintenance window to apply the patch to all EC2 instances would not be a suitable solution, as maintenance windows are not designed to apply patches to third-party software.

</details>

---

