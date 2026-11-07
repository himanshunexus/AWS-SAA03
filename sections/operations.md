# Monitoring and infrastructure management

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Observe the right thing](#observe-the-right-thing)
- [Repeatable operations](#repeatable-operations)

## Observe the right thing

| Question | Tool |
|---|---|
| Is performance deteriorating? | CloudWatch metrics, logs and alarms |
| Who called an AWS API? | CloudTrail |
| Does resource configuration comply? | AWS Config rules |
| How does a request cross services? | Distributed tracing such as X-Ray |

- EC2 does not publish every operating-system metric by default. Use an agent or custom telemetry for memory and application-specific measurements.
- A metric stream exports metrics, not all individual lifecycle events. Use event routing when the required artifact is an event record.
- Config detects configuration state; remediation needs an explicitly configured action such as Systems Manager Automation.

## Repeatable operations

- CloudFormation manages infrastructure from templates. Change sets preview updates; drift detection helps identify changes outside the template.
- Systems Manager supports managed-instance operations such as Run Command, patching and Session Manager access.
- Session Manager reduces the need for inbound SSH/RDP. Configure IAM, network reachability and logging; do not assume session content is always recorded automatically.
- Service Catalog distributes approved products. Trusted Advisor provides recommendations; it is not a replacement for application-specific testing.

## Related PDF practice

[Q27](../practice-exams/questions-001-050.md#question-27) · [Q179](../practice-exams/questions-151-200.md#question-179) · [Q228](../practice-exams/questions-201-250.md#question-228) · [Q308](../practice-exams/questions-301-350.md#question-308) · [Q387](../practice-exams/questions-351-400.md#question-387) · [Q503](../practice-exams/questions-501-550.md#question-503) · [Q619](../practice-exams/questions-601-650.md#question-619)

## Further reading

- [RonitSachdev: CloudWatch CloudTrail Config](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/19-CloudWatch-CloudTrail-Config.md)
- [RonitSachdev: CloudFormation](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/28-CloudFormation.md)
- [RonitSachdev: ServiceCatalog TrustedAdvisor](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/30-ServiceCatalog-TrustedAdvisor.md)

---

[Previous: Databases and analytics selection](analytics.md) · [Next: Encryption, secrets and threat detection](security.md)
