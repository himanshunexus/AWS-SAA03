# IAM and advanced identity

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Identities and credentials](#identities-and-credentials)
- [Read an IAM policy](#read-an-iam-policy)
- [Exam traps](#exam-traps)

## Identities and credentials

- IAM users are identities with potentially long-lived credentials. Groups organize users and permissions; they do not contain roles.
- Roles provide temporary credentials through STS. Use EC2 instance profiles, Lambda execution roles and ECS task roles instead of hardcoded access keys.
- A role's trust policy identifies who may assume it. Its permissions policies describe the actions the assumed role may perform.
- IAM Identity Center provides workforce access across accounts. Cognito supports application user sign-in; identity pools can exchange identities for temporary AWS credentials.
- Managed Microsoft AD supplies a managed directory. AD Connector forwards authentication to an existing directory; it is not a replacement directory.

## Read an IAM policy

| Element | Meaning |
|---|---|
| Effect | Allow or Deny |
| Action | Service API operations |
| Resource | Resource ARNs to which the action applies |
| Condition | Extra restrictions such as source IP or MFA |
| Principal | Who receives access in a resource-based or trust policy |

- Explicit denies override applicable allows. SCPs and permissions boundaries restrict permissions; they do not grant access by themselves.
- Cross-account role access requires the target role's trust and permission for the caller to assume it.
- Protect root credentials with MFA and use federated identities for daily work.

## Exam traps

- A role with the right permissions can still have the wrong trust policy.
- `s3:ListBucket` uses a bucket ARN; `s3:GetObject` and `s3:DeleteObject` use object ARNs ending in a key or `/*`.
- An API key is not proof of user authorization. Premium access needs an entitlement check tied to authenticated identity.

## Related PDF practice

[Q28](../practice-exams/questions-001-050.md#question-28) · [Q96](../practice-exams/questions-051-100.md#question-96) · [Q97](../practice-exams/questions-051-100.md#question-97) · [Q165](../practice-exams/questions-151-200.md#question-165) · [Q168](../practice-exams/questions-151-200.md#question-168) · [Q222](../practice-exams/questions-201-250.md#question-222) · [Q239](../practice-exams/questions-201-250.md#question-239) · [Q253](../practice-exams/questions-251-300.md#question-253) · [Q259](../practice-exams/questions-251-300.md#question-259) · [Q334](../practice-exams/questions-301-350.md#question-334) · [Q368](../practice-exams/questions-351-400.md#question-368) · [Q395](../practice-exams/questions-351-400.md#question-395) · [Q403](../practice-exams/questions-401-450.md#question-403) · [Q418](../practice-exams/questions-401-450.md#question-418) · [Q419](../practice-exams/questions-401-450.md#question-419) · [Q421](../practice-exams/questions-401-450.md#question-421) · [Q423](../practice-exams/questions-401-450.md#question-423) · [Q429](../practice-exams/questions-401-450.md#question-429) · [Q457](../practice-exams/questions-451-500.md#question-457) · [Q476](../practice-exams/questions-451-500.md#question-476) · [Q494](../practice-exams/questions-451-500.md#question-494) · [Q524](../practice-exams/questions-501-550.md#question-524) · [Q550](../practice-exams/questions-501-550.md#question-550) · [Q624](../practice-exams/questions-601-650.md#question-624) · [Q640](../practice-exams/questions-601-650.md#question-640) · [Q668](../practice-exams/questions-651-684.md#question-668) · [Q682](../practice-exams/questions-651-684.md#question-682)

## Further reading

- [RonitSachdev: IAM](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/01-IAM.md)
- [RonitSachdev: Cognito](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/23-Cognito.md)
- [RonitSachdev: Directory Services](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/24-Directory-Services.md)

---

[Previous: Cloud foundations and architecture](cloud-foundations.md) · [Next: EC2 and compute purchasing](ec2.md)
