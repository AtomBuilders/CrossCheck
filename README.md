# CrossCheck

**Check it before you share it.**

An open, free **educational** protocol for questioning claims you see online - news, social media, or AI-generated - using AI tools you already have. **Not** medical, financial, or legal advice. Canonical terms: [`AGREEMENTS.md`](AGREEMENTS.md).

> *Truth is what survives contact with the original record.*

---

## What Is CrossCheck?

CrossCheck is a short process anyone can follow to **practice** examining something they heard before acting on it or sharing it. You define **one claim**, run three independent AI passes (**validator → referee → meta-referee**), then read primary sources yourself.

It takes about ten minutes. It uses free tools. It works for many everyday claims you encounter online - from product safety to breaking news. It is **not** a substitute for professional medical, mental-health, financial, tax, investment, or legal advice.

**[Try the interactive tool](https://atom.builders/crosscheck/)** — or use the copy-paste **[prompt templates](templates/)** in this repository with any AI you already have.

---

## The workflow (human steps)

| Step | What You Do |
|------|-------------|
| **Claim** | Write the **exact wording** you want to verify (question, statement, rumor, quote — anything). One claim only — no “opposite angle” field. |
| **1 — Validator** | New chat → [primary-validator template](templates/primary-validator.md): short answer grounded in **primary** sources **plus** a structured CrossCheck summary in the **same** reply. |
| **2 — Referee** | New chat → [referee template](templates/referee.md): embeds your claim and the **full** validator paste; critiques that pass (not a competing narrative). |
| **3 — Meta-referee** | New chat → [meta-referee template](templates/meta-referee.md): embeds claim, validator paste, and referee report; stress-tests the referee against primaries. |

**The golden rule:** No matter how many AIs agree, click through to the actual primary source and read it yourself.

**Don't have three different tools?** Open separate *new chats* or temporary tabs in the same provider — each conversation must start fresh so no answer influences the next.

Long-form guidance (triage, expanded steps, hallucination checks, checklist): [`CrossCheck_Protocol.md`](CrossCheck_Protocol.md).

---

## What's in This Repository

| File / folder | Description |
|---------------|-------------|
| [`templates/`](templates/) | Copy-paste prompts with `{{CLAIM}}` and paste placeholders — use offline or alongside any chat UI |
| [`CrossCheck_Protocol.md`](CrossCheck_Protocol.md) | Long-form protocol: triage, depth, examples, tests, checklist |
| [`AGENTS.md`](AGENTS.md) | Guidance for AI models in the three passes |
| [`AGREEMENTS.md`](AGREEMENTS.md) | Terms and agreements (canonical) |
| [`LICENSE`](LICENSE) | CC BY 4.0 |
| `README.md` | This overview |

The hosted tool at [atom.builders/crosscheck](https://atom.builders/crosscheck/) implements the same protocol with a guided form (claim field, tool lineup, prompt generation, paste handoffs). It is not part of this documentation repository.

---

## Free AI Tools You Can Use

Any combination works.

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

CrossCheck chains **three** independent model passes and still expects **you** to read primaries — so one model’s blind spots are less likely to become yours.

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

CrossCheck materials in this repository are offered for **educational and academic purposes** only. **Full binding text:** [`AGREEMENTS.md`](AGREEMENTS.md).

**Not professional advice.** Nothing here is medical, financial, or legal advice. Do not use these materials in place of a qualified professional. If you may have a medical emergency, call your local emergency number.

**No warranty.** Materials are provided "as is." AI systems can hallucinate.

---

## Contributing

CrossCheck is a living document. If you find a broken link, a better primary source, or a way to make the steps clearer, open an issue or submit a PR.

---

## License

The CrossCheck **documentation** in this repository is licensed under **CC BY 4.0**. See [`LICENSE`](LICENSE) and [Creative Commons BY 4.0](https://creativecommons.org/licenses/by/4.0/).

---

**CrossCheck** - *Check it before you share it.* - [atom.builders/crosscheck](https://atom.builders/crosscheck/)
