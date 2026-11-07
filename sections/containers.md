# Containers and application platforms

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Choose the control plane](#choose-the-control-plane)
- [Roles and resilience](#roles-and-resilience)
- [Migration decisions](#migration-decisions)

## Choose the control plane

- ECS is AWS's container orchestration service. EKS provides managed Kubernetes control-plane capabilities.
- Fargate runs supported containers without customer-managed worker hosts. EC2 capacity provides more host-level control but adds maintenance.
- ECR stores container images; it does not run them.
- Elastic Beanstalk manages supported application environments and deployments on AWS resources.

## Roles and resilience

- An ECS task role grants permissions to application code. The task execution role supports tasks such as image retrieval and configured logging.
- Spread production tasks across AZs, use health checks, and scale both application tasks and underlying capacity where relevant.
- Persist state outside ephemeral containers. Select storage based on protocol, performance and availability requirements.
- Blue/green deployment uses separate environments and traffic switching. Rolling deployment replaces capacity gradually; each has different rollback and capacity implications.

## Migration decisions

Preserving Kubernetes deployment methods points toward EKS. A managed database can reduce operations, but compatibility still needs testing. Moving MongoDB workloads to DocumentDB is not automatically a zero-code-change migration.

## Related PDF practice

[Q181](../practice-exams/questions-151-200.md#question-181) · [Q187](../practice-exams/questions-151-200.md#question-187) · [Q263](../practice-exams/questions-251-300.md#question-263) · [Q303](../practice-exams/questions-301-350.md#question-303) · [Q371](../practice-exams/questions-351-400.md#question-371) · [Q451](../practice-exams/questions-451-500.md#question-451) · [Q483](../practice-exams/questions-451-500.md#question-483) · [Q514](../practice-exams/questions-501-550.md#question-514) · [Q522](../practice-exams/questions-501-550.md#question-522) · [Q535](../practice-exams/questions-501-550.md#question-535) · [Q563](../practice-exams/questions-551-600.md#question-563) · [Q591](../practice-exams/questions-551-600.md#question-591) · [Q599](../practice-exams/questions-551-600.md#question-599) · [Q613](../practice-exams/questions-601-650.md#question-613) · [Q615](../practice-exams/questions-601-650.md#question-615) · [Q664](../practice-exams/questions-651-684.md#question-664) · [Q677](../practice-exams/questions-651-684.md#question-677)

## Further reading

- [RonitSachdev: ECS EKS Fargate](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/14-ECS-EKS-Fargate.md)
- [RonitSachdev: Elastic Beanstalk](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/15-Elastic-Beanstalk.md)

---

[Previous: Serverless APIs and workflows](serverless.md) · [Next: Messaging and streaming](messaging.md)
