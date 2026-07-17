# AI-Research-Workflow — Review & Revision Register

**Document Metadata**

| | |
|---|---|
| **Store** | living-papers |
| **Version** | v2 |
| **Last updated** | 2026-07-17 |
| **Branch** | `main` |
| **Revision note** | v2: publication-prep pass — extended the evidence window to 2026-07-17 (a second review of practice against the paper, now at v3→v4), verified that F1–F5/F7–F10 are genuinely in v3, closed F6 (self-referential pointer added in §5.5) and F11 (Tech Times URL found by live web search and verified), and added F13–F19 from the additional three days of observed practice (PDF export of digests, committed scratch documents, AI-drawn digest figures, program maintenance sweeps, solo-practice limitation, and two clarity fixes). F12 remains open for the author. |

---

**Scope.** Standing review record for [ai-research-workflow.md](ai-research-workflow.md). F1–F12 were surfaced by reconstructing one week of the author's AI-assisted research activity (2026-07-07 → 2026-07-14) from git across research-workbench, public-portfolio, literature-vault, living-papers, and private-notebook, and comparing observed practice against the paper's v2 description; F13–F19 extend the same method through 2026-07-17 against v3. Findings carry a disposition: **applied** (folded into the paper), **deferred** (agreed, scheduled for a later pass), or **open** (needs author input). This file doubles as the worked example for the open-findings-register practice at F6 — a register kept alongside the manuscript it tracks.

**Evidence base.** The week's commits and artifacts: the multi-document `cfm-dark-sector-program/` (analysis.md → v22, plus background.md, derivations.md, mond-review.md, reference digests, a `data/` folder, and `t4-*.pl` fit scripts); literature-vault acquisitions including the SPARC / RAR / BTFR data tables and Li et al. 2018 Table A.1 (175 galaxies); public-portfolio's dissertation and three journal papers; and the cross-store GitHub-KaTeX rendering fixes now codified in the convert-paper-to-markdown skill (research-workbench `.claude/skills`, §9).

## Findings

