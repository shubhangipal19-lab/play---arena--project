# Skill: Relay

## Purpose

Acts as the communication and workflow coordinator between different AI agents and users.

## Responsibilities

- Passes information between agents (Research Agent → PRD Agent → Marketing Agent).
- Sends notifications to users, venue owners, and organizers.
- Triggers workflows after certain actions.

## Example output (PlayArena)

A user books a badminton court:
1. Relay informs the Booking Agent.
2. Sends confirmation to the user.
3. Notifies the venue owner.
4. Updates the calendar.
5. Sends a reminder 1 hour before the match.

## Inputs

- Any agent output or system event (booking action, approved brief, completed content).

## Outputs

- Routed messages, notifications, and workflow triggers to the correct next agent, user, venue owner, or organizer.

## How it fits the workflow

Relay is the central messenger of the AI ecosystem — no agent talks to another agent or to a user directly. Full flow detail, including the node-by-node n8n build, is documented in [`../docs/relay-workflow.md`](../docs/relay-workflow.md).
