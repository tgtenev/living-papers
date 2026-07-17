# Context Manifest — ai-research-workflow

**Document Metadata**

| | |
|---|---|
| **Store** | living-papers |
| **Version** | v1 |
| **Last updated** | 2026-07-17 |
| **Branch** | `main` |
| **Revision note** | v1: opened the manifest — durable context for [ai-research-workflow.md](ai-research-workflow.md), per its own §5.1. Lists the review register, the AI instruction files that codify the paper's conventions, and example literature-vault entries evidencing the conversion and dataset practices. |

---

**Scope.** Durable context for [ai-research-workflow.md](ai-research-workflow.md) (§5.1): what an AI collaborator should load at the start of a session on this paper, beyond the paper itself. Each entry carries a one-line note on why it matters. This file is itself the paper's worked instance of the practice it describes.

## Companion documents (this repository, public)

- [analysis.md](analysis.md) — the paper's review-and-revision register: findings from reconstructing the author's actual practice from git, each with evidence and a disposition. **Read this first in any revision session** — open findings (currently F12, the forthcoming program worked example) are the standing to-do list, and closed findings explain why the text reads as it does.
- [CONTRIBUTING.md](../CONTRIBUTING.md) and [LICENSE](../LICENSE) — the outside-contribution and licensing terms §4 says a living-papers store needs; this repo's own instances.

## AI instruction files (research-workbench, private — authenticated fetch per §2)

The conventions the paper describes are enforced by skills in the author's private research-workbench repo, at `.claude/skills/`. They are the ground truth for what the practice currently is; when a skill and the paper drift apart, that drift is a finding for the register.

- `manuscript-context/SKILL.md` — the context-manifest check (§5.1) that requires reading this very file.
- `document-metadata-stamping/SKILL.md` — the metadata block schema per store (§5.2), including the versioning and no-commit-hash rules.
- `convert-paper-to-markdown/SKILL.md` — the conversion pipeline (§5.6–§5.7) plus the accumulated GitHub-KaTeX rendering rules (§5.8).
- `md-to-pdf/SKILL.md` — the derived-PDF export path for digests (§5.5), including the machine-specific workarounds §5.8 calls shell/tool-chain tuning.

## Example literature-vault entries (private — authenticated fetch per §2)

Illustrative instances of the practices the paper claims, cited in the register's evidence base. Not context to load wholesale — fetch one only when a session needs a concrete example of the practice it evidences.

- `literature-vault/famaey2012-mond-phenomenology.md` — a large, math-heavy third-party review converted whole (§5.6): multi-hundred-entry reference list, LaTeX math authored to GitHub's renderer.
- `literature-vault/li2018-rar-individual-galaxies.md` — a published **dataset** acquired as Markdown (§2, §5.6): a 175-galaxy results table converted so analysis code can fit against real numbers.
- `literature-vault/burton1951-crystal-growth.md` — a scanned-era paper with all 29 figures extracted as local image files (§5.6's figure-extraction requirement).

## External references

The paper's own reference list ([1]–[7] in [ai-research-workflow.md](ai-research-workflow.md)) is the curated set of external sources; it is not duplicated here. Every entry was verified against the actual source per §5.3 before inclusion.
