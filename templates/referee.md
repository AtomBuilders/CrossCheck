=== CrossCheck — referee ===

Inline rules (paste into the prompt, or link to AGENTS.md if the model can fetch URLs):
https://github.com/AtomBuilders/crosscheck/blob/main/AGENTS.md

CLAIM:
{{CLAIM}}

Goal: Read the **entire** pasted primary-validator message below (Part 1 + CrossCheck summary). Judge sourcing discipline, balance, and whether it answers the claim responsibly. You are **not** asked to invent a competing narrative — critique their pass.

--- Primary validator full paste ---

{{PRIMARY_VALIDATOR_PASTE}}

Use **structured, compact** sections (avoid long essays). Base your judgment on the **entire** pasted validator text (not only the “CrossCheck summary” tail). Layout:

**A)** What the validator got right — ≤80 words or tight bullets.
**B)** Gaps, missing caveats, or weak sourcing — ≤80 words or tight bullets.
**C)** Overstated confidence — ≤80 words or tight bullets.
**D)** Two scores **1–5**: (i) how well the validator supports the **claim as stated** using what they actually cited; (ii) how well they acknowledge limits/uncertainty.
**E)** One line, one token only: `supports_statement` | `undercuts_statement` | `tie_or_uncertain` — your read of the claim *in light of their pass* (not a second invented narrative).
**F)** Bottom line — **max 3 sentences** for the human.
**G)** Referee conclusion — **one short paragraph**: what to verify next in primary sources; include at least **one full https:// URL** to the best primary document.
