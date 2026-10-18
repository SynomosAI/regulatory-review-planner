# regulatory-review-planner

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE.md)
![Skill](https://img.shields.io/badge/type-Agent%20Skill-blue.svg)

> 中文版说明见 [README.md](README.md)

An Agent Skill for model-planned compliance review of **Chinese policy / regulation / internal-rule drafts** in WorkBuddy. It plans the review scope from the document type and user goal, calls authorized pkulaw (法宝) MCPs to verify key facts, and outputs a structured review memo with matched original text, compliance judgment, issue notes, legal basis, source tags, and revision suggestions.

## Features

- Planned review scope (not mechanical checklist run).
- Mandatory minimum set: completeness of rule elements, legal basis, authority limits, internal consistency, operability, language.
- Triggered special reviews: personal information protection, fair competition, labor rights, name/recency, parent-rule conflicts.
- MCP verification with source tags; unverifiable items marked `[待核验]`.

## Quick Start

```bash
git clone --depth 1 https://github.com/SynomosAI/regulatory-review-planner.git
cd regulatory-review-planner
# cp -r . ~/.workbuddy/skills/regulatory-review-planner/
```

```bash
node scripts/split_articles.mjs your_draft.txt
```

## References

- `references/review-taxonomy.md` — review layers and items
- `references/tool-integration-policy.md` — MCP policy and fallback
- `references/legal-source-policy.md` — source tagging
- `references/employment-review-precision.md` — labor-rights precision rules

## License

MIT; see [`LICENSE.md`](LICENSE.md). Rights notice in SKILL.md (© 2026 注册老炮@MedXpert, MIT) preserved verbatim.

## Security

Report issues privately per [`SECURITY.md`](SECURITY.md). Do not commit real drafts or entity data back to this repo.

## Disclaimer

Theoretical stance and tooling exploration; not a claim of certification, commercial delivery, or service to any customer. Review output is advisory; entity facts require human verification.
