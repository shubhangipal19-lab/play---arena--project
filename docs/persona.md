# Personas

PlayArena is a two-sided marketplace. Every product decision is checked against both sides — a player short on teammates, and a venue with an empty slot.

---

## Persona 1 — The Player

**"Get me into a game tonight, without spending 20 minutes messaging friends who can't make it."**

| | |
|---|---|
| Role | Casual player — football, badminton, pickleball, or box cricket |
| Context | Plays regularly with a shifting group of friends and acquaintances in a metro city |
| Core job (JTBD) | Fill a team or find a game fast, without a WhatsApp scramble |

**Goals**
- Find a nearby game that needs 1–2 more people and join in.
- Pay less as more players fill the slot.
- Book the whole slot for a fixed friend group when needed.
- Trust that people they're matched with will actually show up and play fair.

**Frustrations (from the problem research)**
- 30–40% of casual group bookings start one or two players short.
- No fast way to find or advertise "3 spots open" games outside informal WhatsApp groups.
- Joining strangers feels risky with no visible reliability or skill signal.

**What PlayArena gives them**
- A visible, read-only profile before joining strangers, with host approval.
- A three-part trust report (skill accuracy, reliability, sportsmanship) instead of one opaque score.
- No account required to join as a guest; the host handles the split.

---

## Persona 2 — The Venue Owner

**"A small discount beats zero bookings every time."**

| | |
|---|---|
| Role | Owner/manager of a turf, pickleball court, or badminton court |
| Context | Sells peak-hour slots easily; off-peak hours (outside the 6–8 PM crunch window) often sit empty |
| Core job (JTBD) | Turn slots that would otherwise sit empty into revenue, without giving up pricing control |

**Goals**
- Advertise "3 spots open, 40% off, starts in 90 minutes" fast, without manual effort.
- Set their own floor price and discount rules.
- Get demand analytics to understand when and why slots go unsold.
- Opt out of dynamic discounting any time, with no lock-in.

**Frustrations (from the problem research)**
- Off-peak hours go unsold because there's no fast way to advertise last-minute discounted availability.
- Existing booking apps (Playo/Hudle-style) offer basic or no venue analytics.
- No existing tool solves who-owes-whom for a mixed group of members and guests.

**What PlayArena gives them**
- Dynamic off-peak discounting with a guaranteed price floor.
- A venue subscription tier for demand analytics and automatic discount rules.
- Never pushed below a fair rate; subscription-based, not locked in.

---

## How these personas drive prioritization

Both personas map directly to the RICE-scored features in [`research-to-product.md`](./research-to-product.md):
- **Slot matchmaking feed** (RICE 96.0) → serves the Player's core job.
- **Dynamic discount pricing** (RICE 100.8) → serves the Venue Owner's core job.

The AARRR funnel's biggest identified leak — Acquisition → Activation — applies most directly to the Player persona: getting someone from "found PlayArena" to "actually joined or booked a game" is the current priority fix, ahead of spending more on acquisition.
