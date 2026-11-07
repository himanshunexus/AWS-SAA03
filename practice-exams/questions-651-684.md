# Practice questions 651-684

[Home](../README.md) · [All sets](README.md)

Answer notes are source-provided unless labeled suggested. These sets preserve the supplied PDF; they are not official AWS exams.

## Question 651

[Review topic](../sections/s3.md) · Source PDF page 236

A company stores a large volume of image files in an Amazon S3 bucket. The images need to be readily available for the first 180 days. The
images are infrequently accessed for the next 180 days. After 360 days, the images need to be archived but must be available instantly upon
request. After 5 years, only auditors can access the images. The auditors must be able to retrieve the images within 12 hours. The images cannot
be lost during this process.
A developer will use S3 Standard storage for the first 180 days. The developer needs to configure an S3 Lifecycle rule.
Which solution will meet these requirements MOST cost-effectively?

**A.** Transition the objects to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 180 days. S3 Glacier Instant Retrieval after 360 days, and
S3 Glacier Deep Archive after 5 years.

**B.** Transition the objects to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 180 days. S3 Glacier Flexible Retrieval after 360 days, and
S3 Glacier Deep Archive after 5 years.

**C.** Transition the objects to S3 Standard-Infrequent Access (S3 Standard-IA) after 180 days, S3 Glacier Instant Retrieval after 360 days, and S3
Glacier Deep Archive after 5 years.

**D.** Transition the objects to S3 Standard-Infrequent Access (S3 Standard-IA) after 180 days, S3 Glacier Flexible Retrieval after 360 days, and S3
Glacier Deep Archive after 5 years.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company stores a large volume of image files in an Amazon S3 bucket. The images need to be readily available for the first 180 days. The images are infrequently accessed for the next 180 days. After 360 days, the images need to be archived but must be available instantly upon request. After 5 years, only auditors can access the images. The auditors must be able to retrieve the images within 12 hours. The images cannot be lost during this process.

C) Transition the objects to S3 Standard-Infrequent Access (S3 Standard-IA) after 180 days, S3 Glacier Instant Retrieval after 360 days, and S3 Glacier Deep Archive after 5 years.
Explanation:
S3 Standard-IA (instead of One Zone-IA) ensures high durability across multiple AZs for infrequent access.
Glacier Instant Retrieval meets the "instant availability" requirement after 360 days, while Glacier Deep Archive is cost-effective for audits after 5 years.
(Option A/B use less durable One Zone-IA, and Option D uses slower Glacier Flexible Retrieval, which violates the "instant" requirement.)

Answer: C) Configure the General Purpose SSD (gp3) EBS volume storage type and provision 15,000 IOPS.
gp3 allows independent provisioning of IOPS (unlike gp2) and is more cost-effective than io1 for 15,000 IOPS.
Magnetic volumes (Option D) are outdated and cannot meet the performance requirement.

</details>

---

## Question 652

[Review topic](../sections/analytics.md) · Source PDF page 237

A company has a large data workload that runs for 6 hours each day. The company cannot lose any data while the process is running. A solutions
architect is designing an Amazon EMR cluster configuration to support this critical data workload.
Which solution will meet these requirements MOST cost-effectively?

**A.** Configure a long-running cluster that runs the primary node and core nodes on On-Demand Instances and the task nodes on Spot
Instances.

**B.** Configure a transient cluster that runs the primary node and core nodes on On-Demand Instances and the task nodes on Spot Instances.

**C.** Configure a transient cluster that runs the primary node on an On-Demand Instance and the core nodes and task nodes on Spot Instances.

**D.** Configure a long-running cluster that runs the primary node on an On-Demand Instance, the core nodes on Spot Instances, and the task
nodes on Spot Instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a large data workload that runs for 6 hours each day. The company cannot lose any data while the process is running. A solutions
architect is designing an Amazon EMR cluster con guration to support this critical data workload.
Which solution will meet these requirements MOST cost-effectively?

Answer: B) Configure a transient cluster with primary/core nodes on On-Demand Instances and task nodes on Spot Instances.
Transient clusters are cost-effective for short workloads. Spot Instances reduce costs for non-critical task nodes.
Long-running clusters (Options A/D) are unnecessary for a 6-hour workload.

</details>

---

## Question 653

[Review topic](../sections/cost-governance.md) · Source PDF page 237

A company maintains an Amazon RDS database that maps users to cost centers. The company has accounts in an organization in AWS
Organizations. The company needs a solution that will tag all resources that are created in a specific AWS account in the organization. The
solution must tag each resource with the cost center ID of the user who created the resource.
Which solution will meet these requirements?

**A.** Move the specific AWS account to a new organizational unit (OU) in Organizations from the management account. Create a service control
policy (SCP) that requires all existing resources to have the correct cost center tag before the resources are created. Apply the SCP to the new
OU.

**B.** Create an AWS Lambda function to tag the resources after the Lambda function looks up the appropriate cost center from the RDS
database. Configure an Amazon EventBridge rule that reacts to AWS CloudTrail events to invoke the Lambda function.

**C.** Create an AWS CloudFormation stack to deploy an AWS Lambda function. Configure the Lambda function to look up the appropriate cost
center from the RDS database and to tag resources. Create an Amazon EventBridge scheduled rule to invoke the CloudFormation stack.

**D.** Create an AWS Lambda function to tag the resources with a default value. Configure an Amazon EventBridge rule that reacts to AWS
CloudTrail events to invoke the Lambda function when a resource is missing the cost center tag.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company maintains an Amazon RDS database that maps users to cost centers. The company has accounts in an organization in AWS
Organizations. The company needs a solution that will tag all resources that are created in a speci c AWS account in the organization. The
solution must tag each resource with the cost center ID of the user who created the resource.
Which solution will meet these requirements?

Answer: B) Create a Lambda function triggered by EventBridge (via CloudTrail) to tag resources based on the RDS cost center DB.
EventBridge + Lambda automates real-time tagging without manual intervention.
SCPs (Option A) cannot dynamically tag resources, and scheduled rules (Option C) are not event-driven.

</details>

---

## Question 654

[Review topic](../sections/ec2.md) · Source PDF page 238

