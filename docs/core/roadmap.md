# DewanLens roadmap

Approved direction: 30 October 2026. Public MVP target: **30 November 2026**, Asia/Kuala_Lumpur. Only M1 is active. This document describes intended outcomes, not implemented capabilities.

## Purpose and users

DewanLens is an independent, nonpartisan discovery site for BM-reading citizens, students, and occasional researchers. It helps readers understand a deliberately selected collection of Dewan Rakyat discussions and inspect the original evidence. Official Digital Hansard records are the source interface; DewanLens does not replace Parliament's archive or establish the truth of statements made in Parliament.

The product hypothesis is that reviewed BM explanations, contextual highlights, and topic navigation make particular discovery tasks easier. Official search already exists. Product value and competitor feature gaps must be demonstrated rather than assumed. Evidence and uncertainties live in [planning-sources.md](planning-sources.md).

## November release contract

- Aim for 15–20 substantive discussion segments from a small, explicitly identified set of sitting days. Start with five segments from two days in M1.
- Provide multi-label category chips and simple keyword search over the published collection.
- Each discussion includes a source-appropriate concise BM summary, 1–2 exact contextual highlights, correctly attributed speakers, sitting date, source status when available, and an original Digital Hansard link. Use sitting-level links with identification cues until stable speech-level links are proven.
- Publish only human-reviewed material with a documented public-republication basis. Summaries distinguish questions, claims, replies, and announced intentions. Parliamentary claims are not independently established facts merely because Hansard records them.
- Display the selected coverage, source/review dates, independent status, and a correction-contact route. Do not describe this sample as national or Parliament-wide trends.
- Use persisted approved records and static pages. End-user searches and page loads invoke no LLM.
- Verify mobile reading, keyboard use, visible focus, labelled controls, result/no-result states, and citations before release.

**Minimum shippable fallback:** 8–10 reviewed segments, the same fidelity and permission gates, and no issue briefs. No briefs are required for the core release. At most two curated briefs may be considered after the core is ready, within two total editorial hours; they connect cited discussions without political commentary.

November excludes live chat/RAG, a vector database, agents, accounts, daily automatic ingestion, national trend scores, party/MP rankings, promise verification, archive mirroring, multilingual expansion, realtime LLM summaries, and a public API without a demonstrated caller need. RAG may be evaluated after launch; it is not committed scope.

## Sequence and capacity

The schedule starts on 30 October; earlier proposed dates are superseded. About six hours per week is a planning assumption, not a commitment to displace job hunting or AnotherEdenAI. Roughly 26 hours remain at that pace. Full-cohort scope is conditional on measured throughput; use the fallback rather than increasing personal workload by default.

| ID | Target window (2026) | Outcome and entry/exit gates | Effort and main risk | Status |
| --- | --- | --- | --- | --- |
| M1 | 30 Oct–10 Nov | Five-record feasibility evidence and a pass/revise/stop decision. Current contract: [milestone.md](milestone.md). | 10–12 hours; source authority, permissions, fidelity | Approved; DL-F01 source inspection partial; E1 incomplete, E2–E5 pending |
| M2 | 11–17 Nov | After subsequent authorization: repeatable bounded processing and 15–20 reviewed records, or 8–10 fallback records. Requires M1 evidence and permitted operations. | 3–5 hours for fallback expansion; 6–8 for full collection; review throughput | Roadmap only; not authorized to begin |
| M3 | 18–23 Nov | After subsequent authorization: static browse/filter/search/detail flow with working citations and accessibility checks. Requires approved records. | 4–5 hours; scope and usability | Roadmap only; frontend implementation not authorized |
| M4 | 24–26 Nov | Final validation, deployment rehearsal, and separately authorized public deployment. Requires republication clearance and content/operational checks. | 3–4 hours; reuse and release readiness | Roadmap only; public deployment not authorized |
| Buffer | 27–30 Nov | Corrections, source changes, and deadline protection; no new features. | Reserve about two hours | Contingency |

Fallback work totals approximately 22–28 hours including the buffer. Full-cohort work may exceed the assumed capacity. Estimates are provisional until M1 measures actual effort.

On 10 November, unresolved feasibility issues trigger an explicit revise/stop decision. On 17 November, retain full collection size only if review throughput supports it; otherwise select the approved fallback. Freeze features by 23 November. Readiness by 26 November protects the remaining days for corrections. Never relax source fidelity or permission requirements to meet a date.

M2 and frontend work need subsequent user authorization even after M1 passes. Paid LLM calls and public deployment each require their own subsequent authorization. Model-processing permission is a separate requirement from approval to spend money.

## Execution and completion

Keep a single active [milestone.md](milestone.md). Later milestones remain outcomes here until authorized and promoted. Research uses `architect-planner` with important source-authority audits through `contract-auditor`; implementation uses `builder-executor -> tdd-loop`; verification uses `tdd-loop`. Final release-document reconciliation uses `release-manager-sync` only after implementation and verification are proven.

Use one commit per completed feature, including its necessary planning, evidence, tests, and milestone update. The one-time initial planning-baseline commit explicitly authorized on 31 October 2026 is an exception; otherwise, do not create a preparation-only or workflow-transition commit. Reconstructable handoffs remain ignored under `.sdd/`. Preserve the completed milestone through its final feature commit, then summarize it here and reuse the active milestone file.

Completed milestones: none.
