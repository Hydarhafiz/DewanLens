# Planning sources and authority gaps

Plan recorded: 30 October 2026. Public-source observations below come from the **23 October 2026 discovery session**; they were not rechecked during planning preparation. They establish leads and bounded observations, not completed M1 evidence. Recheck access, record versions, terms and relevant features during DL-F01.

## Product and repository authority

- [CHATGPT.md](../../CHATGPT.md) owns the engineering-review principles and source-of-truth ordering. Preserve the existing file.
- The user's initial request establishes the independent/nonpartisan product, November deadline, five experiments, non-goals, and another-project/job-hunting priorities.
- The user's 30 October approval establishes static-first architecture and M1, with minimal contracts, exploratory discovery assessment, source-appropriate summaries, sample-limited classification reporting, and three distinct permission checks. It authorizes canonical planning and M1 preparation. M2, frontend implementation, paid LLM calls and public deployment need subsequent authorization.
- [roadmap.md](roadmap.md) owns scope/order; [milestone.md](milestone.md) owns active feature acceptance; [architecture.md](architecture.md) owns shared design. Current implementation still needs to be inspected independently when execution resumes.

## Official sources inspected during discovery

| Source | Observed support and status | Limits / required follow-up |
| --- | --- | --- |
| [Digital Hansard](https://hansard.parlimen.gov.my/) | VERIFIED: public keyword/speech discovery interface and description of archive access | Does not establish republication or provider-processing permission; parser interface not proven |
| [14 October 2026 sitting](https://hansard.parlimen.gov.my/hansard/dewan-rakyat/2026-10-14?search=undefined) | VERIFIED: readable sitting content, speaker/time/draft cues, multi-block contributions and candidate topic material | Bare URL retrieval failed in the discovery tool while this query URL worked. Verify a suitable citation URL and direct-navigation behaviour; do not depend on the incidental query parameter |
| [15 October 2026 sitting](https://hansard.parlimen.gov.my/hansard/dewan-rakyat/2026-10-15) | VERIFIED: readable content and candidate material; repeated timestamps, short turns and contribution continuations | Does not prove stable speech IDs, complete extraction or final-status meaning |
| [Official Hansard listing](https://parlimen.gov.my/hansard-dewan-rakyat.html?uweb=dr) | VERIFIED in indexed discovery results: dated official Hansard listing | Direct fetches timed out. Follow actual listed document links before accepting PDF provenance; guessed PDF URLs are not authoritative evidence |
| [Ministry of Digital system handover release, 9 June 2026](https://www.digital.gov.my/en-GB/siaran/Kementerian-Digital-Serah-Sistem-Hansard-Parlimen-Kepada-Parlimen-Malaysia) | VERIFIED official description: cross-session search, MP filtering, term-frequency/word-cloud analysis; digital system does not replace official Hansard documents | Advertised capabilities were not functionally benchmarked. Resolve material text disagreements with official-document authority |
| [ParlimenAI login](https://ai.parlimen.gov.my/login) | VERIFIED limited observation: portal redirects to login; indexed login text advertises transcript and Chat Hansard | UNVERIFIED actual functionality, access eligibility, service relationship, or gaps relative to DewanLens. Do not authenticate or rely on developer replies |
| [Parliament public page](https://www.parlimen.gov.my/pac/?lang=bm) | VERIFIED limited observation: Parliament copyright reservation | A generic footer does not establish Hansard-specific reuse terms or a prohibition covering every intended operation |
| [Hansard robots location](https://hansard.parlimen.gov.my/robots.txt) | UNVERIFIED: retrieval failed through the discovery tool | A fetch failure is neither absence of rules nor permission. Check via an appropriate bounded method before automated collection |

## Separate permission decisions

Use `unknown`, `permitted`, `restricted`, or `not-applicable`, with the evidence URL/document, observation date, applicable operation, restrictions, and decision owner. A term must be shown to apply to Hansard and the intended use; do not borrow licences from another government site.

| ID | Decision | Initial state | Requirement before operation |
| --- | --- | --- | --- |
| P-ACCESS | Access and retain the selected source material/fixtures | Unknown for automated access and retention; public reading was technically observed | Inspect applicable access rules, robots/terms and retention restrictions; use bounded access and permitted storage. Technical readability alone is not permission |
| P-LLM | Submit source text to the selected external provider and retain resulting outputs | Unknown; no provider selected | Establish that source rights and provider terms allow this processing, including retention/training settings. Separately obtain user authorization for real calls and any spending |
| P-PUBLIC | Republish excerpts and derived summaries, including any public Git fixtures | Unknown | Establish an applicable documented permission/licence or qualified assessment for the particular publication. Public excerpts remain a go/no-go blocker while unresolved |

Keep these decisions independent. Private evaluation is not automatically public republication; source access permission is not automatically provider-processing permission. Provider permission does not authorize publication. Use synthetic fixtures for preparation when an operation's basis is missing, and label them synthetic; they cannot prove real-source feasibility.

If written clarification is necessary, prepare a narrowly scoped question for the owner. Do not send messages or assume replies from the two contacted developers. Unresolved important authority decisions require human review rather than an invented legal conclusion.

## Candidate collection and competitive hypothesis

Candidates are identified in [milestone.md](milestone.md); source boundaries are not yet frozen. The two sitting days were recent at discovery, not asserted to be the latest available records. Five records do not support population accuracy estimates or representative parliamentary coverage.

**ASSUMPTION:** reviewed BM explanation and contextual navigation make some tasks easier than keyword finding in the same source days. Test this in E5. **UNVERIFIED:** any claim that official portals lack these capabilities. E5 records observed benefits, failures and uncertainty without a statistical superiority requirement.

## DL-F01 gaps to resolve

Verify two usable source versions, acquisition method and format variability; speaker/turn/discussion boundaries; date and status meaning; exact citation stability; text completeness and any PDF discrepancy; a bounded source-update check; all three permission decisions and what they permit next. Preserve applicable provenance or durable storage references without collecting or publishing an archive. Do not treat this list as findings already established.
