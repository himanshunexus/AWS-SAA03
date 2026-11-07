# AWS Solutions Architect Associate Study Notes (SAA-C03)

Text-only revision notes, service comparisons, architecture decisions and practice questions for SAA-C03. Start with a topic, learn the decision rules, then test yourself with its linked questions.

- [Study guide and reading plan](study-guide.md)
- [Practice exams: all 684 questions](practice-exams/README.md)
- [Sources, attribution and answer notes](SOURCES.md)

## Table of contents

- [Cloud foundations and architecture](sections/cloud-foundations.md)
  - Global infrastructure, Shared responsibility, Architecture decisions.
- [IAM and advanced identity](sections/iam.md)
  - Identities and credentials, Read an IAM policy, Exam traps.
- [EC2 and compute purchasing](sections/ec2.md)
  - Choose the instance, Purchasing choices, Design for replacement.
- [EBS, EFS and FSx](sections/ec2-storage.md)
  - Storage model, Practical rules, Scenario.
- [Elastic Load Balancing and Auto Scaling](sections/elb-asg.md)
  - Load balancer selection, Scaling policies, Exam distinction.
- [Amazon S3](sections/s3.md)
  - Objects and access, Storage-class decisions, Protect and retain data.
- [VPC and network controls](sections/vpc.md)
  - Routing, Security groups versus NACLs, Private service access.
- [Route 53, CloudFront and global delivery](sections/global-delivery.md)
  - DNS routing, Edge-service comparison, Protect delivery.
- [RDS and Aurora](sections/rds-aurora.md)
  - Availability versus read scale, Aurora features, Source-backed clarification.
- [DynamoDB and caching](sections/dynamodb-caching.md)
  - DynamoDB design, Cache selection.
- [Serverless APIs and workflows](sections/serverless.md)
  - Lambda architecture, APIs and orchestration, Security clarification.
- [Containers and application platforms](sections/containers.md)
  - Choose the control plane, Roles and resilience, Migration decisions.
- [Messaging and streaming](sections/messaging.md)
  - Service comparison, Queue processing, Streaming decisions.
- [Databases and analytics selection](sections/analytics.md)
  - Select by workload, Data lake design, Scenario.
- [Monitoring and infrastructure management](sections/operations.md)
  - Observe the right thing, Repeatable operations.
- [Encryption, secrets and threat detection](sections/security.md)
  - Encryption and keys, Security-service chooser, Common mistakes.
- [Hybrid connectivity and migration](sections/migration.md)
  - Connectivity choices, Migration-service chooser, Offline transfer questions.
- [Organizations, governance and cost](sections/cost-governance.md)
  - Account structure, Cost workflow, Cost decisions.
- [Backup and disaster recovery](sections/disaster-recovery.md)
  - Recovery objectives, Build a complete plan, Exam trap.
- [AI services and document processing](sections/ai-services.md)
  - Choose the managed capability, Document pipeline, Avoid mismatches.
- [Final revision and decision patterns](sections/exam-revision.md)
  - How to solve a scenario, Frequent distinctions, Review method.

## How to use these notes

1. Read the study guide and work through the topic sections.
2. Use comparison tables to understand when to choose each service.
3. Attempt the related PDF questions without opening the answers.
4. Review mistakes by requirement, not only by answer letter.
5. Finish with [decision patterns](sections/exam-revision.md) and mixed practice.

## About this collection

The navigation follows the topic-notes and separate-practice format of [kananinirav’s Cloud Practitioner notes](https://github.com/kananinirav/AWS-Certified-Cloud-Practitioner-Notes). The content targets **SAA-C03**, not Cloud Practitioner. Notes synthesize the supplied PDF scenarios and service coverage from [RonitSachdev’s SAA-C03 guides](https://github.com/RonitSachdev/aws-saa-c03-guides), with attribution in Sources. No image assets are used.

Community study material; not affiliated with or endorsed by AWS. Source answers are not an official answer key.
