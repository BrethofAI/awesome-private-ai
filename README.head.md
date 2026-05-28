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
