# babs-audits-skills
Smart Contract Audits and Triage Skills


Name: babs-audits-skills

Description: Reusable smart-contract audit instruction and triage.

# babs-audits-skills

Follow the requested instruction exactly. Apply it to the current repository or the most recent finding if no target is specified.

## Global Rules
- Search the local repository first. Never assume function names, file names, or architecture.
- In-scope files only.
- Be harsh. Reject weak, speculative, or low-impact claims.
- State broken invariants explicitly for every bug discussion.
- Downgrade severity one tier per precondition the attacker does not control.
- Prefer concise, evidence-driven reasoning. No generic security advice.

## Trigger Routing
- `/instruction-01.md
- `/instruction-02-attack-surface`
- `/instruction-02-invariant`
- `/instruction-03-adversarial`
- `/instruction-03-poc`
- `/instruction-04-fuzzing`
- `/instruction-05-cantina`
- `/instruction-05-sherlock`
- `/instruction-06-duplicates`
- `/instruction-07-triage`

- `/INSTRUCTION-01` → Architecture, invariants, attack surfaces
- `/INSTRUCTION-02` or `/INSTRUCTION-02-T2` → Attack surface bug hunt
- `/INSTRUCTION-02-T1` → Invariant break hunt
- `/INSTRUCTION-03` → Adversarial verification (+ optional PoC)
- `/INSTRUCTION-04` → Reserved
- `/INSTRUCTION-05` → Report formatting

```md
babs-audits-skills/
  SKILL.md
  agents/
    openai.yaml
  references/
    instruction-01.md
    instruction-02-attack-surface.md
    instruction-02-invariant.md
    instruction-03-adversarial.md
    instruction-03-poc.md
    instruction-04-fuzzing.md
    instruction-05-cantina.md
    instruction-05-sherlock.md
    instruction-06-duplicates.md
    instruction-07-triage.md
```