A company recently migrated its web application to the AWS Cloud. The company uses an Amazon EC2 instance to run multiple processes to host
the application. The processes include an Apache web server that serves static content. The Apache web server makes requests to a PHP
application that uses a local Redis server for user sessions.
The company wants to redesign the architecture to be highly available and to use AWS managed solutions.
Which solution will meet these requirements?

**A.** Use AWS Elastic Beanstalk to host the static content and the PHP application. Configure Elastic Beanstalk to deploy its EC2 instance into a
public subnet. Assign a public IP address.

**B.** Use AWS Lambda to host the static content and the PHP application. Use an Amazon API Gateway REST API to proxy requests to the
Lambda function. Set the API Gateway CORS configuration to respond to the domain name. Configure Amazon ElastiCache for Redis to handle
session information.

**C.** Keep the backend code on the EC2 instance. Create an Amazon ElastiCache for Redis cluster that has Multi-AZ enabled. Configure the
ElastiCache for Redis cluster in cluster mode. Copy the frontend resources to Amazon S3. Configure the backend code to reference the EC2
instance.

**D.** Configure an Amazon CloudFront distribution with an Amazon S3 endpoint to an S3 bucket that is configured to host the static content.
Configure an Application Load Balancer that targets an Amazon Elastic Container Service (Amazon ECS) service that runs AWS Fargate tasks
for the PHP application. Configure the PHP application to use an Amazon ElastiCache for Redis cluster that runs in multiple Availability Zones.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company recently migrated its web application to the AWS Cloud. The company uses an Amazon EC2 instance to run multiple processes to host
the application. The processes include an Apache web server that serves static content. The Apache web server makes requests to a PHP
application that uses a local Redis server for user sessions.
The company wants to redesign the architecture to be highly available and to use AWS managed solutions.
Which solution will meet these requirements?

Answer: D) Use CloudFront + S3 for static content, ALB + ECS Fargate for PHP, and Multi-AZ ElastiCache for Redis.
Fully managed services (ECS, ElastiCache) ensure high availability. CloudFront improves static content delivery.
Elastic Beanstalk (Option A) lacks decoupling, and Lambda (Option B) is unsuitable for PHP sessions.

</details>

---

## Question 655

[Review topic](../sections/elb-asg.md) · Source PDF page 238

A company runs a web application on Amazon EC2 instances in an Auto Scaling group that has a target group. The company designed the
application to work with session affinity (sticky sessions) for a better user experience.
The application must be available publicly over the internet as an endpoint. A WAF must be applied to the endpoint for additional security. Session
affinity (sticky sessions) must be configured on the endpoint.
Which combination of steps will meet these requirements? (Choose two.)

**A.** Create a public Network Load Balancer. Specify the application target group.

**B.** Create a Gateway Load Balancer. Specify the application target group.

**C.** Create a public Application Load Balancer. Specify the application target group.

**D.** Create a second target group. Add Elastic IP addresses to the EC2 instances.

**E.** Create a web ACL in AWS WAF. Associate the web ACL with the endpoint

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a web application on Amazon EC2 instances in an Auto Scaling group that has a target group. The company designed the
application to work with session a nity (sticky sessions) for a better user experience.
The application must be available publicly over the internet as an endpoint. A WAF must be applied to the endpoint for additional security. Session
a nity (sticky sessions) must be con gured on the endpoint.
Which combination of steps will meet these requirements? (Choose two.)

Answers: C) Create a public ALB + E) Associate a WAF web ACL with the endpoint.
ALB supports sticky sessions (unlike NLB/GWLB). WAF provides security.
Elastic IPs (Option D) are not scalable.

</details>

---

## Question 656

[Review topic](../sections/cost-governance.md) · Source PDF page 239

A company runs a website that stores images of historical events. Website users need the ability to search and view images based on the year
that the event in the image occurred. On average, users request each image only once or twice a year. The company wants a highly available
solution to store and deliver the images to users.
Which solution will meet these requirements MOST cost-effectively?

**A.** Store images in Amazon Elastic Block Store (Amazon EBS). Use a web server that runs on Amazon EC2.

**B.** Store images in Amazon Elastic File System (Amazon EFS). Use a web server that runs on Amazon EC2.

**C.** Store images in Amazon S3 Standard. Use S3 Standard to directly deliver images by using a static website.

**D.** Store images in Amazon S3 Standard-Infrequent Access (S3 Standard-IA). Use S3 Standard-IA to directly deliver images by using a static
website.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a website that stores images of historical events. Website users need the ability to search and view images based on the year
that the event in the image occurred. On average, users request each image only once or twice a year. The company wants a highly available
solution to store and deliver the images to users.
Which solution will meet these requirements MOST cost-effectively?

Answer: D) Store images in S3 Standard-IA and deliver via static website.
Standard-IA is cost-effective for rarely accessed images. Static websites simplify delivery.
EBS/EFS (Options A/B) are expensive and lack S3’s durability.

</details>

---

## Question 657

[Review topic](../sections/vpc.md) · Source PDF page 239

A company has multiple AWS accounts in an organization in AWS Organizations that different business units use. The company has multiple
offices around the world. The company needs to update security group rules to allow new office CIDR ranges or to remove old CIDR ranges across
the organization. The company wants to centralize the management of security group rules to minimize the administrative overhead that updating
CIDR ranges requires.
Which solution will meet these requirements MOST cost-effectively?

**A.** Create VPC security groups in the organization's management account. Update the security groups when a CIDR range update is necessary.

**B.** Create a VPC customer managed prefix list that contains the list of CIDRs. Use AWS Resource Access Manager (AWS RAM) to share the
prefix list across the organization. Use the prefix list in the security groups across the organization.

**C.** Create an AWS managed prefix list. Use an AWS Security Hub policy to enforce the security group update across the organization. Use an
AWS Lambda function to update the prefix list automatically when the CIDR ranges change.

**D.** Create security groups in a central administrative AWS account. Create an AWS Firewall Manager common security group policy for the
whole organization. Select the previously created security groups as primary groups in the policy.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has multiple AWS accounts in an organization in AWS Organizations that different business units use. The company has multiple
o ces around the world. The company needs to update security group rules to allow new o ce CIDR ranges or to remove old CIDR ranges across
the organization. The company wants to centralize the management of security group rules to minimize the administrative overhead that updating
CIDR ranges requires.
Which solution will meet these requirements MOST cost-effectively?

