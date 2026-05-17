# CrossCheck prompt templates

Plain-text prompts you can copy into any AI chat **without** the interactive site. Replace placeholders before sending.

| Placeholder | Used in |
|-------------|---------|
| `{{CLAIM}}` | All three passes — the exact wording you want verified (question, headline, rumor, quote, etc.) |
| `{{PRIMARY_VALIDATOR_PASTE}}` | Referee, meta-referee — the validator’s **full** reply (Part 1 + CrossCheck summary) |
| `{{REFEREE_REPORT}}` | Meta-referee — the referee’s **full** structured report |
| `{{PRIMARY_VALIDATOR_TOOL}}` | Summary skeleton only — name of the AI you used for step 1 (e.g. ChatGPT) |

## Files

| File | Role |
|------|------|
| [`primary-validator.md`](primary-validator.md) | Pass 1 — one-shot answer + CrossCheck summary |
| [`crosscheck-summary-skeleton.txt`](crosscheck-summary-skeleton.txt) | Part 2 skeleton for the validator (append after Part 1) |
| [`referee.md`](referee.md) | Pass 2 — critique the validator |
| [`meta-referee.md`](meta-referee.md) | Pass 3 — stress-test the referee against primaries |
| [`agents-inline.txt`](agents-inline.txt) | Short rules block if the model cannot fetch URLs |

## Order of operations

1. New chat → paste [`primary-validator.md`](primary-validator.md) with your claim filled in.
2. New chat → paste [`referee.md`](referee.md) with claim + full validator reply.
3. New chat → paste [`meta-referee.md`](meta-referee.md) with claim + both pastes.

Use a **different** chat (or provider) for each pass so later steps are not primed by earlier ones.

Built-in example claim (if you want a worked run): *Are Legos generally safe for children under 5?*

See [`CrossCheck_Protocol.md`](../CrossCheck_Protocol.md) for triage, checklist, and literacy notes.
