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
