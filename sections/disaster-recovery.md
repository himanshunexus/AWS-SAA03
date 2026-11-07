# Backup and disaster recovery

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Recovery objectives](#recovery-objectives)
- [Build a complete plan](#build-a-complete-plan)
- [Exam trap](#exam-trap)

## Recovery objectives

- RPO is the acceptable amount of data loss measured in time. RTO is the acceptable time to restore service.
- Replication frequency affects RPO. Provisioning, restoration, failover, DNS and application validation all affect RTO.

| Strategy | Recovery preparation | Typical tradeoff |
|---|---|---|
| Backup and restore | Backups plus restoration procedures | Lower standing cost, longer recovery |
| Pilot light | Essential core replicated/running | Additional capacity and services must start |
| Warm standby | Reduced-capacity working system | Faster recovery with ongoing cost |
| Multi-site active/active | Multiple serving environments | More complexity and replication coordination |

## Build a complete plan

- Back up configuration, secrets and dependencies as well as application data.
- Consider cross-account and cross-Region copies and protected retention where appropriate.
- Test restore permissions and encryption keys. An unreadable encrypted backup is not useful recovery capacity.
- Define failback and reconciliation after recovery. Do not assume moving traffic back is risk-free.
- Elastic Disaster Recovery replicates server data for recovery; AWS Backup coordinates supported backups. They solve related but different problems.

## Exam trap

A second database replica does not make the whole application region-resilient if the application tier, credentials or routing cannot recover with it.

## Related PDF practice

[Q71](../practice-exams/questions-051-100.md#question-71) · [Q133](../practice-exams/questions-101-150.md#question-133) · [Q160](../practice-exams/questions-151-200.md#question-160) · [Q215](../practice-exams/questions-201-250.md#question-215) · [Q274](../practice-exams/questions-251-300.md#question-274) · [Q293](../practice-exams/questions-251-300.md#question-293) · [Q304](../practice-exams/questions-301-350.md#question-304) · [Q324](../practice-exams/questions-301-350.md#question-324) · [Q343](../practice-exams/questions-301-350.md#question-343) · [Q391](../practice-exams/questions-351-400.md#question-391) · [Q453](../practice-exams/questions-451-500.md#question-453) · [Q539](../practice-exams/questions-501-550.md#question-539) · [Q546](../practice-exams/questions-501-550.md#question-546) · [Q585](../practice-exams/questions-551-600.md#question-585) · [Q588](../practice-exams/questions-551-600.md#question-588) · [Q647](../practice-exams/questions-601-650.md#question-647)

## Further reading

- [RonitSachdev: Disaster Recovery](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/35-Disaster-Recovery.md)

---

[Previous: Organizations, governance and cost](cost-governance.md) · [Next: AI services and document processing](ai-services.md)