| ID | Finding | Evidence | Disposition |
|---|---|---|---|
| F1 | The unit of work is often a multi-document *program*, not a single manuscript + `context.md`. | `cfm-dark-sector-program/` holds an analysis, a background doc, a derivations doc, reference digests, a context manifest, `data/`, and `figures/`. | **applied** — new §5.5 (foundational paper + dependents). |
| F2 | literature-vault also stores acquired **datasets** for numerical validation, not only reference prose. | SPARC tables; Li 2018 Table A.1; McGaugh 2016 RAR; Lelli 2016 BTFR — acquired and fit against. | **applied** — §2 literature-vault bullet + §5.6. |
| F3 | AI-written analysis/validation **code** is a first-class artifact, co-located with the manuscript. | `t4-fit-pergalaxy.pl`, `t4-calibration.pl`, `t4-fit-robustness.pl`, etc. in the program folder; outcomes flow back into analysis.md. | **applied** — §5.5. |
| F4 | Dead raw URLs: §4 fetches the paper from research-workbench, but the file was moved to living-papers. | `git ls-files`: no longer tracked in research-workbench; lives in living-papers. | **applied** — §4 URLs point to living-papers. |
| F5 | GitHub-KaTeX math rendering needs a documented authoring discipline; the paper implied it "just works." | Brace-stripping fix across 14 vault conversions; `\operatorname`→`\mathrm`; dissertation split for size; backtick inline-math commits — across every store this week. | **applied** — new §5.8 (tuning section). |
| F6 | A persistent **open-questions / findings register**, distinct from durable context (§5.1). | `notes.md` at the repo root; analysis.md structured as hypothesis → outcome → delta, with O2/O5 retired on closure. | **applied** (v4) — §5.5's register bullet now points at *this* file as a live instance; the fuller self-referential expansion stays with F12. |
| F7 | Encode recurring conventions as **auto-loaded AI skills** so the fixes stick without re-prompting. | `.claude/skills`: manuscript-context, document-metadata-stamping, convert-paper-to-markdown. | **applied** — §5.8 close. |
| F8 | "Figures mirrored to a bucket" vs. the skill's link-only rule; reconcile in-repo vs. CDN for public stores. | Skill: "link to the CDN, don't commit image files"; yet this paper commits `figures/` in-repo (R2 path is optional per §3). | **applied** — §2 figures paragraph + Figure 2 caption. |
| F9 | §2 and §3 overstate GitHub rendering as seamless. | Same evidence as F5. | **applied** — softened, with forward-references to §5.8. |
| F10 | Stale metadata block (v2 / 2026-07-12). | Metadata block predates this revision. | **applied** — bumped to v3. |
| F11 | Reference [5] lacks a stable URL. | References list; [5] cites *Tech Times* (28 June 2026) with no link. | **applied** (v4) — URL located by live web search on 2026-07-17 and verified to match the cited title and date, per the §5.3 citation-verification rule. |
| F12 | Second worked example (the multi-doc program) and a `context.md` for this paper. | — | **open** — author to lead; this register is the intended input for the self-referential-example expansion. |
| F13 | Digests are exported to **PDF** for reading away from the editor — a derived render, regenerated from source, produced by a repo-local skill. | `md-to-pdf` skill added to research-workbench `.claude/skills`; `bcf-theory-digest.pdf`, `mond-digest.pdf`, `soc-avalanche-digest.pdf` committed alongside their `.md` sources. | **applied** (v4) — §5.5 digests bullet. |
| F14 | A middle context form between durable and ephemeral (§5.1): the **committed scratch document**, folded in and retired once its decision lands. | `scratch-publication-prep.md` created (cd89e92) then folded and deleted (ef37564); `analysis-ish.md` folded into 02-background and retired (2e7ebf5); `scratch-marginalized-adoption.md`, `scratch-time-domain-g.md`. | **applied** (v4) — §5.1 new paragraph. |
| F15 | Digest figures are **original AI-drawn vector graphics**, since a digest cannot redistribute the source's figures. | `soc-avalanche-digest` committed with 6 original SVG figures; `mond-digest` with original SVGs (rotation curve, RAR). | **applied** (v4) — §5.5 digests bullet. |
| F16 | A program needs **cross-document maintenance sweeps**: notation renames rippling through dependents/digests/scripts, and superseded documents folded into successors and retired. | `R_g → Gamma_g` rename ripple across 03-model, preliminaries, bcf-theory-digest (fc11760); `mond-review.md` + `famaey2012-digest.md` folded into `mond-digest.md` (bd465dc). | **applied** (v4) — §5.5 closing paragraph. |
| F17 | The paper's multi-author machinery (§5.4 review, collaborator sharing, outside PRs) is **designed but not yet exercised** — all practice to date is one researcher + AI. | No issues, PRs, or second collaborator in any store's history; every commit is the author's. | **applied** (v4) — stated plainly in §6 Limitations. |
| F18 | §6 Limitations referenced a "figure-naming convention (§2, §5)" the paper no longer describes — a dangling remnant of the F8 reconciliation. | v3 text vs. §2/§3/§5, which define no `<figure-id>` convention. | **applied** (v4) — rewritten as the publish-time figure-reference rewrite limitation. |
| F19 | Clarity fixes: the §4 credentials note interrupted the numbered list between steps 5 and 6; §5.8 cited "the conversion pipeline (§5.5–5.7)" (conversion is §5.6–§5.7). | v3 source. | **applied** (v4). |

## Notes

**Applied in v3 of the paper.** F1–F5, F7–F10: the dead-URL fix (§4), the datasets correction (§2, §5.6), the multi-document-program subsection (§5.5), the tool-chain tuning subsection (§5.8, absorbing the GitHub-KaTeX rules, the shell gotcha, and conventions-as-skills), the figure-hosting reconciliation (§2, Figure 2), the softened rendering claims (§2, §3), and the metadata bump. All verified present in v3 during the 2026-07-17 pass.

**Applied in v4 of the paper.** F6, F11, F13–F19: the scratch-document middle tier (§5.1), the digest figure/PDF and register self-reference additions plus the maintenance-sweep paragraph (§5.5), the solo-practice and figure-rewrite limitations (§6), the reference [5] URL, and the §4/§5.8 clarity fixes.

**Open.** F12 (second worked example built from the multi-document program, plus this paper's own `context.md`) is the one remaining item, held for the author-led self-referential-example pass — this register is meant to be that pass's raw material. Two judgment calls from the v4 pass that the author may want to revisit: the scratch-document practice was added as a *middle form* inside §5.1's two-tier scheme rather than restructuring the scheme into three tiers, and the PDF-export practice was kept to one clause in §5.5 rather than given its own subsection.
