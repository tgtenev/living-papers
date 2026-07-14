# AI-Research-Workflow — Review & Revision Register

**Document Metadata**

| | |
|---|---|
| **Store** | living-papers |
| **Version** | v1 |
| **Last updated** | 2026-07-14 |
| **Branch** | `main` |
| **Revision note** | v1: opened the register — records the 2026-07-14 workflow-review findings (faithfulness gaps, additional best practices, clarity fixes) against [ai-research-workflow.md](ai-research-workflow.md) v2, each with evidence from the week's git history and a disposition. Companion to the paper; itself an instance of the open-findings-register practice it recommends (F6). |

---

**Scope.** Standing review record for [ai-research-workflow.md](ai-research-workflow.md). Each finding was surfaced by reconstructing one week of the author's AI-assisted research activity (2026-07-07 → 2026-07-14) from git across research-workbench, public-portfolio, literature-vault, living-papers, and private-notebook, and comparing observed practice against the paper's v2 description. Findings carry a disposition: **applied** (folded into the paper), **deferred** (agreed, scheduled for a later pass), or **open** (needs author input). This file doubles as the worked example for the open-findings-register practice at F6 — a register kept alongside the manuscript it tracks.

**Evidence base.** The week's commits and artifacts: the multi-document `cfm-dark-sector-program/` (analysis.md → v22, plus background.md, derivations.md, mond-review.md, reference digests, a `data/` folder, and `t4-*.pl` fit scripts); literature-vault acquisitions including the SPARC / RAR / BTFR data tables and Li et al. 2018 Table A.1 (175 galaxies); public-portfolio's dissertation and three journal papers; and the cross-store GitHub-KaTeX rendering fixes now codified in the convert-paper-to-markdown skill (research-workbench `.claude/skills`, §9).

## Findings

| ID | Finding | Evidence | Disposition |
|---|---|---|---|
| F1 | The unit of work is often a multi-document *program*, not a single manuscript + `context.md`. | `cfm-dark-sector-program/` holds an analysis, a background doc, a derivations doc, reference digests, a context manifest, `data/`, and `figures/`. | **applied** — new §5.5 (foundational paper + dependents). |
| F2 | literature-vault also stores acquired **datasets** for numerical validation, not only reference prose. | SPARC tables; Li 2018 Table A.1; McGaugh 2016 RAR; Lelli 2016 BTFR — acquired and fit against. | **applied** — §2 literature-vault bullet + §5.6. |
| F3 | AI-written analysis/validation **code** is a first-class artifact, co-located with the manuscript. | `t4-fit-pergalaxy.pl`, `t4-calibration.pl`, `t4-fit-robustness.pl`, etc. in the program folder; outcomes flow back into analysis.md. | **applied** — §5.5. |
| F4 | Dead raw URLs: §4 fetches the paper from research-workbench, but the file was moved to living-papers. | `git ls-files`: no longer tracked in research-workbench; lives in living-papers. | **applied** — §4 URLs point to living-papers. |
| F5 | GitHub-KaTeX math rendering needs a documented authoring discipline; the paper implied it "just works." | Brace-stripping fix across 14 vault conversions; `\operatorname`→`\mathrm`; dissertation split for size; backtick inline-math commits — across every store this week. | **applied** — new §5.8 (tuning section). |
| F6 | A persistent **open-questions / findings register**, distinct from durable context (§5.1). | `notes.md` at the repo root; analysis.md structured as hypothesis → outcome → delta, with O2/O5 retired on closure. | **deferred** — to fold into the self-referential-example expansion (author to lead); demonstrated live by *this* file. |
| F7 | Encode recurring conventions as **auto-loaded AI skills** so the fixes stick without re-prompting. | `.claude/skills`: manuscript-context, document-metadata-stamping, convert-paper-to-markdown. | **applied** — §5.8 close. |
| F8 | "Figures mirrored to a bucket" vs. the skill's link-only rule; reconcile in-repo vs. CDN for public stores. | Skill: "link to the CDN, don't commit image files"; yet this paper commits `figures/` in-repo (R2 path is optional per §3). | **applied** — §2 figures paragraph + Figure 2 caption. |
| F9 | §2 and §3 overstate GitHub rendering as seamless. | Same evidence as F5. | **applied** — softened, with forward-references to §5.8. |
| F10 | Stale metadata block (v2 / 2026-07-12). | Metadata block predates this revision. | **applied** — bumped to v3. |
| F11 | Reference [5] lacks a stable URL. | References list; [5] cites *Tech Times* (28 June 2026) with no link. | **open** — needs a verifiable URL; deliberately **not** fabricated, per the paper's own citation-verification rule (§5.3). Author or a web search to supply. |
| F12 | Second worked example (the multi-doc program) and a `context.md` for this paper. | — | **deferred** — author will provide; this register is the intended input for the self-referential-example expansion. |

## Notes

**Applied in v3 of the paper.** F1–F5, F7–F10: the dead-URL fix (§4), the datasets correction (§2, §5.6), the multi-document-program subsection (§5.5), the tool-chain tuning subsection (§5.8, absorbing the GitHub-KaTeX rules, the shell gotcha, and conventions-as-skills), the figure-hosting reconciliation (§2, Figure 2), the softened rendering claims (§2, §3), and the metadata bump.

**Deferred / open.** F6 (findings-register practice) and F12 (second worked example + this paper's own `context.md`) are held for the self-referential-example pass the author will lead — this file is meant to be that pass's raw material. F11 (reference [5] URL) is open pending a verifiable link; it is left unfixed rather than filled with a plausible-but-unchecked URL.
