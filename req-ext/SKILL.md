---
name: req-ext
description: |
  Extracts well-formed requirements from unstructured text per ISO/IEC/IEEE 29148:2011, Section 5.2.4 (Figure 1). Saves results to `req.md`. Output is in Russian; table column headers remain in English. Use when transforming raw text into structured, verifiable requirements.
---

# Purpose

Transform raw text into structured requirements stored in `req.md`. Requirement text and notes are in Russian. Column headers remain in English: `#`, `Condition`, `Subject`, `Action`, `Object`, `Constraint`.

# How It Works

1. **Input**: Unstructured text describing needs, constraints, or capabilities.
2. **Parse**: Split into sentences/clauses expressing requirements.
3. **Extract**: Identify or infer `Condition`, `Subject`, `Action`, `Object`, and `Constraint`. Mark missing parts as `(нет)` or `(не указано)`.
4. **Table**: Number requirements and present them in a Markdown table.
5. **Persistence**: Write to `req.md`, overwriting existing content. Follow the template in `assets/req-template.md`.
6. **Notes**: Add a rationale section in Russian for ambiguous cases.

# Instructions

When the user provides text:

1. Parse and extract requirements as described above.
2. Display the table in the conversation and write it to `req.md`.
3. Add notes explaining inferences, splits, or ambiguities.
4. If information is missing, flag the requirement as "Incomplete" and suggest what is needed.
<!-- 5. Keep Russian verbs in their original conjugated form (e.g., «создаёт», not «создавать») in the `Action` column. Do not normalise to infinitive unless the text explicitly uses an infinitive or a modal verb.
6. Object column: include both direct and indirect objects; highlight the direct one in bold.
7. Constraint column: fill only with explicit constraints and non‑functional requirements -->

# What the Skill Does NOT Do

- Invent requirements not present in the source.
- Perform validation or prioritization unless instructed.
- Generate design solutions.

# Additional Guidance

- Prefer active voice; avoid negative statements.
- Keep each requirement singular (one action per requirement).
- Flag vague terms and suggest measurable alternatives.
- Design constraints are extracted but noted as such.

# Contact

Refer to ISO/IEC/IEEE 29148 or the requirements engineering team.
