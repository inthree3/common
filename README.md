# Common

A shared workspace for coding agents.

Stella, Lily, and Alex connect over SSH to one VM and work in the same Git checkout. Saved edits are immediately visible to everyone; Git records the agreed checkpoints.

## Layout

```text
/srv/project/
├── stella/              # App and voice API
├── lily/                # Analysis and suggestions
├── alex/                # Local execution system
├── AGENTS.md            # Collaboration rules
├── contracts/           # Interface agreements
├── handoffs/messages/   # Requests and progress updates
└── tools/               # Shared build, test, and deployment commands
```

This README describes the starting layout. Add directories and tools as they become necessary.

## Workflow

1. Read `AGENTS.md` and relevant contracts before starting.
2. Announce the task and files you intend to edit in `handoffs/messages/`.
3. Agree on an interface in `contracts/` before changing behavior another agent uses.
4. Make the change, run relevant checks, and leave a short handoff.
5. Alex coordinates Git commits and shared builds.

## Collaboration rules

Copy these rules into `AGENTS.md` when setting up the workspace:

- Work in your own directory by default. Agree with the owner before editing elsewhere.
- Only one agent edits a file at a time. Wait for acknowledgement when ownership overlaps.
- Alex alone stages, commits, and pushes to `main`. Stage explicit paths and review the staged diff.
- Everyone shares the current branch and staging area. Never switch branches, reset, stash, or clean while others are working.
- Pause edits to affected files during a shared build or test run. Record what was checked and the result.
- Preserve other agents' work. Ask before overwriting or deleting it.
- Keep credentials out of code, contracts, and messages.
- Deploy only when explicitly requested.

These are coordination rules, not enforced file locks.

## Handoffs

Use one Markdown file per message, named `YYYYMMDD-HHMMSS-agent-topic.md`:

```markdown
From: stella
To: alex
Status: ready

Task: Add the voice endpoint.
Files: stella/voice/...
Contract: contracts/voice.md
Checks: command and result
Next: Review and commit.
```

## Start

On the shared VM, clone once into an empty destination:

```sh
git clone git@github.com:inthree3/common.git /srv/project
cd /srv/project
mkdir -p stella lily alex contracts handoffs/messages tools
```

Use a writable parent directory and configure SSH access first. Each agent then connects to that same VM, enters `/srv/project`, and follows the rules above.

Start with files and Git. Add automation when coordination actually needs it.
