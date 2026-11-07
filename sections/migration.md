# Hybrid connectivity and migration

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Connectivity choices](#connectivity-choices)
- [Migration-service chooser](#migration-service-chooser)
- [Offline transfer questions](#offline-transfer-questions)

## Connectivity choices

- Site-to-Site VPN provides encrypted tunnels over a network path such as the internet.
- Direct Connect provides dedicated connectivity; private transport is not automatically end-to-end encryption. Add supported encryption where required.
- Transit Gateway connects multiple networks through a routing hub. Configure segmentation and redundant connections deliberately.

## Migration-service chooser

| Requirement | Candidate |
|---|---|
| Transfer files between supported stores | DataSync |
| Expose hybrid storage interfaces | Storage Gateway |
| Managed SFTP/FTPS/FTP workflows | Transfer Family with supported storage |
| Database migration and CDC | DMS, with schema conversion where required |
| Rehost servers | Application Migration Service |

- DataSync tasks run when scheduled or invoked; do not assume an always-on change listener.
- File Gateway exposes supported shares backed by S3, with local caching and asynchronous upload behavior.
- A heterogeneous database migration needs schema and application compatibility analysis, not only copying rows.
- Concurrent writes at both migration endpoints require conflict and replication-loop planning.

## Offline transfer questions

Older questions refer to Snow-family devices. Learn the bandwidth-versus-shipping tradeoff, but verify current ordering eligibility and product availability before treating a historical device choice as deployable. Estimate transfer duration from data volume and usable bandwidth, then include operational overhead.

## Related PDF practice

[Q240](../practice-exams/questions-201-250.md#question-240) · [Q301](../practice-exams/questions-301-350.md#question-301) · [Q346](../practice-exams/questions-301-350.md#question-346) · [Q445](../practice-exams/questions-401-450.md#question-445) · [Q499](../practice-exams/questions-451-500.md#question-499) · [Q659](../practice-exams/questions-651-684.md#question-659) · [Q667](../practice-exams/questions-651-684.md#question-667) · [Q683](../practice-exams/questions-651-684.md#question-683)

## Further reading

- [RonitSachdev: StorageGateway DataSync TransferFamily](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/25-StorageGateway-DataSync-TransferFamily.md)
- [RonitSachdev: Snow Family](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/27-Snow-Family.md)
- [RonitSachdev: DirectConnect VPN](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/32-DirectConnect-VPN.md)
- [RonitSachdev: Transit Gateway](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/33-Transit-Gateway.md)

---

[Previous: Encryption, secrets and threat detection](security.md) · [Next: Organizations, governance and cost](cost-governance.md)
