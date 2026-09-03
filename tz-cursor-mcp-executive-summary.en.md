# Why deploy Cursor and 1C search - brief for leadership

**Language:** [Русский](tz-cursor-mcp-executive-summary.ru.md) | [English](tz-cursor-mcp-executive-summary.en.md)

**Version:** 3.1 · **Date:** 2026-09-03  
**Details:** [project description](tz-cursor-mcp-team.en.md) · [approval assessment](tz-cursor-mcp-governance-assessment.en.md) · [leadership FAQ](tz-cursor-mcp-leadership-faq.en.md)

---

## What we are deciding

Give the 1C team an AI assistant grounded in **our** configurations - not a generic public chatbot.

**We ask to approve:**
- tools for **15** developers and analysts;
- later - a **help chat for up to 50** 1C users (same budget envelope);
- a server under company control;
- rule: **no live production databases with customer data.**

---

## The problem

Knowledge of 15 configurations sits in people’s heads; finding “where is this in the system” takes too long; repeated user questions pull analysts off project work.

---

## What we get

| Who | What |
|-----|------|
| IT (15) | Cursor + shared search over configuration exports on our server |
| Users (up to 50) | Web help chat: “how do I / how does it work” |
| Company | Sources and index on our side; access via corporate rules; revoke on exit |

---

## Money

| | |
|-|-|
| Yearly guide | about **$16k** external spend |
| Start-up (one-off) | about **$230-310** (MCP ~RUB 7,000-8,500 / ~$80-110 + host setup if needed) - inside the yearly guide |
| Setup work | in-house, not in that figure |
| Cursor | $20/person/mo (stipend) |

**1C firm** commercial search/AI product licenses are **not included:** the product is still in testing; official 1C pricing is expected no earlier than October 2026. Start does not depend on them.  
Breakdown: [leadership FAQ](tz-cursor-mcp-leadership-faq.en.md) §1.

Server site (market-class dedicated server or our Azure) to be agreed with IT within the same guide. The expensive ITG quote (~$960/mo) is not proposed as the primary option.

---

## Rollout

1. Approve the idea, budget guide, and the production-DB rule.  
2. Pilot with a few people and configurations.  
3. If value is proven - full IT team.  
4. Chat - staged, after access is agreed with IT/Cyber.

We can stop after the pilot.

---

## Risks - briefly

| Risk | Approach |
|------|----------|
| Code fragments in the AI cloud | Inherent to the tool; vendor privacy mode; ban passwords and customer data in prompts |
| Leak via chat | No live DBs; logging; staged open |
| Cost | Hold ~$16k/year; no invented 1C license lines |

---

## Ask

> Approve launch of Cursor and search over our configurations for IT and (staged) a web help chat for users, without live production databases, with a budget guide of about **$16k/year** external spend.
