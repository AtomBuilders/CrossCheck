# CrossCheck

**Check it before you share it.**

An open, free **educational** protocol for questioning claims you see online - news, social media, or AI-generated - using AI tools you already have. **Not** medical, financial, or legal advice. Canonical terms: [`AGREEMENTS.md`](AGREEMENTS.md).

> *Truth is what survives contact with the original record.*

---

## What Is CrossCheck?

CrossCheck is a short process anyone can follow to **practice** examining something they heard before acting on it or sharing it. On the interactive page you accept the terms, enter **one claim** in a single text field (or leave it empty to use the built-in Lego safety example), pick three AI tools, then run copy-paste prompts for a **validator → referee → meta-referee** chain.

It takes about ten minutes. It uses free tools. It works for many everyday claims you encounter online - from product safety to breaking news. It is **not** a substitute for professional medical, mental-health, financial, tax, investment, or legal advice, and it does not meet any regulatory or clinical standard for verifying those topics.

**[Try it live: atom.builders/crosscheck](https://atom.builders/crosscheck/)**

---

## The workflow (human steps)

| Step | What You Do |
|------|-------------|
| **Claim** | After accepting terms, type or paste the **exact wording** you want to verify into the **single claim field** (question, statement, rumor, quote — anything). Leave the field empty to keep the built-in Lego example in every prompt. Click **Continue to lineup**. |
| **Lineup** | Pick three AI tools (validator, referee, meta-referee). Click **Continue to CrossCheck steps**. |
| **1** | Ask the **primary validator** using the page’s **one-shot** prompt: a concise answer grounded in **primary** sources **plus** a small structured “CrossCheck summary” block in the **same** reply. There is **no** second “opposite angle” prompt — one claim only. |
| **2** | Paste that **entire** reply into the page, then open a **new chat** for the **referee** and run the Step 2 prompt (it embeds your claim and paste). |
| **3** | Paste the referee’s **full** report, then open a **third new chat** for the **meta-referee** and run the Step 3 prompt. Optionally paste that reply into the form for a complete export. |
| **Publish** | When validator + referee pastes are done, you can export or **publish** a record to the moderated community feed (see `CONFIGURATION.md`). |

**The golden rule:** No matter how many AIs agree, click through to the actual primary source and read it yourself.

**Don't have three different tools?** Open separate *new chats* or temporary tabs in the same provider — the key is that each conversation starts fresh so no answer influences the next.

Long-form guidance (triage, expanded steps, hallucination checks, checklist): [`CrossCheck_Protocol.md`](https://github.com/AtomBuilders/crosscheck/blob/main/CrossCheck_Protocol.md) in the main CrossCheck repository.

---

## What's in This Repo

| File | Description |
|------|-------------|
| `index.html` | Interactive page: terms gate, **single claim field**, phased workflow (claim → lineup → run), prompts, paste workflow, exports. Dark / light theme. |
| `AGENTS.md` | **AI assistant guide** for validator / referee / meta-referee prompts: fact-checking (including health/science) is in scope; personalized professional advice is not. Linked from those prompts on the page. |
| `CrossCheck_Protocol.md` | Long-form protocol (complements this README): triage, expanded steps, hallucination checks, printable-style checklist. |
| `AGREEMENTS.md` | **Terms and agreements** (canonical). |
| `LICENSE` | **CC BY 4.0** legal text for the materials. |
| `README.md` | This overview. |
| [`CONFIGURATION.md`](CONFIGURATION.md) | **Server / publishing:** environment variables, optional `api/config.local.php`, Slack webhook, moderation, SQLite paths. |

---

## Server operators: SQLite and the publications table

If you run the optional **publish-to-feed** flow, each submission is stored as a row in SQLite (default file: **`data/crosscheck.sqlite`** at the repository root). You can override the path with **`CROSSCHECK_DB_PATH`** — see [`CONFIGURATION.md`](CONFIGURATION.md).

### Install the SQLite CLI (Ubuntu)

```bash
sudo apt update
sudo apt install sqlite3
sqlite3 --version
```

### Connect and inspect

From the repository root (adjust the path if your checkout lives elsewhere):

```bash
cd /path/to/crosscheck
sqlite3 data/crosscheck.sqlite
```

Useful interactive commands: `.tables`, `.schema publications`, `.headers on`, `.mode column`, `.quit`.

List stored publications (IDs are 32-character hex strings; you will also see them in `browse.html?id=…` and in Slack if configured):

```sql
SELECT * FROM publications;
```

For a shorter overview:

```sql
SELECT id, moderation_state, datetime(created_at, 'unixepoch') AS created_utc,
       substr(claim_text, 1, 100) AS claim_preview
FROM publications
ORDER BY created_at DESC;
```

### Unpublish an approved post (keep the row)

**Shared runs** and **`api/publication.php`** only expose rows where **`moderation_state` is `approved`**. To take a live post down while keeping the stored JSON for your own records, set the state to **`rejected`**:

```sql
UPDATE publications
SET moderation_state = 'rejected'
WHERE id = '<your-32-char-hex-publication-id>';
```

Valid values in this codebase are **`pending`**, **`approved`**, and **`rejected`**. You can also set a row back to **`pending`** if you want it to sit for re-review.

### Delete a row entirely

```sql
DELETE FROM publications WHERE id = '<your-32-char-hex-publication-id>';
```

This removes the full **`record_json`** payload for that id.

### Permissions

If the web server created **`data/crosscheck.sqlite`**, your user may need **`sudo sqlite3 …`** or appropriate read/write access on the file (and its directory) to run **`UPDATE`** / **`DELETE`**.

### HTTP alternative

To change moderation state without SQL, use **`api/moderate.php`** with the **`CROSSCHECK_MODERATE_SECRET`** token (see [`CONFIGURATION.md`](CONFIGURATION.md)).

---

## Free AI Tools You Can Use

Any combination works. The interactive page lets you pick your own.

| Tool | Free Tier | Link |
|------|-----------|------|
| ChatGPT | Yes | [chat.openai.com](https://chat.openai.com) |
| Gemini | Yes | [gemini.google.com](https://gemini.google.com) |
| Claude | Yes | [claude.ai](https://claude.ai) |
| Copilot | Yes | [copilot.microsoft.com](https://copilot.microsoft.com) |
| Grok | Yes (on X) | [x.com](https://x.com) |
| Meta AI | Yes | [meta.ai](https://meta.ai) |
| DeepSeek | Yes | [chat.deepseek.com](https://chat.deepseek.com) |
| Le Chat (Mistral) | Yes | [chat.mistral.ai](https://chat.mistral.ai) |
| Perplexity | Yes | [perplexity.ai](https://perplexity.ai) |
| Proton Lumo | Yes | [lumo.proton.me](https://lumo.proton.me/) |

---

## Why Not Just Ask One AI?

A single AI model can:

- **Agree with your framing** instead of correcting it (sycophancy)
- **Invent a citation** that looks real but links to nothing (hallucination)
- **Reflect its training biases** without flagging them
- **Sound confident** even when it's wrong

CrossCheck chains **three** independent model passes (validator, referee, meta-referee) and still expects **you** to read primaries — so one model’s blind spots are less likely to become yours.

---

## Resources & References

### Guides to Evaluating Information

- [News Literacy Project](https://newslit.org/) - nonpartisan educational resources
- [Stanford Civic Online Reasoning](https://cor.stanford.edu/) - teaches "lateral reading"
- [AP Fact Check](https://apnews.com/ap-fact-check) - Associated Press fact-checking hub
- [Reuters Fact Check](https://www.reuters.com/fact-check) - Reuters fact-checking desk
- [IFLA: How to Spot Fake News](https://www.ifla.org/publications/node/11174) - library-standard infographic

### Why This Protocol Works (AI Research)

- [Towards Understanding Sycophancy in Language Models](https://arxiv.org/abs/2310.13548) - Sharma et al., 2023
- [A Survey on Hallucination in Large Language Models](https://arxiv.org/abs/2311.07838) - Huang et al., 2023
- [A Multitask, Multilingual, Multimodal Evaluation of ChatGPT](https://arxiv.org/abs/2302.04023) - Bang et al., 2023

### Primary Source Databases

- [PubMed](https://pubmed.ncbi.nlm.nih.gov/) - biomedical research
- [Google Scholar](https://scholar.google.com/) - academic papers across all fields
- [CPSC](https://www.cpsc.gov/) - U.S. product safety
- [CDC](https://www.cdc.gov/) - U.S. public health
- [FDA](https://www.fda.gov/) - drugs, food, medical devices
- [WHO](https://www.who.int/) - international health
- [Congress.gov](https://www.congress.gov/) - U.S. federal legislation
- [IRS](https://www.irs.gov/) - U.S. tax rules
- [PACER](https://pacer.uscourts.gov/) - U.S. federal court records
- [National Weather Service](https://www.weather.gov/) - official forecasts

---

## Disclaimer and terms of use

CrossCheck (this repository, the interactive page, prompts, and related materials) is offered for **educational and academic purposes** only. **Full binding text:** [`AGREEMENTS.md`](AGREEMENTS.md). A short on-page summary also appears at [atom.builders/crosscheck/#terms](https://atom.builders/crosscheck/#terms).

**Not professional advice.** Nothing here is medical, financial, or legal advice. Do not use these materials in place of a qualified professional. If you may have a medical emergency, call your local emergency number.

**No warranty.** Materials are provided "as is." AI systems can hallucinate.

**Acceptance.** By using the interactive page you agree to [`AGREEMENTS.md`](AGREEMENTS.md). The page requires checking an acceptance box before tools unlock.

---

## Contributing

CrossCheck is a living document. If you find a broken link, a better primary source, or a way to make the steps clearer, open an issue or submit a PR.

---

## License

The CrossCheck **documentation and code** in this repository are licensed under **CC BY 4.0**. See the [`LICENSE`](LICENSE) file and [Creative Commons BY 4.0](https://creativecommons.org/licenses/by/4.0/). You are free to share and adapt - give credit.

---

**CrossCheck** - *Check it before you share it.* - [atom.builders/crosscheck](https://atom.builders/crosscheck/)
