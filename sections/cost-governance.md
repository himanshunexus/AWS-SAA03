# Organizations, governance and cost

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Account structure](#account-structure)
- [Cost workflow](#cost-workflow)
- [Cost decisions](#cost-decisions)

## Account structure

- Separate workloads and environments into accounts to improve isolation and cost ownership. Organizations manages account grouping and consolidated billing.
- SCPs set permission boundaries for affected accounts; they do not grant permissions. The organization's management account is not restricted by its SCPs.
- Control Tower helps establish and govern a multi-account landing zone. AWS RAM shares supported resources; it is not a general mechanism for sharing discounts.

## Cost workflow

1. Tag resources consistently and activate relevant cost allocation tags.
2. Use Cost Explorer and detailed billing data to identify the largest drivers.
3. Remove unused resources and right-size workloads.
4. Apply commitments to an appropriate predictable baseline.
5. Track changes with budgets and anomaly detection.

## Cost decisions

- Compute Savings Plans can cover eligible EC2, Fargate and Lambda usage; EC2 Instance Savings Plans have narrower flexibility.
- Discount sharing is managed through consolidated billing preferences. A commitment does not disappear when instances are deleted.
- Include NAT processing, cross-AZ/Region transfer, logging, storage retrieval and minimum duration charges when comparing designs.
- The cheapest instance price does not always produce the cheapest architecture; operational effort and data movement can dominate.

## Related PDF practice

[Q49](../practice-exams/questions-001-050.md#question-49) · [Q63](../practice-exams/questions-051-100.md#question-63) · [Q118](../practice-exams/questions-101-150.md#question-118) · [Q132](../practice-exams/questions-101-150.md#question-132) · [Q137](../practice-exams/questions-101-150.md#question-137) · [Q147](../practice-exams/questions-101-150.md#question-147) · [Q300](../practice-exams/questions-251-300.md#question-300) · [Q347](../practice-exams/questions-301-350.md#question-347) · [Q398](../practice-exams/questions-351-400.md#question-398) · [Q433](../practice-exams/questions-401-450.md#question-433) · [Q443](../practice-exams/questions-401-450.md#question-443) · [Q455](../practice-exams/questions-451-500.md#question-455) · [Q459](../practice-exams/questions-451-500.md#question-459) · [Q467](../practice-exams/questions-451-500.md#question-467) · [Q488](../practice-exams/questions-451-500.md#question-488) · [Q491](../practice-exams/questions-451-500.md#question-491) · [Q525](../practice-exams/questions-501-550.md#question-525) · [Q541](../practice-exams/questions-501-550.md#question-541) · [Q559](../practice-exams/questions-551-600.md#question-559) · [Q580](../practice-exams/questions-551-600.md#question-580) · [Q583](../practice-exams/questions-551-600.md#question-583) · [Q586](../practice-exams/questions-551-600.md#question-586) · [Q628](../practice-exams/questions-601-650.md#question-628) · [Q641](../practice-exams/questions-601-650.md#question-641) · [Q643](../practice-exams/questions-601-650.md#question-643) · [Q653](../practice-exams/questions-651-684.md#question-653) · [Q656](../practice-exams/questions-651-684.md#question-656)

## Further reading

- [RonitSachdev: Organizations ControlTower](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/29-Organizations-ControlTower.md)
- [RonitSachdev: ServiceCatalog TrustedAdvisor](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/30-ServiceCatalog-TrustedAdvisor.md)
- [RonitSachdev: Cost Management](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/31-Cost-Management.md)

---

[Previous: Hybrid connectivity and migration](migration.md) · [Next: Backup and disaster recovery](disaster-recovery.md)
