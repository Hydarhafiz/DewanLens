# M1 — Five-record feasibility

Approved: 30 October 2026 with the user's refinements. Target decision: 10 November 2026; public MVP deadline remains 30 November. **Status: prepared; source research and all experiments are pending.** Only M1 is active. [Roadmap](roadmap.md) owns later scope and authorization; [architecture](architecture.md) owns minimal shared contracts; [planning sources](planning-sources.md) distinguishes observed facts and authority gaps.

## Outcome and limits

Establish whether five substantive Dewan Rakyat discussions from two sitting days can be traced, classified, summarized and highlighted faithfully, then assess their discovery value. Use offline Python/JSON with mocks and saved-response replay. A local fixture/CLI evaluation is sufficient. Do not build a frontend, public API, database service, broad crawler, generic processing framework, or M2 collection.

Preparation establishes canonical documents and the local workflow only. It does not count as completed research, a passed experiment, or authority to spend money. No preparation-only commit is needed. Paid LLM calls, M2, frontend implementation and public deployment need subsequent authorization. Any provider submission also needs P-LLM clearance regardless of price.

## Candidate inputs and human references

Use the two sitting records identified in [planning-sources.md](planning-sources.md). Freeze actual boundaries during DL-F01; the following are source cues, not accepted spans or model labels.

| Candidate | Sitting / identification cue | Intended challenge |
| --- | --- | --- |
| A | 14 Oct 2026, about 10:40; Tebrau question and Economy Minister response | AI/workforce subject, question versus reply, several speakers |
| B | 14 Oct 2026, about 17:20; Puncak Borneo rural-mobility portion | Topic boundaries within a longer contribution; include sufficient source for a faithful concise summary |
| C | 15 Oct 2026, about 11:10; Rasah question and Health Minister response | Public-health measures, attribution, continuation blocks |
| D | 15 Oct 2026, about 12:41–12:50; Bagan fiscal/enterprise portion | Numerical claims, requests and proposals |
| E | 15 Oct 2026, about 16:00–16:10; Betong contribution | Multi-topic contribution, completeness and overlap |

Preserve at least one multi-topic contribution. Add a procedural turn, a short substantive turn and an out-of-taxonomy control outside the five publication records. Shortness alone must not determine substantive value. If a candidate is unsuitable, replace it within the same two-day/five-record boundary while preserving diversity; record the reason and adjust references before model generation.

Before generation, the human owner freezes category references and a source-point checklist covering important content, speakers, speech acts, numbers and qualifications. Record uncertainty rather than treating disputed references as an oracle. The owner reviews BM outputs against original context; disclose if the same person authored references and evaluated results. Human corrections cannot retroactively improve generated-output metrics.

Starting labels: Teknologi & digital; Ekonomi & kewangan; Pengangkutan & infrastruktur; Kesihatan; Pendidikan; Alam sekitar. Define inclusion/exclusion examples before classification. Label substantive treatment rather than incidental mentions. Permit multiple labels and explicit abstention/review for out-of-taxonomy material; procedural turns have no topic label.

## Feature contracts

### DL-F01 — Establish usable sources

- **Type / status:** research / prepared; research not executed.
- **Outcome and scope:** inspect two sitting days, identify five candidate spans and controls, establish traceability, and document P-ACCESS, P-LLM and P-PUBLIC independently. No product code or automated verification tests in this research feature.
- **Entry:** approved architecture/M1 and preserved existing user work.
- **F01-01:** E1 technical findings have direct source evidence; each accepted segment has date, speaker, observed status, precise boundaries and a verified official citation. Label any incomplete/unavailable source comparison.
- **F01-02:** all three permission decisions have operation-specific evidence or explicit unresolved states and consequences. A negative/unknown decision is a valid research finding, not permission to proceed through that gate.
- **F01-03:** nominate a permitted evaluation corpus and record the human boundary/reference checkpoint, or issue an evidence-backed revise/stop finding if no corpus can be admitted. No claim that five real sources are ready while source access/retention is unresolved.
- **Exit/evidence:** E1 findings and candidate provenance in the nearest source manifest and planning sources; permission state and next permissible operation are clear. Public clearance need not precede permitted private evaluation, but unresolved P-PUBLIC blocks publication.
- **Route:** `architect-planner`. Use `contract-auditor` as a read-only checkpoint before accepting important disputed source authority, provenance or permission evidence; read that role and preflight its bounded audit scope when invoked. Human decisions settle unresolved authority.
- **Commit boundary:** one completed research feature commit containing source findings, permitted provenance/fixtures if suitable, necessary canonical planning and the milestone update. Preparation alone does not complete DL-F01.

### DL-F02 — Evaluate controlled AI processing

