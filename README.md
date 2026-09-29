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

- [On-Device AI](#on-device-ai) (7)
- [Self-Hostable AI Stacks](#self-hostable-ai-stacks) (7)
- [Open-Weights Models You Can Audit](#open-weights-models-you-can-audit) (9)
- [Privacy Auditing Tools](#privacy-auditing-tools) (5)
- [Verifiable Confidential Cloud](#verifiable-confidential-cloud) (2)

<!-- The list below is generated from entries/*.yaml by scripts/gen_awesome_readme.py. Edit the YAML, not this section. -->

## On-Device AI

The strongest privacy guarantee: nothing leaves the machine. See [awesome-local-ai](https://github.com/BrethofAI/awesome-local-ai) for the full catalog — highlights here.

- **[Brethof Voice Pro](https://brethof.ai/voice/)** — 🏠 🔒 💰  
  Voice-to-text, translation and subtitles that never leave your machine: audio, transcripts, translations and personal training data stay local. 30 transcription languages (+22 Chinese dialects), offline translation across 38, SRT/VTT subtitles, a voice keyboard, an MCP server for agents. The network sees a licence key and a version string at launch, and nothing once the update check is off and the models are on disk. *Disclosure: maintained by us.*
- **[Ente Photos](https://ente.com)** — 🏠 🔓 🆓 💰  
  End-to-end encrypted photo storage whose AI search (faces, scenes) runs on your device; the server only ever holds ciphertext and can be self-hosted. AGPL-3.0.
- **[Jan](https://jan.ai)** — 🏠 🔓 🆓  
  Open-source (Apache-2.0) desktop chat that works fully offline; conversations and logs stay on your computer unless you choose a remote API.
- **[llama.cpp](https://github.com/ggml-org/llama.cpp)** — 🏠 🔓 🆓  
  The C/C++ inference engine most local tools build on, with an OpenAI-compatible llama-server. MIT, no account, runs on your own hardware.
- **[LM Studio](https://lmstudio.ai)** — 🏠 🔒 🆓  
  Desktop app for running local models; chats and documents stay on your machine when you use local models. Closed source (only the lms CLI is MIT). It still contacts LM Studio for update checks and model search, and now sells optional paid cloud tiers — the free tier is local.
- **[Ollama](https://ollama.com)** — 🏠 🔓 🆓  
  Local LLM runtime, MIT, no account needed for local models. Its cloud features (cloud models, web search) are on by default — for local-only, set OLLAMA_NO_CLOUD=1 or "disable_ollama_cloud": true.
- **[whisper.cpp](https://github.com/ggml-org/whisper.cpp)** — 🏠 🔓 🆓  
  Whisper speech recognition fully offline on-device, including phones. MIT.

## Self-Hostable AI Stacks

Run the whole pipeline on your own infrastructure.

- **[Anything LLM](https://anythingllm.com)** — 🏠 🏗️ 🔓 🆓  
  Self-hosted workspace with built-in RAG over your documents, MIT. Anonymous telemetry (PostHog) is ON by default — turn it off with DISABLE_TELEMETRY=true or under Privacy in the app.
- **[LibreChat](https://github.com/LibreChat-AI/LibreChat)** — 🏗️ 🔓 🆓  
  Multi-model chat platform. Self-host with full audit logging if you want it, none if you don't.
- **[LocalAI](https://localai.io)** — 🏠 🏗️ 🔓 🆓  
  OpenAI-compatible inference server. Self-host once, swap in any client app.
- **[Open Notebook](https://github.com/lfnovo/open-notebook)** — 🏗️ 🔓 🆓  
  Self-hosted, open-source alternative to NotebookLM (MIT), with your own model backends and no cloud dependency.
- **[Open WebUI](https://openwebui.com)** — 🏗️ 🆓  
  Self-hosted chat UI for local + remote LLMs; pair it with Ollama or any OpenAI-compatible backend. Source-available since 2025: BSD-3 plus a branding clause (deployments over 50 users may not remove the Open WebUI branding without permission) — its own docs say it is not OSI open source. No paywalled features; telemetry off in the official image.
- **[RAGFlow](https://github.com/infiniflow/ragflow)** — 🏗️ 🔓 🆓  
  Self-hosted RAG engine with agents (Apache-2.0); you host the whole stack in Docker and can pair it with local models.
- **[vLLM](https://docs.vllm.ai)** — 🏗️ 🔓 🆓  
  High-throughput LLM serving you run yourself — no per-token middleman. Sends anonymous usage stats (hardware, model architecture, config) by default; opt out with VLLM_NO_USAGE_STATS=1 or DO_NOT_TRACK=1.

## Open-Weights Models You Can Audit

Closed weights = closed privacy story. Public weights let you read what the model is, run it offline, and verify there's no hidden phone-home in the inference path.

- **[DeepSeek V4 / V4.1](https://huggingface.co/deepseek-ai)**  
  Open-weights frontier reasoning models, MIT: V4-Pro and V4-Flash (April 2026) and V4.1-Flash (September 2026). Run the weights locally — deepseek.com is the hosted service.
- **[Gemma 4](https://deepmind.google/models/gemma/)**  
  Google's open-weights family; Gemma 4 (March 2026) is Apache-2.0 and not gated.
- **[GLM-5.3](https://huggingface.co/zai-org/GLM-5.3)**  
  Zhipu (Z.AI) open weights, August 2026. GLM-5.3-Flash is plain MIT; the full GLM-5.3 has its own licence whose main condition applies only to companies above $10B revenue (a Z.AI security review).
- **[Kimi K3](https://huggingface.co/moonshotai/Kimi-K3)**  
  Moonshot AI's open-weights model (June 2026) under the Kimi K3 License, a modified MIT: model-as-a-service businesses above $20M revenue need a separate agreement, and very large products must display "Kimi K3".
- **[Mistral Large 3 / Small 4](https://huggingface.co/mistralai)**  
  Mistral's Apache-2.0 open weights: Large 3 (675B) and Small 4 (119B). Note Mistral Medium 3.5 is under a modified MIT licence that bars companies with over $20M monthly revenue.
- **[Muse Glimmer (Meta)](https://huggingface.co/meta-models/Muse-Glimmer-30B)**  
  Meta's current open-weights line (30B, August 2026), Apache-2.0 and not gated — unlike Llama 4, whose custom licence needs manual download approval.
- **[Qwen 3.8](https://huggingface.co/Qwen)**  
  Alibaba's current open-weights family (August 2026). Mixed licences: Qwen3.8-27B is Apache-2.0, but Flash-Next and the flagship carry custom licences restricting large or model-as-a-service businesses — check the model card.
- **[Qwen3-ASR](https://github.com/QwenLM/Qwen3-ASR)**  
  Multilingual ASR model (0.6B / 1.7B, open weights). Powers transcription in Brethof Voice Pro.
- **[Whisper](https://github.com/openai/whisper)**  
  OpenAI's open-weights speech recognition, MIT. No model newer than large-v3-turbo (October 2024), but the repo is maintained.

## Privacy Auditing Tools

Verify the claims of vendors you have to use.

- **[Exodus Privacy](https://exodus-privacy.eu.org)** — 🔓 🆓 🇪🇺  
  Static analysis of Android apps' tracker libraries.
- **[Little Snitch](https://www.obdev.at/products/littlesnitch/)** — 🔒 💰 🍎 🐧  
  The de-facto standard for spotting what an app sends home. macOS, and since 2026 a Linux edition (eBPF component and web UI GPL-2.0, daemon free but proprietary).
- **[mitmproxy](https://mitmproxy.org)** — 🔓 🆓  
  Intercept-and-inspect HTTP/S traffic. See what an "offline" tool actually sends home.
- **[OpenSnitch](https://github.com/evilsocket/opensnitch)** — 🔓 🆓 🐧  
  Application-level firewall for Linux. Confirm a desktop AI tool isn't talking to anyone.
- **[Wireshark](https://www.wireshark.org)** — 🔓 🆓  
  Packet capture and analysis. Last-resort proof of what crosses the network.

## Verifiable Confidential Cloud

Hosted, but you do not have to take their word for it: the model runs in a hardware enclave, and your client checks a signed measurement of the exact code running before it sends anything. Cryptographic isolation, with a receipt — not a no-log promise.

- **[Maple (OpenSecret)](https://github.com/MaplePrivacyLabs/Maple)** — ☁️ 🔓 🆓 💰  
  Private AI chat whose backend runs in AWS Nitro Enclaves; the client checks signed measurements of the running code before sending anything. Hosted, and needs an account.
- **[Tinfoil](https://tinfoil.sh)** — ☁️ 🔓 💰  
  Confidential-computing inference for open models: the client verifies the enclave's attestation against open-source code in transparency logs, then encrypts end-to-end to it — isolated from the host operator. Hosted.

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
