# RDS and Aurora

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Availability versus read scale](#availability-versus-read-scale)
- [Aurora features](#aurora-features)
- [Source-backed clarification](#source-backed-clarification)

## Availability versus read scale

| Need | Typical response |
|---|---|
| Automatic database failover | Supported Multi-AZ deployment |
| Offload reporting queries | Read replica |
| Reduce repeated query work | Application cache |
| Manage many short-lived connections | RDS Proxy |

- A traditional Multi-AZ **DB instance** has a standby that does not serve reads. A supported Multi-AZ **DB cluster** can have readable standby instances. Do not apply one model's rules to the other.
- Replication mode, replica limits and failover behavior depend on engine and deployment type.
- Backups and point-in-time restore solve recovery needs; replicas can reproduce unwanted writes and do not replace backups.

## Aurora features

- Aurora offers a cluster storage architecture with reader instances. Applications should use the correct writer/reader endpoints.
- Aurora Serverless adjusts supported capacity automatically; check version-specific scaling and idle behavior.
- Global Database supports cross-Region replication and recovery. Define failover procedures and acceptable data loss explicitly.
- Cloning supports efficient test copies. Backtrack is a specific supported Aurora MySQL capability, not a universal database undo button.

## Source-backed clarification

The distinction between the two Multi-AZ deployment models is documented in [AWS RDS Multi-AZ guidance](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html).

## Related PDF practice

[Q13](../practice-exams/questions-001-050.md#question-13) · [Q16](../practice-exams/questions-001-050.md#question-16) · [Q30](../practice-exams/questions-001-050.md#question-30) · [Q39](../practice-exams/questions-001-050.md#question-39) · [Q86](../practice-exams/questions-051-100.md#question-86) · [Q93](../practice-exams/questions-051-100.md#question-93) · [Q95](../practice-exams/questions-051-100.md#question-95) · [Q108](../practice-exams/questions-101-150.md#question-108) · [Q121](../practice-exams/questions-101-150.md#question-121) · [Q136](../practice-exams/questions-101-150.md#question-136) · [Q152](../practice-exams/questions-151-200.md#question-152) · [Q157](../practice-exams/questions-151-200.md#question-157) · [Q182](../practice-exams/questions-151-200.md#question-182) · [Q191](../practice-exams/questions-151-200.md#question-191) · [Q197](../practice-exams/questions-151-200.md#question-197) · [Q235](../practice-exams/questions-201-250.md#question-235) · [Q247](../practice-exams/questions-201-250.md#question-247) · [Q268](../practice-exams/questions-251-300.md#question-268) · [Q269](../practice-exams/questions-251-300.md#question-269) · [Q281](../practice-exams/questions-251-300.md#question-281) · [Q314](../practice-exams/questions-301-350.md#question-314) · [Q330](../practice-exams/questions-301-350.md#question-330) · [Q336](../practice-exams/questions-301-350.md#question-336) · [Q337](../practice-exams/questions-301-350.md#question-337) · [Q338](../practice-exams/questions-301-350.md#question-338) · [Q339](../practice-exams/questions-301-350.md#question-339) · [Q349](../practice-exams/questions-301-350.md#question-349) · [Q350](../practice-exams/questions-301-350.md#question-350) · [Q365](../practice-exams/questions-351-400.md#question-365) · [Q372](../practice-exams/questions-351-400.md#question-372) · [Q376](../practice-exams/questions-351-400.md#question-376) · [Q386](../practice-exams/questions-351-400.md#question-386) · [Q392](../practice-exams/questions-351-400.md#question-392) · [Q394](../practice-exams/questions-351-400.md#question-394) · [Q411](../practice-exams/questions-401-450.md#question-411) · [Q416](../practice-exams/questions-401-450.md#question-416) · [Q420](../practice-exams/questions-401-450.md#question-420) · [Q427](../practice-exams/questions-401-450.md#question-427) · [Q431](../practice-exams/questions-401-450.md#question-431) · [Q435](../practice-exams/questions-401-450.md#question-435) · [Q436](../practice-exams/questions-401-450.md#question-436) · [Q440](../practice-exams/questions-401-450.md#question-440) · [Q449](../practice-exams/questions-401-450.md#question-449) · [Q464](../practice-exams/questions-451-500.md#question-464) · [Q486](../practice-exams/questions-451-500.md#question-486) · [Q511](../practice-exams/questions-501-550.md#question-511) · [Q518](../practice-exams/questions-501-550.md#question-518) · [Q526](../practice-exams/questions-501-550.md#question-526) · [Q536](../practice-exams/questions-501-550.md#question-536) · [Q540](../practice-exams/questions-501-550.md#question-540) · [Q565](../practice-exams/questions-551-600.md#question-565) · [Q574](../practice-exams/questions-551-600.md#question-574) · [Q579](../practice-exams/questions-551-600.md#question-579) · [Q590](../practice-exams/questions-551-600.md#question-590) · [Q601](../practice-exams/questions-601-650.md#question-601) · [Q607](../practice-exams/questions-601-650.md#question-607) · [Q629](../practice-exams/questions-601-650.md#question-629) · [Q633](../practice-exams/questions-601-650.md#question-633) · [Q649](../practice-exams/questions-601-650.md#question-649) · [Q669](../practice-exams/questions-651-684.md#question-669)

## Further reading

- [RonitSachdev: RDS Aurora](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/09-RDS-Aurora.md)

---

[Previous: Route 53, CloudFront and global delivery](global-delivery.md) · [Next: DynamoDB and caching](dynamodb-caching.md)