- **Type / status:** build / pending DL-F01 and applicable permissions.
- **Outcome and scope:** minimal source preparation and typed JSON contracts; one mocked/replayable model boundary; deterministic output/source checks; E2–E4 evaluation. No provider framework, UI, server, database, or cohort expansion.
- **Entry:** admitted evaluation corpus and frozen human references. Mock-only work may proceed using permitted fixtures; real submissions need P-LLM and user call/spending authorization. A source-processing restriction must not be bypassed with a free provider.
- **F02-01:** accepted records retain immutable source references, prompt/model/configuration identities, validated category values and exact source spans. Saved-response replay needs no live call. Malformed output and invalid/stale spans are rejected.
- **F02-02:** E2 reports expected and predicted label sets, per-record errors, exact-set matches, per-label counts and precision/recall/F1 where defined. Show denominators and zero-support cases; never generalize five-record results to overall model accuracy.
- **F02-03:** E3 accepted summaries have zero unsupported assertions, wrong attribution or material omissions against frozen reference points. Length reflects the material; no fixed minimum/maximum word-count gate. Retain generated and human-edited evaluations separately.
- **F02-04:** E4 accepted highlights match exactly, have the correct speaker/local context, and become stale when source identity changes. Each accepted discussion has 1–2 reviewed highlights.
- **Exit/evidence:** E2–E4 results and meaningful failure examples; five reviewed evaluation records or an explicit revise/stop result. Mock/synthetic success alone cannot establish real-model or real-source feasibility.
- **Route:** `builder-executor -> tdd-loop`; use contained `feature-planner` refinement if necessary without changing the approved architecture.
- **Commit boundary:** one feature commit including implementation, retained capability tests/fixtures, accepted evidence and the milestone update. Do not commit intermediate role changes.

### DL-F03 — Assess discovery value and decide feasibility

- **Type / status:** verification-only / pending reviewed records.
- **Scope:** E5 using a CLI/fixture viewer and official keyword baseline over the same two days. No frontend or further inference is required.
- **Entry:** five reviewed records and predeclared tasks/expected evidence. If records are unavailable, record the unmet dependency rather than fabricate task results.
- **F03-01:** report three task attempts, answers/citations, failures, useful differences, time/effort observations when practical, and learning/coverage bias. Test 5 is exploratory: no 25% improvement gate, statistical superiority claim, or required speedup.
- **F03-02:** give an evidence-backed pass/revise/stop recommendation with measured human effort, costs, permission limits and remaining uncertainties. Separate technical feasibility, model observations, exploratory discovery value, and public-launch eligibility.
- **Exit/evidence:** compact accepted E5/overall assessment; milestone retention sweep and accurate roadmap summary. Negative or inconclusive findings remain legitimate outcomes. M1 may complete with a stop decision; passing does not authorize M2.
- **Route:** `tdd-loop`.
- **Commit boundary:** one verification feature commit with durable evidence, any necessary verification remediation, final M1 documentation and cleanup. No cleanup-only follow-up commit.

## Five experiments and execution order

Run E1 first; freeze the corpus/references; implement mocked validation/replay; run authorized real processing for E2–E4 only after permission and budget gates; then perform E5. All experiments currently have status **not run**.

| ID | Inputs and tool/fixture strategy | Exact accepted artifact | Acceptance, failure modes, and decision |
| --- | --- | --- | --- |
| E1 — Source access/reuse/traceability | Few bounded reads of two official sitting pages and actually linked documents where available. Compare dates/status, speaker turns, continuations and sections. Inspect applicable robots/terms/licensing. Repeat a bounded retrieval during M1 to observe versions; do not claim update stability from one read. | Findings/evidence links in `docs/core/planning-sources.md`; admitted source identity/spans in `tests/fixtures/hansard/manifest.json` when suitable/permitted | All five accepted spans trace correctly and have working original links. Separate observed accessibility from permitted operations. Failures: incomplete text, HTML/PDF conflict, unstable links, ambiguous status/rights. Pass usable permitted inputs; revise to manual import if needed; stop affected operations when their basis is missing. Source-update invalidation is specified here and exercised in E4. |
| E2 — Multi-label classification | Five segments and three controls, frozen human label references; one bounded taxonomy; structured generated output; mocks for malformed/unknown labels. | `artifacts/evidence/feasibility/classification.json` | Report raw label sets, counts and defined metrics transparently. Accepted records have valid human-reviewed labels and all controls have reviewed dispositions. Failures: incidental labels, missed overlap, forcing unknowns, discarding substantive short turns. Pass when reviewed classification and correction effort are viable; revise taxonomy/prompt once if needed; stop expansion if unresolved errors or review burden defeat the limited product. No population accuracy claim. |
| E3 — Summary fidelity | Same source spans and surrounding context; frozen material-point/speech-act checklist; source-appropriate BM summaries; sentence-to-source human review. | `artifacts/evidence/feasibility/summary-review.json` | Every accepted assertion is supported/attributed, important reference points/qualifications survive, and material omissions are corrected. No rigid word count. Record first-generation errors and human corrections separately. Failures: converted questions, invented conclusions, distorted numbers, omitted topics or padding. Pass accepted fidelity and viable review effort; revise prompt/boundaries once; stop expansion if material errors persist within the time/call budget. |
| E4 — Highlight fidelity | 1–2 proposed contiguous passages per discussion with immutable references/offsets. Mock fabricated text, wrong speaker, wrong occurrence, invalid bounds, changed punctuation, removed negation, stitched quotes and stale hashes. | `artifacts/evidence/feasibility/highlight-review.json`; capability-named span/invalidation regression tests | 100% of accepted highlights match their exact source and pass speaker/context review. Reject every deliberately invalid test case; source changes invalidate approval. Removed-negation/stitched cases must also be rejected by contiguous-span validation or human context review as appropriate. No synthesized or silently normalized quote. Revise candidate selection once; hold any record without a faithful highlight. |
| E5 — Exploratory discovery value | Five reviewed records, three frozen tasks, CLI/fixture navigation versus official keyword finding within the same two sitting days. Alternate task order where practical; record single-reviewer familiarity. | `artifacts/evidence/feasibility/discovery-tasks.json` | All attempts have evidence-backed outcomes, including failures/inconclusive outcomes. Describe benefits, friction and limitations; elapsed times are descriptive only. Failures: little added value, misleading simplification, baseline unavailable, learning bias. Pass a narrowly described useful proposition, revise navigation/scope if mixed, or recommend stop when no useful proposition emerges. No statistically unsupported improvement threshold. |

