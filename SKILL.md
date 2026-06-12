---
name: babs-audits-skills
description: Reusable smart-contract audit and triage workflows. Use when the user invokes `/instruction-01, /instruction-02-attack-surface, /instruction-02-invariant, /instruction-03-adversarial, /instruction-03-poc, / instruction-04-fuzzing, /instruction-05-cantina, /instruction-05-sherlock, /instruction-06-duplicates, /instruction-07-triage or asks to run a Babs audit instruction for architecture mapping, invariant hunting, attack-surface bug hunting, adversarial verification, PoC writing, fuzzing, report formatting, duplicate triage, or finding triage.
---

# Babs Audits Skills

Follow the requested instruction exactly. Apply it to the current repository or the most recent finding if no target is specified.

## Global Rules

- Search the local repository first. Never assume function names, file names, or architecture.
- Stay within in-scope files only.
- Be harsh. Reject weak, speculative, or low-impact claims.
- State broken invariants explicitly for every bug discussion.
- Downgrade severity one tier per precondition the attacker does not control.
- Prefer concise, evidence-driven reasoning. No generic security advice.

## Trigger Routing

- `/instruction-01` or `run instruction-01` read references/instruction-01.md
- `/instruction-02-attack-surface` or `run instruction-02-attack-surface` read references/instruction-02-attack-surface.md
- `/instruction-02-invariant` or `run instruction-02-invariant` read references/instruction-02-invarian
- `/instruction-03-adversarial` or `run instruction-03-adversarial` read references/instruction-03-adversarial.md
- `/instruction-03-poc` or `run instruction-03-poc` read references/instruction-03-poc.md
- `/instruction-04-fuzzing` or `run instruction-04-fuzzing` read references/instruction-04-fuzzing.md
- `/instruction-05-cantina` or `run instruction-05-cantina` read references/instruction-05-cantina.md
- `/instruction-05-sherlock` or `run instruction-05-sherlock` read references/instruction-05-sherlock.md
- `/instruction-06-duplicates` or `run instruction-06-duplicates` read references/instruction-06-duplicates.md
- `/instruction-07-triage` or `run instruction-07-triage` read references/instruction-07-triage.md

## Usage
After selecting the matching reference file, follow it exactly. If a reference asks for missing inputs that cannot be inferred safely, ask one concise clarifying question. Otherwise, proceed using the current repository and any explicit scope files provided by the user.

## Output Discipline
- Preserve the output format required by the selected instruction.
- Do not mix unrelated instruction modes unless the user explicitly requests multiple instructions.
- For audit claims, separate confirmed bugs from investigation targets.
- For report formatting, do not invent PoC numbers or USD impact; derive them from the finding or state the estimate basis clearly.