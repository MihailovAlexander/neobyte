# Why deploy Cursor and 1C search — brief for leadership

**Language:** [Русский](tz-cursor-mcp-executive-summary.ru.md) | [English](tz-cursor-mcp-executive-summary.en.md)

**Version:** 2.0 · **Date:** 2026-08-27  
**Details:** [technical description](tz-cursor-mcp-team.en.md) · [risk and governance assessment](tz-cursor-mcp-governance-assessment.en.md)

---

## What we are deciding

Give the 1C team and end users an **AI assistant that knows our 15 configurations** — not a generic public chatbot.

**We ask to approve now:**
- tools for **15** developers and analysts;
- a **help chat for up to 50** regular 1C users;
- a server we control (recommended: Hetzner ~€259/mo);
- security rules (**no** connection to live production databases with customer data).

---

## The problem

| Today | Business impact |
|-------|-----------------|
| 15 configurations, daily code changes | Knowledge is stuck in people’s heads |
| Finding “where is this in the system” takes hours | Changes ship slower |
| New hires ramp up slowly | Expensive onboarding |
| 50 users ask analysts the same questions | Analysts are pulled off projects |

---

## What we get

| Who | What appears |
|-----|----------------|
| Developers and analysts (15) | **Cursor** editor + a shared knowledge base of all configurations on our server |
| 1C users (up to 50) | Simple **web chat**: “how do I / how does it work” without calling an analyst |
| Company | Indexes and sources on **our** server; access only via the corporate network; access removed on exit |

We do **not** connect live production databases with real customer data. Only code exports and (optionally later) **test** copies.

---

## Money

| | |
|-|-|
| Per month (full scope) | about **$830–1,140** |
| Per year | about **$15–16k** + 1C search-server licenses (to be confirmed) |
| Server | ~€259/mo (Hetzner). ITG quote at $960/mo is **not competitive** |
| Setup work | in-house, not in the cash budget |
| Cursor | $20/person/mo (payroll stipend) |

Compared with half a 1C specialist’s cost, this is smaller — and it serves the whole team plus users.

**Payback (estimate):** IT time saved on the order of **$4–10k/mo** against ~$1k spend — plus less analyst load from end users.

---

## How we roll out (not “everything at once”)

1. **Approve now** the idea, budget, and security rules (including chat for 50).  
2. Pilot with a few people and a few configurations.  
3. If value is proven — all 15 IT.  
4. Then chat: 10–15 users first, security check, then up to 50.

We can stop after the pilot — it is not all-or-nothing.

---

## Risks — briefly

| Risk | How we handle it |
|------|------------------|
| Does code go to the AI cloud? | Partly yes (as with any Cursor) — privacy mode on; ban passwords and customer data in chats |
| Leak via user chat | No live production DB; personal-data filter; full question log |
| Cost | Cheap dedicated server, not the expensive ITG virtual machine |

---

## Ask

> Approve launch: Cursor and search across 15 configurations for IT **and** a web help chat for up to 50 users, without live production databases, budget about **$15–16k/year** (+ search licenses), staged rollout with a security check before opening chat to all users.
