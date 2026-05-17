# CrossCheck Protocol (expanded guide)

This document **complements** [`README.md`](README.md). The README is the short overview; this file is the **long-form protocol**: how to think about claims, how to run the three linked passes well, quick hallucination checks, and a printable-style checklist.

**Educational use only.** CrossCheck is not medical, financial, or legal advice. Read [`AGREEMENTS.md`](AGREEMENTS.md) and [`LICENSE`](LICENSE).

---

## How this relates to the README and the tools

| Resource | Role |
|----------|------|
| `README.md` | Project introduction, step summary, tool table, references, disclaimer summary |
| `CrossCheck_Protocol.md` | This file: triage, depth, examples, tests, checklist |
| [`templates/`](templates/) | Copy-paste prompts for validator, referee, and meta-referee (no site required) |
| [Interactive site](https://atom.builders/crosscheck/) | Guided workflow: single claim field, lineup picker, generated prompts, paste handoffs |
| `AGENTS.md` | Guidance for AI models in the three passes |

---

## When to spend ten minutes on CrossCheck (claim triage)

Use CrossCheck when a claim is **actionable** or **spreadable**: you might share it, spend money on it, change health behavior, or vote based on it. Skip or skim when the stakes are trivial and wrongness would not matter.

**Higher stakes** (health, safety, money, law): treat CrossCheck as **literacy practice** only. Decisions still belong with qualified professionals and official sources.

**Lower stakes** (idle curiosity): you can still run the workflow to build the habit of reading laterally.

---

## Define your claim (one field)

Whether you use the [interactive site](https://atom.builders/crosscheck/) or the [`templates/`](templates/), you work from **one** claim — a question, headline, rumor, quote, transcript snippet, or anything else. There is **no** paired “opposite angle” or second claim field; every prompt embeds this **same** wording.

- **Your claim:** Use the exact wording you want verified.
- **Worked example:** *“Are Legos generally safe for children under 5?”* — useful for a first practice run.
- **Offline / manual:** Fill `{{CLAIM}}` in the template files (see [`templates/README.md`](templates/README.md)).

---

## The three linked passes (expanded)

### Pass 1 — Primary validator (answer + summary in one reply)

Open a **new chat** in your first AI. Paste the [primary-validator](templates/primary-validator.md) prompt (or use the site’s Step 1 prompt): a **short** evidence-based answer grounded in **primary** sources (tight word caps) **and**, in the same message, a small **CrossCheck summary** block. Read the whole reply. Note every source name, URL, or "study" it cites — you will verify these later, not trust the model’s paraphrase of them.

### Pass 2 — Paste the validator’s full reply

Keep the validator’s **entire** message (Part 1 plus the CrossCheck summary section). You will embed it in the referee prompt.

### Pass 3 — Referee (critique the validator)

Open a **separate new chat** in your second AI. The [referee](templates/referee.md) prompt includes the **same single claim** and your pasted validator output. The referee judges sourcing discipline and balance — **not** a second competing narrative or “other side” of the claim.

### Pass 4 — Meta-referee (check the referee)

Open a **third new chat** in your third AI. The [meta-referee](templates/meta-referee.md) prompt includes the claim, the validator paste, and the referee report. This pass stress-tests the referee against primaries again.

---

## Worked mental model (Lego / product safety)

The default example claim is toy safety. The pattern generalizes:

1. **Claim (one field):** *“Are Legos generally safe for children under 5?”* — or your own wording.  
2. **Validator:** one-shot answer + CrossCheck summary against primaries for **that** claim only.  
3. **Referee:** critiques that validator pass (same claim embedded in the prompt).  
4. **Meta-referee:** checks the referee against **CPSC**, standards documents, or the manufacturer's own safety communications — not blog posts alone.

Swap in your domain's **real** primary authorities (FDA, CDC, IRS, court dockets, etc.) using the database list in the README.

---

## Quick hallucination and overconfidence tests

After any AI answer, ask yourself:

1. **Citation check:** Did it give a specific URL or DOI? If you cannot find the source in 60 seconds of searching, treat the citation as **unverified**.  
2. **Certainty check:** Does the tone exceed the evidence (words like "proven," "always," "never" without scope)?  
3. **Layer check:** Did the referee fairly represent what the validator actually wrote — including caveats in the middle of the paste?  
4. **Date check:** Is the claim about a fast-moving topic (prices, laws, outbreaks) without a date?

If two or more fail, slow down and lean harder on primary reading yourself.

---

## Pocket checklist (copy or print)

- [ ] I defined **one claim** (or deliberately used the Lego example for practice).  
- [ ] I used **separate chats** for validator, referee, and meta-referee.  
- [ ] I pasted **full** messages (not only summary tails) forward at each handoff.  
- [ ] I have a **referee** report in writing.  
- [ ] I ran (or plan to run) the **meta-referee** pass against primaries.  
- [ ] I **clicked** at least one primary link and read the relevant section myself.  
- [ ] If the topic is medical, financial, or legal, I know this workflow is **not** a substitute for a professional.

---

## After CrossCheck

- Keep your own notes or exports if you want a record.  
- For high-stakes topics, repeat CrossCheck later or ask a different human to review your sources — **double validation is allowed and encouraged** where the stakes justify it.

---

## Further reading

See the **Resources & References** section in [`README.md`](README.md) for guides, research papers, and primary-source databases.
