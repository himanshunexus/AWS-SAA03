# DynamoDB and caching

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [DynamoDB design](#dynamodb-design)
- [Cache selection](#cache-selection)

## DynamoDB design

- Choose partition keys that distribute work. Adding capacity does not automatically fix a hot partition key.
- On-demand capacity suits variable usage; provisioned capacity with scaling suits workloads with a manageable capacity plan.
- Global tables replicate supported DynamoDB data across Regions. Understand conflict and consistency behavior for the selected configuration.
- TTL removes expired items asynchronously. Filter logically expired records when the application must stop displaying them immediately.
- Secondary indexes support other access patterns; select projections and keys based on queries instead of scanning the entire table.

## Cache selection

| Requirement | Candidate |
|---|---|
| Accelerate supported DynamoDB read patterns | DAX |
| Shared application cache or sessions | ElastiCache with suitable engine/configuration |
| Durable application session records | DynamoDB or another durable datastore |

- Cache-aside reads the cache first and populates it after a miss. Set TTLs and invalidation rules to avoid stale or unbounded data.
- Replication improves cache availability, but asynchronous replication does not guarantee that the latest write survives every failure.
- A cache does not solve a write-throughput bottleneck simply by existing. Identify the actual read/write pattern first.

## Related PDF practice

[Q78](../practice-exams/questions-051-100.md#question-78) · [Q79](../practice-exams/questions-051-100.md#question-79) · [Q177](../practice-exams/questions-151-200.md#question-177) · [Q196](../practice-exams/questions-151-200.md#question-196) · [Q223](../practice-exams/questions-201-250.md#question-223) · [Q262](../practice-exams/questions-251-300.md#question-262) · [Q279](../practice-exams/questions-251-300.md#question-279) · [Q348](../practice-exams/questions-301-350.md#question-348) · [Q472](../practice-exams/questions-451-500.md#question-472) · [Q481](../practice-exams/questions-451-500.md#question-481) · [Q520](../practice-exams/questions-501-550.md#question-520) · [Q521](../practice-exams/questions-501-550.md#question-521) · [Q523](../practice-exams/questions-501-550.md#question-523) · [Q578](../practice-exams/questions-551-600.md#question-578) · [Q670](../practice-exams/questions-651-684.md#question-670)

## Further reading

- [RonitSachdev: DynamoDB](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/10-DynamoDB.md)
- [RonitSachdev: ElastiCache](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/11-ElastiCache.md)

---

[Previous: RDS and Aurora](rds-aurora.md) · [Next: Serverless APIs and workflows](serverless.md)
