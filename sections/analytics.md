# Databases and analytics selection

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Select by workload](#select-by-workload)
- [Data lake design](#data-lake-design)
- [Scenario](#scenario)

## Select by workload

| Workload | Candidate |
|---|---|
| SQL over files in S3 | Athena |
| Analytical warehouse | Redshift |
| Managed ETL and catalog | Glue |
| Managed big-data frameworks | EMR |
| Business dashboards | QuickSight |
| Graph relationships | Neptune |
| Compatible document model | DocumentDB after compatibility testing |

## Data lake design

- Keep raw and curated data distinguishable. Catalog schemas and use partitioned, columnar formats when they fit query patterns.
- Athena charges and performance depend partly on data scanned. Partition pruning and suitable formats can reduce work substantially.
- Lake Formation governs supported data lake permissions, including fine-grained access. IAM and S3 permissions alone are not a substitute for column-level governance.
- A BI dashboard is the presentation layer; it does not replace ingestion, cleaning, security or retention.

## Scenario

For occasional SQL queries over JSON logs already in S3, Athena often requires less operational work than loading and maintaining a new database cluster. For a sustained warehouse workload, evaluate Redshift instead of assuming every SQL use case is the same.

## Related PDF practice

[Q107](../practice-exams/questions-101-150.md#question-107) · [Q145](../practice-exams/questions-101-150.md#question-145) · [Q341](../practice-exams/questions-301-350.md#question-341) · [Q442](../practice-exams/questions-401-450.md#question-442) · [Q515](../practice-exams/questions-501-550.md#question-515) · [Q528](../practice-exams/questions-501-550.md#question-528) · [Q587](../practice-exams/questions-551-600.md#question-587) · [Q609](../practice-exams/questions-601-650.md#question-609) · [Q652](../practice-exams/questions-651-684.md#question-652)

## Further reading

- [RonitSachdev: Other Databases](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/12-Other-Databases.md)
- [RonitSachdev: GapFill Services](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/37-GapFill-Services.md)

---

[Previous: Messaging and streaming](messaging.md) · [Next: Monitoring and infrastructure management](operations.md)
