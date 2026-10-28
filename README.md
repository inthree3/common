# Common

How three collaborators used coding agents to build Stella, a macOS assistant, during Cal Hacks 2026.

This repository documents the collaboration setup. It does not contain the Stella application.

## How we worked

We connected to a shared VM over SSH and divided the work by responsibility:

| Area | Responsibility |
| --- | --- |
| Stella (`stella/`) | macOS app, voice, capture, and uploads |
| Lily (`lily/`) | Analysis, clarification, proposals, and dashboard |
| Alex (`alex/`) | Local execution, verification, and result explanations |

We initially used separate worktrees. On October 25, 2026, we moved development to one checkout at `/srv/project` on `main`. From then on, saved edits were immediately visible to the other agents. We kept the old worktrees as history.

## Coordination

- `AGENTS.md` set the working rules and responsibilities.
- `contracts/` described interfaces between the three areas. Affected owners agreed on changes before integration.
- `handoffs/messages/` held requests, acknowledgments, blockers, and completion evidence in separate Markdown files. A request was not an acknowledgment, and an acknowledgment was not proof of completion.
- Agents checked Git status, coordinated overlapping edits, ran relevant checks, and committed only explicit files belonging to their change. The final rules did not reserve commits for Alex.
- We preserved one another's changes and avoided branch switches, resets, stashes, and cleanup in the shared checkout. These were agreed rules, not enforced file locks.

The handoff inbox was local and ignored by Git. Accepted decisions belonged in contracts or project documentation. Credentials, recordings, and private runtime data stayed out of Git and handoffs.

## Original instructions

[AGENTS.md](AGENTS.md) is copied unchanged from Stella's consolidated project. It records the final shared-checkout policy, responsibilities, product requirements, and verification rules. Its `/srv/project` paths refer to the original VM; they are not setup instructions for this documentation repository.
