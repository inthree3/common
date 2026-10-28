# Common

This repository details how Alex, Lily and Stella built Stella (yes, named after a team member) during Cal Hacks 2026.

## How we worked

We connected to a shared VM over SSH and divided the work by responsibility:

| Area | Responsibility |
| --- | --- |
| Stella (`stella/`) | macOS app, voice, capture, and uploads |
| Lily (`lily/`) | Analysis, clarification, proposals, and dashboard |
| Alex (`alex/`) | Local execution, verification, and result explanations |

We initially used separate worktrees and later merged development to one checkout on the `main` branch. From then on, saved edits were immediately visible to the other agents.

## Coordination

- `AGENTS.md` set the working rules and responsibilities.
- `contracts/` described interfaces between the three areas. Affected owners agreed on changes before integration.
- `handoffs/messages/` held requests, acknowledgments, blockers, and completion evidence in separate Markdown files. A request was not an acknowledgment, and an acknowledgment was not proof of completion.
- Agents checked Git status, coordinated overlapping edits, ran relevant checks, and committed only explicit files belonging to their change.
- We preserved one another's changes and avoided branch switches, resets, stashes, and cleanup in the shared checkout.

## Instructions and examples

[AGENTS.md](AGENTS.md) adapts our project instructions and adds setup steps for the worktree phase and the later shared checkout.

[Mock task-board workspace](examples/task-board/README.md) shows a folder layout, ownership rules, an interface agreement, and a request/reply pair. All example names, tasks, and check results are fictional.
