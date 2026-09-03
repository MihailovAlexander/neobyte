# Response to leadership follow-up questions

**Language:** [Русский](tz-cursor-mcp-leadership-faq.ru.md) | [English](tz-cursor-mcp-leadership-faq.en.md)

**Version:** 2.1 · **Date:** 2026-09-03  
**Status:** reply before continuing  
**Related:** [summary](tz-cursor-mcp-executive-summary.en.md) · [project description](tz-cursor-mcp-team.en.md) · [approval assessment](tz-cursor-mcp-governance-assessment.en.md)

---

This document answers five leadership questions. Access, network and hosting details will be agreed separately with IT and Cyber - below is only what is needed to decide go / no-go.

---

## 1. Cost

**Approval figure: about $20k per year** (external cash spend, excluding staff payroll).  
One-off start-up payments are small and sit inside the same annual figure.

### 1.1 Start-up (one-off)

| Item | Guide | Note |
|------|-------|------|
| MCP server pack for configuration search | ~RUB 7,000-8,500 (~$80-110) | Once per company (vendor list price); not multiplied by number of configurations |
| Host setup fee (if dedicated server) | ~$150-200 | Only when ordering the server |
| Install, access, initial configuration exports | $0 external | Done by staff |
| **Total one-off external** | **about $230-310** | MCP + host setup; fits inside the ~$20k/year guide |

### 1.2 Recurring (inside ~$20k/year)

| Item | Guide |
|------|-------|
| Server and backup | ~$4-4.5k/year |
| Cursor Teams for 15 people | $7.2k/year (~$40/person/mo) |
| External AI (search + chat) | ~$3-5k/year |
| 1C:Assistant (one seat) | within the buffer inside ~$20k |
| Buffer for FX and usage | included in the ~$20k guide |

### 1.3 Explicitly not included

Commercial **1C firm** search / AI product licenses are **not included.**  
As of September 2026 the product is still in testing; **1C plans to announce pricing no earlier than October 2026.** Project start **does not** depend on those licenses.
---

## 2. Confidentiality and AI

**Out of scope:** live production databases and customer data.

**Stored on our side:** configuration exports (code/metadata) and the search index built from them - on a company server.

**What may leave to external AI services in use:** the question text and **fragments** of code/metadata from exports needed to answer. That is inherent to this class of tool; we therefore do not claim that “nothing ever leaves.”

**Which AI providers / services may process this**

| Service | Role | What it may receive |
|---------|------|---------------------|
| **Cursor** | AI in the editor for IT | The question and context fragments from the open work; Cursor then routes the request to the chosen model (typically Anthropic, OpenAI, Google, etc. - within models available in Cursor) |
| **Model router for chat and search indexing** (at start: OpenRouter or equivalent) | Web-chat answers and embeddings for the index | Question text / fragments for chat answers; text used to build the search index |
| **Our server** | Stores exports, indexes, chat log | Processes data **on our side**; it is not an external AI provider |

Full configuration exports and indexes are **not** uploaded as a whole archive: only what is needed for a given request or overnight index build is sent.  
Allowed models inside Cursor / OpenRouter can be narrowed by project rules and Cyber (allow-list). Switching a specific model within already agreed providers is an operational setting, not a new project.

**Model training:** on Cursor Teams we enable organization-level privacy mode; per the vendor’s public policy, code is not used for training in that mode. OpenRouter and chosen-model terms follow their policies and contract; if needed, we clarify with Cyber in a separate meeting.

**Usage rules:** no passwords, personal data, or production exports in prompts. Web-chat question logs stay with us.

---

## 3. Access

We agree the model must be stronger than “network + key only.”

**Principles (details with IT and Cyber):**

- separation: IT (editor and search) vs business users (help chat only) - no business access to code files or admin;
- MFA - aligned with existing company standards (VPN / corporate login); chat via corporate account;
- grant and revoke via IT on join/leave; admin access for at least two people;
- developers/analysts - read; changing exports on the server - administration only.

Directory groups, ticket templates and SSO - for the technical meeting, not for this reply.

---

## 4. Infrastructure

We compare sites on the **same profile** (capacity, disks, backup) for security, integration, operations and cost.

| Option | Position |
|--------|----------|
| Market-class dedicated server (Hetzner-class) | Reasonable cost; fits overnight search load |
| Our Azure | May be preferable for integration and familiar IT processes - if a comparable profile after IT costing fits the budget |
| ITG (~$960/mo compute alone) | Materially more expensive for little extra benefit; not proposed as the primary option |

**Hosting decision** with IT and Cyber after numbers are compared - not “because the first draft said so.” Section 1 assumes a market-class dedicated server; if Azure wins, we recalculate in one line.

---

## 5. Ownership and support

| Area | Who |
|------|-----|
| Delivery and application support for search/chat | Alexander |
| Server, network, access, OS updates | System administrator |
| Security policy | Cyber / Security |
| Budget and product priorities | 1C product owner |

Single-person dependency is avoided by: a second admin from production day one; recovery and access runbooks; secrets in corporate storage, not on one laptop.

Alexander owns delivery and the application side; he is **not** the sole failure point for infrastructure and access.

---

## 6. Next step

We support a separate discussion with system administrators, network engineers and Cyber/Security.

Enough for that meeting: confirm the budget figure; agree AI data flows; lock the access model; choose the site (Azure vs dedicated server).

---

## In one line each

| Question | Answer |
|----------|--------|
| Cost per year? | About **$20k** external; start-up ~$230-310 one-off (inside the guide). **1C firm** search/AI product licenses **excluded** (pricing from 1C no earlier than October 2026) |
| What goes to AI cloud? | Questions and code/metadata fragments from exports; not live customer data |
| Which AI providers? | Cursor (and models through it); OpenRouter or equivalent for chat and indexing; full exports stay on our server |
| Model training? | Vendor privacy mode; model-specific details with Cyber if needed |
| MFA and roles? | Yes, strengthen per company standards; details with IT/Cyber |
| Where to host? | Decide with IT after Azure vs dedicated comparison; ITG not proposed as primary |
| Who owns it? | Delivery - Alexander; infra/access - sysadmin; security - Cyber; no single irreplaceable person |

---

*Reply to leadership request, September 2026. Does not replace the IT/Cyber meeting record.*