Answer: B) Create a shared prefix list via AWS RAM and reference it in security groups.
Prefix lists centralize CIDR management. AWS RAM enables cross-account sharing.
Firewall Manager (Option D) is overkill for CIDR updates.

</details>

---

## Question 658

[Review topic](../sections/ec2-storage.md) · Source PDF page 239

A company uses an on-premises network-attached storage (NAS) system to provide file shares to its high performance computing (HPC)
workloads. The company wants to migrate its latency-sensitive HPC workloads and its storage to the AWS Cloud. The company must be able to
provide NFS and SMB multi-protocol access from the file system.
Which solution will meet these requirements with the LEAST latency? (Choose two.)

**A.** Deploy compute optimized EC2 instances into a cluster placement group.

**B.** Deploy compute optimized EC2 instances into a partition placement group.

**C.** Attach the EC2 instances to an Amazon FSx for Lustre file system.

**D.** Attach the EC2 instances to an Amazon FSx for OpenZFS file system.

**E.** Attach the EC2 instances to an Amazon FSx for NetApp ONTAP file system.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses an on-premises network-attached storage (NAS) system to provide le shares to its high performance computing (HPC)
workloads. The company wants to migrate its latency-sensitive HPC workloads and its storage to the AWS Cloud. The company must be able to
provide NFS and SMB multi-protocol access from the le system.
Which solution will meet these requirements with the LEAST latency? (Choose two.)

Answers: A) Deploy compute-optimized EC2 in a cluster placement group + E) Use FSx for NetApp ONTAP.
Cluster placement minimizes latency. FSx for ONTAP supports multi-protocol (NFS/SMB) access.
Lustre (Option C) lacks SMB support.

</details>

---

## Question 659

[Review topic](../sections/migration.md) · Source PDF page 240

A company is relocating its data center and wants to securely transfer 50 TB of data to AWS within 2 weeks. The existing data center has a Site-to-
Site VPN connection to AWS that is 90% utilized.
Which AWS service should a solutions architect use to meet these requirements?

**A.** AWS DataSync with a VPC endpoint

**B.** AWS Direct Connect

**C.** AWS Snowball Edge Storage Optimized

**D.** AWS Storage Gateway

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is relocating its data center and wants to securely transfer 50 TB of data to AWS within 2 weeks. The existing data center has a Site-to-
Site VPN connection to AWS that is 90% utilized.
Which AWS service should a solutions architect use to meet these requirements?

Answer: C) Use AWS Snowball Edge Storage Optimized.
Snowball Edge is ideal for large offline transfers (50 TB in 2 weeks) without VPN bottlenecks.
DataSync (Option A) is for online transfers; Direct Connect (Option B) is too slow.

</details>

---

## Question 660

[Review topic](../sections/elb-asg.md) · Source PDF page 240

A company hosts an application on Amazon EC2 On-Demand Instances in an Auto Scaling group. Application peak hours occur at the same time
each day. Application users report slow application performance at the start of peak hours. The application performs normally 2-3 hours after
peak hours begin. The company wants to ensure that the application works properly at the start of peak hours.
Which solution will meet these requirements?

**A.** Configure an Application Load Balancer to distribute traffic properly to the instances.

**B.** Configure a dynamic scaling policy for the Auto Scaling group to launch new instances based on memory utilization.

**C.** Configure a dynamic scaling policy for the Auto Scaling group to launch new instances based on CPU utilization.

**D.** Configure a scheduled scaling policy for the Auto Scaling group to launch new instances before peak hours.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company hosts an application on Amazon EC2 On-Demand Instances in an Auto Scaling group. Application peak hours occur at the same time
each day. Application users report slow application performance at the start of peak hours. The application performs normally 2-3 hours after
peak hours begin. The company wants to ensure that the application works properly at the start of peak hours.
Which solution will meet these requirements?

Answer: D) Configure scheduled scaling to launch instances before peak hours.
Proactively scales instances to handle predictable traffic spikes.
Dynamic scaling (Options B/C) reacts too slowly for known peaks.

</details>

---

## Question 661

[Review topic](../sections/exam-revision.md) · Source PDF page 240

A company runs applications on AWS that connect to the company's Amazon RDS database. The applications scale on weekends and at peak
times of the year. The company wants to scale the database more effectively for its applications that connect to the database.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use Amazon DynamoDB with connection pooling with a target group configuration for the database. Change the applications to use the
DynamoDB endpoint.

**B.** Use Amazon RDS Proxy with a target group for the database. Change the applications to use the RDS Proxy endpoint.

**C.** Use a custom proxy that runs on Amazon EC2 as an intermediary to the database. Change the applications to use the custom proxy
endpoint.

**D.** Use an AWS Lambda function to provide connection pooling with a target group configuration for the database. Change the applications to
use the Lambda function.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs applications on AWS that connect to the company's Amazon RDS database. The applications scale on weekends and at peak
times of the year. The company wants to scale the database more effectively for its applications that connect to the database.
Which solution will meet these requirements with the LEAST operational overhead?

Answer: B) Use Amazon RDS Proxy for connection pooling.
RDS Proxy manages scaling connections with minimal code changes.
DynamoDB (Option A) is incompatible with RDS.

</details>

---

## Question 662

[Review topic](../sections/ec2-storage.md) · Source PDF page 241

A company uses AWS Cost Explorer to monitor its AWS costs. The company notices that Amazon Elastic Block Store (Amazon EBS) storage and
snapshot costs increase every month. However, the company does not purchase additional EBS storage every month. The company wants to
optimize monthly costs for its current storage usage.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use logs in Amazon CloudWatch Logs to monitor the storage utilization of Amazon EBS. Use Amazon EBS Elastic Volumes to reduce the
size of the EBS volumes.

**B.** Use a custom script to monitor space usage. Use Amazon EBS Elastic Volumes to reduce the size of the EBS volumes.

**C.** Delete all expired and unused snapshots to reduce snapshot costs.

**D.** Delete all nonessential snapshots. Use Amazon Data Lifecycle Manager to create and manage the snapshots according to the company's
snapshot policy requirements.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses AWS Cost Explorer to monitor its AWS costs. The company notices that Amazon Elastic Block Store (Amazon EBS) storage and
snapshot costs increase every month. However, the company does not purchase additional EBS storage every month. The company wants to
optimize monthly costs for its current storage usage.
Which solution will meet these requirements with the LEAST operational overhead

