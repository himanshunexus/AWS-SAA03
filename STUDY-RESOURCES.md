# Additional study resources

The index below is adapted from [RonitSachdev’s AWS SAA-C03 guides](https://github.com/RonitSachdev/aws-saa-c03-guides), by **RonitSachdev**, under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Changes: links converted to absolute GitHub URLs and this attribution added. The guides are supplemental community notes, not an official answer key.

# SAA-C03 Topic Guides — Study Index

37 self-contained topic guides for the AWS Solutions Architect Associate (SAA-C03) exam. Each file follows the same pattern:

1. **The idea** — the service explained from zero with a real-world analogy
2. **Core concepts** — the exam-tested facts, numbers, tables, and explicit "THE trap" callouts
3. **Question patterns** — realistic exam scenarios with answers and the signal keywords that crack them
4. **Pocket card** — a keyword → answer table for rapid review

## Suggested reading order (grouped by exam weight)

### 🏗️ Core infrastructure (heaviest-tested — do these first)
| # | Guide | Owns the questions about |
|---|---|---|
| 06 | [VPC](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/06-VPC.md) | subnets, NAT, SG vs NACL, endpoints, peering/TGW/PrivateLink |
| 02 | [S3](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/02-S3.md) | storage classes, encryption, Object Lock |
| 03 | [EC2](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/03-EC2.md) | instance families, pricing options, placement groups |
| 04 | [EBS, EFS & Instance Store](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/04-EBS-EFS-InstanceStore.md) | volume types, shared storage, ephemeral |
| 05 | [ELB & Auto Scaling](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/05-ELB-AutoScaling.md) | ALB/NLB/GLB, scaling policies |
| 01 | [IAM](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/01-IAM.md) | roles, policies, SCPs, STS |

### 🗄️ Databases
| # | Guide | |
|---|---|---|
| 09 | [RDS & Aurora](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/09-RDS-Aurora.md) | Multi-AZ vs Read Replicas (the #1 DB question) |
| 10 | [DynamoDB](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/10-DynamoDB.md) | DAX, Global Tables, Streams, GSI/LSI |
| 11 | [ElastiCache](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/11-ElastiCache.md) | Redis vs Memcached, caching strategies |
| 12 | [Other Databases](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/12-Other-Databases.md) | the keyword zoo: Redshift, Athena, Neptune, QLDB… |

### ⚡ Serverless & application integration
| # | Guide | |
|---|---|---|
| 13 | [Lambda](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/13-Lambda.md) | 15-min limit, concurrency, VPC access |
| 14 | [ECS, EKS & Fargate](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/14-ECS-EKS-Fargate.md) | containers, the two roles |
| 15 | [Elastic Beanstalk](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/15-Elastic-Beanstalk.md) | deployment policies |
| 16 | [API Gateway](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/16-API-Gateway.md) | auth trio, 29s timeout, throttling |
| 17 | [SQS, SNS & Kinesis](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/17-SQS-SNS-Kinesis.md) | decoupling — the heaviest single question source |
| 18 | [EventBridge & Step Functions](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/18-EventBridge-StepFunctions.md) | events, workflows |

### 🌍 Networking & edge
| # | Guide | |
|---|---|---|
| 07 | [Route 53](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/07-Route53.md) | routing policies, Alias vs CNAME |
| 08 | [CloudFront & Global Accelerator](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/08-CloudFront-GlobalAccelerator.md) | CDN vs backbone |
| 32 | [Direct Connect & VPN](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/32-DirectConnect-VPN.md) | hybrid connectivity |
| 33 | [Transit Gateway](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/33-Transit-Gateway.md) | hub-and-spoke |

### 🔐 Security & identity
| # | Guide | |
|---|---|---|
| 20 | [KMS & CloudHSM](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/20-KMS-CloudHSM.md) | encryption keys |
| 21 | [Secrets Manager & Parameter Store](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/21-SecretsManager-ParameterStore.md) | rotation |
| 22 | [WAF, Shield & Security Services](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/22-WAF-Shield-SecurityServices.md) | + GuardDuty/Macie/Inspector zoo |
| 23 | [Cognito](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/23-Cognito.md) | User Pools vs Identity Pools |
| 24 | [Directory Services](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/24-Directory-Services.md) | Managed AD / Connector / Simple |

### 📊 Monitoring, management & governance
| # | Guide | |
|---|---|---|
| 19 | [CloudWatch, CloudTrail & Config](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/19-CloudWatch-CloudTrail-Config.md) | who watches what |
| 28 | [CloudFormation](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/28-CloudFormation.md) | IaC |
| 29 | [Organizations & Control Tower](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/29-Organizations-ControlTower.md) | SCPs, multi-account |
| 30 | [Service Catalog & Trusted Advisor](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/30-ServiceCatalog-TrustedAdvisor.md) | governance tools |
| 31 | [Cost Management](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/31-Cost-Management.md) | Explorer/Budgets/CUR |

### 📦 Hybrid storage & migration
| # | Guide | |
|---|---|---|
| 25 | [Storage Gateway, DataSync & Transfer Family](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/25-StorageGateway-DataSync-TransferFamily.md) | hybrid bridges |
| 26 | [FSx Family](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/26-FSx.md) | Windows/Lustre/ONTAP/OpenZFS |
| 27 | [Snow Family](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/27-Snow-Family.md) | offline transfer |

### 🎯 Final review (read last, and on exam morning)
| # | Guide | |
|---|---|---|
| 34 | [Well-Architected Framework](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/34-Well-Architected.md) | the 6 pillars as question framing |
| 35 | [Disaster Recovery](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/35-Disaster-Recovery.md) | RPO/RTO, the 4 strategies |
| 37 | [Gap-Fill Services](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/37-GapFill-Services.md) | MQ, ACM, Textract, SSM… the 1-question services |
| 36 | [Exam Traps & Key Patterns](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/36-Exam-Traps-KeyPatterns.md) | ⭐ the greatest-hits trap list + exam technique |

## How to use these guides
1. **First pass:** read in the suggested order above — the analogies do the heavy lifting.
2. **Second pass:** cover the pocket cards' right columns and quiz yourself from the keywords.
3. **After practice tests:** for every miss, come back to that topic's "Question patterns" section — the crack explanations show which signal words you skipped.
4. **Exam morning:** skim guide 36 (traps) and each guide's pocket card only. Nothing new on exam day.
