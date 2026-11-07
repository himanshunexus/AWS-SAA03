# Elastic Load Balancing and Auto Scaling

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Load balancer selection](#load-balancer-selection)
- [Scaling policies](#scaling-policies)
- [Exam distinction](#exam-distinction)

## Load balancer selection

| Service | Choose it for |
|---|---|
| ALB | HTTP/HTTPS routing by host, path and application rules |
| NLB | TCP/UDP workloads and stable IP requirements |
| Gateway Load Balancer | Inserting compatible network appliances into traffic paths |

- Health checks remove unhealthy targets from service. Configure meaningful application checks, not only whether a process accepts TCP connections.
- TLS can terminate at a load balancer, with backend TLS added when required.
- Store sessions in shared storage when users must survive instance replacement. Stickiness alone does not make session state durable.

## Scaling policies

- Target tracking adjusts capacity to maintain a metric near a target. Scheduled scaling suits known recurring demand.
- CPU is not always the right metric. Queue workers often scale better using backlog per instance and expected processing time.
- Configure minimum, desired and maximum capacity; an undersized maximum can prevent recovery during demand spikes.
- Spread instances across AZs and ensure remaining capacity can handle a failure. Use lifecycle handling to finish or return queued work safely.

## Exam distinction

Load balancing distributes work; Auto Scaling changes capacity. A durable queue absorbs work while capacity catches up. They solve different parts of the same architecture.

## Related PDF practice

[Q12](../practice-exams/questions-001-050.md#question-12) · [Q14](../practice-exams/questions-001-050.md#question-14) · [Q29](../practice-exams/questions-001-050.md#question-29) · [Q35](../practice-exams/questions-001-050.md#question-35) · [Q60](../practice-exams/questions-051-100.md#question-60) · [Q69](../practice-exams/questions-051-100.md#question-69) · [Q70](../practice-exams/questions-051-100.md#question-70) · [Q130](../practice-exams/questions-101-150.md#question-130) · [Q141](../practice-exams/questions-101-150.md#question-141) · [Q169](../practice-exams/questions-151-200.md#question-169) · [Q170](../practice-exams/questions-151-200.md#question-170) · [Q174](../practice-exams/questions-151-200.md#question-174) · [Q180](../practice-exams/questions-151-200.md#question-180) · [Q209](../practice-exams/questions-201-250.md#question-209) · [Q213](../practice-exams/questions-201-250.md#question-213) · [Q217](../practice-exams/questions-201-250.md#question-217) · [Q234](../practice-exams/questions-201-250.md#question-234) · [Q245](../practice-exams/questions-201-250.md#question-245) · [Q246](../practice-exams/questions-201-250.md#question-246) · [Q257](../practice-exams/questions-251-300.md#question-257) · [Q261](../practice-exams/questions-251-300.md#question-261) · [Q266](../practice-exams/questions-251-300.md#question-266) · [Q272](../practice-exams/questions-251-300.md#question-272) · [Q275](../practice-exams/questions-251-300.md#question-275) · [Q276](../practice-exams/questions-251-300.md#question-276) · [Q297](../practice-exams/questions-251-300.md#question-297) · [Q335](../practice-exams/questions-301-350.md#question-335) · [Q340](../practice-exams/questions-301-350.md#question-340) · [Q342](../practice-exams/questions-301-350.md#question-342) · [Q357](../practice-exams/questions-351-400.md#question-357) · [Q358](../practice-exams/questions-351-400.md#question-358) · [Q378](../practice-exams/questions-351-400.md#question-378) · [Q382](../practice-exams/questions-351-400.md#question-382) · [Q388](../practice-exams/questions-351-400.md#question-388) · [Q390](../practice-exams/questions-351-400.md#question-390) · [Q405](../practice-exams/questions-401-450.md#question-405) · [Q409](../practice-exams/questions-401-450.md#question-409) · [Q434](../practice-exams/questions-401-450.md#question-434) · [Q437](../practice-exams/questions-401-450.md#question-437) · [Q441](../practice-exams/questions-401-450.md#question-441) · [Q461](../practice-exams/questions-451-500.md#question-461) · [Q473](../practice-exams/questions-451-500.md#question-473) · [Q479](../practice-exams/questions-451-500.md#question-479) · [Q509](../practice-exams/questions-501-550.md#question-509) · [Q545](../practice-exams/questions-501-550.md#question-545) · [Q549](../practice-exams/questions-501-550.md#question-549) · [Q572](../practice-exams/questions-551-600.md#question-572) · [Q575](../practice-exams/questions-551-600.md#question-575) · [Q589](../practice-exams/questions-551-600.md#question-589) · [Q595](../practice-exams/questions-551-600.md#question-595) · [Q608](../practice-exams/questions-601-650.md#question-608) · [Q614](../practice-exams/questions-601-650.md#question-614) · [Q616](../practice-exams/questions-601-650.md#question-616) · [Q642](../practice-exams/questions-601-650.md#question-642) · [Q644](../practice-exams/questions-601-650.md#question-644) · [Q655](../practice-exams/questions-651-684.md#question-655) · [Q660](../practice-exams/questions-651-684.md#question-660) · [Q674](../practice-exams/questions-651-684.md#question-674) · [Q676](../practice-exams/questions-651-684.md#question-676)

## Further reading

- [RonitSachdev: ELB AutoScaling](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/05-ELB-AutoScaling.md)

---

[Previous: EBS, EFS and FSx](ec2-storage.md) · [Next: Amazon S3](s3.md)