Answer: D) Delete nonessential snapshots + use Data Lifecycle Manager.
Automates snapshot retention per policy, reducing costs.
Manual resizing (Options A/B) adds overhead.

</details>

---

## Question 663

[Review topic](../sections/s3.md) · Source PDF page 241

A company is developing a new application on AWS. The application consists of an Amazon Elastic Container Service (Amazon ECS) cluster, an
Amazon S3 bucket that contains assets for the application, and an Amazon RDS for MySQL database that contains the dataset for the application.
The dataset contains sensitive information. The company wants to ensure that only the ECS cluster can access the data in the RDS for MySQL
database and the data in the S3 bucket.
Which solution will meet these requirements?

**A.** Create a new AWS Key Management Service (AWS KMS) customer managed key to encrypt both the S3 bucket and the RDS for MySQL
database. Ensure that the KMS key policy includes encrypt and decrypt permissions for the ECS task execution role.

**B.** Create an AWS Key Management Service (AWS KMS) AWS managed key to encrypt both the S3 bucket and the RDS for MySQL database.
Ensure that the S3 bucket policy specifies the ECS task execution role as a user.

**C.** Create an S3 bucket policy that restricts bucket access to the ECS task execution role. Create a VPC endpoint for Amazon RDS for MySQL.
Update the RDS for MySQL security group to allow access from only the subnets that the ECS cluster will generate tasks in.

**D.** Create a VPC endpoint for Amazon RDS for MySQL. Update the RDS for MySQL security group to allow access from only the subnets that
the ECS cluster will generate tasks in. Create a VPC endpoint for Amazon S3. Update the S3 bucket policy to allow access from only the S3
VPC endpoint.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is developing a new application on AWS. The application consists of an Amazon Elastic Container Service (Amazon ECS) cluster, an
Amazon S3 bucket that contains assets for the application, and an Amazon RDS for MySQL database that contains the dataset for the application.
The dataset contains sensitive information. The company wants to ensure that only the ECS cluster can access the data in the RDS for MySQL
database and the data in the S3 bucket.
Which solution will meet these requirements?

Answer: C) Restrict S3/RDS access via VPC endpoints + security groups.
VPC endpoints keep traffic private. Security groups limit access to ECS subnets.
KMS (Options A/B) doesn’t restrict network access.

</details>

---

## Question 664

[Review topic](../sections/containers.md) · Source PDF page 242

A company has a web application that runs on premises. The application experiences latency issues during peak hours. The latency issues occur
twice each month. At the start of a latency issue, the application's CPU utilization immediately increases to 10 times its normal amount.
The company wants to migrate the application to AWS to improve latency. The company also wants to scale the application automatically when
application demand increases. The company will use AWS Elastic Beanstalk for application deployment.
Which solution will meet these requirements?

**A.** Configure an Elastic Beanstalk environment to use burstable performance instances in unlimited mode. Configure the environment to scale
based on requests.

**B.** Configure an Elastic Beanstalk environment to use compute optimized instances. Configure the environment to scale based on requests.

**C.** Configure an Elastic Beanstalk environment to use compute optimized instances. Configure the environment to scale on a schedule.

**D.** Configure an Elastic Beanstalk environment to use burstable performance instances in unlimited mode. Configure the environment to scale
on predictive metrics.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has a web application that runs on premises. The application experiences latency issues during peak hours. The latency issues occur
twice each month. At the start of a latency issue, the application's CPU utilization immediately increases to 10 times its normal amount.
The company wants to migrate the application to AWS to improve latency. The company also wants to scale the application automatically when
application demand increases. The company will use AWS Elastic Beanstalk for application deployment.
Which solution will meet these requirements?

Answer: A) Use Elastic Beanstalk with burstable instances (unlimited mode) + request-based scaling.
Burstable instances handle CPU spikes cost-effectively. Request-based scaling matches demand.
Compute-optimized instances (Option B) are overprovisioned for intermittent spikes.

</details>

---

## Question 665

[Review topic](../sections/exam-revision.md) · Source PDF page 242

A company has customers located across the world. The company wants to use automation to secure its systems and network infrastructure. The
company's security team must be able to track and audit all incremental changes to the infrastructure.
Which solution will meet these requirements?

**A.** Use AWS Organizations to set up the infrastructure. Use AWS Config to track changes.

**B.** Use AWS CloudFormation to set up the infrastructure. Use AWS Config to track changes.

**C.** Use AWS Organizations to set up the infrastructure. Use AWS Service Catalog to track changes.

**D.** Use AWS CloudFormation to set up the infrastructure. Use AWS Service Catalog to track changes.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company has customers located across the world. The company wants to use automation to secure its systems and network infrastructure. The
company's security team must be able to track and audit all incremental changes to the infrastructure.
Which solution will meet these requirements?

Answer: B) Use AWS CloudFormation + AWS Config.
CloudFormation automates infrastructure; Config tracks changes for auditing.
Service Catalog (Options C/D) is for governance, not change tracking.

</details>

---

## Question 666

[Review topic](../sections/ec2.md) · Source PDF page 242

A startup company is hosting a website for its customers on an Amazon EC2 instance. The website consists of a stateless Python application and
a MySQL database. The website serves only a small amount of traffic. The company is concerned about the reliability of the instance and needs to
migrate to a highly available architecture. The company cannot modify the application code.
Which combination of actions should a solutions architect take to achieve high availability for the website? (Choose two.)

**A.** Provision an internet gateway in each Availability Zone in use.

**B.** Migrate the database to an Amazon RDS for MySQL Multi-AZ DB instance.

**C.** Migrate the database to Amazon DynamoDB, and enable DynamoDB auto scaling.

**D.** Use AWS DataSync to synchronize the database data across multiple EC2 instances.

**E.** Create an Application Load Balancer to distribute traffic to an Auto Scaling group of EC2 instances that are distributed across two
Availability Zones.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A startup company is hosting a website for its customers on an Amazon EC2 instance. The website consists of a stateless Python application and
a MySQL database. The website serves only a small amount of tra c. The company is concerned about the reliability of the instance and needs to
migrate to a highly available architecture. The company cannot modify the application code.
Which combination of actions should a solutions architect take to achieve high availability for the website? (Choose two.)

