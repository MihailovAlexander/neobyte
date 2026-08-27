# Project description: Cursor and smart search across 1C configurations

**Language:** [Русский](tz-cursor-mcp-team.ru.md) | [English](tz-cursor-mcp-team.en.md)

**Version:** 2.0 · **Date:** 2026-08-27  
**Sponsor:** 1C product owner  
**For leadership:** [one-page summary](tz-cursor-mcp-executive-summary.en.md)  
**For approval / security:** [project assessment](tz-cursor-mcp-governance-assessment.en.md)

---

## 0. What we ask to approve now

| Question | Answer |
|----------|--------|
| What we approve | Search server + Cursor for 15 IT + **web chat for up to 50 users** + security rules + budget |
| Is this building new 1C modules? | No. Tools around configurations we already have |
| Do we connect live databases with customer data? | **No** |
| When is chat | In the **decision and budget now**; open to users after the server is ready, in stages |
| Where are risk details | [project assessment](tz-cursor-mcp-governance-assessment.en.md) |

---

## 1. Why this matters

| Goal | How we know it worked |
|------|------------------------|
| IT finds answers across 15 configurations faster | Survey: search about **7×** faster |
| Fewer mistakes when changing the system | People see what else is affected before they change |
| Users interrupt analysts less | Up to 50 people use the help chat |
| Search refresh does not disturb work | Updates at night / weekends; lag no more than one week |

---

## 2. Scale

| Parameter | Value |
|-----------|-------|
| Developers | 10 |
| Analysts | 5 |
| Chat users | up to 50 (in current approval) |
| 1C configurations | 15 |
| 1C platform versions | about 6 |
| Code updates | almost daily, via configuration repository |
| Size of one configuration export | about 1 GB (~15 GB total) |

---

## 3. How it works (non-technical)

Three layers:

```
People
  • IT uses Cursor on their PC and sees code on the shared server (read-only)
  • Users open a chat website and ask questions in plain language

Company hub server
  • Stores configuration exports
  • Builds fast search (“memory” of the systems)
  • Also hosts monitoring, IT alerts, and the web chat

Optional separate track
  • 1C test server — tests only, no live customer data
```

**Important:**
- Live databases with customer data are **not** connected.
- ITG’s “$960/mo virtual machine with no direct link to our servers” is **not competitive** — see §6.
- We recommend a normal dedicated server (Hetzner ~€259/mo as a reference) with two disks: one for the system and files, one for search “memory” so night updates do not slow daytime work.

---

## 4. Refreshing search “memory”

After configuration changes, search must be refreshed.

| When | What we do |
|------|------------|
| Night | Update what changed |
| Weekend | Full refresh of all 15 if needed |
| On admin command | Urgent refresh of one configuration |

Target: search not older than **7 days**. If older — alert the IT channel.

Two disks are for **isolation of heavy night work**, not because we need many terabytes. About **0.5 TB + 1 TB** is enough; the cheap Hetzner model ships with larger disks — that is spare capacity, not a hard requirement.

---

## 5. Watching that it works

On the same server — simple status screens and alerts in a company messenger (free Mattermost is enough for IT).

We need to see:
- search is up or down;
- search older than a week;
- disk space low;
- user chat: how many questions (full log).

---

## 6. Server: Hetzner or ITG

| | Hetzner (recommended) | ITG (quote 26 Aug 2026) |
|-|----------------------|-------------------------|
| Price per month | about **€259** | **$960** |
| Type | Dedicated physical server | External virtual machine |
| Direct network to our existing servers | No (same as any external host) | **No** (confirmed by ITG) |
| Disks for night search | Two separate fast disks | One shared cloud disk |

**Leadership takeaway:** at ~3× the price and with no network advantage, ITG has **almost no upside**. Prefer a dedicated server like Hetzner AX102 (or similar).

Need roughly: 16–24 CPU cores, 128 GB memory, two disk volumes, no graphics card at the start.

---

## 7. Security (short)

Full version: [project assessment](tz-cursor-mcp-governance-assessment.en.md).

| Topic | Approach |
|-------|----------|
| IT access | Corporate network only; read-only files on the server |
| When someone leaves | Cut network → remove server access → stop Cursor stipend |
| Live customer data | Not indexed, not connected |
| AI cloud | Cursor and chat questions may go to external AI — ban passwords and customer data in questions; turn on privacy mode |
| Web chat | Consulting only; full dialog log; no customer-list exports |

---

## 8. Web chat for users (up to 50)

Included in the **current** approval and budget.

User flow:
1. Signs in.  
2. Picks a configuration from a list.  
3. Asks in everyday language.  
4. Gets an explanation and pointers to system objects (without ability to break the live database).

We recommend open-source **Open WebUI** on our server.  
**Telegram** is not recommended for this (data leaves our control).

Chat answers use a separate AI service (not the Cursor subscription). We pay from the day chat goes live.

---

## 9. Money

Setup and support are in-house and not in the table below.

| Item | Per month (guideline) |
|------|------------------------|
| Cursor for 15 people | $300 |
| Hetzner server | ~$300 |
| Building search indexes (external service) | $60–160 |
| AI answers in web chat | $150–300 (when chat is on) |
| 1C search licenses | to confirm |
| 1C Assistant (one shared access) | ~$20–80 |
| **Total with chat (excl. search licenses)** | **~$830–1,140** |

**Year:** about **$15–16k** + search licenses.

Early months can cost less (before chat), but we **approve the budget including chat** so we do not need a second decision later.

Cursor subscription: ordinary personal **Pro** ($20). Access to our systems is cut by company network controls, not by the Cursor plan.

---

## 10. Work plan

| Step | Timing | Outcome |
|------|--------|---------|
| 1. Server and pilot | 1–3 weeks | A few configurations, a few IT people |
| 2. All IT | 4–8 weeks | 15 configurations, 15 people, alerts |
| 3. Steady operation | up to 3 months | “Search not older than a week”; test databases if needed |
| 4. Chat | months 3–6 | Pilot 10–15 users → security check → up to 50 |

After step 1 we can stop if value is not proven.

---

## 11. Risks

| Risk | How we reduce it |
|------|------------------|
| Night search refresh takes too long | Separate disk; refresh several configurations in parallel |
| Expensive server “because we already use ITG” | Market dedicated server (~€259), not $960 |
| AI says too much in chat | No live databases; filters; log; check before “all 50” |
| Search licenses cost more than expected | Pilot on a few configurations first; buy more as needed |

---

## 12. Decisions already taken

| Topic | Decision |
|-------|----------|
| 1C search licenses | Confirm and buy as we grow |
| 1C Assistant | One shared access on the server, not 15 |
| Configuration export | Manual at the start; automate later |
| Messenger for IT alerts | We install the free edition ourselves |

---

*Written for management approval. Installation details (ports, containers) will be prepared for administrators after the budget is approved.*
