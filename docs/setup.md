# Setup

This project has two setup tracks: the **product app stack** (Next.js + Firebase) described in the build roadmap, and the **AI agent workflow demo** (n8n) used to demonstrate the Brand Creator → Relay → Brief Goal Checker pipeline.

This doc covers the n8n workflow demo setup, since that's the runnable artifact in this repository. The app stack setup is scoped for the 7-week / 260-hour build described in [`architecture.md`](./architecture.md) and is not yet implemented in code.

## Prerequisites

- [n8n](https://n8n.io) — self-hosted or n8n Cloud account
- Node.js 18+ (only if self-hosting n8n locally)
- A free tier account with any notification channel you want to test Relay against (e.g., email, Slack, or WhatsApp via Twilio sandbox)

## 1. Install n8n

**Option A — n8n Cloud (fastest to demo)**
1. Create a free account at [n8n.io](https://n8n.io).
2. Open a new workflow canvas.

**Option B — Self-hosted (local)**
```bash
npm install n8n -g
n8n start
```
n8n will be available at `http://localhost:5678`.

## 2. Import the PlayArena agent workflow

1. In n8n, go to **Workflows → Import from File**.
2. Import the workflow file for the Relay orchestration pipeline (see [`relay-workflow.md`](./relay-workflow.md) for the node-by-node structure to build if you're recreating it manually).
3. Confirm three logical stages exist on the canvas: **Trigger → Relay → Agent nodes (Brand Creator / Brief Goal Checker) → Notification**.

## 3. Configure credentials

- Add credentials for any notification channel Relay will send to (email/SMS/WhatsApp).
- If testing the Brief Goal Checker against a real brief format, set up a simple form trigger or webhook node to submit a feature idea as input.

## 4. Run the demo

1. Trigger the workflow manually from the n8n canvas, or via the configured webhook/form.
2. Watch execution move through: **Relay receives the trigger → routes to the relevant agent (Brand Creator or Brief Goal Checker) → Relay sends the resulting notification/output.**
3. Record what happened in [`demo-result.md`](./demo-result.md) — that file is a template until a real run is logged there.

## 5. What's not yet built

Per the Priority 3 placeholders in [`architecture.md`](./architecture.md), the following are out of scope for this demo and intentionally deferred:
- Real payment settlement (Razorpay integration)
- Live WhatsApp/SMS delivery (Twilio integration)
- The actual Next.js/Firebase booking app — this repository documents its architecture and roadmap, not a running build
