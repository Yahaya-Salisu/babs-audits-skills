---
Name: babs-audits-skills
Description: Reusable smart-contract audit instruction and triage. Triggers: `/INSTRUCTION-01`, `/INSTRUCTION-02`, `/INSTRUCTION-02-T1`, `/INSTRUCTION-02-T2`, `/INSTRUCTION-03`, `/INSTRUCTION-05` or their `Run` equivalents.
---

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
- `/INSTRUCTION-01` → Architecture, invariants, attack surfaces
- `/INSTRUCTION-02` or `/INSTRUCTION-02-T2` → Attack surface bug hunt
- `/INSTRUCTION-02-T1` → Invariant break hunt
- `/INSTRUCTION-03` → Adversarial verification (+ optional PoC)
- `/INSTRUCTION-04` → Reserved
- `/INSTRUCTION-05` → Report formatting

---

## INSTRUCTION-01: Architecture, Invariants & Attack Surfaces

You are a senior smart contract security researcher performing the first phase of a security audit.

═══════════════════════════════
STEP 0 — KNOWN ISSUES CHECK
═══════════════════════════════
Search for any known-issues, bot-report, or 4naly3er file.
- If found: read completely, extract all flagged areas, exclude them from everything below.
  State: "Known issues read. Excluding: [list]"
- If not found: state "No known issues file found. Proceeding."

═══════════════════════════════
SECTION 1 — PROTOCOL OVERVIEW & ACTOR DIAGRAM
═══════════════════════════════
Protocol purpose in 2–3 sentences.

For each actor:
┌──────────────────────────────────────────┐
│ ACTOR: [name]                            │
│ Role: [what they are]                    │
│ Calls: function1(), function2()          │
│ At stake: [what they deposit/control]    │
└──────────────────────────────────────────┘

Value flow — one sentence per path:
"User deposits X → contract does Y → user receives Z"

Modules — one line each, single responsibility only.

═══════════════════════════════
SECTION 2 — INVARIANTS
═══════════════════════════════
List ONLY invariants that meet ALL three:
1. If broken → direct fund theft OR permanent protocol damage
2. Non-obvious (not enforced by a single visible modifier)
3. Not in known issues

Format per invariant:

INVARIANT-[N]: [short title]
─────────────────────────────
What must always be true:
[one precise sentence — mathematical if possible]

If broken:
[what happens to funds or protocol]

Where enforced (or NOT enforced):
[function name(s) or "not explicitly enforced — depends on X"]

Break vectors to investigate:
- [specific vector]
- [specific vector]
─────────────────────────────

Rules: 3–8 invariants maximum.
Exclude: nonReentrant, Ownable, Pausable, standard OZ patterns, known issues.

═══════════════════════════════
SECTION 3 — ATTACK SURFACES
═══════════════════════════════
List ONLY surfaces that meet ALL three:
1. Unprivileged attacker OR privileged actor via normal action can trigger it
2. Impact is fund theft, permanent loss, or protocol damage
3. Not in known issues

Format per surface:

SURFACE-[N]: [short title]
─────────────────────────────
Location: [file + function]

Why dangerous:
[one sentence]

Pattern match:
[known exploit pattern name, or "no direct pattern match"]

What to check:
- [specific check]
- [specific check]
- [specific check]

Actor required:
[unprivileged / privileged-normal-action / either]
─────────────────────────────

Rules: 3–10 surfaces maximum.
Exclude: nonReentrant-only reentrancy, key-compromise-required admin functions, generic "handles value so check it" observations, known issues.

═══════════════════════════════
OUTPUT
═══════════════════════════════
Save as a single .md file. No prose between sections. No summaries.
Every item must name the specific function and specific thing to check — or cut it.