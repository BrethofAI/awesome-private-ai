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

Privacy is not yes-or-no, so every tool here sits on one rung of a
ladder, and the list is ordered by it:

1. **On your device** — nothing leaves the machine.
2. **On your server** — you host the whole stack; the vendor never sees
   your data.
3. **Can't see, provably** — hosted, but cryptography keeps the operator
   out (hardware enclaves you can verify, end-to-end encryption).
4. **Sees it to process it, keeps none of it** — the service must read
   your data to work, and is built and bound not to keep it or train on
   it. To be listed at this level a tool must show all three:
   (a) a written no-retention / no-training commitment in its terms, not
   just a marketing page; (b) whatever it stores is on your machine or
   encrypted under a key only you hold; (c) a data flow you can check —
   a source-available client or a documented architecture.

**Sees it and keeps it** is the rung we don't list. A local tool that
sends your data home doesn't make level 1 either.

Each entry also says what still leaves the machine — telemetry defaults,
update checks, optional cloud features — and how to turn it off.

We list both **architectures** and **vendors / tools** that implement
them. Be skeptical of any vendor's claim — verify against their
[awesome-ai-minefield](https://github.com/BrethofAI/awesome-ai-minefield) entry
when in doubt.

<!-- github-only -->
## Legend

- 🏠 on-device · 🏗️ self-hosted · ☁️ hosted (with privacy claims)
- 🔓 open source · 🔒 closed source
- 📜 audited · ❓ unaudited
- 🆓 free · 💰 paid · 🆓💰 mixed
- 🇪🇺 EU-hosted (often relevant for GDPR-sensitive workloads)
- 🆕 new — listed in the last 60 days
<!-- /github-only -->

<!-- LIST:START -->
## Contents

- [Level 1 — On Your Device](#level-1-—-on-your-device) (7)
- [Level 2 — On Your Server](#level-2-—-on-your-server) (8)
- [Level 3 — Can't See, Provably](#level-3-—-can't-see-provably) (5)
- [Level 4 — Processes, Never Stores](#level-4-—-processes-never-stores) (2)
- [Open-Weights Models You Can Audit](#open-weights-models-you-can-audit) (9)
- [Privacy Auditing Tools](#privacy-auditing-tools) (6)

<!-- The list below is generated from entries/*.yaml by scripts/gen_awesome_readme.py. Edit the YAML, not this section. -->

## Level 1 — On Your Device

Nothing leaves the machine — the strongest guarantee there is. The full catalog of local tools lives in [awesome-local-ai](https://github.com/BrethofAI/awesome-local-ai); these are the ones whose privacy story we checked.

- **[Brethof Voice Pro](https://brethof.ai/voice/)** — 🏠 🔒 💰  
  Voice-to-text, translation and subtitles that never leave your machine: audio, transcripts, translations and personal training data stay local. 30 transcription languages (+22 Chinese dialects), offline translation across 38, SRT/VTT subtitles, a voice keyboard, an MCP server for agents. The network sees a licence key and a version string at launch, and nothing once the update check is off and the models are on disk. *Disclosure: maintained by us.*
- **[Hyperconsciousness (hc)](https://github.com/louis030195/hyperconsciousness)** — 🆕 🏠 🔓 🆓 ❓  
  Encrypted, append-only knowledge store for agents (Rust, MIT) with scoped, expiring grants over MCP/HTTP; works with no hosted service, device sync optional. Developer alpha, no independent audit yet; installer builds auto-update from GitHub by default. Anything returned to a hosted model is visible to that model's provider.  
  <sub>★ 5 · last push 2026-10-05</sub>
- **[Jan](https://jan.ai)** — 🆕 🏠 🔓 🆓  
  Open-source (Apache-2.0) desktop chat that works fully offline; conversations and logs stay on your computer unless you choose a remote API. It checks jan.ai/GitHub for updates; usage analytics are opt-in at first launch.
- **[llama.cpp](https://github.com/ggml-org/llama.cpp)** — 🆕 🏠 🔓 🆓  
  The C/C++ inference engine most local tools build on, with an OpenAI-compatible server (`llama serve` / llama-server). MIT, no account, no telemetry; the network is touched only when you pull models from Hugging Face (`-hf`) or use the installer.  
  <sub>★ 130.4k · v0.5.0 (2026-09-23)</sub>
- **[LM Studio](https://lmstudio.ai)** — 🏠 🔒 🆓  
  Desktop app for running local models (plus the newer Bionic agent app); chats and documents stay on your machine when you use local models, no account needed. Closed source (CLI, SDKs and MLX engine are MIT). It still sends update checks and model searches to LM Studio, and sells optional paid cloud models (Bionic+/Pro) — the free tier is local.
- **[Ollama](https://ollama.com)** — 🏠 🔓 🆓  
  Local LLM runtime, MIT, no account needed for local models. Its cloud features (cloud models, web search) are on by default — for local-only, set OLLAMA_NO_CLOUD=1 or "disable_ollama_cloud": true in ~/.ollama/server.json. The macOS/Windows app auto-downloads updates.
- **[whisper.cpp](https://github.com/ggml-org/whisper.cpp)** — 🆕 🏠 🔓 🆓  
  Whisper speech recognition fully offline on-device, including phones. MIT.  
  <sub>★ 54.1k · v1.9.4 (2026-09-11)</sub>

## Level 2 — On Your Server

You run the whole stack on hardware you control, so the vendor never sees your data. Watch the defaults: several phone home for telemetry until you switch it off, and each entry says how.

- **[Anything LLM](https://anythingllm.com)** — 🏠 🏗️ 🔓 🆓  
  Self-hosted workspace with built-in RAG over your documents, MIT. Anonymous telemetry (PostHog) is ON by default — turn it off with DISABLE_TELEMETRY=true or under Privacy in the app.
- **[Immich](https://immich.app/)** — 🆕 🏗️ 🔓 🆓  
  Self-hosted photo and video library; face recognition, CLIP search and OCR run in your own machine-learning container. Leaves the server by default: a new-version check, map tiles from tiles.immich.cloud, and a one-time ML model download from Hugging Face — all can be switched off in the config. AGPL-3.0.
- **[LibreChat](https://github.com/LibreChat-AI/LibreChat)** — 🏗️ 🔓 🆓  
  Multi-model chat platform (MIT), owned by ClickHouse since Nov 2025. No vendor telemetry; logs stay on your server unless you point OpenTelemetry/Langfuse somewhere.  
  <sub>★ 45.3k · last push 2026-10-05</sub>
- **[LocalAI](https://localai.io)** — 🏠 🏗️ 🔓 🆓  
  OpenAI- and Anthropic-compatible server for text, voice, image, video and agents (MIT). No telemetry; only model/backend downloads from its gallery leave the box.
- **[Open Notebook](https://github.com/lfnovo/open-notebook)** — 🆕 🏗️ 🔓 🆓  
  Self-hosted, open-source alternative to NotebookLM (MIT), with your own model backends and no cloud dependency.  
  <sub>★ 39.8k · v1.15.0 (2026-10-04)</sub>
- **[Open WebUI](https://openwebui.com)** — 🏗️ 🆓  
  Self-hosted chat UI for local + remote LLMs; pair it with Ollama or any OpenAI-compatible backend. Source-available since v0.6.6 (Apr 2025): BSD-3 plus a branding clause (over 50 users in 30 days may not remove the branding without permission); its docs say it is not OSI open source. Telemetry off in the official image, but it checks GitHub for updates by default — ENABLE_VERSION_UPDATE_CHECK=false or OFFLINE_MODE=true. Core is free; Terminals needs an enterprise licence.
- **[RAGFlow](https://github.com/infiniflow/ragflow)** — 🆕 🏗️ 🔓 🆓  
  Self-hosted RAG engine with agents (Apache-2.0); you host the whole stack in Docker and can pair it with local models.  
  <sub>★ 91.7k · v1.0.0-rc1 (2026-09-29)</sub>
- **[vLLM](https://docs.vllm.ai)** — 🏗️ 🔓 🆓  
  High-throughput LLM serving you run yourself — no per-token middleman. Sends anonymous usage stats (hardware, model architecture, config) by default; opt out with VLLM_NO_USAGE_STATS=1 or DO_NOT_TRACK=1.

## Level 3 — Can't See, Provably

Hosted, but the operator is locked out by cryptography, not by promise: end-to-end encryption, or a hardware enclave whose running code your client verifies before it sends anything.

- **[Confer](https://confer.to/)** — 🆕 ☁️ 🆓 💰  
  AI chat from Signal's founder: history encrypted with passkey-derived keys that never leave your device; prompts are encrypted from your device into a confidential VM whose attestation the client checks against a public transparency log first; reproducible builds. Leaves the machine: product analytics to Confer's own API (pageviews, login events, timezone, user ID), and connectors (Gmail, Calendar) call Google from the client. Server source published without a licence. Free tier 20 messages a day; membership $34.99/month.
- **[Ente Photos](https://ente.com)** — 🆕 ☁️ 🏗️ 🏠 🔓 📜 🇪🇺 🆓 💰  
  End-to-end encrypted photo storage whose AI search (faces, scenes) runs on your device; the server only ever holds ciphertext and can be self-hosted. AGPL-3.0.
- **[Maple (OpenSecret)](https://github.com/MaplePrivacyLabs/Maple)** — 🆕 ☁️ 🔓 🆓 💰  
  Private AI chat: messages encrypted on device, decrypted only inside attested AWS Nitro Enclaves, inference in GPU TEEs; the client checks signed measurements first. Hosted, needs an account.  
  <sub>★ 98 · v3.4.1 (2026-09-15)</sub>
- **[Privatemode](https://www.privatemode.ai/)** — 🆕 ☁️ 🔓 🆓 💰 🇪🇺  
  Confidential-computing AI API and chat from Edgeless Systems (Germany) on AMD SEV-SNP / Intel TDX / NVIDIA H100-B200 confidential computing; the client-side proxy or SDK verifies remote attestation before any prompt is sent. Prompts are not stored or trained on; the web app keeps history in the browser. Leaves the machine: IP, timestamps, API key and token usage (up to 90 days; per-key usage kept for billing). Proxy and chat client MIT, core source-available for audit. EU-hosted.
- **[Tinfoil](https://tinfoil.sh)** — 🆕 ☁️ 🔓 💰  
  Confidential-computing inference for open models: the client verifies the enclave's attestation against open-source code in transparency logs, then encrypts end-to-end to it — isolated from the host operator. Hosted.

## Level 4 — Processes, Never Stores

These services have to read your data to do their job. What earns a place here is what happens next: a written no-retention, no-training commitment; nothing stored except on your machine or under a key only you hold; and a data flow you can check.

- **[Brethof Brain](https://brethof.ai/brain/)** — 🆕 ☁️ 🆓 💰  
  Memory for AI agents that processes your conversations and stores none of them on our side: our hub reads each exchange to curate it and keeps none of it. The memory itself lives on your machine (local edition), or encrypted in Germany under a passphrase only you hold (hosted) — ciphertext to everyone, us included, while locked. Processing runs on secure compute in Zurich; the model provider is bound by contract not to log, retain or train. The client is source-available: read every line and see what leaves. Disclosure: maintained by us.
- **[Lumo (Proton)](https://lumo.proton.me)** — 🆕 ☁️ 🔓 🇪🇺 🆓 💰  
  Proton's AI assistant: its Terms bar using your chats to improve the service and say content is zero-access encrypted once processed; saved chats live on your device and sync with zero-access encryption. Runs on Proton-controlled servers in the EU; the apps are open source (the backend is not). Optional web search sends a simplified query to partner APIs. Guest use needs no account.

## Open-Weights Models You Can Audit

Closed weights = closed privacy story. Public weights let you read what the model is, run it offline, and verify there's no hidden phone-home in the inference path.

- **[DeepSeek V4 / V4.1](https://huggingface.co/deepseek-ai)**  
  Open-weights frontier reasoning models, MIT: V4-Pro and V4-Flash (April 2026 preview; official releases V4-Flash-0731 and V4-Pro-0813 in July/August 2026) and V4.1-Flash (September 2026). Run the weights locally — deepseek.com is the hosted service.
- **[Gemma 4](https://deepmind.google/models/gemma/)**  
  Google's open-weights family; Gemma 4 (April 2026; 12B added June 2026) is Apache-2.0 and not gated.
- **[GLM-5.3](https://huggingface.co/zai-org/GLM-5.3)** — 🆕  
  Zhipu (Z.AI) open weights, August 2026. GLM-5.3-Flash is plain MIT; the full GLM-5.3 is MIT-style with one condition — a Z.AI security review, and only for model-as-a-service businesses above $10B revenue. Self-hosting is unrestricted.
- **[Kimi K3](https://huggingface.co/moonshotai/Kimi-K3)** — 🆕  
  Moonshot AI's open-weights model (July 2026) under the Kimi K3 License, a modified MIT: model-as-a-service businesses above $20M annual revenue need a separate agreement, and products over 100M MAU or $20M monthly revenue must display "Kimi K3". Internal use is exempt.
- **[Mistral Large 3 / Small 4](https://huggingface.co/mistralai)** — 🆕  
  Mistral's Apache-2.0 open weights: Large 3 (675B) and Small 4 (119B). Note Mistral Medium 3.5 is under a modified MIT licence that bars companies with over $20M monthly revenue.
- **[Muse Glimmer (Meta)](https://huggingface.co/meta-models/Muse-Glimmer-30B)** — 🆕  
  Meta's current open-weights line (30B, August 2026), Apache-2.0 and not gated — unlike Llama 4, whose custom licence needs manual download approval.
- **[Qwen 3.8](https://huggingface.co/Qwen)** — 🆕  
  Alibaba's current open-weights family (August 2026). Mixed licences: Qwen3.8-27B is Apache-2.0, but Flash-Next and the flagship carry custom licences restricting large or model-as-a-service businesses — check the model card.
- **[Qwen3-ASR](https://github.com/QwenLM/Qwen3-ASR)**  
  Multilingual ASR model (0.6B / 1.7B, open weights). Powers transcription in Brethof Voice Pro.  
  <sub>★ 3.6k · last push 2026-06-26</sub>
- **[Whisper](https://github.com/openai/whisper)**  
  OpenAI's open-weights speech recognition, MIT. No model newer than large-v3-turbo (October 2024), but the repo is maintained.  
  <sub>★ 110k · v20250625 (2025-06-26)</sub>

## Privacy Auditing Tools

Verify the claims of vendors you have to use.

- **[Exodus Privacy](https://exodus-privacy.eu.org)** — 🔓 🆓 🇪🇺  
  Static analysis of Android apps' tracker libraries.
- **[Little Snitch](https://www.obdev.at/products/littlesnitch/)** — 🔒 💰 🆓 🍎 🐧  
  The de-facto standard for spotting what an app sends home. macOS, and since 2026 a Linux edition (eBPF component and web UI GPL-2.0, daemon free but proprietary).
- **[mitmproxy](https://mitmproxy.org)** — 🔓 🆓  
  Intercept-and-inspect HTTP/S traffic. See what an "offline" tool actually sends home.
- **[OpenSnitch](https://github.com/evilsocket/opensnitch)** — 🔓 🆓 🐧  
  Application-level firewall for Linux. Confirm a desktop AI tool isn't talking to anyone.  
  <sub>★ 14.1k · v1.8.0 (2025-12-15)</sub>
- **[Portmaster](https://safing.io/)** — 🆕 🔓 🆓 💰 🐧  
  Application firewall that shows and blocks every connection per app — see what your AI tools contact. Windows and Linux. Leaves the machine: signed updates and blocklist/GeoIP data download automatically, and DNS goes to Cloudflare over DoT by default (configurable). Network history and the SPN relay are paid. GPL-3.0.
- **[Wireshark](https://www.wireshark.org)** — 🔓 🆓  
  Packet capture and analysis. Last-resort proof of what crosses the network.

<!-- LIST:END -->

## Related work

- **[awesome-local-ai](https://github.com/BrethofAI/awesome-local-ai)** — Stricter "100% on-device" filter.
- **[awesome-ai-minefield](https://github.com/BrethofAI/awesome-ai-minefield)** — Vendor ToS / license analysis. Receipts for the privacy claims here.
- **[awesome-llms-txt](https://github.com/BrethofAI/awesome-llms-txt)** — Tool discovery for AI agents.
- **[awesome-linux-for-ai](https://github.com/BrethofAI/awesome-linux-for-ai)** — Linux distros for the self-hosted privacy-respecting AI stack.
- **[awesome-mcp-servers](https://github.com/BrethofAI/awesome-mcp-servers)** — MCP servers; the permission-tag column there matches the privacy filter here.
- **[anti-dev-tier-list](https://github.com/BrethofAI/anti-dev-tier-list)** — The privacy-violating practices we recommend avoiding.

## Contributing

Open an issue with the tool, the level of the ladder you think it
reaches (on-device, self-hosted, provably can't see, or processes but
keeps nothing), and the verifiable evidence — repo URL,
ToS clause, whitepaper. Marketing copy is not evidence. Entries live as
one YAML file each under `entries/`; this README is generated from them,
so edit the YAML, not the list above.

## License

[MIT](LICENSE).

---

Maintained by **[Brethof AI](https://brethof.ai)** — AI tools built for
people who take their data seriously.
