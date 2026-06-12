---
name: babs-audits-skills
description: Reusable smart-contract audit and triage workflows. Use when the user invokes `/instruction-01`, `/instruction-02-attack-surface`, `/instruction-02-invariant`, `/instruction-03-adversarial`, `/instruction-03-poc`, `/ instruction-04-fuzzing`, `/instruction-05-cantina`, `/instruction-05-sherlock`, `/instruction-06-duplicates`, `/instruction-07-triage` or asks to run a Babs audit instruction for architecture mapping, invariant hunting, attack-surface bug hunting, adversarial verification, PoC writing, fuzzing, report formatting, duplicate triage, or finding triage.
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

- `/INSTRUCTION-01` or `Run INSTRUCTION-01`: read `references/instruction-01.md`.
- `/INSTRUCTION-02`, `/INSTRUCTION-02-T2`, or their `Run` equivalents: read `references/instruction-02-attack-surface.md`.
- `/INSTRUCTION-02-T1` or `Run INSTRUCTION-02-T1`: read `references/instruction-02-invariant.md`.
- `/INSTRUCTION-03` or `Run INSTRUCTION-03`: read `references/instruction-03-adversarial.md`.
- `/INSTRUCTION-03-T1` or `Run INSTRUCTION-03-T1`: read `references/instruction-03-poc.md`.
- `/INSTRUCTION-04` or `Run INSTRUCTION-04`: read `references/instruction-04-fuzzing.md`.
- `/INSTRUCTION-05 TASK-01`, `/INSTRUCTION-05 Cantina`, or `Run INSTRUCTION-05 Cantina`: read `references/instruction-05-cantina.md`.
- `/INSTRUCTION-05 TASK-02`, `/INSTRUCTION-05 Sherlock`, or `Run INSTRUCTION-05 Sherlock`: read `references/instruction-05-sherlock.md`.
- `/INSTRUCTION-06` or `Run INSTRUCTION-06`: read `references/instruction-06-duplicates.md`.
- `/INSTRUCTION-07` or `Run INSTRUCTION-07`: read `references/instruction-07-triage.md`.

## Usage

After selecting the matching reference file, follow it exactly. If a reference asks for missing inputs that cannot be inferred safely, ask one concise clarifying question. Otherwise, proceed using the current repository and any explicit scope files provided by the user.

## Output Discipline

- Preserve the output format required by the selected instruction.
- Do not mix unrelated instruction modes unless the user explicitly requests multiple instructions.
- For audit claims, separate confirmed bugs from investigation targets.
- For report formatting, do not invent PoC numbers or USD impact; derive them from the finding or state the estimate basis clearly.