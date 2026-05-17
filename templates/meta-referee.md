=== CrossCheck — meta-referee ===

Inline rules (paste into the prompt, or link to AGENTS.md if the model can fetch URLs):
https://github.com/AtomBuilders/crosscheck/blob/main/AGENTS.md

CLAIM:
{{CLAIM}}

The blocks below contain the full primary-validator paste and the full referee report.

--- Primary validator full paste ---

{{PRIMARY_VALIDATOR_PASTE}}

--- Referee full report ---

{{REFEREE_REPORT}}

Validate against **primary** sources only. Keep the response **structured and concise** (no long essays). Layout:

**A)** Key claims to verify — short bullets (each claim + finding + **full https:// URL** to the primary document).
**B)** Where the referee misread the validator or primaries — ≤80 words.
**C)** One line, one token only: `referee_sound` | `referee_flawed` | `tie_or_uncertain`.
**D)** Two scores **1–5**: (i) how well the referee’s read matches authoritative sources on the claim; (ii) how fairly they summarized the validator.
**E)** Closing verdict — **max 3 sentences**; include at least **one https:// URL** to the definitive primary you want the human to open first.
