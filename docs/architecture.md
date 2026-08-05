# Architecture

PlayArena has two architecture layers: the **product/tech stack** that runs the booking and matchmaking app, and the **AI agent workflow** (built in n8n) that automates brand content, cross-agent coordination, and product-vision checks.

## 1. Product tech stack

| Layer | Choice | Notes |
|---|---|---|
| Frontend | Next.js / React + Tailwind | Responsive web UI, filter system, component library, mobile-optimized |
| Backend / Auth / DB | Firebase | Auth, core schema, hosting & DB on free tier under 10GB at launch |
| Payments | Razorpay | 2% per transaction; UPI-linked auto-split for members |
| Notifications | Twilio | WhatsApp API for booking confirmations & alerts |
| Concurrency | Real-time slot-locking | Prevents double-booking during the matchmaking join flow |

### Core modules (Priority 1 — MVP)

Auth, profiles, venue & slot management, matchmaking, join/approval flow, capacity locking, deposits, check-in, ratings, dashboards.

### Priority 2 — smart marketplace features

Recommendations, rule-based matchmaking, configurable discounts, occupancy analytics, waitlists, moderation, promo codes.

### Priority 3 — future placeholders

ML-based pricing & ranking, real payment settlement, maps/geocoding, SMS/WhatsApp expansion, calendar sync, subscription billing.

## 2. Booking flow architecture

Two demand paths feed the same matched game:

**Path A — book the whole slot**
1. Search & select a slot
2. Book & pay the full price
3. Invite friends — split optional

**Path B — join a short-handed game**
1. Host posts an open spot
2. Players join — profiles visible, read-only
3. Host approves; price auto-splits as more join

## 3. Trust layer architecture

A rule-based aggregation engine (not a black-box model) at launch:

```
Self-rated skill at signup ─┐
                             ├─→ Aggregation engine → 3-part trust report
Peer ratings after each game ┘
```

The three scores stay **separate and visible** — never merged into one opaque number a player can't see or appeal:
- **Skill accuracy** — does self-rated level match how peers rate actual play (feeds fair matching)
- **Reliability** — punctuality, no-shows, cancellations
- **Sportsmanship** — friendliness and fair play

## 4. AI agent workflow architecture (n8n)

PlayArena's internal product/marketing operations run on a small agent pipeline orchestrated in n8n:

```
Research Agent → PRD Agent → Marketing Agent
                     │
                     ▼
                  Relay (orchestrator)
              ┌──────┴──────┐
              ▼             ▼
      Brand Creator   Brief Goal Checker
              │             │
              ▼             ▼
      Notifications    Go / No-go on
      to users, venue   proposed features
      owners, organizers
```

- **Relay** is the central messenger: it passes information between agents, sends notifications, and triggers downstream workflows after key actions (e.g., a court booking).
- **Brand Creator** generates on-brand marketing content — captions, taglines, campaign ideas — once a brief clears the Brief Goal Checker.
- **Brief Goal Checker** gates new feature or campaign ideas against PlayArena's product vision before any agent spends effort on them.

Full detail on the Relay orchestration flow is in [`relay-workflow.md`](./relay-workflow.md). Individual agent responsibilities are documented under [`/skills`](../skills).

## 5. Risk-driven design decisions

| Risk | Architectural mitigation |
|---|---|
| Trust with strangers | ID/phone verification before joining; visible read-only profiles; two-way ratings |
| No-shows | Refundable deposit on booking; visible reliability score per player |
| Venue buy-in | Venues set their own floor price; subscription model, not lock-in; opt-out any time |
| Cold-start liquidity | Phase 1 anchor venues + Phase 2 WhatsApp organizer seeding before open matchmaking |
| Pricing integrity | Discount floor & caps — venues never pushed below a fair price |
| Privacy | Only first name and rating shown until both sides confirm |
