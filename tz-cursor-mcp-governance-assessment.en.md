# Project assessment for approval: Cursor and 1C search

**Language:** [Русский](tz-cursor-mcp-governance-assessment.ru.md) | [English](tz-cursor-mcp-governance-assessment.en.md)

**Version:** 3.0 · **Date:** 2026-09-03  
**Audience:** leadership and security  
**Related:** [summary](tz-cursor-mcp-executive-summary.en.md) · [description](tz-cursor-mcp-team.en.md) · [leadership FAQ](tz-cursor-mcp-leadership-faq.en.md)

Briefly: what we approve, who runs it, cost, security. Access and hosting details - separate meeting with IT and Cyber.

---

## What we approve now

| In | Out |
|----|-----|
| Server with search over configuration exports | Connecting **live** production DBs with customer data |
| Cursor Teams for 15 IT people | Invented 1C product licenses before an official price list |
| Web help chat (up to 50) in the budget envelope; go-live staged | Expensive ITG quote (~$960/mo) as the primary option |
| Usage rules and chat logging | External implementers for launch |

---

## 1. What it is

Not a new 1C configuration and not a people replacement. Tools to find answers in our configurations faster and unload analysts.

| Part | Meaning |
|------|---------|
| Cursor | AI editor for IT |
| Server | Holds exports and search |
| Web chat | Help for end users |

Order: pilot → full IT team → chat staged. AI does not write into production; configuration changes stay on the normal process.

---

## 2. Who owns it

| Role | Focus |
|------|--------|
| 1C product owner | Budget and go/stop |
| Alexander | Delivery and application support |
| System administrator | Server, network, access |
| Cyber / Security | Policy and checks |
| IT team / chat users | Use under the rules |

No external implementers required at start. Single-person risk is reduced with a second admin and runbooks (see [FAQ](tz-cursor-mcp-leadership-faq.en.md)).

---

## 3. Cost

Guide: about **$20k/year** external (server and backup, Cursor Teams, AI services, buffer). In-house setup not in that figure.

**1C firm** commercial search/AI product licenses are **not budgeted:** product still in testing; 1C pricing no earlier than October 2026. If needed later - a short separate request after prices exist.

Server site (dedicated or Azure) agreed with IT within the same guide.

---

## 4. Security

| Topic | Position |
|-------|----------|
| Live databases | Not connected, not indexed |
| Code exports | On our server; **fragments** may go to AI when asking - normal for this tool class |
| AI providers | Cursor (models through it); OpenRouter or equivalent for chat and indexing; details - [FAQ §2](tz-cursor-mcp-leadership-faq.en.md) |
| Model training | Vendor privacy mode; contracts with Cyber/Legal if required |
| Access | IT vs business separated; MFA and revoke per company standards (details with IT/Cyber) |
| Chat | Consultations only; logging; staged open |

We do not claim “nothing ever leaves the cloud.” We claim: no live customer data, clear rules, access can be revoked.

---

## 5. What people can do

| | IT | Chat user |
|--|-----|-----------|
| Ask about a configuration | yes | yes (plain language) |
| Code files on the server | read | no |
| Live DB / customer export | no | no |
| Change production config via this contour | no | no |

---

## 6. Decision stages

| When | Decision |
|------|----------|
| Now | Idea, ~$20k/year guide, production-DB rule |
| After pilot | Continue to full IT or stop |
| Before chat for all | Access agreed with IT/Cyber |
| Later | 1C product licenses only if price list and need appear |

---

## Decision wording

> Approve launch of Cursor and search over our configuration exports for IT and (staged) a web help chat for users, without live production databases; budget guide about **$20k/year** external; in-house delivery; hosting and access model to be agreed with IT and Cyber.
