# Project description: Cursor and search over 1C configurations

**Language:** [Русский](tz-cursor-mcp-team.ru.md) | [English](tz-cursor-mcp-team.en.md)

**Version:** 3.1 · **Date:** 2026-09-03  
**Owner:** 1C product owner  
**For leadership:** [summary](tz-cursor-mcp-executive-summary.en.md) · [assessment](tz-cursor-mcp-governance-assessment.en.md) · [FAQ](tz-cursor-mcp-leadership-faq.en.md)

Management description. Installation details - after approval, for administrators.

---

## 0. What we ask to approve

| Question | Answer |
|----------|--------|
| What | Cursor + search over our configuration exports for IT; web help chat for users - same envelope, staged go-live |
| Is this new 1C module development? | No |
| Live production DBs with customer data? | **No** |
| Budget | About **$20k/year** external |

---

## 1. Why

Faster answers across 15 configurations; less analyst time spent on repeated user questions.

---

## 2. Scale

| | |
|-|-|
| Developers / analysts | 10 + 5 |
| Chat users | up to 50 |
| Configurations | 15 |
| Code updates | regular, via the normal repository process |

---

## 3. How it works (non-technical)

- **IT** uses Cursor; search is based on configuration exports on a company server (read-only).  
- **Users** - web help chat only.  
- **Server** holds exports and the index; monitoring and chat in the same contour.  
- Live databases are **not** connected.

Server site (market-class dedicated server or our Azure) agreed with IT. ITG (~$960/mo) is not proposed as the primary option.

---

## 4. Keeping search fresh

We refresh the index outside peak hours. Goal - not lag unacceptably behind configuration changes; alert IT on failure. Schedule details belong to delivery.

---

## 5. Security (brief)

Details in the [assessment](tz-cursor-mcp-governance-assessment.en.md) and [FAQ](tz-cursor-mcp-leadership-faq.en.md).

- Access under corporate rules; IT and business separated.  
- Access revoked on exit.  
- AI prompts may include fragments from exports - ban passwords and customer data in text.  
- Chat - consultations and logging; no code-file access.

---

## 6. Web chat

In the approved envelope. Go-live after server prep and access agreement, starting with a limited group. We do not use Telegram for this corporate configuration help.

---

## 7. Money

| | |
|-|-|
| Yearly guide | ~**$20k** (server and backup, Cursor Teams × 15, AI services, buffer) |
| Start-up (one-off) | about **$230-310** (MCP ~RUB 7,000-8,500 / ~$80-110 + host setup if needed) - inside the yearly guide |
| Setup and support | in-house, not in that figure |
| 1C firm search/AI product licenses | **not included** - product in testing; 1C pricing no earlier than October 2026; start does not depend on them |

Details: [FAQ §1](tz-cursor-mcp-leadership-faq.en.md).

---

## 8. Plan

1. Pilot (few people and configurations).  
2. Full IT team.  
3. Chat - staged.  

We can stop after the pilot.

---

## 9. Ownership

Delivery and application - Alexander; infrastructure and access - system administrator; security - Cyber; budget - product owner. A second administrator is required.

---

*Document for management approval.*
