# Study guide

[Home](README.md) · [Practice questions](practice-exams/README.md)

## What to learn

SAA-C03 tests architecture decisions: choosing secure, resilient, performant and cost-effective solutions under specific constraints. Use the [official AWS exam guide](https://docs.aws.amazon.com/aws-certification/latest/solutions-architect-associate-03.html) for the current scope and exam requirements.

## Reading plan

| Pass | Read | Goal |
|---|---|---|
| 1 | Foundations, IAM, VPC | Understand isolation, permissions and traffic paths |
| 2 | EC2, storage, load balancing, S3 | Build scalable application infrastructure |
| 3 | RDS, DynamoDB, analytics | Match data models and access patterns |
| 4 | Serverless, containers, messaging | Decouple and automate applications |
| 5 | Security, operations, governance | Protect and operate the design |
| 6 | Global delivery, migration, recovery, AI | Handle specialized requirements |
| 7 | Final revision and mixed practice | Explain tradeoffs without memorizing letters |

## Practice routine

- Begin with the questions linked from each topic. Topic mapping is a navigation aid based on scenario vocabulary; questions can span multiple topics.
- Work through all 14 sequential sets to cover the complete PDF.
- Record the question number, your choice, the deciding requirement and the misconception to revisit.
- Reattempt missed questions after reviewing the relevant notes.
- Do not treat repeated-question accuracy as a measured probability of passing.

## Hands-on checks

- Trace an application request through DNS, load balancer, security groups and database permissions.
- Read IAM policies and explain why an explicit deny applies.
- Design a queue worker that safely retries and avoids duplicate side effects.
- Describe how a backup is restored and which credentials and keys it needs.
- Estimate transfer time and recovery time using the scenario's actual numbers.

## Answer quality

The question bank preserves the supplied answer notes, including their limitations. Forty-one suggested answers fill missing or placeholder entries. The topic notes clarify concepts, but this project does not claim a full independent verification of all 684 source answers. Check uncertain choices against AWS documentation.
