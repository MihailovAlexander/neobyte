# Project assessment for approval: Cursor and 1C search

**Language:** [Русский](tz-cursor-mcp-governance-assessment.ru.md) | [English](tz-cursor-mcp-governance-assessment.en.md)

**Version:** 2.0 · **Date:** 2026-08-27  
**Audience:** leadership and security  
**Related:** [one-page summary](tz-cursor-mcp-executive-summary.en.md) · [project description](tz-cursor-mcp-team.en.md)

This document answers the usual approval questions: what we build, who runs it, what it costs, how we secure it, what people can do, and what we approve now.

---

## What we approve now

| In today’s decision | Not in today’s decision (later if needed) |
|---------------------|-------------------------------------------|
| Server with “memory” of 15 configurations | Connecting **live** databases with customer data |
| Cursor for 15 IT people | More expensive Cursor company plan (only if security requires it) |
| Web help chat for **up to 50** users | Expensive ITG quote at $960/mo |
| Access rules and a log of chat questions | Own GPU box for AI (possible after the pilot) |
| Monthly budget for server, subscriptions, AI services | Paying external implementers |

Chat for 50 users is **in the budget and decision now**. We do not have to open it to everyone on day one: hub and IT first, then chat in stages.

---

## 1. What it is and how we roll out

This is **not** a new 1C product and **not** a replacement for developers.  
It is **tooling** so people find answers in our configurations faster and analysts get fewer repetitive questions.

| Part | In plain words |
|------|----------------|
| Cursor | Smart code editor for developers and analysts |
| Hub server | Our machine in a data centre: stores configuration exports and fast search over them |
| Web chat | Help site for users: “how do I post a document”, “what is this setting for” |
| Test databases (optional) | Separate 1C server with **tests only**, no live customer data |

**Order of work:**
1. Pilot: a few people, a few configurations.  
2. If useful — all 15 IT.  
3. Chat: 10–15 users first, check, then up to 50.

Changes to working configurations stay as today — through the 1C repository. AI does **not** write into the live system by itself.

---

## 2. Who runs it

| Role | Does what | Time |
|------|-----------|------|
| 1C product owner | Goals, budget, go / stop | as approvals require |
| Hub administrator | Server, search refresh, chat, alerts | about 1–1.5 days per week |
| System administrator | Network, access, cut-off on exit | on request |
| Security / approver | Rules and reviews | at start and before opening chat to all |
| 15 IT | Use Cursor, give feedback | +$20/mo stipend |
| Up to 50 users | Use chat | short training |

**No external implementers required to start.** We pay subscriptions, server, and AI services only.

---

## 3. What it costs

In-house setup is not in the cash table.

| Item | IT pilot | When everything runs (per month) |
|------|----------|----------------------------------|
| Server (Hetzner) | ~€259 | ~€259 (~$300) |
| Cursor (5 then 15 people) | ~$100 | $300 |
| Services to build search indexes | ~$30–80 | ~$60–160 |
| AI answers in web chat | $0 until chat is live | ~$150–300 |
| Chat software (Open WebUI) | free | free |
| Team messenger for IT alerts | free | free |
| 1C search licenses | to confirm | to confirm |
| **Total excl. search licenses** | **~$450–600** | **~$830–1,140** |

**Per year (guideline):** about **$15–16k** + search licenses.  
We approve the budget **including chat**; we start paying chat AI when chat actually goes live.

---

## 4. Security — the calm version

### Where data goes

| Data | Where it lives | Leaves our perimeter? |
|------|----------------|------------------------|
| Configuration code exports | Our server | Snippets may go to Cursor / AI cloud when someone asks a question — normal for this class of tools |
| Customer data in live databases | **Not connected, not indexed** | Forbidden |
| Names/phones in chat questions | We try to filter before sending to AI | Goal: do not send |

We do **not** promise “nothing ever goes to the cloud”. We promise: **no live databases**, strict rules, logging, and fast access cut-off.

### Who can access what

| Who | How | On exit |
|-----|-----|---------|
| IT (15) | Corporate network + personal key to the server (read-only) | Cut network → remove key → stop Cursor stipend |
| Chat users (up to 50) | Chat login, **no** access to code files | Disable chat account |
| Live database via this contour | Nobody | — |

### Rules

- No passwords, customer lists, or live-database extracts in chat.  
- Privacy mode on in Cursor.  
- All web-chat questions are logged; admin can see usage.  
- Before opening chat to 50 people — security review (pilot logs).

### User chat limits

- Consulting only (“how do I”).  
- **No** code changes, **no** customer exports, **no** live database.  
- Rate limits; personal-data filter.

---

## 5. What different people can do

| Ability | Developer | Analyst | Chat user |
|---------|-----------|---------|-----------|
| Ask “where is X in the system” | yes | yes | yes (in plain language) |
| See impact of a change | yes | yes | no / only briefly in the answer |
| Change live configuration via AI | no* | no | **no** |
| See code files on the server | read-only | read-only | **no** |
| Live database | **no** | **no** | **no** |
| Export customers | **no** | **no** | **no** |

\* Configuration changes stay through the normal repository process.

**Allowed:** “How do I post this document?”, “What is this setting for?”  
**Not allowed:** “Export all counterparties”, “Run a query on the live database”.

---

## 6. Staged decisions

| Stage | When | Decision |
|-------|------|----------|
| **Now** | Before start | Approve idea, budget (IT + chat for 50), security rules, Hetzner server (not ITG $960) |
| **After IT pilot** | in 3–4 weeks | Scale to all 15 or stop / narrow |
| **Before chat at 50** | after chat pilot | Security check (logs, access) — budget already approved |
| **Later if wanted** | — | Own on-prem AI power; stricter company Cursor plan |

---

## 7. Mapping to the approver’s ask

| You asked for | Where it is |
|---------------|-------------|
| Technical approach | §1 |
| Own people vs contractors | §2 — contractors not required |
| Implementation and support cost | §3 |
| Security and access | §4 |
| What users can do | §5 (including 50 chat users) |
| Total cost before work starts | §6 “Now” |

**Decision wording:**

> Approve launch of Cursor and search across 15 configurations for the IT team and a web help chat for up to 50 users, without connecting live databases with customer data; budget on a dedicated Hetzner server and external AI services; staged rollout with a security check before opening chat to all users.
