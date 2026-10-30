# DewanLens architecture

Status: approved design, incorporating the 30 October 2026 refinements. No product implementation exists. Scope, sequencing, and authorization are owned by [roadmap.md](roadmap.md) and [milestone.md](milestone.md).

## Processing and ownership

```text
Official sitting records
  -> bounded fetch/manual import + immutable source references
  -> speaker turns + explicitly bounded discussion segments
  -> offline labels, BM summary, highlight candidates
  -> deterministic validation + human review
  -> approved JSON -> static pages and browser search (future milestones)
```

Python owns the offline flow: read a small permitted source set, prepare segments, call the authorized model when allowed, validate structured output, produce a review package, and retain approved results. The normal path should be explainable as a few explicit functions. Keep source preparation, the model-call boundary, validation, and review/export responsibilities visible. Do not introduce a provider registry, workflow engine, generic repository/service layer, ORM, agent framework, or configurable processing DAG.

A bounded manual import is acceptable if source automation is fragile. No broad crawler or universal PDF parser is required for M1. Choose extraction dependencies only when inspected source formats justify them. Never silently truncate long contributions to fit a model context window.

Use plain typed records with validation at external input/output boundaries. JSON is sufficient working and approved storage for five records and the November collection. One model-call boundary must support mocks and recorded-response replay; multiple provider implementations are unnecessary.

Future static generation reads only reviewed records. Public assets contain approved publication fields, not full sitting snapshots, unreviewed outputs, or internal review notes. Search/page loads have no model or application-server dependency. Local discussion IDs produce site links; original citations remain official-source links.

## Minimal record contracts

Use a source manifest plus discussion records. The rows below are nested concerns, not a requirement for separate classes, tables, files, or services. No independent summary, highlight, review, or processing-run entity is needed in M1.

| Location | Minimum information |
| --- | --- |
| Source manifest entry | Stable source/version reference; chamber and sitting date; retrieval and citation URLs; retrieved-at time; observed draft/final/unknown status and its evidence; extracted-text SHA-256 and extraction version; raw checksum when raw material is retained; durable retained-source location if permitted; separate permission evidence references |
| Discussion | Local stable ID; scope/title; ordered source spans; source speaker names/roles; timestamp/section cues; category IDs; BM summary; 1–2 highlights |
| Source span within discussion/highlight | Immutable source reference, turn identifier/ordinal, speaker, and start/end Unicode character offsets in the extracted text; original context must remain recoverable |
| Processing metadata within discussion | Input hashes; prompt, taxonomy, extraction and configuration versions/hashes; exact returned provider/model identity when available; saved response reference/hash; token counts, elapsed time, and cost |
| Review metadata within discussion | Pending/approved/rejected/stale state; reviewer and time; reviewed input/output hashes; rubric outcomes and material corrections/reasons |

The source manifest is the single place for source identity and permission evidence. Discussion records refer to it rather than duplicating a permission database. A small versioned taxonomy definition supplies category IDs and rules. Record format evolution can be explicit when needed; M1 does not need a generalized migration system.

## Provenance and fidelity invariants

- A discussion is a scoped topic unit, possibly covering multiple turns and speakers. A source turn is not automatically a discussion. Preserve ordered speaker-specific spans; never attribute a reply to the questioner.
- Timestamps repeat and are identification cues, not unique IDs. Displayed timestamps are interpreted in the source's Malaysian sitting context; preserve their original precision.
- A citation uses a verified official sitting URL plus speaker/date/time/section cues. Do not manufacture speech anchors from DOM positions. Prove speech-level deep links by direct navigation before adopting them.
- Highlights are contiguous exact substrings of the identified immutable extracted text. Validate bounds, source identity, speaker, and equality. Do not synthesize, stitch, silently repair punctuation, or remove qualifications. Start without quote normalization; any later normalization needs an explicit mapping back to the exact source.
- Human context review is mandatory even when exact matching passes. A technically exact quotation can still be misleading.
- Summaries use source-appropriate length. Preserve factual accuracy, attribution, material points and qualifications before brevity. A short source must not be padded to meet a word count; a complex contribution must not lose material meaning to fit one.
- Questions, claims, ministerial replies and intentions retain their speech act. Hansard proves that a statement was recorded, not that its contents are independently true. Do not infer motives, sincerity, fulfilment of promises, or public opinion.
- Invalid/malformed model output fails validation and cannot enter approved records. Source text is untrusted content, not instructions to the processor; keep it separate from processing instructions. Render source/model text as escaped text in future HTML.

## Reproducibility and changes

Save enough permitted input, prompt/configuration identity, and model output to replay deterministic checks without a live call. Versioned inputs and recorded responses reproduce an accepted result; a future live model run may differ even with the same settings. If an immutable input cannot legally or durably be retained, document that replay limitation rather than claiming full reproducibility.

Keep an accepted source version immutable. Compare extracted-text hashes so markup-only changes can be distinguished from transcript changes. Changed text or draft/final status requires review; for this small pilot, mark dependent records stale and hold them from new publication until re-approved. Never silently repoint an approved quote at a newer source. Preserve the identity of material supporting previously accepted output.

Digital Hansard is the discovery/retrieval interface. The Ministry's statement that it does not replace official Hansard documents makes material disagreement with an underlying official document an authority checkpoint. Record the conflict and hold affected output; do not silently choose a convenient version.

## Permission and publication boundaries

Maintain three distinct decisions: source access/retention, provider LLM processing, and public republication. Their evidence and initial states are in [planning-sources.md](planning-sources.md). Permission for one does not imply either of the others. Spending authorization and deployment authorization are additional user controls.

Source access uncertainty constrains collection/retention. Provider-processing uncertainty constrains external submission; use mocks or permitted local fixtures instead. Public-republication uncertainty blocks public excerpts/derived content but does not itself prove private evaluation forbidden. Evaluate the actual operation rather than applying one blanket permission flag. No developer approval can substitute for applicable source rights.

## Alternatives and limits

| Decision | Reason and cost |
| --- | --- |
| Static JSON/pages with Python offline processing | Matches a small reviewed collection; no per-view inference, mutable public database, or application-server operations. Content updates require a rebuild. |
| Defer FastAPI + SQLite | Server queries, multi-user editing or a real API caller might justify them later. They currently add service hosting, persistent storage and backup/security work without a required workflow. |
| Keep human review | Small-sample AI evaluation cannot establish general political-summary accuracy. Review time limits collection size and must be measured. |
| No archive/trend claims | A deliberately selected sample has substantial selection bias. Exact quotations and neutral wording do not eliminate editorial selection effects. |
| Simple browser search later | Search covers the published collection only. Test useful navigation before adding semantic retrieval. |

The useful backend/AI engineering story is reproducible inputs, explicit transformations, source validation, controlled failures, review, and cost accounting. Infrastructure is added only for a concrete supported need.
