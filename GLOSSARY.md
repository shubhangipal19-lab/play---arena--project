# Glossary

Terms used throughout this repository, in alphabetical order.

### AARRR (Pirate Metrics)
Growth funnel framework: **A**cquisition → **A**ctivation → **R**etention → **R**eferral → **R**evenue. Used in `docs/research-to-product.md` to identify PlayArena's biggest leak (Acquisition → Activation).

### Anchor venue
One of the 15–20 turfs, pickleball, or badminton courts signed in Phase 1 of go-to-market to seed real, bookable inventory before opening the marketplace to the public.

### Fill-the-slot matchmaking
PlayArena's core mechanic: a host posts an open spot in an already-booked game, other players join with a visible read-only profile, and the price auto-splits as more players join.

### Host-collected split payment
PlayArena calculates each participant's share of a booking; the host collects payment (cash, UPI link, or covers it) rather than PlayArena processing payments directly. Keeps guests welcome without needing an account, and keeps the MVP out of payment-processor regulation.

### JTBD (Jobs To Be Done)
Product framework centered on the job a user is "hiring" the product to do. PlayArena's core JTBD: *"Get me into a game tonight, without spending 20 minutes messaging friends who can't make it."*

### RICE score
Prioritization framework: **R**each × **I**mpact × **C**onfidence ÷ **E**ffort. Used to rank PlayArena features — e.g., dynamic discount pricing scored 100.8, the highest of any evaluated feature.

### SAM (Serviceable Addressable Market)
Casual group sports across metro India — football, pickleball, badminton, box cricket & tennis in Tier-1/Tier-2 cities where demand outpaces supply.

### SOM (Serviceable Obtainable Market)
PlayArena's Phase 1 launch target: 15–20 anchor turfs & courts in one metro city.

### TAM (Total Addressable Market)
India's sports-facility booking market — turf, court & padel/pickleball bookings nationwide.

### Trust layer
PlayArena's rule-based reputation system (not a black-box model) combining self-rated skill, peer ratings, and an aggregation engine into three separate, visible scores: **skill accuracy**, **reliability**, and **sportsmanship**.

---

## AI agent / skill terms

### Agent
An automated, task-scoped worker in PlayArena's internal AI workflow (built and orchestrated in n8n) that performs one job — e.g., research, brand content, or workflow coordination — and hands off its output to the next agent or system.

### Brand Creator
The agent responsible for PlayArena's brand identity and marketing content — captions, taglines, campaign ideas, and visual identity suggestions. See `skills/brand-creator.md`.

### Brief Goal Checker
The agent that validates whether a proposed feature or task aligns with PlayArena's product vision and user goals before it moves forward. See `skills/brief-goal-checker.md`.

### Relay
The orchestration agent that passes information between other agents (e.g., Research Agent → PRD Agent → Marketing Agent) and triggers downstream notifications and workflows. See `skills/relay.md` and `docs/relay-workflow.md`.
