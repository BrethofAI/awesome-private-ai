# awesome-private-ai

> AI tools that treat your data as yours. **Privacy by architecture, not by policy page.**

Maintained by [Brethof AI](https://brethof.com). Companion to
[awesome-local-ai](https://github.com/BrethofAI/awesome-local-ai),
[awesome-ai-mine](https://github.com/BrethofAI/awesome-ai-mine), and
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

Five things we look for, in order:

1. **Architectural privacy** — the tool *can't* see your data, not just
   *won't*. End-to-end encryption, on-device inference, attestable
   enclaves, trusted execution environments.
2. **Contractual zero-retention** — when (1) isn't possible, the
   provider commits in writing to no training, no logging, and no
   retention beyond the request lifecycle. Audit-clause friendly.
3. **Self-hostable open source** — you can run the whole stack on your
   own metal if you choose. No "open core, key features paywalled".
4. **No mandatory account** for offline / local modes.
5. **Transparent data flow** — explicit about what leaves your device,
   to where, and for how long.

We list both **architectures** and **vendors / tools** that implement
them. Be skeptical of any vendor's claim — verify against their
[awesome-ai-mine](https://github.com/BrethofAI/awesome-ai-mine) entry
when in doubt.

## Legend

- 🏠 on-device · 🏗️ self-hosted · ☁️ hosted (with privacy claims)
- 🔓 open source · 🔒 closed source
- 📜 audited · ❓ unaudited
- 🆓 free · 💰 paid · 🆓💰 mixed
- 🇪🇺 EU-hosted (often relevant for GDPR-sensitive workloads)

## Contents

- [On-Device AI](#on-device-ai)
- [Self-Hostable AI Stacks](#self-hostable-ai-stacks)
- [Zero-Retention Cloud LLMs](#zero-retention-cloud-llms)
- [Encrypted / Confidential Inference](#encrypted--confidential-inference)
- [Privacy-First Browsers with AI](#privacy-first-browsers-with-ai)
- [AI-Powered Privacy Tools](#ai-powered-privacy-tools)
- [Federated & Decentralised AI](#federated--decentralised-ai)
- [Differential Privacy & Synthetic Data](#differential-privacy--synthetic-data)
- [Anonymous AI Access](#anonymous-ai-access)
- [Open-Weights Models You Can Audit](#open-weights-models-you-can-audit)
- [Privacy Auditing Tools](#privacy-auditing-tools)

## On-Device AI

The strongest privacy guarantee: nothing leaves the machine. See
[awesome-local-ai](https://github.com/BrethofAI/awesome-local-ai) for
the full catalog. Highlights here:

- **[Brethof Voice Pro](https://brethof.com)** — 🏠 🔒 🆓💰
  Offline voice-to-text. Audio, transcripts, and personal training data
  never leave your machine. 36 languages. *Disclosure: maintained by us.*
- **[Ollama](https://ollama.com)** — 🏠 🔓 🆓
  Local LLM runtime. Single binary, no account, no telemetry by default.
- **[LM Studio](https://lmstudio.ai)** — 🏠 🔒 🆓
  Polished desktop app for local models. Free for personal + commercial.
- **[GPT4All](https://www.nomic.ai/gpt4all)** — 🏠 🔓 🆓
  Privacy-first desktop chat with curated quantised models.
- **[Apple Intelligence](https://www.apple.com/apple-intelligence/)** — 🏠 🔒 🆓
  On-device foundation models for Apple Silicon. Cloud "Private Compute"
  fallback uses attested enclaves with public-binary verification.

## Self-Hostable AI Stacks

Run the whole pipeline on your own infrastructure.

- **[Open WebUI](https://openwebui.com)** — 🏗️ 🔓 🆓
  Self-hosted chat UI for local + remote LLMs. Pair with Ollama or
  any OpenAI-compatible backend.
- **[LibreChat](https://www.librechat.ai)** — 🏗️ 🔓 🆓
  Multi-model chat platform. Self-host with full audit logging if you
  want it, none if you don't.
- **[Anything LLM](https://anythingllm.com)** — 🏗️🏠 🔓 🆓
  Self-hosted RAG + chat. Workspace per project, all data on your disk.
- **[LocalAI](https://localai.io)** — 🏗️🏠 🔓 🆓
  OpenAI-compatible inference server. Self-host once, swap in any
  client app.
- **[vLLM](https://docs.vllm.ai)** — 🏗️ 🔓 🆓
  High-throughput LLM serving. Self-host the same engine the big labs
  use — no per-token middleman.
- **[OpenLLM](https://github.com/bentoml/OpenLLM)** — 🏗️ 🔓 🆓
  Run any open-source LLM as a production-grade endpoint on your
  Kubernetes / Docker.
- **[Verba](https://github.com/weaviate/verba)** — 🏗️ 🔓 🆓
  Self-hosted RAG over your documents. By the Weaviate team.
- **[Danswer](https://github.com/danswer-ai/danswer)** — 🏗️ 🔓 🆓
  Open-source enterprise search + chat over your team's docs. SSO,
  audit, all on-prem.
- **[FOSS-AI Workbench](https://github.com/foss-ai/workbench)** — 🏗️ 🔓 🆓
  All-in-one self-hosted notebook for fine-tuning, evals, and
  inference.

## Zero-Retention Cloud LLMs

When you must use the cloud, these have written commitments to no
retention or training on your inputs. Always re-verify the live ToS —
[awesome-ai-mine](https://github.com/BrethofAI/awesome-ai-mine) tracks
the exact clauses.

- **[Anthropic Claude](https://www.anthropic.com/legal/commercial-terms)** — ☁️ 🔒 📜 💰
  Commercial API: zero retention by default, no training on customer
  data per the Commercial Terms. Free tier and Claude.ai consumer
  product follow different rules — read the consumer agreement.
- **[Mistral Le Chat](https://mistral.ai/terms/)** — ☁️ 🔒 💰 🇪🇺
  EU-based provider. La Plateforme commercial API offers zero-retention
  enterprise tier.
- **[Brave Leo](https://brave.com/leo/)** — ☁️ 🔒 🆓💰
  Anonymized, no-account chat in the Brave browser. Reverse-proxy
  architecture means the model provider never sees your IP or identity.
- **[OpenRouter](https://openrouter.ai)** — ☁️ 🔒 🆓💰
  Aggregator routing to multiple providers. Per-route privacy is the
  underlying provider's; some routes mark "no logging" explicitly.
- **[Together AI](https://together.ai)** — ☁️ 🔒 💰
  Open-model API host with documented zero-retention enterprise tier.

> ⚠️ "Zero retention" rarely applies to abuse / safety classifiers and
> prompt caches with very short TTLs. Read the specific commitment.

## Encrypted / Confidential Inference

Cryptographic isolation: the operator can run the model but cannot see
your prompts or outputs.

- **[Apple Private Compute](https://security.apple.com/blog/private-cloud-compute/)** — ☁️ 🔒 📜
  Apple's attested-enclave fallback for Apple Intelligence. Public
  binary, third-party-verifiable.
- **[Zama / Concrete ML](https://github.com/zama-ai/concrete-ml)** — 🔓 🆓
  Fully Homomorphic Encryption (FHE) library for ML. Run inference on
  encrypted data — slow, but cryptographically private.
- **[Phala Network](https://phala.network)** — ☁️ 🔓 🆓💰
  TEE-based confidential AI runtime. Run any LLM inside an Intel SGX /
  AMD SEV-SNP enclave with on-chain attestation.
- **[Nillion](https://nillion.com)** — ☁️ 🔒 💰
  Multi-party-computation network for AI workloads on private inputs.
- **[Microsoft Azure Confidential AI](https://azure.microsoft.com/en-us/solutions/confidential-compute/)** — ☁️ 🔒 💰
  Confidential VMs (AMD SEV / NVIDIA H100 CC mode) for AI workloads
  with attestation.

## Privacy-First Browsers with AI

- **[Brave + Leo](https://brave.com/leo/)** — 🔓 🆓💰
  Privacy-first browser with built-in AI assistant. Anonymized routing.
- **[Vivaldi + Lookup](https://vivaldi.com)** — 🔒 🆓
  Vivaldi's lightweight, opt-in AI assistant.
- **[Mullvad Browser](https://mullvad.net/en/browser)** — 🔓 🆓
  Tor-Browser-derived, no AI built in — pair with a self-hosted local
  model for an anonymous AI workflow.

## AI-Powered Privacy Tools

AI tools that protect privacy *for* you (rather than just being
private themselves).

- **[ProtonMail Scribe](https://proton.me/blog/proton-scribe-writing-assistant)** — 🏠 🔒 🆓💰 🇪🇺
  Email-writing assistant that runs in the browser; no data sent to
  Proton servers.
- **[NordVPN Threat Protection AI](https://nordvpn.com/features/threat-protection/)** — ☁️ 🔒 💰
  AI-powered tracker / phishing blocker integrated into the VPN.
- **[Privacybot](https://github.com/privacytoolsio/privacybot)** — 🔓 🆓
  Automated GDPR / CCPA data-deletion request generator.

## Federated & Decentralised AI

Train on data without centralising it.

- **[Flower](https://flower.ai)** — 🔓 🆓 🐍
  Friendly, mature federated-learning framework. Train across mobile,
  edge, and cloud nodes without pooling raw data.
- **[OpenFL](https://github.com/securefederatedai/openfl)** — 🔓 🆓 🐍
  Intel's federated learning framework with TEE integration.
- **[FedML](https://fedml.ai)** — 🔓🔒 🆓💰 🐍
  Federated learning + analytics platform. Open core.
- **[NVFlare](https://github.com/NVIDIA/NVFlare)** — 🔓 🆓 🐍
  NVIDIA's federated learning platform; production hospitals use it.
- **[Bittensor](https://bittensor.com)** — 🔓 🆓 🐍
  Decentralised AI compute and intelligence marketplace.

## Differential Privacy & Synthetic Data

- **[Opacus](https://opacus.ai)** — 🔓 🆓 🐍
  Train PyTorch models with differential privacy. Maintained by Meta AI.
- **[TensorFlow Privacy](https://github.com/tensorflow/privacy)** — 🔓 🆓 🐍
  Reference DP-SGD trainer for TensorFlow / Keras.
- **[SmartNoise](https://smartnoise.org)** — 🔓 🆓 🐍
  OpenDP project's tools for differentially-private analytics.
- **[Synthea](https://synthetichealth.github.io/synthea/)** — 🔓 🆓 🐹
  Synthetic-patient data generator for healthcare ML — no real PHI.
- **[Gretel](https://gretel.ai)** — ☁️ 🔒 🆓💰
  Synthetic data platform with differential-privacy guarantees.

## Anonymous AI Access

When you can't trust the provider with your identity.

- **[OpenWebUI on Tor](https://openwebui.com)** — 🏗️ 🔓 🆓
  Self-host Open WebUI on a Tor onion service for fully-anonymous
  remote access to your LLM.
- **[venice.ai](https://venice.ai)** — ☁️ 🔒 🆓💰
  Crypto-payable, no-account LLM provider. Open-model selection.
- **[Brave Leo](https://brave.com/leo/)** — ☁️ 🔒 🆓💰
  No account; reverse-proxy hides your IP from the model provider.

## Open-Weights Models You Can Audit

Closed weights = closed privacy story. Public weights let you read
what the model is, run it offline, and verify there's no hidden
phone-home in the inference path.

- **[Llama 3 / 3.1 / 3.2](https://www.llama.com)** — Meta's open-weights family.
- **[Qwen 2.5 / 3](https://qwenlm.github.io)** — Alibaba's strongly-multilingual family.
- **[Mistral / Mixtral](https://mistral.ai)** — Permissive licensing, Apache 2.0 weights for older + flagship variants.
- **[DeepSeek-V3 / V3.1](https://www.deepseek.com)** — Open-weights frontier reasoning model.
- **[Gemma](https://ai.google.dev/gemma)** — Google's open-weights family.
- **[Qwen3-ASR](https://github.com/QwenLM/Qwen3-ASR)** — Multilingual ASR model. Powers Brethof Voice Pro.
- **[Whisper](https://github.com/openai/whisper)** — OpenAI's open-weights ASR.

## Privacy Auditing Tools

Verify the claims of vendors you have to use.

- **[mitmproxy](https://mitmproxy.org)** — 🔓 🆓
  Intercept-and-inspect HTTP/S traffic. See what an "offline" tool
  actually sends home.
- **[OpenSnitch](https://github.com/evilsocket/opensnitch)** — 🐧 🔓 🆓
  Application-level firewall for Linux. Confirm a desktop AI tool
  isn't talking to anyone.
- **[Little Snitch](https://www.obdev.at/products/littlesnitch/)** — 🍎 🔒 💰
  macOS equivalent. The de-facto standard for spotting telemetry.
- **[Wireshark](https://www.wireshark.org)** — 🔓 🆓
  Packet capture and analysis. Last-resort proof of what crosses the
  network.
- **[Exodus Privacy](https://exodus-privacy.eu.org)** — 🔓 🆓 🇪🇺
  Static analysis of Android apps' tracker libraries.

## Related work

- **[awesome-local-ai](https://github.com/BrethofAI/awesome-local-ai)** — Stricter "100% on-device" filter.
- **[awesome-ai-mine](https://github.com/BrethofAI/awesome-ai-mine)** — Vendor ToS / license analysis. Receipts for the privacy claims here.
- **[awesome-llms-txt](https://github.com/BrethofAI/awesome-llms-txt)** — Tool discovery for AI agents.

## Contributing

Open an issue with the tool, the privacy architecture (on-device,
self-hosted, encrypted, etc.), and the verifiable evidence — repo
URL, ToS clause, whitepaper. Marketing copy is not evidence.

## License

[MIT](LICENSE).

---

Maintained by **[Brethof AI](https://brethof.com)** — AI tools built for
people who take their data seriously.
