# babs-audits-skills

Reusable Codex skill for smart-contract audit workflows, finding verification, PoC writing, fuzzing, report formatting, duplicate grouping, and bounty triage.

## Install

Clone this repository into your Codex skills directory:

    ~/.codex/skills/babs-audits-skills/

## Triggers

- /INSTRUCTION-01: Architecture, invariants, and attack surfaces
- /INSTRUCTION-02 or /INSTRUCTION-02-T2: Attack-surface bug hunt
- /INSTRUCTION-02-T1: Invariant break hunt
- /INSTRUCTION-03: Adversarial verification
- /INSTRUCTION-03-T1: Foundry PoC writing
- /INSTRUCTION-04: Foundry fuzzing test writer
- /INSTRUCTION-05 Cantina: Cantina report formatting
- /INSTRUCTION-05 Sherlock: Sherlock report formatting
- /INSTRUCTION-06: Duplicate finding triage
- /INSTRUCTION-07: Bounty finding triage

## Structure

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
