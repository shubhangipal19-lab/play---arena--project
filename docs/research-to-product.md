# Research to Product

How PlayArena moved from raw problem research to a prioritized, structured product plan using four frameworks.

## 1. The research

**Problem research (internal survey estimate of casual sports group organizers, class research, 2026):**
- 30–40% of casual group bookings start 1–2 players short.
- 6–8 PM is the daily crunch window — courts sit idle before and after it.
- ₹0 is currently spent by venues on a dedicated fill-the-slot + discount layer.

**Market research:**
- 35M+ racket-sport players nationwide.
- 70% annualised growth in new pickleball & padel courts (2026).
- 12.5% projected CAGR for India's online sports-booking market.

**Competitive research:** no existing player (WhatsApp groups, Playo/Hudle-style apps, Khelomore/local turf sites, direct venue booking) combines fill-the-slot matching, dynamic discounting, *and* venue analytics. PlayArena is positioned to be first to combine all three.

## 2. Jobs To Be Done (JTBD)

> *"Get me into a game tonight, without spending 20 minutes messaging friends who can't make it."*

This single statement is the filter every screen and feature is checked against — the goal is never a generic "booking app," but a fast answer to a specific job on each side of the marketplace (see [`persona.md`](./persona.md) for the Player and Venue Owner versions of this job).

## 3. RICE prioritization

RICE score = (Reach × Impact × Confidence) ÷ Effort. Highest score wins the next build slot.

| Feature | Reach | Impact | Confidence | Effort | RICE Score |
|---|---|---|---|---|---|
| Dynamic discount pricing | 8 | 9 | 7 | 5 | **100.8** |
| Slot matchmaking feed | 9 | 8 | 8 | 6 | **96.0** |

Dynamic discount pricing scored highest, directly shaping the Priority 1 MVP scope in [`architecture.md`](./architecture.md).

## 4. AARRR growth funnel

| Stage | Volume (modeled) |
|---|---|
| Acquisition | 1000 |
| Activation | 600 |
| Retention | 400 |
| Referral | 150 |
| Revenue | 60 |

**Biggest leak: Acquisition → Activation.** The product decision this drives: fix onboarding before spending more on ads — a direct constraint on go-to-market sequencing (see below).

## 5. The flywheel model

```
More slots listed → Players find & fill fast → Venues see better fill-rate → Trust & engagement grow → (loop)
```

Every filled slot also generates a rating, improving match quality and trust for the next round. The weakest link sets the speed of the whole wheel — currently, that weak link is Activation (per the AARRR data above), not Acquisition.

## 6. From frameworks to go-to-market

The frameworks above directly produced the three-phase launch sequence:

1. **Phase 1 — anchor venues:** sign 15–20 turfs, pickleball & badminton courts in one metro to seed real inventory before trying to fix Activation with more users.
2. **Phase 2 — community seeding:** recruit existing WhatsApp game-group organizers as hosts, avoiding a cold start with strangers — directly addressing the "trust with strangers" and "cold-start liquidity" risks.
3. **Phase 3 — off-peak discount push:** expand into venue-initiated discounted slots that don't need an existing group at all, once liquidity and trust exist.

This sequencing is deliberate: it fixes the Activation leak identified in the AARRR data (Phase 1–2) before scaling Acquisition-driving mechanics like open discounting (Phase 3).
