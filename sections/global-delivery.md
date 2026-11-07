# Route 53, CloudFront and global delivery

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [DNS routing](#dns-routing)
- [Edge-service comparison](#edge-service-comparison)
- [Protect delivery](#protect-delivery)

## DNS routing

- Route 53 resolves names and supports routing strategies such as weighted, latency, failover and multivalue answers.
- Weighted routing supports controlled traffic distribution. Latency routing considers latency to configured endpoints. Failover routing supports primary/secondary recovery.
- Alias records can target supported AWS resources at the zone apex. A conventional CNAME cannot coexist there with required apex records.
- DNS caching means a routing change is not instantaneous for every client.

## Edge-service comparison

| Requirement | Choice |
|---|---|
| Cache HTTP content near users | CloudFront |
| Global TCP/UDP entry with static anycast addresses | Global Accelerator |
| Name resolution and DNS failover | Route 53 |

## Protect delivery

- Use CloudFront origin access control to keep a supported S3 origin private while serving through the distribution.
- Signed URLs or cookies limit access to private content; configure cache keys so authorization and response variation are handled correctly.
- CloudFront caching does not replace database replication. Global Accelerator does not cache objects.
- WAF can filter application requests at supported entry points. Restrict direct origin access when the design requires all requests to pass through edge controls.

## Related PDF practice

[Q38](../practice-exams/questions-001-050.md#question-38) · [Q142](../practice-exams/questions-101-150.md#question-142) · [Q172](../practice-exams/questions-151-200.md#question-172) · [Q205](../practice-exams/questions-201-250.md#question-205) · [Q264](../practice-exams/questions-251-300.md#question-264) · [Q280](../practice-exams/questions-251-300.md#question-280) · [Q367](../practice-exams/questions-351-400.md#question-367) · [Q396](../practice-exams/questions-351-400.md#question-396) · [Q530](../practice-exams/questions-501-550.md#question-530) · [Q532](../practice-exams/questions-501-550.md#question-532) · [Q538](../practice-exams/questions-501-550.md#question-538) · [Q577](../practice-exams/questions-551-600.md#question-577) · [Q582](../practice-exams/questions-551-600.md#question-582)

## Further reading

- [RonitSachdev: Route53](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/07-Route53.md)
- [RonitSachdev: CloudFront GlobalAccelerator](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/08-CloudFront-GlobalAccelerator.md)

---

[Previous: VPC and network controls](vpc.md) · [Next: RDS and Aurora](rds-aurora.md)
