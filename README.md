# PlayArena

**Turn a half-empty court, or a short-handed team, into a full game — at a fair price for everyone.**

PlayArena is a sports matchmaking and venue-capacity marketplace. It treats every booked time-slot as shared inventory: matched to fill a short-handed game, discounted to fill an empty court, and split fairly among whoever shows up — friends or strangers.

This repository documents the product strategy, system architecture, and AI-agent workflow built for PlayArena as a product management capstone project.

---

## The problem

- **30–40%** of casual group bookings start one or two players short (internal estimate).
- **6–8 PM** is the daily crunch window — before and after, courts sit idle with no fast way to advertise open, discounted slots.
- **₹0** is currently spent by venues on a dedicated fill-the-slot + discount layer.

## The solution

Fill-the-slot matchmaking, dynamic off-peak discounting, and host-collected split payments — even for guests with no account.

## Market

| Layer | Definition |
|---|---|
| TAM | India's sports-facility booking market — turf, court & padel/pickleball bookings nationwide |
| SAM | Casual group sports across metro India — football, pickleball, badminton, box cricket, tennis in Tier-1/Tier-2 cities |
| SOM | Phase 1 launch — 15–20 anchor turfs & courts in one metro, seeded through existing WhatsApp game-group organizers |

35M+ racket-sport players nationwide, 70% annualised growth in new pickleball & padel courts (2026), 12.5% projected CAGR for India's online sports-booking market.

## Revenue model

1. **Booking commission** — a cut of every slot booked or filled through the app.
2. **Dynamic discount take-rate** — a small spread on the price movement created.
3. **Venue subscription** — flat fee for demand analytics and automatic discount rules.
4. **Sports brand & gear ads** — reaching an active, local audience.
5. **Premium player pass** — priority matching and early access to popular evening slots.

## Repository structure

```
playarena/
├── README.md                      — this file
├── LICENSE                        — MIT license
├── GLOSSARY.md                    — key terms and definitions
├── docs/
│   ├── architecture.md            — system + AI agent architecture
│   ├── persona.md                 — player and venue-owner personas
│   ├── research-to-product.md     — from problem research to product frameworks
│   ├── setup.md                   — environment and n8n workflow setup
│   ├── relay-workflow.md          — the Relay orchestration workflow, documented in detail
│   └── demo-result.md             — demo execution log and results template
└── skills/
    ├── brand-creator.md           — Brand Creator agent skill
    ├── relay.md                   — Relay agent skill
    └── brief-goal-checker.md      — Brief Goal Checker agent skill
```

## Build snapshot

- **Team:** 7 weeks, 260 resourced development hours, lean cross-functional core team (Lead Full-Stack Developer, Frontend/UI-UX Developer, QA/Scrum Master).
- **Stack:** Next.js + Firebase, Razorpay for payments, Twilio for WhatsApp alerts.
- **Estimated dev cost:** ₹2.73L (freelance team route) vs. ₹6.5–9L (boutique agency route).

## Go-to-market

1. **Phase 1 — anchor venues:** sign 15–20 turfs, pickleball & badminton courts in one metro.
2. **Phase 2 — community seeding:** recruit existing WhatsApp game-group organizers as hosts.
3. **Phase 3 — off-peak discount push:** expand into venue-initiated discounted slots without needing an existing group.

## License

Released under the [MIT License](./LICENSE).

---

*Sports matchmaking + venue-capacity marketplace · business & product strategy review · 2026*
