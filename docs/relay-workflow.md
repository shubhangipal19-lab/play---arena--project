# Relay Workflow

Relay is PlayArena's central messenger and orchestrator. It sits between agents (and between the product and its users) so no agent has to know how to talk to any other agent directly — everything routes through Relay.

## Purpose

Acts as the communication and workflow coordinator between different AI agents and users.

## Responsibilities

- Passes information between agents (Research Agent → PRD Agent → Marketing Agent).
- Sends notifications to users, venue owners, and organizers.
- Triggers workflows after certain actions.

## Reference flow: a user books a badminton court

This is the canonical example Relay is built around:

1. A user books a badminton court.
2. **Relay** informs the **Booking Agent**.
3. **Relay** sends a booking confirmation to the user.
4. **Relay** notifies the venue owner.
5. **Relay** updates the calendar.
6. **Relay** sends a reminder 1 hour before the match.

```
User books court
      │
      ▼
   [ Relay ]
      │
      ├──→ Booking Agent (informed)
      ├──→ User (confirmation sent)
      ├──→ Venue owner (notified)
      ├──→ Calendar (updated)
      └──→ Reminder queued (T-1 hour before match)
```

## How Relay connects to Brand Creator and Brief Goal Checker

Relay is not limited to booking events. Any time an agent produces output that another agent or a user needs, Relay is the handoff point:

- When the **Brief Goal Checker** approves a new feature or campaign idea, Relay passes that approval to the **Brand Creator** to generate the actual marketing content.
- When the **Brand Creator** finishes a caption, campaign, or promotional copy, Relay routes it to the intended channel (e.g., queued for posting, sent to a reviewer, or delivered to the requester).
- If the **Brief Goal Checker** rejects an idea, Relay is what closes the loop — notifying whoever proposed it, with the checker's reasoning, instead of the idea silently going nowhere.

