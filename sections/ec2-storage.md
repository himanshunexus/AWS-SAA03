# EBS, EFS and FSx

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Storage model](#storage-model)
- [Practical rules](#practical-rules)
- [Scenario](#scenario)

## Storage model

| Service | Interface | Typical use |
|---|---|---|
| EBS | Block volume in an AZ | EC2 disks and database volumes |
| Instance store | Host-local block storage | Scratch data and rebuildable caches |
| EFS | Managed NFS file system | Shared Linux application files |
| FSx for Windows File Server | SMB | Windows shares and AD integration |
| FSx for Lustre | Parallel file system | HPC and high-throughput analytics |
| FSx for NetApp ONTAP | Multiprotocol file/block features | NFS and SMB access to managed storage |

## Practical rules

- EBS is not a general shared filesystem across AZs. Multi-Attach has specific volume, instance and application constraints and still requires safe write coordination.
- EFS lets multiple application instances access the same files. Choose Regional versus One Zone deployment according to resilience requirements.
- Use a Multi-AZ FSx deployment when the relevant engine supports it and the workload needs AZ failover.
- An instance-store disk is unsuitable as the only copy of important data. Stop, termination or host loss can remove it.
- Snapshot and restore workflows support backup and encrypted-copy migrations. Test restores instead of assuming that a snapshot alone proves recovery.

## Scenario

If users see different uploaded files depending on the web server handling their request, move shared content from separate local/EBS disks to suitable shared storage. Sticky sessions hide the symptom but do not synchronize the data.

## Related PDF practice

[Q6](../practice-exams/questions-001-050.md#question-6) · [Q9](../practice-exams/questions-001-050.md#question-9) · [Q48](../practice-exams/questions-001-050.md#question-48) · [Q52](../practice-exams/questions-051-100.md#question-52) · [Q80](../practice-exams/questions-051-100.md#question-80) · [Q99](../practice-exams/questions-051-100.md#question-99) · [Q102](../practice-exams/questions-101-150.md#question-102) · [Q249](../practice-exams/questions-201-250.md#question-249) · [Q260](../practice-exams/questions-251-300.md#question-260) · [Q277](../practice-exams/questions-251-300.md#question-277) · [Q283](../practice-exams/questions-251-300.md#question-283) · [Q305](../practice-exams/questions-301-350.md#question-305) · [Q407](../practice-exams/questions-401-450.md#question-407) · [Q410](../practice-exams/questions-401-450.md#question-410) · [Q487](../practice-exams/questions-451-500.md#question-487) · [Q496](../practice-exams/questions-451-500.md#question-496) · [Q500](../practice-exams/questions-451-500.md#question-500) · [Q598](../practice-exams/questions-551-600.md#question-598) · [Q617](../practice-exams/questions-601-650.md#question-617) · [Q618](../practice-exams/questions-601-650.md#question-618) · [Q646](../practice-exams/questions-601-650.md#question-646) · [Q658](../practice-exams/questions-651-684.md#question-658) · [Q662](../practice-exams/questions-651-684.md#question-662) · [Q673](../practice-exams/questions-651-684.md#question-673) · [Q675](../practice-exams/questions-651-684.md#question-675)

## Further reading

- [RonitSachdev: EBS EFS InstanceStore](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/04-EBS-EFS-InstanceStore.md)
- [RonitSachdev: FSx](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/26-FSx.md)

---

[Previous: EC2 and compute purchasing](ec2.md) · [Next: Elastic Load Balancing and Auto Scaling](elb-asg.md)
