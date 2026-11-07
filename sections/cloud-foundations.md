# Cloud foundations and architecture

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Global infrastructure](#global-infrastructure)
- [Shared responsibility](#shared-responsibility)
- [Architecture decisions](#architecture-decisions)
- [Common mistakes](#common-mistakes)

## Global infrastructure

- A Region is a geographic deployment area. Choose it based on compliance, latency, service availability and cost.
- Availability Zones are isolated locations within a Region. Distribute production capacity across AZs so one failure does not stop the application.
- Edge locations bring content and network entry points closer to users. They are not interchangeable with general-purpose Regions.
- Local Zones place supported resources closer to metropolitan users. Outposts brings supported AWS infrastructure into customer premises. Wavelength supports applications close to telecommunications networks.

## Shared responsibility

- AWS operates the underlying cloud infrastructure. Customers control their data, identities, application configuration and permissions.
- With EC2, customers also manage the guest operating system and software patches. Managed services move more operational tasks to AWS, but do not remove customer responsibility for access or data.
- High availability keeps a service running through component failures; disaster recovery restores operation after a larger disruption.

## Architecture decisions

| Requirement | Design response |
|---|---|
| Survive an AZ failure | Multiple AZs with sufficient remaining capacity |
| Survive a regional outage | A tested cross-Region recovery design |
| Reduce operational work | Prefer a managed service when it meets every requirement |
| Handle variable demand | Elastic capacity, queues and stateless workers |

## Common mistakes

- A backup is not a running standby. A second instance in the same AZ does not protect against an AZ outage.
- Read the final constraint: cost, recovery time and operational overhead can favor different valid designs.

## Related PDF practice

[Q5](../practice-exams/questions-001-050.md#question-5) · [Q20](../practice-exams/questions-001-050.md#question-20) · [Q22](../practice-exams/questions-001-050.md#question-22) · [Q68](../practice-exams/questions-051-100.md#question-68) · [Q72](../practice-exams/questions-051-100.md#question-72) · [Q138](../practice-exams/questions-101-150.md#question-138) · [Q151](../practice-exams/questions-151-200.md#question-151) · [Q178](../practice-exams/questions-151-200.md#question-178) · [Q186](../practice-exams/questions-151-200.md#question-186) · [Q273](../practice-exams/questions-251-300.md#question-273) · [Q298](../practice-exams/questions-251-300.md#question-298) · [Q353](../practice-exams/questions-351-400.md#question-353) · [Q374](../practice-exams/questions-351-400.md#question-374) · [Q389](../practice-exams/questions-351-400.md#question-389) · [Q408](../practice-exams/questions-401-450.md#question-408) · [Q444](../practice-exams/questions-401-450.md#question-444) · [Q465](../practice-exams/questions-451-500.md#question-465) · [Q466](../practice-exams/questions-451-500.md#question-466) · [Q475](../practice-exams/questions-451-500.md#question-475) · [Q504](../practice-exams/questions-501-550.md#question-504) · [Q508](../practice-exams/questions-501-550.md#question-508) · [Q510](../practice-exams/questions-501-550.md#question-510) · [Q553](../practice-exams/questions-551-600.md#question-553) · [Q593](../practice-exams/questions-551-600.md#question-593) · [Q621](../practice-exams/questions-601-650.md#question-621) · [Q635](../practice-exams/questions-601-650.md#question-635) · [Q684](../practice-exams/questions-651-684.md#question-684)

## Further reading

- [RonitSachdev: Well Architected](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/34-Well-Architected.md)
- [RonitSachdev: Disaster Recovery](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/35-Disaster-Recovery.md)

---

[Next: IAM and advanced identity](iam.md)