E5 task set (freeze expected source evidence before attempts): locate the AI/workforce discussion and the government's stated response; locate rural-mobility and rural-health discussions; distinguish ministerial haze-response measures from an MP request for local monitoring. Adapt only if final admitted source boundaries require it, before observing task results.

The human owner reviews source boundaries, independent reference labels/points, all five summaries and all highlights, and performs/observes discovery tasks. A readily available second reviewer is useful, but recruitment is not a dependency. Codex can prepare comparisons and deterministic checks; it cannot substitute a claimed human review.

## Time and real-call controls

M1 is estimated at 10–12 hours: E1 2–3 hours; minimal preparation/checks/replay 2–3; E2 references/evaluation about one; E3 review about two; E4 review about one; E5/decision about one to two. Record actual preparation, model latency and human review time separately; overlapping E2–E4 generations are counted once. If the estimate is exceeded, decide revise/stop rather than automatically consume time reserved for other priorities.

No real calls are currently authorized. The proposed later ceiling is five initial combined calls plus up to five revision calls, 60,000 input tokens, 12,000 output tokens and US$3, stopping at the first reached limit. This is a proposal, not an approved spend or verified model-price estimate. Confirm model/provider terms, prices and input capacity before requesting bounded call authorization. Count retries and failed billed requests. No model shopping or automatic unbounded retry loop.

Track actual provider/model identity, prompt/config versions, input/output tokens, billed amount/currency or explicitly estimated cost, price basis/date, elapsed time and correction minutes. Do not read or log credentials. Use safe configured interfaces later, not secrets inspection. Local mocks and replay cost zero inference tokens. Synthetic fixtures must be labelled and cannot be counted as real-source/model results.

## Verification and retention

Preparation uses documentation review, link/path consistency checks, JSON parsing and SDD preflight; no product tests are required. No repository Python toolchain currently exists. For DL-F02, the approved plan admits narrowly scoped Python configuration and development dependencies for pytest, Ruff and mypy; choose/pin them during implementation, not preparation. Candidate commands are `python -m pytest`, `python -m ruff check`, `python -m ruff format --check`, and `python -m mypy` over the implemented Python paths. Preflight must name their actual path scope before writes; no broad CI/tooling expansion is implied.

Retain representative permitted fixtures under `tests/fixtures/hansard/`: source manifest/text where suitable, `segments.json`, `reference-labels.json`, `reference-points.json`, and one accepted recorded-response set. Keep prompt/model/config identities with the nearest existing record, not duplicate registries. Capability tests protect parsing/source identity, schema validation, spans and invalidation. Expected labels and source points must be independently human-reviewed, not copied from model outputs.

Keep only compact irreplaceable evaluation mappings/failure examples in `artifacts/evidence/feasibility/`. For large/restricted sources, retain an approved durable location and checksum instead of committing raw data. A public Git repository is itself republication. Do not commit restricted material before P-PUBLIC clearance. Source text and scratch downloads never enter a future public site bundle by default.

Promote durable architecture/source decisions into their canonical documents. Purge scratch downloads, duplicate generations, command logs, temporary scenarios and generated reports when no longer useful. Keep no empty fixture scaffolding now. At each completed feature, retain/consolidate/remove its tests and evidence deliberately. At M1 completion, summarize the decision in the roadmap, retain the completed milestone through its final feature commit, then reuse this file for the next authorized milestone. Local `.sdd/` state is ignored and reconstructable.

## Current evidence and next checkpoint

Planning preparation is the only established outcome. No source manifest, reference annotations, processing code, generated records, evaluation results or human approvals exist yet. The next substantive work is DL-F01's bounded source/access investigation and candidate preparation, followed by human boundary/reference review and any unresolved important authority decision. Paid model calls remain a later explicit checkpoint. Public-republication uncertainty must remain visible without being mistaken for either source-access or provider-processing permission.
