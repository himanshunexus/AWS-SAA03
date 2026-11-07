# AI services and document processing

[Home](../README.md) · [Study guide](../study-guide.md) · [Practice index](../practice-exams/README.md)

- [Choose the managed capability](#choose-the-managed-capability)
- [Document pipeline](#document-pipeline)
- [Avoid mismatches](#avoid-mismatches)

## Choose the managed capability

| Input and goal | Service |
|---|---|
| Scanned document text, forms and tables | Textract |
| Text entities and sentiment | Comprehend |
| Supported medical text entity extraction | Comprehend Medical |
| Audio to text | Transcribe |
| Text to speech | Polly |
| Translate text | Translate |
| Supported image/video analysis | Rekognition |
| Conversational interfaces | Lex |
| Custom ML development and hosting | SageMaker capabilities |

## Document pipeline

- Store uploaded documents in S3 and trigger processing with a supported event integration.
- Extract text with Textract, then analyze the text with the service appropriate to its domain.
- Store structured results separately from original files; catalog them for analytics and apply retention and access controls to both.
- Use asynchronous processing and durable queues for jobs that cannot finish during a synchronous request.
- Treat extracted data as potentially sensitive. Limit access, audit usage and validate extraction quality before relying on automated decisions.

## Avoid mismatches

Rekognition is not the default document OCR service; Transcribe expects audio rather than already extracted text. Choosing a managed service with the right input/output model usually reduces custom code.

## Related PDF practice

Review the mixed practice sets for cross-topic scenarios.

## Further reading

- [RonitSachdev: GapFill Services](https://github.com/RonitSachdev/aws-saa-c03-guides/blob/main/topic-guides/37-GapFill-Services.md)

---

[Previous: Backup and disaster recovery](disaster-recovery.md) · [Next: Final revision and decision patterns](exam-revision.md)
