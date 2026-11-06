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

## DL-F01 bounded source inspection — 31 October 2026

This update records source metadata and access observations only; it does not admit a corpus or approve candidate boundaries.

### Technical access and traceability

| Record | Direct official citation | Observed status and identification cues | Boundary/version limits |
| --- | --- | --- | --- |
| 14 October 2026 | [Dewan Rakyat, 14 October](https://hansard.parlimen.gov.my/hansard/dewan-rakyat/2026-10-14) | The date-level URL opened without a query parameter. The page identifies the sitting date and chamber and displays `Draf`; speaker blocks carry repeated time cues and draft markers. The Tebrau question 5 cue appears at about 10:40; Puncak Borneo appears at about 17:20. | No stable speech-level URL or anchor was verified. A timestamp can repeat across blocks and does not identify a unique span. No origin response validator, immutable version ID, or complete-text comparison was obtained. |
| 15 October 2026 | [Dewan Rakyat, 15 October](https://hansard.parlimen.gov.my/hansard/dewan-rakyat/2026-10-15) | The date-level URL opened without a query parameter. The page identifies the sitting date and chamber and displays `Draf`; speaker blocks carry repeated time cues and draft markers. Rasah question 3 appears at about 11:10; Bagan begins at about 12:41; Betong appears at about 16:00 and 16:10. | No stable speech-level URL or anchor was verified. A timestamp can repeat across blocks and does not identify a unique span. No origin response validator, immutable version ID, or complete-text comparison was obtained. |

The web reader returned transcript-body excerpts while opening the official pages. Later page-open requests intended only to verify date/status metadata also returned body excerpts. After recognizing this behavior, no further targeted transcript searches or content analysis were performed. The excerpts were not saved as local files, quoted into this document, or committed; no labels, summaries, highlights, or human reference annotations were generated. This event is an unresolved provider-processing exposure, not P-LLM clearance. Provider retention and training terms for this tool were not established. Do not send more transcript text to a hosted model while this remains unresolved.

The date-level URL was usable in the bounded browser check; this establishes current navigability only, not long-term stability. The `search=undefined` parameter is unnecessary for the 14 October link and should not be used as a citation dependency. The 15 October queryless link opened; a query-bearing variant timed out. The browser output showed multiple speaker/time blocks, but it did not provide raw HTML, origin headers, an extraction API, or a completeness guarantee. These observations do not establish an automatic acquisition method or reliable parser. Use date-level citations with speaker/date/time/section cues; never invent speech anchors from display order or DOM position.

The official [Hansard catalogue](https://hansard.parlimen.gov.my/katalog/kamar-khas) describes daily publication on the next working day. Both selected pages still displayed draft status during this check. The status lifecycle and the point at which a draft becomes final remain unknown. The Ministry of Digital's [system handover release](https://www.digital.gov.my/en-GB/siaran/Kementerian-Digital-Serah-Sistem-Hansard-Parlimen-Kepada-Parlimen-Malaysia) says the Digital Hansard system does not replace Parliament's official Hansard documents. The [official Hansard listing](https://parlimen.gov.my/hansard-dewan-rakyat.html?uweb=dr) timed out in the available browser tool, and no actual linked PDF or document correspondence for either sitting was verified. Do not guess PDF URLs or declare the digital page text complete or authoritative over an official document.

The Parliament site displays a reserved-copyright notice. Its 2026 [Hansard preparation guide](https://www.parlimen.gov.my/images/webuser/dn/Buku%20Panduan%20Penyediaan%20Verbatim%20Penyata%20Rasmi%20Hansard.pdf) also carries a written-permission notice for reproduction of that guide. That notice applies to the guide itself; it does not settle rights in the Hansard transcript, excerpts, summaries, model inputs, or public Git fixtures. The Hansard `robots.txt` endpoint was inaccessible through the browser tool, and a local metadata-only request could not resolve the host. Neither failure is permission or evidence that no access rules exist.

### Proposed candidate boundaries — human review pending

The following are identification cues from the approved M1 plan cross-checked against the date pages. They are proposals only: no accepted start/end offsets, frozen boundaries, category references, or source-point checklist exist. The human owner must review the official page directly and decide whether to include the full reply, a connected follow-up, a subsection of a longer speech, or an entire multi-topic contribution.

| Candidate | Proposed source boundary cue | Provenance and unresolved boundary question |
| --- | --- | --- |
| A | 14 October, about 10:40: Tuan Jimmy Puah Wee Tse (Tebrau), question 5 and the Economy Minister's response. | [14 October page](https://hansard.parlimen.gov.my/hansard/dewan-rakyat/2026-10-14). Confirm which continuation blocks and any follow-up are part of the discussion, and the exact end before the next independent question. |
| B | 14 October, about 17:20: Datuk Willie anak Mongin (Puncak Borneo), the rural-mobility portion within a longer contribution. | [14 October page](https://hansard.parlimen.gov.my/hansard/dewan-rakyat/2026-10-14). Confirm the exact topic transition and whether the selected span is complete enough to preserve context; do not silently include or exclude adjacent topics. |
| C | 15 October, about 11:10: Tuan Cha Kee Chin (Rasah), question 3 and the Health Minister's response. | [15 October page](https://hansard.parlimen.gov.my/hansard/dewan-rakyat/2026-10-15). Confirm response continuation blocks, whether a follow-up belongs, and the exact end before the next question. |
| D | 15 October, about 12:41–12:50: Tuan Lim Guan Eng (Bagan), the fiscal/enterprise portion identified in the approved plan. | [15 October page](https://hansard.parlimen.gov.my/hansard/dewan-rakyat/2026-10-15). Confirm the source section and transition that delimit this topic within the wider contribution. |
| E | 15 October, about 16:00–16:10: Dato Dr. Richard Rapu @ Aman anak Begri (Betong), proposed as the multi-topic contribution. | [15 October page](https://hansard.parlimen.gov.my/hansard/dewan-rakyat/2026-10-15). Confirm the full speaker-turn end and whether preserving the whole contribution is preferable to a narrower topic span. |

These cues do not satisfy F01-01's precise-boundary acceptance criterion. The three controls are also not yet source-frozen: the procedural turn, a short substantive turn, and an out-of-taxonomy turn must each be selected by human review from these two sitting pages and recorded outside the five publication candidates. The exact speaker, time, boundaries, and rationale for each control remain open; do not infer or invent them from the page-level observations above.

### Permission state after bounded inspection

| Gate | Current state | Evidence and consequence |
| --- | --- | --- |
| P-ACCESS | **Unknown** | Public date pages were technically readable, but robots/access rules were not retrieved; transcript retention, local fixture storage, and automated retrieval terms were not established. Do not automate, bulk-download, or retain transcript text until the applicable basis is clear. |
| P-LLM | **Unknown; unresolved exposure recorded** | No provider was selected and no provider terms were checked. Transcript excerpts were returned to the hosted model context by the browser tool, so this inspection cannot be represented as having avoided external processing. Stop further transcript submission; determine the applicable processing and retention terms before any additional model use. |
| P-PUBLIC | **Unknown** | Reserved-copyright notices and the separate guide's permission clause do not determine transcript reuse rights. No excerpt, summary, transcript fixture, or source text may be published or committed without an operation-specific reuse basis. |

**Provisional DL-F01 disposition: REVISE / HOLD; the feature is incomplete.** The date pages are technically reachable, but accepted boundaries, controls, draft-to-final handling, official-document correspondence, and permitted retention are not established. No permitted evaluation corpus can yet be nominated under the current evidence. Reassess after the human boundary checkpoint and operation-specific permission evidence; stop only the affected operation if its basis remains unavailable.

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