Answers: B) Migrate DB to RDS Multi-AZ + E) Use ALB + Auto Scaling for EC2.
RDS Multi-AZ ensures DB high availability. ALB + Auto Scaling distributes traffic across AZs.
DynamoDB (Option C) requires code changes; DataSync (Option D) doesn’t solve HA.

</details>

---

## Question 667

[Review topic](../sections/migration.md) · Source PDF page 243

A company is moving its data and applications to AWS during a multiyear migration project. The company wants to securely access data on
Amazon S3 from the company's AWS Region and from the company's on-premises location. The data must not traverse the internet. The company
has established an AWS Direct Connect connection between its Region and its on-premises location.
Which solution will meet these requirements?

**A.** Create gateway endpoints for Amazon S3. Use the gateway endpoints to securely access the data from the Region and the on-premises
location.

**B.** Create a gateway in AWS Transit Gateway to access Amazon S3 securely from the Region and the on-premises location.

**C.** Create interface endpoints for Amazon S3. Use the interface endpoints to securely access the data from the Region and the on-premises
location.

**D.** Use an AWS Key Management Service (AWS KMS) key to access the data securely from the Region and the on-premises location.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is moving its data and applications to AWS during a multiyear migration project. The company wants to securely access data on
Amazon S3 from the company's AWS Region and from the company's on-premises location. The data must not traverse the internet. The company
has established an AWS Direct Connect connection between its Region and its on-premises location.
Which solution will meet these requirements?

Answer: A) Create S3 gateway endpoints.
Gateway endpoints allow secure S3 access via Direct Connect/VPC without internet.
Interface endpoints (Option C) are for private-link services, not S3.

</details>

---

## Question 668

[Review topic](../sections/iam.md) · Source PDF page 243

A company created a new organization in AWS Organizations. The organization has multiple accounts for the company's development teams. The
development team members use AWS IAM Identity Center (AWS Single Sign-On) to access the accounts. For each of the company's applications,
the development teams must use a predefined application name to tag resources that are created.
A solutions architect needs to design a solution that gives the development team the ability to create resources only if the application name tag
has an approved value.
Which solution will meet these requirements?

**A.** Create an IAM group that has a conditional Allow policy that requires the application name tag to be specified for resources to be created.

**B.** Create a cross-account role that has a Deny policy for any resource that has the application name tag.

**C.** Create a resource group in AWS Resource Groups to validate that the tags are applied to all resources in all accounts.

**D.** Create a tag policy in Organizations that has a list of allowed application names.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company created a new organization in AWS Organizations. The organization has multiple accounts for the company's development teams. The
development team members use AWS IAM Identity Center (AWS Single Sign-On) to access the accounts. For each of the company's applications,
the development teams must use a prede ned application name to tag resources that are created.
A solutions architect needs to design a solution that gives the development team the ability to create resources only if the application name tag
has an approved value.
Which solution will meet these requirements?

Answer: D) Create a tag policy in Organizations with allowed application names.
Tag policies enforce standardized tagging across accounts.
IAM policies (Option A) cannot validate tag values.

</details>

---

## Question 669

[Review topic](../sections/rds-aurora.md) · Source PDF page 243

A company runs its databases on Amazon RDS for PostgreSQL. The company wants a secure solution to manage the master user password by
rotating the password every 30 days.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Use Amazon EventBridge to schedule a custom AWS Lambda function to rotate the password every 30 days.

**B.** Use the modify-db-instance command in the AWS CLI to change the password.

**C.** Integrate AWS Secrets Manager with Amazon RDS for PostgreSQL to automate password rotation.

**D.** Integrate AWS Systems Manager Parameter Store with Amazon RDS for PostgreSQL to automate password rotation.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs its databases on Amazon RDS for PostgreSQL. The company wants a secure solution to manage the master user password by
rotating the password every 30 days.
Which solution will meet these requirements with the LEAST operational overhead?

Answer: C) Use Secrets Manager with RDS for automated password rotation.
Secrets Manager automates rotation every 30 days with zero operational effort.
Manual rotation (Option B) or Parameter Store (Option D) lacks automation.

</details>

---

## Question 670

[Review topic](../sections/dynamodb-caching.md) · Source PDF page 244

A company performs tests on an application that uses an Amazon DynamoDB table. The tests run for 4 hours once a week. The company knows
how many read and write operations the application performs to the table each second during the tests. The company does not currently use
DynamoDB for any other use case. A solutions architect needs to optimize the costs for the table.
Which solution will meet these requirements?

**A.** Choose on-demand mode. Update the read and write capacity units appropriately.

**B.** Choose provisioned mode. Update the read and write capacity units appropriately.

**C.** Purchase DynamoDB reserved capacity for a 1-year term.

**D.** Purchase DynamoDB reserved capacity for a 3-year term.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company performs tests on an application that uses an Amazon DynamoDB table. The tests run for 4 hours once a week. The company knows
how many read and write operations the application performs to the table each second during the tests. The company does not currently use
DynamoDB for any other use case. A solutions architect needs to optimize the costs for the table.
Which solution will meet these requirements?

Answer: B) Choose provisioned mode with calculated RCU/WCU.
Provisioned mode is cost-effective for predictable weekly workloads.
On-demand (Option A) is expensive for infrequent use.

</details>

---

## Question 671

[Review topic](../sections/ec2.md) · Source PDF page 244

A company runs its applications on Amazon EC2 instances. The company performs periodic financial assessments of its AWS costs. The
company recently identified unusual spending.
The company needs a solution to prevent unusual spending. The solution must monitor costs and notify responsible stakeholders in the event of
unusual spending.
Which solution will meet these requirements?

**A.** Use an AWS Budgets template to create a zero spend budget.

**B.** Create an AWS Cost Anomaly Detection monitor in the AWS Billing and Cost Management console.

**C.** Create AWS Pricing Calculator estimates for the current running workload pricing details.

**D.** Use Amazon CloudWatch to monitor costs and to identify unusual spending.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs its applications on Amazon EC2 instances. The company performs periodic nancial assessments of its AWS costs. The
company recently identi ed unusual spending.
The company needs a solution to prevent unusual spending. The solution must monitor costs and notify responsible stakeholders in the event of
unusual spending.
Which solution will meet these requirements?

