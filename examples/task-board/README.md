# Mock task-board workspace

Everything here is fictional, including the reported checks. It illustrates our coordination method without reproducing project messages.

```text
/srv/project/
├── AGENTS.md
├── client/
│   └── AGENTS.md
├── service/
│   └── AGENTS.md
├── qa/
│   └── AGENTS.md
├── contracts/
│   └── tasks.md
├── handoffs/messages/
│   ├── 20300115-100000-client-service-task-list.md
│   └── 20300115-103000-service-client-task-list.md
└── .worktrees/
    ├── client/     (branch client/work; full checkout)
    ├── service/    (branch service/work; full checkout)
    └── qa/         (branch qa/work; full checkout)
```

Each worktree contains the whole repository; ownership limits which files its agent edits. The inbox is shared at the absolute path above, outside the worktrees. In a live workspace it is ignored by Git; these mock messages are tracked so readers can inspect them.

1. The client owner requests an endpoint using the shared inbox.
2. Both owners agree on `contracts/tasks.md`; the integrator commits that agreement to `main`, and owners merge it into their branches.
3. The service owner implements and checks the endpoint, commits its files, and replies with evidence. The reply does not claim that the client integration is done.
4. The integrator merges the implementation; the client owner merges `main`, connects the UI, and requests an integration check from QA.

See the root [setup instructions](../../AGENTS.md) for worktree commands; use `client`, `service`, and `qa` as the owners for this fictional project.
