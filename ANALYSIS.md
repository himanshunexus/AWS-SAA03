# Source coverage and review notes

## Coverage

| Item | Result |
|---|---:|
| PDF pages processed | 249 |
| Questions extracted | 684 |
| Number range | 1-684, no missing or duplicate IDs |
| Companion question blocks recovered | 674 |
| Questions entirely absent from companion | 191-200 |
| Suggested answers added | 41 |
| Embedded policy/option images preserved | 11 |

All pages were text-extracted. A rendered sample was visually checked, and image-based answer choices for question 477 and the policy for question 429 were inspected. This is full extraction coverage, not a claim that every page was visually audited or every supplied answer independently fact-checked.

The companion file mixes `1]` and `51.` numbering. Its second entry labeled `215]` actually matches PDF question 315 and has been remapped. Some entries contain a question without an answer, empty content, or placeholders such as `Json format`. Suggested answers complete those entries. Original notes remain available in collapsible sections for comparison.

Policy images belong to questions 96, 253, 423, 429, 477 and 494. Question 477 has four image-based answer choices; read their labeled images together with the policy.

## Material content limitations

- **Q198:** DocumentDB compatibility must be tested; MongoDB compatibility does not guarantee every application can migrate without changes.
- **Q224:** Multivalue DNS is the intended routing choice, but it is not a full load balancer or a guarantee of perfectly random traffic distribution.
- **Q235:** DMS full load and CDC is the closest option. Concurrent writes on both engines require a carefully designed bidirectional replication and conflict strategy.
- **Q257:** CloudWatch metric streams export metrics, not individual lifecycle events. The wording mixes these concepts.
- **Q315:** Inspector is the vulnerability service; the option uses historical agent terminology.
- **Q366:** API keys and usage plans are not authorization. The intended option must be combined with real entitlement checks before protecting premium content.
- **Q390:** Redis replication alone is not equivalent to strongly durable storage. Configure and test the persistence requirements.
- **Q543:** Existing and new Organizations management accounts can both support discount sharing. The offered pairs are ambiguous; the suggested pair is labeled accordingly.
- The original notes contain historical service names, operational claims, and answer selections that need current AWS documentation checks. For example, a source explanation saying DataSync runs continuously should not be read as an automatic, persistent event watcher; tasks must be scheduled or invoked. Lifecycle expiration is also asynchronous, not an exact deletion-time guarantee.

## Reference repository review

The reference repository's root README advertises 38 guides, while its topic index says 37. The inspected tree contains **37 numbered topic guides plus one index**, which explains the count discrepancy. Its structure covers core infrastructure, databases, serverless integration, networking, security, governance, migration and exam review.

The root README, complete topic index, and exam-traps guide were read. Other individual topic guides were inventoried, not comprehensively fact-checked. The reference is supplemental reading, not the source of the PDF answer key. Some compressed rules need scope: a traditional RDS Multi-AZ DB-instance standby differs from readable instances in a Multi-AZ DB cluster; security certifications and service limits also change.

## Validation

The build verifies consecutive unique PDF question IDs and a nonempty supplied-note or suggested-answer section for every record. JSON and Markdown question counts must both equal 684, and all referenced local images must exist. This validates extraction completeness, not the correctness of every community answer.