Answer: B) Create a Cost Anomaly Detection monitor.
Automatically detects and alerts on unusual spending.
CloudWatch (Option D) lacks built-in anomaly detection.

</details>

---

## Question 672

[Review topic](../sections/s3.md) · Source PDF page 244

A marketing company receives a large amount of new clickstream data in Amazon S3 from a marketing campaign. The company needs to analyze
the clickstream data in Amazon S3 quickly. Then the company needs to determine whether to process the data further in the data pipeline.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create external tables in a Spark catalog. Configure jobs in AWS Glue to query the data.

**B.** Configure an AWS Glue crawler to crawl the data. Configure Amazon Athena to query the data.

**C.** Create external tables in a Hive metastore. Configure Spark jobs in Amazon EMR to query the data.

**D.** Configure an AWS Glue crawler to crawl the data. Configure Amazon Kinesis Data Analytics to use SQL to query the data.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A marketing company receives a large amount of new clickstream data in Amazon S3 from a marketing campaign. The company needs to analyze
the clickstream data in Amazon S3 quickly. Then the company needs to determine whether to process the data further in the data pipeline.
Which solution will meet these requirements with the LEAST operational overhead?

Answer: B) Use AWS Glue crawler + Athena for ad-hoc queries.
Glue catalogs data; Athena provides serverless SQL queries.
EMR (Option C) adds operational overhead.

</details>

---

## Question 673

[Review topic](../sections/ec2-storage.md) · Source PDF page 245

A company runs an SMB file server in its data center. The file server stores large files that the company frequently accesses for up to 7 days after
the file creation date. After 7 days, the company needs to be able to access the files with a maximum retrieval time of 24 hours.
Which solution will meet these requirements?

**A.** Use AWS DataSync to copy data that is older than 7 days from the SMB file server to AWS.

**B.** Create an Amazon S3 File Gateway to increase the company's storage space. Create an S3 Lifecycle policy to transition the data to S3
Glacier Deep Archive after 7 days.

**C.** Create an Amazon FSx File Gateway to increase the company's storage space. Create an Amazon S3 Lifecycle policy to transition the data
after 7 days.

**D.** Configure access to Amazon S3 for each user. Create an S3 Lifecycle policy to transition the data to S3 Glacier Flexible Retrieval after 7
days.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs an SMB le server in its data center. The le server stores large les that the company frequently accesses for up to 7 days after
the le creation date. After 7 days, the company needs to be able to access the les with a maximum retrieval time of 24 hours.
Which solution will meet these requirements?

Answer: B) Use S3 File Gateway + Lifecycle policy to Glacier Deep Archive.
File Gateway extends on-prem storage; Glacier Deep Archive is cost-effective for archives.
DataSync (Option A) doesn’t automate tiering.

</details>

---

## Question 674

[Review topic](../sections/elb-asg.md) · Source PDF page 245

A company runs a web application on Amazon EC2 instances in an Auto Scaling group. The application uses a database that runs on an Amazon
RDS for PostgreSQL DB instance. The application performs slowly when traffic increases. The database experiences a heavy read load during
periods of high traffic.
Which actions should a solutions architect take to resolve these performance issues? (Choose two.)

**A.** Turn on auto scaling for the DB instance.

**B.** Create a read replica for the DB instance. Configure the application to send read traffic to the read replica.

**C.** Convert the DB instance to a Multi-AZ DB instance deployment. Configure the application to send read traffic to the standby DB instance.

**D.** Create an Amazon ElastiCache cluster. Configure the application to cache query results in the ElastiCache cluster.

**E.** Configure the Auto Scaling group subnets to ensure that the EC2 instances are provisioned in the same Availability Zone as the DB
instance.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company runs a web application on Amazon EC2 instances in an Auto Scaling group. The application uses a database that runs on an Amazon
RDS for PostgreSQL DB instance. The application performs slowly when tra c increases. The database experiences a heavy read load during
periods of high tra c.
Which actions should a solutions architect take to resolve these performance issues? (Choose two.)

Answers: B) Create a read replica + D) Use ElastiCache for caching.
Read replicas offload read traffic. ElastiCache reduces DB load.
Multi-AZ (Option C) doesn’t scale reads; auto scaling (Option A) isn’t for RDS.

</details>

---

## Question 675

[Review topic](../sections/ec2-storage.md) · Source PDF page 245

A company uses Amazon EC2 instances and Amazon Elastic Block Store (Amazon EBS) volumes to run an application. The company creates one
snapshot of each EBS volume every day to meet compliance requirements. The company wants to implement an architecture that prevents the
accidental deletion of EBS volume snapshots. The solution must not change the administrative rights of the storage administrator user.
Which solution will meet these requirements with the LEAST administrative effort?

**A.** Create an IAM role that has permission to delete snapshots. Attach the role to a new EC2 instance. Use the AWS CLI from the new EC2
instance to delete snapshots.

**B.** Create an IAM policy that denies snapshot deletion. Attach the policy to the storage administrator user.

**C.** Add tags to the snapshots. Create retention rules in Recycle Bin for EBS snapshots that have the tags.

**D.** Lock the EBS snapshots to prevent deletion.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses Amazon EC2 instances and Amazon Elastic Block Store (Amazon EBS) volumes to run an application. The company creates one
snapshot of each EBS volume every day to meet compliance requirements. The company wants to implement an architecture that prevents the
accidental deletion of EBS volume snapshots. The solution must not change the administrative rights of the storage administrator user.
Which solution will meet these requirements with the LEAST administrative effort?

Answer: D) Lock the EBS snapshots.
Prevents accidental deletion without IAM changes.
Recycle Bin (Option C) requires tagging; IAM (Option B) changes permissions.

</details>

---

## Question 676

[Review topic](../sections/elb-asg.md) · Source PDF page 246

A company's application uses Network Load Balancers, Auto Scaling groups, Amazon EC2 instances, and databases that are deployed in an
Amazon VPC. The company wants to capture information about traffic to and from the network interfaces in near real time in its Amazon VPC. The
company wants to send the information to Amazon OpenSearch Service for analysis.
Which solution will meet these requirements?

**A.** Create a log group in Amazon CloudWatch Logs. Configure VPC Flow Logs to send the log data to the log group. Use Amazon Kinesis Data
Streams to stream the logs from the log group to OpenSearch Service.

