# EC2 and compute purchasing

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Choose the instance](#choose-the-instance)
- [Purchasing choices](#purchasing-choices)
- [Design for replacement](#design-for-replacement)

## Choose the instance

- Match compute, memory, storage and network requirements to the instance family. In-memory analytics often need memory-optimized capacity; CPU-bound jobs favor compute-optimized capacity.
- User data bootstraps an instance. An AMI provides a repeatable machine image. Neither is a suitable place for long-lived AWS credentials.
- Cluster placement groups reduce latency between closely placed instances. Spread placement reduces correlated hardware failure; partition placement separates groups of instances.

## Purchasing choices

| Choice | Good fit | Constraint |
|---|---|---|
| On-Demand | Short or uncertain workloads | No usage commitment discount |
| Spot | Interruptible batch jobs and flexible workers | Design for interruption |
| Savings Plans | Predictable eligible compute spend | Commitment still applies when usage falls |
| Reserved Instances | Predictable supported instance usage | Scope and flexibility depend on offering |
| Dedicated Hosts | Host-bound licensing and placement needs | More capacity management |

## Design for replacement

- Keep durable state outside replaceable instances. Use health checks and Auto Scaling to recover failed workers.
- Size surviving capacity for the failure scenario, not just normal demand. Two AZs with one instance each cannot keep two instances running immediately after losing an AZ.
- For stateful workloads, plan draining, replication and recovery before simply adding an Auto Scaling group.

## Related PDF practice

[Q11](../practice-exams/questions-001-050.md#question-11) · [Q24](../practice-exams/questions-001-050.md#question-24) · [Q31](../practice-exams/questions-001-050.md#question-31) · [Q41](../practice-exams/questions-001-050.md#question-41) · [Q42](../practice-exams/questions-001-050.md#question-42) · [Q47](../practice-exams/questions-001-050.md#question-47) · [Q50](../practice-exams/questions-001-050.md#question-50) · [Q54](../practice-exams/questions-051-100.md#question-54) · [Q73](../practice-exams/questions-051-100.md#question-73) · [Q74](../practice-exams/questions-051-100.md#question-74) · [Q84](../practice-exams/questions-051-100.md#question-84) · [Q91](../practice-exams/questions-051-100.md#question-91) · [Q104](../practice-exams/questions-101-150.md#question-104) · [Q110](../practice-exams/questions-101-150.md#question-110) · [Q111](../practice-exams/questions-101-150.md#question-111) · [Q114](../practice-exams/questions-101-150.md#question-114) · [Q115](../practice-exams/questions-101-150.md#question-115) · [Q120](../practice-exams/questions-101-150.md#question-120) · [Q124](../practice-exams/questions-101-150.md#question-124) · [Q125](../practice-exams/questions-101-150.md#question-125) · [Q140](../practice-exams/questions-101-150.md#question-140) · [Q146](../practice-exams/questions-101-150.md#question-146) · [Q150](../practice-exams/questions-101-150.md#question-150) · [Q162](../practice-exams/questions-151-200.md#question-162) · [Q176](../practice-exams/questions-151-200.md#question-176) · [Q193](../practice-exams/questions-151-200.md#question-193) · [Q194](../practice-exams/questions-151-200.md#question-194) · [Q195](../practice-exams/questions-151-200.md#question-195) · [Q210](../practice-exams/questions-201-250.md#question-210) · [Q219](../practice-exams/questions-201-250.md#question-219) · [Q221](../practice-exams/questions-201-250.md#question-221) · [Q224](../practice-exams/questions-201-250.md#question-224) · [Q226](../practice-exams/questions-201-250.md#question-226) · [Q229](../practice-exams/questions-201-250.md#question-229) · [Q232](../practice-exams/questions-201-250.md#question-232) · [Q236](../practice-exams/questions-201-250.md#question-236) · [Q238](../practice-exams/questions-201-250.md#question-238) · [Q242](../practice-exams/questions-201-250.md#question-242) · [Q244](../practice-exams/questions-201-250.md#question-244) · [Q248](../practice-exams/questions-201-250.md#question-248) · [Q252](../practice-exams/questions-251-300.md#question-252) · [Q271](../practice-exams/questions-251-300.md#question-271) · [Q282](../practice-exams/questions-251-300.md#question-282) · [Q290](../practice-exams/questions-251-300.md#question-290) · [Q299](../practice-exams/questions-251-300.md#question-299) · [Q306](../practice-exams/questions-301-350.md#question-306) · [Q312](../practice-exams/questions-301-350.md#question-312) · [Q315](../practice-exams/questions-301-350.md#question-315) · [Q319](../practice-exams/questions-301-350.md#question-319) · [Q320](../practice-exams/questions-301-350.md#question-320) · [Q327](../practice-exams/questions-301-350.md#question-327) · [Q328](../practice-exams/questions-301-350.md#question-328) · [Q329](../practice-exams/questions-301-350.md#question-329) · [Q333](../practice-exams/questions-301-350.md#question-333) · [Q369](../practice-exams/questions-351-400.md#question-369) · [Q370](../practice-exams/questions-351-400.md#question-370) · [Q377](../practice-exams/questions-351-400.md#question-377) · [Q380](../practice-exams/questions-351-400.md#question-380) · [Q384](../practice-exams/questions-351-400.md#question-384) · [Q417](../practice-exams/questions-401-450.md#question-417) · [Q424](../practice-exams/questions-401-450.md#question-424) · [Q425](../practice-exams/questions-401-450.md#question-425) · [Q452](../practice-exams/questions-451-500.md#question-452) · [Q456](../practice-exams/questions-451-500.md#question-456) · [Q462](../practice-exams/questions-451-500.md#question-462) · [Q470](../practice-exams/questions-451-500.md#question-470) · [Q480](../practice-exams/questions-451-500.md#question-480) · [Q492](../practice-exams/questions-451-500.md#question-492) · [Q502](../practice-exams/questions-501-550.md#question-502) · [Q505](../practice-exams/questions-501-550.md#question-505) · [Q527](../practice-exams/questions-501-550.md#question-527) · [Q537](../practice-exams/questions-501-550.md#question-537) · [Q543](../practice-exams/questions-501-550.md#question-543) · [Q552](../practice-exams/questions-551-600.md#question-552) · [Q556](../practice-exams/questions-551-600.md#question-556) · [Q562](../practice-exams/questions-551-600.md#question-562) · [Q566](../practice-exams/questions-551-600.md#question-566) · [Q581](../practice-exams/questions-551-600.md#question-581) · [Q584](../practice-exams/questions-551-600.md#question-584) · [Q594](../practice-exams/questions-551-600.md#question-594) · [Q602](../practice-exams/questions-601-650.md#question-602) · [Q610](../practice-exams/questions-601-650.md#question-610) · [Q611](../practice-exams/questions-601-650.md#question-611) · [Q632](../practice-exams/questions-601-650.md#question-632) · [Q639](../practice-exams/questions-601-650.md#question-639) · [Q654](../practice-exams/questions-651-684.md#question-654) · [Q666](../practice-exams/questions-651-684.md#question-666) · [Q671](../practice-exams/questions-651-684.md#question-671)

## Further reading

- [RonitSachdev: EC2](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/03-EC2.md)

---

[Previous: IAM and advanced identity](iam.md) · [Next: EBS, EFS and FSx](ec2-storage.md)
