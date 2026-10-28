# Mock project instructions

Read your area's instructions, `contracts/tasks.md`, and the shared inbox before editing.

- Client owns `client/`; Service owns `service/`; QA owns `qa/`.
- During the worktree phase, use `/srv/project/.worktrees/<owner>` on `<owner>/work`. The designated integrator alone merges into `/srv/project` on `main`.
- Send cross-area requests through `/srv/project/handoffs/messages/`. Write replies as new files referencing the request ID.
- Agree on interface changes with affected owners before the integrator updates contracts.
- Check Git status, preserve unrelated edits, and stage explicit paths. Report checks and remaining work accurately.
- If the team switches to a shared checkout, pause and integrate work first, then update these instructions so there is one active mode.
