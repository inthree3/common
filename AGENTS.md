# Agent instructions

Read this file, your area's AGENTS.md, contracts/README.md, and the shared handoff inbox before working.

## Setup on a shared VM

These steps reproduce our initial worktree setup in a new project. Use an existing Git repository at `/srv/project` with an initial commit on `main`; give each collaborator SSH access and shared write access to the project. Run setup once, before agents start editing:

```sh
cd /srv/project
mkdir -p .worktrees handoffs/messages
printf '\n.worktrees/\nhandoffs/messages/\n' >> .git/info/exclude
git worktree add -b stella/work .worktrees/stella main
git worktree add -b lily/work .worktrees/lily main
git worktree add -b alex/work .worktrees/alex main
```

Each agent starts in its assigned worktree, edits its owned directory, and commits explicit paths there. Worktrees share Git history but have separate files, branches, and staging areas. All agents read and write the **same absolute inbox**, `/srv/project/handoffs/messages/`; contracts travel through Git.

The designated integrator reviews and merges committed owner branches into `main` from `/srv/project`, one at a time, then runs integration checks. Owners merge committed `main` updates into their own branches as needed. Agree on contract changes before integration.

We later moved everyone into `/srv/project` on `main`. To make that transition, pause edits, inspect every worktree for uncommitted work, commit and integrate the intended changes, and verify the combined result before moving sessions. Preserve old worktrees; do not remove or reset unfinished work. After the switch, use only the shared checkout and coordinate overlapping files through the inbox.

## Working checkout

Check `git status` before editing. Coordinate overlapping files through `/srv/project/handoffs/messages/`; leave other agents' changes alone. Stage and commit only explicit paths belonging to your change. Never use `git add .` or `git add -A`. Do not reset or stash the shared checkout. Re-read a file before editing if another agent may have changed it.

## Responsibilities

- Stella: `stella/` — native UI, voice, capture, upload, and voice API.
- Lily: `lily/` — ingestion, analysis, clarification, proposals, dashboard, and execution-report receiver.
- Alex: `alex/` — validated local execution, browser integration, verification, and result explanations.

Use these responsibilities to coordinate; a direct user integration assignment can span areas. Record shared interface changes in handoffs and contracts. Do not claim acknowledgment until the recipient replies.

## Shared rules

No emojis. Minimize code comments. Use plain, functional UI copy; no slogans or taglines.
Keep credentials, recordings, keystrokes, personal data, private provider responses, runtime directories, and release archives out of Git and handoffs. Shared development service credentials are private at `/srv/project/.credentials/services.env`; preserve named-user access and never print values.
