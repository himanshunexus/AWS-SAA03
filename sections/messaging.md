# Messaging and streaming

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Service comparison](#service-comparison)
- [Queue processing](#queue-processing)
- [Streaming decisions](#streaming-decisions)

## Service comparison

| Requirement | Service pattern |
|---|---|
| Durable work backlog | SQS |
| Fan out one event to many consumers | SNS, often with one SQS queue per consumer |
| Ordered stream with replay | Kinesis Data Streams with appropriate retention |
| Managed delivery to supported destinations | Amazon Data Firehose |
| Preserve supported broker protocols | Amazon MQ |

## Queue processing

- A visibility timeout temporarily hides a message during processing. Delete the message after successful processing, not before.
- Standard queues can deliver duplicates. FIFO features do not remove the need to handle downstream retries and side effects safely.
- Use a dead-letter queue and redrive process for repeated failures. Monitor age of oldest messages as well as queue depth.
- Scale workers using backlog and processing time so work completes within the required window.

## Streaming decisions

- Retention must exceed consumer delay plus recovery margin. A consumer that reads less often than retained history can lose access to older records.
- Ordering and throughput depend on keys and partition/shard design. Multiple consumers may need independent throughput planning.
- Firehose delivery buffering means near-real-time delivery is not identical to immediate per-record processing.

## Related PDF practice

[Q67](../practice-exams/questions-051-100.md#question-67) · [Q98](../practice-exams/questions-051-100.md#question-98) · [Q158](../practice-exams/questions-151-200.md#question-158) · [Q167](../practice-exams/questions-151-200.md#question-167) · [Q203](../practice-exams/questions-201-250.md#question-203) · [Q211](../practice-exams/questions-201-250.md#question-211) · [Q316](../practice-exams/questions-301-350.md#question-316) · [Q344](../practice-exams/questions-301-350.md#question-344) · [Q364](../practice-exams/questions-351-400.md#question-364) · [Q555](../practice-exams/questions-551-600.md#question-555)

## Further reading

- [RonitSachdev: SQS SNS Kinesis](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/17-SQS-SNS-Kinesis.md)

---

[Previous: Containers and application platforms](containers.md) · [Next: Databases and analytics selection](analytics.md)