**B.** Create a log group in Amazon CloudWatch Logs. Configure VPC Flow Logs to send the log data to the log group. Use Amazon Kinesis Data
Firehose to stream the logs from the log group to OpenSearch Service.

**C.** Create a trail in AWS CloudTrail. Configure VPC Flow Logs to send the log data to the trail. Use Amazon Kinesis Data Streams to stream the
logs from the trail to OpenSearch Service.

**D.** Create a trail in AWS CloudTrail. Configure VPC Flow Logs to send the log data to the trail. Use Amazon Kinesis Data Firehose to stream the
logs from the trail to OpenSearch Service.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company's application uses Network Load Balancers, Auto Scaling groups, Amazon EC2 instances, and databases that are deployed in an
Amazon VPC. The company wants to capture information about tra c to and from the network interfaces in near real time in its Amazon VPC. The
company wants to send the information to Amazon OpenSearch Service for analysis.
Which solution will meet these requirements?

Answer: B) Use VPC Flow Logs → CloudWatch → Kinesis Firehose → OpenSearch.
Flow Logs capture traffic; Firehose streams to OpenSearch.
CloudTrail (Options C/D) logs API calls, not network traffic.

</details>

---

## Question 677

[Review topic](../sections/containers.md) · Source PDF page 246

A company is developing an application that will run on a production Amazon Elastic Kubernetes Service (Amazon EKS) cluster. The EKS cluster
has managed node groups that are provisioned with On-Demand Instances.
The company needs a dedicated EKS cluster for development work. The company will use the development cluster infrequently to test the
resiliency of the application. The EKS cluster must manage all the nodes.
Which solution will meet these requirements MOST cost-effectively?

**A.** Create a managed node group that contains only Spot Instances.

**B.** Create two managed node groups. Provision one node group with On-Demand Instances. Provision the second node group with Spot
Instances.

**C.** Create an Auto Scaling group that has a launch configuration that uses Spot Instances. Configure the user data to add the nodes to the EKS
cluster.

**D.** Create a managed node group that contains only On-Demand Instances.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is developing an application that will run on a production Amazon Elastic Kubernetes Service (Amazon EKS) cluster. The EKS cluster
has managed node groups that are provisioned with On-Demand Instances.
The company needs a dedicated EKS cluster for development work. The company will use the development cluster infrequently to test the
resiliency of the application. The EKS cluster must manage all the nodes.
Which solution will meet these requirements MOST cost-effectively?

Answer: B) Use mixed On-Demand + Spot Instances in managed node groups.
Balances cost (Spot) and reliability (On-Demand) for infrequent dev workloads.
All-Spot (Option A) risks interruptions; self-managed ASG (Option C) adds overhead.

</details>

---

## Question 678

[Review topic](../sections/security.md) · Source PDF page 246

A company stores sensitive data in Amazon S3. A solutions architect needs to create an encryption solution. The company needs to fully control
the ability of users to create, rotate, and disable encryption keys with minimal effort for any data that must be encrypted.
Which solution will meet these requirements?

**A.** Use default server-side encryption with Amazon S3 managed encryption keys (SSE-S3) to store the sensitive data.

**B.** Create a customer managed key by using AWS Key Management Service (AWS KMS). Use the new key to encrypt the S3 objects by using
server-side encryption with AWS KMS keys (SSE-KMS).

**C.** Create an AWS managed key by using AWS Key Management Service (AWS KMS). Use the new key to encrypt the S3 objects by using
server-side encryption with AWS KMS keys (SSE-KMS).

**D.** Download S3 objects to an Amazon EC2 instance. Encrypt the objects by using customer managed keys. Upload the encrypted objects back
into Amazon S3.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company stores sensitive data in Amazon S3. A solutions architect needs to create an encryption solution. The company needs to fully control
the ability of users to create, rotate, and disable encryption keys with minimal effort for any data that must be encrypted.
Which solution will meet these requirements?

Answer: B) Use customer-managed KMS keys (SSE-KMS).
Grants full control over key rotation/access. SSE-S3 (Option A) lacks key management.
Client-side encryption (Option D) is complex.

</details>

---

## Question 679

[Review topic](../sections/s3.md) · Source PDF page 247

A company wants to back up its on-premises virtual machines (VMs) to AWS. The company's backup solution exports on-premises backups to an
Amazon S3 bucket as objects. The S3 backups must be retained for 30 days and must be automatically deleted after 30 days.
Which combination of steps will meet these requirements? (Choose three.)

**A.** Create an S3 bucket that has S3 Object Lock enabled.

**B.** Create an S3 bucket that has object versioning enabled.

**C.** Configure a default retention period of 30 days for the objects.

**D.** Configure an S3 Lifecycle policy to protect the objects for 30 days.

**E.** Configure an S3 Lifecycle policy to expire the objects after 30 days.

**F.** Configure the backup solution to tag the objects with a 30-day retention period

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to back up its on-premises virtual machines (VMs) to AWS. The company's backup solution exports on-premises backups to an
Amazon S3 bucket as objects. The S3 backups must be retained for 30 days and must be automatically deleted after 30 days.
Which combination of steps will meet these requirements? (Choose three.)

Answers: B) Enable versioning + C) Set 30-day retention + E) Expire objects after 30 days.
Versioning + retention policies automate compliance. Lifecycle rules expire objects.
Object Lock (Option A) prevents deletion; tagging (Option F) doesn’t enforce retention.

</details>

---

## Question 680

[Review topic](../sections/s3.md) · Source PDF page 247

A solutions architect needs to copy files from an Amazon S3 bucket to an Amazon Elastic File System (Amazon EFS) file system and another S3
bucket. The files must be copied continuously. New files are added to the original S3 bucket consistently. The copied files should be overwritten
only if the source file changes.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create an AWS DataSync location for both the destination S3 bucket and the EFS file system. Create a task for the destination S3 bucket
and the EFS file system. Set the transfer mode to transfer only data that has changed.

**B.** Create an AWS Lambda function. Mount the file system to the function. Set up an S3 event notification to invoke the function when files are
created and changed in Amazon S3. Configure the function to copy files to the file system and the destination S3 bucket.

**C.** Create an AWS DataSync location for both the destination S3 bucket and the EFS file system. Create a task for the destination S3 bucket
and the EFS file system. Set the transfer mode to transfer all data.

