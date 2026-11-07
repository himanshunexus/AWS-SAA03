# Encryption, secrets and threat detection

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Encryption and keys](#encryption-and-keys)
- [Security-service chooser](#security-service-chooser)
- [Common mistakes](#common-mistakes)

## Encryption and keys

- KMS integrates managed key operations with AWS services. Customer-managed keys give control over policies and lifecycle; check rotation support for the key type.
- Key authorization depends on key policies, grants and applicable IAM permissions. An IAM allow by itself does not bypass key-policy restrictions.
- Envelope encryption uses a data key for the payload and protects that key with a wrapping key. It avoids sending an entire large file to KMS for direct encryption.
- CloudHSM provides dedicated HSM capabilities for requirements needing that control model. Verify current certifications rather than memorizing an outdated KMS-versus-HSM level comparison.
- Secrets Manager supports managed secret workflows including configured rotation. Parameter Store stores configuration and secure parameters; it is not interchangeable with automatic secret rotation.

## Security-service chooser

| Need | Service |
|---|---|
| Filter supported HTTP requests | WAF |
| DDoS protection | Shield capabilities appropriate to the design |
| Detect suspicious account/workload activity | GuardDuty |
| Find supported software vulnerabilities | Inspector |
| Discover sensitive data in S3 | Macie |
| Manage TLS certificates | ACM |

## Common mistakes

Encryption at rest does not secure transport. A private network path is not necessarily encrypted. Threat detection does not automatically fix an application vulnerability.

## Related PDF practice

[Q62](../practice-exams/questions-051-100.md#question-62) · [Q82](../practice-exams/questions-051-100.md#question-82) · [Q123](../practice-exams/questions-101-150.md#question-123) · [Q571](../practice-exams/questions-551-600.md#question-571) · [Q678](../practice-exams/questions-651-684.md#question-678) · [Q681](../practice-exams/questions-651-684.md#question-681)

## Further reading

- [RonitSachdev: KMS CloudHSM](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/20-KMS-CloudHSM.md)
- [RonitSachdev: SecretsManager ParameterStore](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/21-SecretsManager-ParameterStore.md)
- [RonitSachdev: WAF Shield SecurityServices](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/22-WAF-Shield-SecurityServices.md)

---

[Previous: Monitoring and infrastructure management](operations.md) · [Next: Hybrid connectivity and migration](migration.md)
