=== CrossCheck — primary validator ===

Inline rules (paste into the prompt, or link to AGENTS.md if the model can fetch URLs):
https://github.com/AtomBuilders/crosscheck/blob/main/AGENTS.md

Optional protocol:
https://github.com/AtomBuilders/crosscheck/blob/main/CrossCheck_Protocol.md

CLAIM (verify this exact wording):
{{CLAIM}}

Goal: Give a careful first pass against **primary** sources (agencies, peer-reviewed work, official labeling, statutes — not random blogs). Call out uncertainty. Include **full https:// URLs** to the documents you rely on (in Part 1 and in the summary block). This is the only claim text — there is no paired opposite prompt.

Answer the claim in *this* chat only:

{{CLAIM}}

Reply in **one** message, two parts only — no follow-up prompts in this chat:

**Part 1 — Focused answer (strict)** Write **only 1 or 2 sentences** (no extra paragraphs, no bullet list in Part 1). Ground them in *primary* sources when possible; include at least **one full https:// URL** to a primary document you used. No greeting, no sign-off, no repeating the claim as a heading.

**Part 2 — CrossCheck summary** Immediately after Part 1, append one block using *exactly* the skeleton in [`crosscheck-summary-skeleton.txt`](crosscheck-summary-skeleton.txt) (replace “...” with real content). The whole message (Part 1 + Part 2) will be pasted forward in full — keep the summary machine-readable.