**D.** Launch an Amazon EC2 instance in the same VPC as the file system. Mount the file system. Create a script to routinely synchronize all
objects that changed in the origin S3 bucket to the destination S3 bucket and the mounted file system.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A solutions architect needs to copy les from an Amazon S3 bucket to an Amazon Elastic File System (Amazon EFS) le system and another S3
bucket. The les must be copied continuously. New les are added to the original S3 bucket consistently. The copied les should be overwritten
only if the source le changes.
Which solution will meet these requirements with the LEAST operational overhead?

Answer: A) Use DataSync with "changed data only" mode.
Continuously syncs only modified files to S3/EFS.
Lambda (Option B) requires custom code; full syncs (Option C) are inefficient.

</details>

---

## Question 681

[Review topic](../sections/security.md) · Source PDF page 247

A company uses Amazon EC2 instances and stores data on Amazon Elastic Block Store (Amazon EBS) volumes. The company must ensure that
all data is encrypted at rest by using AWS Key Management Service (AWS KMS). The company must be able to control rotation of the encryption
keys.
Which solution will meet these requirements with the LEAST operational overhead?

**A.** Create a customer managed key. Use the key to encrypt the EBS volumes.

**B.** Use an AWS managed key to encrypt the EBS volumes. Use the key to configure automatic key rotation.

**C.** Create an external KMS key with imported key material. Use the key to encrypt the EBS volumes.

**D.** Use an AWS owned key to encrypt the EBS volumes.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company uses Amazon EC2 instances and stores data on Amazon Elastic Block Store (Amazon EBS) volumes. The company must ensure that
all data is encrypted at rest by using AWS Key Management Service (AWS KMS). The company must be able to control rotation of the encryption
keys.
Which solution will meet these requirements with the LEAST operational overhead?

Answer: A) Use customer-managed KMS keys for EBS encryption.
Allows control over key rotation. AWS-managed keys (Option B) limit rotation flexibility.

</details>

---

## Question 682

[Review topic](../sections/iam.md) · Source PDF page 248

A company needs a solution to enforce data encryption at rest on Amazon EC2 instances. The solution must automatically identify noncompliant
resources and enforce compliance policies on findings.
Which solution will meet these requirements with the LEAST administrative overhead?

**A.** Use an IAM policy that allows users to create only encrypted Amazon Elastic Block Store (Amazon EBS) volumes. Use AWS Config and AWS
Systems Manager to automate the detection and remediation of unencrypted EBS volumes.

**B.** Use AWS Key Management Service (AWS KMS) to manage access to encrypted Amazon Elastic Block Store (Amazon EBS) volumes. Use
AWS Lambda and Amazon EventBridge to automate the detection and remediation of unencrypted EBS volumes.

**C.** Use Amazon Macie to detect unencrypted Amazon Elastic Block Store (Amazon EBS) volumes. Use AWS Systems Manager Automation
rules to automatically encrypt existing and new EBS volumes.

**D.** Use Amazon inspector to detect unencrypted Amazon Elastic Block Store (Amazon EBS) volumes. Use AWS Systems Manager Automation
rules to automatically encrypt existing and new EBS volumes.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company needs a solution to enforce data encryption at rest on Amazon EC2 instances. The solution must automatically identify noncompliant
resources and enforce compliance policies on ndings.
Which solution will meet these requirements with the LEAST administrative overhead?

Answer: A) Use IAM + AWS Config + Systems Manager for enforcement.
Config detects noncompliant volumes; Systems Manager automates remediation.
Macie (Option C) is for data classification, not encryption.

</details>

---

## Question 683

[Review topic](../sections/migration.md) · Source PDF page 248

A company is migrating its multi-tier on-premises application to AWS. The application consists of a single-node MySQL database and a multi-node
web tier. The company must minimize changes to the application during the migration. The company wants to improve application resiliency after
the migration.
Which combination of steps will meet these requirements? (Choose two.)

**A.** Migrate the web tier to Amazon EC2 instances in an Auto Scaling group behind an Application Load Balancer.

**B.** Migrate the database to Amazon EC2 instances in an Auto Scaling group behind a Network Load Balancer.

**C.** Migrate the database to an Amazon RDS Multi-AZ deployment.

**D.** Migrate the web tier to an AWS Lambda function.

**E.** Migrate the database to an Amazon DynamoDB table.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company is migrating its multi-tier on-premises application to AWS. The application consists of a single-node MySQL database and a multi-node
web tier. The company must minimize changes to the application during the migration. The company wants to improve application resiliency after
the migration.
Which combination of steps will meet these requirements? (Choose two.)

Answers: A) Migrate web tier to ALB + Auto Scaling + C) Migrate DB to RDS Multi-AZ.
Auto Scaling improves web tier resiliency; RDS Multi-AZ ensures DB HA.
Lambda (Option D) requires code changes; DynamoDB (Option E) is incompatible.

</details>

---

## Question 684

[Review topic](../sections/cloud-foundations.md) · Source PDF page 248

A company wants to migrate its web applications from on premises to AWS. The company is located close to the eu-central-1 Region. Because of
regulations, the company cannot launch some of its applications in eu-central-1. The company wants to achieve single-digit millisecond latency.
Which solution will meet these requirements?

**A.** Deploy the applications in eu-central-1. Extend the company’s VPC from eu-central-1 to an edge location in Amazon CloudFront.

**B.** Deploy the applications in AWS Local Zones by extending the company's VPC from eu-central-1 to the chosen Local Zone.

**C.** Deploy the applications in eu-central-1. Extend the company’s VPC from eu-central-1 to the regional edge caches in Amazon CloudFront.

**D.** Deploy the applications in AWS Wavelength Zones by extending the company’s VPC from eu-central-1 to the chosen Wavelength Zone.

<details>
<summary>Show answer and explanation</summary>

**Original companion notes (not independently verified):**

A company wants to migrate its web applications from on premises to AWS. The company is located close to the eu-central-1 Region. Because of
regulations, the company cannot launch some of its applications in eu-central-1. The company wants to achieve single-digit millisecond latency.
Which solution will meet these requirements?

Answer: B) Deploy in AWS Local Zones.
Local Zones provide single-digit latency near eu-central-1 while complying with regulations.
CloudFront (Option A) is for caching, not app hosting.

</details>

---

