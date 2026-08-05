# Skill: Brief Goal Checker

## Purpose

Ensures every task or project aligns with PlayArena's product objectives before execution.

## Responsibilities

- Checks whether a feature solves a real user problem.
- Validates if the request aligns with PlayArena's vision.
- Verifies business goals, user goals, and success metrics.
- Flags incomplete or unclear requirements.

## Example evaluations (PlayArena)

**Proposal:** *"Let's add a movie ticket booking feature."*
- ❌ Doesn't align with PlayArena's mission of sports and fitness.
- ❌ Doesn't solve the target users' core problem.
- **Verdict:** recommend rejecting or revising the idea.

**Proposal:** *"Add AI teammate matching."*
- ✅ Solves players' problem of finding teammates.
- ✅ Increases engagement and retention.
- ✅ Matches the product vision.
- **Verdict:** approve.

## Inputs

- A proposed feature, campaign, or task brief.

## Outputs

- A pass/fail verdict with reasoning, referencing PlayArena's user goals and vision.

## How it fits the workflow

Brief Goal Checker is the gate before **Brand Creator** or any build effort starts. **Relay** routes the brief here first; only approved briefs move forward (see [`../docs/relay-workflow.md`](../docs/relay-workflow.md)).

## Reference for evaluation

Use the JTBD statement and problem research in [`../docs/research-to-product.md`](../docs/research-to-product.md) as the standard every proposal is checked against.
