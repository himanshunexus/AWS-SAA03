# Serverless APIs and workflows

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Lambda architecture](#lambda-architecture)
- [APIs and orchestration](#apis-and-orchestration)
- [Security clarification](#security-clarification)

## Lambda architecture

- Lambda runs event-driven code without customer-managed servers. Keep functions stateless and store durable state externally.
- Execution roles authorize AWS API access. VPC attachment controls network placement; it does not automatically provide internet access.
- Use idempotent handlers because events may be retried. Configure retry limits, failure destinations or dead-letter handling for the integration used.
- Choose a different compute service when runtime or resource requirements exceed Lambda's limits.

## APIs and orchestration

| Service | Responsibility |
|---|---|
| API Gateway | Managed API entry, integration and access controls |
| Step Functions | Workflow state, branching, retries and coordination |
| EventBridge | Event routing and supported scheduling patterns |

- Cognito or custom authorizers can validate identity and authorization for supported API types. Usage plans support metering/throttling; API keys alone are not authorization.
- Step Functions can coordinate work that is too long or complex for one function execution.
- EventBridge routes events; SQS provides a queue for buffering and worker consumption. Combine them when both behaviors are needed.

## Security clarification

[AWS API Gateway guidance](https://aws.amazon.com/api-gateway/faqs/) distinguishes API keys from authorization. Enforce subscription entitlements using authenticated identity and backend/authorizer checks.

## Related PDF practice

[Q10](../practice-exams/questions-001-050.md#question-10) · [Q25](../practice-exams/questions-001-050.md#question-25) · [Q45](../practice-exams/questions-001-050.md#question-45) · [Q56](../practice-exams/questions-051-100.md#question-56) · [Q65](../practice-exams/questions-051-100.md#question-65) · [Q87](../practice-exams/questions-051-100.md#question-87) · [Q105](../practice-exams/questions-101-150.md#question-105) · [Q119](../practice-exams/questions-101-150.md#question-119) · [Q148](../practice-exams/questions-101-150.md#question-148) · [Q159](../practice-exams/questions-151-200.md#question-159) · [Q175](../practice-exams/questions-151-200.md#question-175) · [Q200](../practice-exams/questions-151-200.md#question-200) · [Q207](../practice-exams/questions-201-250.md#question-207) · [Q220](../practice-exams/questions-201-250.md#question-220) · [Q345](../practice-exams/questions-301-350.md#question-345) · [Q354](../practice-exams/questions-351-400.md#question-354) · [Q366](../practice-exams/questions-351-400.md#question-366) · [Q375](../practice-exams/questions-351-400.md#question-375) · [Q379](../practice-exams/questions-351-400.md#question-379) · [Q399](../practice-exams/questions-351-400.md#question-399) · [Q404](../practice-exams/questions-401-450.md#question-404) · [Q428](../practice-exams/questions-401-450.md#question-428) · [Q447](../practice-exams/questions-401-450.md#question-447) · [Q458](../practice-exams/questions-451-500.md#question-458) · [Q531](../practice-exams/questions-501-550.md#question-531) · [Q544](../practice-exams/questions-501-550.md#question-544) · [Q569](../practice-exams/questions-551-600.md#question-569) · [Q573](../practice-exams/questions-551-600.md#question-573) · [Q576](../practice-exams/questions-551-600.md#question-576) · [Q597](../practice-exams/questions-551-600.md#question-597) · [Q623](../practice-exams/questions-601-650.md#question-623) · [Q637](../practice-exams/questions-601-650.md#question-637)

## Further reading

- [RonitSachdev: Lambda](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/13-Lambda.md)
- [RonitSachdev: API Gateway](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/16-API-Gateway.md)
- [RonitSachdev: EventBridge StepFunctions](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/18-EventBridge-StepFunctions.md)

---

[Previous: DynamoDB and caching](dynamodb-caching.md) · [Next: Containers and application platforms](containers.md)
