# CrossCheck Protocol (expanded guide)

**[Try it now](https://atom.builders/crosscheck/)** — open the interactive CrossCheck workflow on Atom Builders.

This document **complements** [`README.md`](README.md). The README is the short overview and repo map; this file is the **long-form protocol**: how to think about claims, how to run the five steps well, quick hallucination checks, and a printable-style checklist.

**Educational use only.** CrossCheck is not medical, financial, or legal advice. Read [`AGREEMENTS.md`](AGREEMENTS.md) and [`LICENSE`](LICENSE).

---

## How this relates to the README and the web page

| Resource | Role |
|----------|------|
| `README.md` | Project introduction, step summary, tool table, references, disclaimer summary |
| `CrossCheck_Protocol.md` | This file: triage, depth, examples, tests, checklist |
| [`atom.builders/crosscheck`](https://atom.builders/crosscheck/) | **Try it now:** hosted interactive prompts, paste workflow, exports |
| `index.html` | Same workflow as a local/static copy (interactive prompts, paste workflow, exports) |
| `AGENTS.md` | Guidance for AI models in referee/validator steps (linked from those prompts) |
| `AGREEMENTS.md` | Binding terms and acceptance (canonical) |

---

## When to spend ten minutes on CrossCheck (claim triage)

Use CrossCheck when a claim is **actionable** or **spreadable**: you might share it, spend money on it, change health behavior, or vote based on it. Skip or skim when the stakes are trivial and wrongness would not matter.

**Higher stakes** (health, safety, money, law): treat CrossCheck as **literacy practice** only. Decisions still belong with qualified professionals and official sources.

**Lower stakes** (idle curiosity): you can still run the workflow to build the habit of reading laterally.

---

## The five steps (expanded)

### Step 1 - First angle (answer + summary in one reply)

Open a **new chat** in your first AI. Paste the Step 1 prompt from `index.html`: it asks for a **short** evidence-based answer (tight word caps) **and**, in the same message, a small **CrossCheck summary** block. Read the whole reply. Note every source name, URL, or "study" it cites — you will verify these later, not trust the model’s paraphrase of them.

### Step 2 - Opposite angle (same pattern)

Open a **separate new chat** in your second AI. Same topic, opposite framing, same one-shot answer + CrossCheck summary format. If the conclusion flips entirely based on wording alone, treat that as a **bias warning**, not as proof either side is right.

### Step 3 - Paste both full replies

Copy each model’s **entire** reply from Steps 1–2 into the matching boxes on `index.html` (answer plus the CrossCheck summary section). No third “summary-only” prompt in those chats — the interactive page bundles these for the referee.

### Step 4 - Referee

A **third** AI compares the two pasted replies without having seen the original chats. The page’s copy prompt asks for **structured, concise** output and an explicit **verdict**: evidence weights (1–5) for the **direct** vs **opposite** angles, which angle is **factually stronger** (`direct` | `opposite` | `tie_or_uncertain`), and a **≤3 sentence** bottom line that answers both angles.

### Step 5 - Primary sources

A **fourth** AI (or the same tool in a new chat) checks the referee's analysis against **primary** documents: agency sites, statutes, peer-reviewed papers, manufacturer pages. The page asks for **short, structured** verification and a clear primary-source lean between the two original angles. **You** still open the links and read them. AI consensus without reading the source is not CrossCheck done.

---

## Worked mental model (Lego / product safety)

The interactive page defaults to a toy-safety style example. The pattern generalizes:

1. Direct question: "Is X generally safe / true?" (one-shot answer + CrossCheck summary)  
2. Opposite angle: "What concerns exist about X?" (same pattern, new chat)  
3. Paste both full replies on the page.  
4. Referee compares.  
5. Validator ties claims to **CPSC**, standards documents, or the manufacturer's own safety communications - not to blog posts alone.

Swap in your domain's **real** primary authorities (FDA, CDC, IRS, court dockets, etc.) using the database list in the README.

---

## Quick hallucination and overconfidence tests

After any AI answer, ask yourself:

1. **Citation check:** Did it give a specific URL or DOI? If you cannot find the source in 60 seconds of searching, treat the citation as **unverified**.  
2. **Certainty check:** Does the tone exceed the evidence (words like "proven," "always," "never" without scope)?  
3. **Framing check:** Would the opposite question get the same caveats?  
4. **Date check:** Is the claim about a fast-moving topic (prices, laws, outbreaks) without a date?

If two or more fail, slow down and lean harder on Step 5 and your own reading.

---

## Pocket checklist (copy or print)

- [ ] I used **separate chats** where the protocol says so.  
- [ ] I have **two** independent full replies (from separate chats), not one model paraphrasing itself.  
- [ ] I have a **referee** comparison in writing.  
- [ ] I asked for **primary-source** verification and received **links**.  
- [ ] I **clicked** at least one primary link and read the relevant section myself.  
- [ ] If the topic is medical, financial, or legal, I know this workflow is **not** a substitute for a professional.

---

## After CrossCheck

- Export JSON / Markdown from `index.html` if you want a record (see README).  
- For high-stakes topics, repeat CrossCheck later or ask a different human to review your sources - **double validation is allowed and encouraged** where the stakes justify it.

---

## Further reading

See the **Resources & References** section in [`README.md`](README.md) for guides, research papers, and primary-source databases.
