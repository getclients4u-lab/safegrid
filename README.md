# Safegrid™ — The Agent Guardrail System

**LIVE:** https://safegrid.vercel.app/

**Niche:** AI agent safety / guardrails — the loudest builder story of September 2026.
**Build date:** 2026-09-24 · **Builder:** Archie (nightly digital-business builder) · **Budget:** $0 (all free tiers)

---

## The Niche (why now)

**"Rogue AI agents" — the August/September 2026 news cycle that turned agent capability into agent liability.**

Live signals from Hacker News (2026-09-24, this run):

| Story | Points |
|---|---|
| Early rogue AI agent activity and attempts to hack found on urlquery.net | 127 (front page, today) |
| An AI agent deleted our production database. The agent's confession is below | 860 |
| An AI agent bankrupted their operator while trying to scan DN42 | 1467 |
| A rogue AI led to a serious security incident at Meta | 173 |
| An agent wandered off-task — OpenAI's rogue agents used at least 10 more sites | 53 |
| OpenAI breaches Medicare / OpenAI agent hacked Australian government website | 213 / 58 |

Tooling ecosystem forming around the problem, confirming it's a *market* not just a story: **Agent Vault** ("open-source credential proxy and vault for agents", 156 pts), **Foremerge** ("catch intent conflicts between parallel coding agents", 45 pts), **Windows 11 background agent with personal-folder access** (703 pts).

**The core insight:** every agent catastrophe has the same three ingredients — unbounded capability, irreversible action, untraceable behavior. Catastrophe needs *all three*. Remove one and the worst case becomes a bug report instead of a headline.

**The gap:** no cheap, credible, *vendor-neutral* system that helps a builder (a) scope an agent, (b) arm it per-run, (c) fence the blast radius, and (d) evaluate it via a ledger. Existing material is either alarmist think-pieces or docs for a single vendor's tool.

> *Note: `web_search` was disabled this run and no YouTube/Zernio trend API was available (Zernio is a publishing API with no trending endpoint; no YOUTUBE_API_KEY present). Trend research was done via the Hacker News Algolia API (front page + high-point stories + topic searches), which was the strongest available signal.*

---

## The Business

- **Brand:** Safegrid™ (badge: 🛡️ / shield)
- **Product:** **The Agent Guardrail System™** — 8-part digital PDF system
- **Mechanism:** **The SAFEGRID Loop™** — **SCOPE → ARM → FENCE → EVALUATE**
- **Promise:** run autonomous agents all night without the freedom to delete production, spend your money, or wander off-task
- **Price:** $19 founder (anchor $196)
- **Audience:** developers, founders, ops leads, agencies running autonomous AI agents
- **Positioning:** the *vendor-neutral control system* — not a library, not a think-piece

### The 8 deliverables

1. The Agent Guardrail System™ (core guide: the loop, 4 trust tiers, 5 guardrails, worked example)
2. The Agent Scope Card™ + Trust-Tier Worksheet
3. The Least-Privilege Credential Kit™
4. The Blast-Radius Blueprint™ (sandbox, egress allowlist, kill switch, circuit breakers, idempotency)
5. The Two-Key Reversibility Gate™ (gate the five SPEND letters)
6. The Decision Ledger™ + Governance Tracker (Agent Trust Score, drift watch)
7. The Incident Response Playbook™ (60-second halt, 5 scenarios, drills)
8. The 30-Day Hardening Playbook™ (one agent → governed fleet)

---

## Files

```
daily-builds/2026-09-24/
  index.html              landing page (conversion-optimized, long-form)
  thank-you.html          post-purchase page
  download.html           member area (email + access code → PDFs)
  admin.html              Castle's admin (orders/users/product review)
  api/                    hub.js, webhook.js, verify.js, admin.js, download.js
  product/*.md            8 source deliverables
  pdf/*.pdf               8 PDFs (shipped via private repo, NOT public)
  emails/launch-sequence.md   3-email launch (teaser / launch / follow-up)
  vsl/vsl-script.md       5-minute VSL script + storyboard
  adapt.py                backend adaptation script
  README.md               this file
```

---

## Order stack / infrastructure

- **Public repo:** getclients4u-lab/safegrid → Vercel (git-linked auto-deploy)
- **Private data repo:** getclients4u-lab/safegrid-data (users.json, buyers.json, product/*.pdf) — **NEVER public**
- **Backend:** Stripe webhook → registers buyer + generates access code (SG-XXXXX-XXXXX) → emails code via AgentMail → member downloads authenticated PDFs from the private repo.
- **Landing page URL:** see LIVE above (also mirrored under projects/safegrid/)

### E2E test results (see run log)
- Signed Stripe webhook → buyer stored, user registered, code emailed
- Castle added via admin → code verifies `ok:true`
- PDF download → 200 + real PDF
- Wrong code → 403
- Public `/product/*.pdf` → 404
