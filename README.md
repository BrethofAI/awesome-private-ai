# awesome-private-ai

> AI tools that treat your data as yours. **Privacy by architecture, not by policy page.**

Maintained by [Brethof AI](https://brethof.ai). Companion to
[awesome-local-ai](https://github.com/BrethofAI/awesome-local-ai),
[awesome-ai-minefield](https://github.com/BrethofAI/awesome-ai-minefield), and
[awesome-llms-txt](https://github.com/BrethofAI/awesome-llms-txt).

## Why this list exists — and how it differs from awesome-local-ai

> **`local` ≠ `private`.** A local tool that phones home isn't private.
> A self-hosted cloud service that you control on your hardware *is*.

[awesome-local-ai](https://github.com/BrethofAI/awesome-local-ai) is
strict about *where the math runs*. This list is broader: tools that
protect data sovereignty by **architecture** — local, self-hosted,
cryptographically isolated, or contractually no-retention with audit
trail. A privacy-respecting cloud service belongs here. A local tool
that exfiltrates telemetry doesn't.

What we look for:

1. **Architectural privacy** — the tool *can't* see your data, not just
   *won't*. On-device inference, self-hosting, end-to-end encryption.
2. **Self-hostable open source** — you can run the whole stack on your
   own metal. No "open core, key features paywalled".
3. **No mandatory account** for offline / local modes.
4. **Transparent, verifiable data flow** — you can confirm with a packet
   capture what does and doesn't leave your device.

If a privacy claim can only be taken on trust — a cloud "no-log" toggle
you can't audit — it doesn't belong here. We removed the entire
contractual/cloud tier for exactly that reason: no receipt, no entry.

We list both **architectures** and **vendors / tools** that implement
them. Be skeptical of any vendor's claim — verify against their
[awesome-ai-minefield](https://github.com/BrethofAI/awesome-ai-minefield) entry
when in doubt.

## Legend

- 🏠 on-device · 🏗️ self-hosted · ☁️ hosted (with privacy claims)
- 🔓 open source · 🔒 closed source
- 📜 audited · ❓ unaudited
- 🆓 free · 💰 paid · 🆓💰 mixed
- 🇪🇺 EU-hosted (often relevant for GDPR-sensitive workloads)

## Contents

- [On-Device AI](#on-device-ai) (4)
- [Self-Hostable AI Stacks](#self-hostable-ai-stacks) (8)
- [Open-Weights Models You Can Audit](#open-weights-models-you-can-audit) (7)
- [Privacy Auditing Tools](#privacy-auditing-tools) (5)

<!-- The list below is generated from entries/*.yaml by scripts/gen_awesome_readme.py. Edit the YAML, not this section. -->

## On-Device AI

The strongest privacy guarantee: nothing leaves the machine. See [awesome-local-ai](https://github.com/BrethofAI/awesome-local-ai) for the full catalog — highlights here.

- **[Brethof Voice Pro](https://brethof.ai/voice/)** — 🏠 🔒 🆓 💰  
  Offline voice-to-text. Audio, transcripts, and personal training data never leave your machine. 30 transcription languages, 38 for offline translation. *Disclosure: maintained by us.*
- **[GPT4All](https://www.nomic.ai/gpt4all)** — 🏠 🔓 🆓  
  Privacy-first desktop chat with curated quantised models.
- **[LM Studio](https://lmstudio.ai)** — 🏠 🔒 🆓  
  Polished desktop app for local models. Free for personal + commercial.
- **[Ollama](https://ollama.com)** — 🏠 🔓 🆓  
  Local LLM runtime. Single binary, no account, no telemetry by default.

## Self-Hostable AI Stacks

Run the whole pipeline on your own infrastructure.

- **[Anything LLM](https://anythingllm.com)** — 🏠 🏗️ 🔓 🆓  
  Self-hosted RAG + chat. Workspace per project, all data on your disk.
- **[LibreChat](https://www.librechat.ai)** — 🏗️ 🔓 🆓  
  Multi-model chat platform. Self-host with full audit logging if you want it, none if you don't.
- **[LocalAI](https://localai.io)** — 🏠 🏗️ 🔓 🆓  
  OpenAI-compatible inference server. Self-host once, swap in any client app.
- **[Onyx (formerly Danswer)](https://github.com/danswer-ai/danswer)** — 🏗️ 🔓 🆓  
  Open-source enterprise search + chat over your team's docs. SSO, audit, all on-prem.
- **[Open WebUI](https://openwebui.com)** — 🏗️ 🔓 🆓  
  Self-hosted chat UI for local + remote LLMs. Pair with Ollama or any OpenAI-compatible backend.
- **[OpenLLM](https://github.com/bentoml/OpenLLM)** — 🏗️ 🔓 🆓  
  Run any open-source LLM as a production-grade endpoint on your Kubernetes / Docker.
- **[Verba](https://github.com/weaviate/verba)** — 🏗️ 🔓 🆓  
  Self-hosted RAG over your documents. By the Weaviate team.
- **[vLLM](https://docs.vllm.ai)** — 🏗️ 🔓 🆓  
  High-throughput LLM serving. Self-host the same engine the big labs use — no per-token middleman.

## Open-Weights Models You Can Audit

Closed weights = closed privacy story. Public weights let you read what the model is, run it offline, and verify there's no hidden phone-home in the inference path.

- **[DeepSeek V4](https://www.deepseek.com)**  
  Open-weights frontier reasoning model.
- **[Gemma](https://ai.google.dev/gemma)**  
  Google's open-weights family.
- **[Llama 4](https://www.llama.com)**  
  Meta's open-weights family.
- **[Mistral / Mixtral](https://mistral.ai)**  
  Permissive licensing, Apache 2.0 weights for older + flagship variants.
- **[Qwen 3.5 / 3.6](https://qwenlm.github.io)**  
  Alibaba's strongly-multilingual family.
- **[Qwen3-ASR](https://github.com/QwenLM/Qwen3-ASR)**  
  Multilingual ASR model. Powers Brethof Voice Pro.
- **[Whisper](https://github.com/openai/whisper)**  
  OpenAI's open-weights ASR.

## Privacy Auditing Tools

Verify the claims of vendors you have to use.

- **[Exodus Privacy](https://exodus-privacy.eu.org)** — 🔓 🆓 🇪🇺  
  Static analysis of Android apps' tracker libraries.
- **[Little Snitch](https://www.obdev.at/products/littlesnitch/)** — 🔒 💰 🍎  
  macOS equivalent. The de-facto standard for spotting telemetry.
- **[mitmproxy](https://mitmproxy.org)** — 🔓 🆓  
  Intercept-and-inspect HTTP/S traffic. See what an "offline" tool actually sends home.
- **[OpenSnitch](https://github.com/evilsocket/opensnitch)** — 🔓 🆓 🐧  
  Application-level firewall for Linux. Confirm a desktop AI tool isn't talking to anyone.
- **[Wireshark](https://www.wireshark.org)** — 🔓 🆓  
  Packet capture and analysis. Last-resort proof of what crosses the network.

## Related work

- **[awesome-local-ai](https://github.com/BrethofAI/awesome-local-ai)** — Stricter "100% on-device" filter.
- **[awesome-ai-minefield](https://github.com/BrethofAI/awesome-ai-minefield)** — Vendor ToS / license analysis. Receipts for the privacy claims here.
- **[awesome-llms-txt](https://github.com/BrethofAI/awesome-llms-txt)** — Tool discovery for AI agents.
- **[awesome-linux-for-ai](https://github.com/BrethofAI/awesome-linux-for-ai)** — Linux distros for the self-hosted privacy-respecting AI stack.
- **[awesome-mcp-servers](https://github.com/BrethofAI/awesome-mcp-servers)** — MCP servers; the permission-tag column there matches the privacy filter here.
- **[anti-dev-tier-list](https://github.com/BrethofAI/anti-dev-tier-list)** — The privacy-violating practices we recommend avoiding.

## Contributing

Open an issue with the tool, the privacy architecture (on-device,
self-hosted, encrypted, etc.), and the verifiable evidence — repo URL,
ToS clause, whitepaper. Marketing copy is not evidence. Entries live as
one YAML file each under `entries/`; this README is generated from them,
so edit the YAML, not the list above.

## License

[MIT](LICENSE).

---

Maintained by **[Brethof AI](https://brethof.ai)** — AI tools built for
people who take their data seriously.
