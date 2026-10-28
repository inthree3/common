# Mock request

From: Client
To: Service
Request ID: task-list-01
Status: proposed

Request: Add `GET /tasks` so the task list can load.
Affected paths: `service/`, `contracts/tasks.md`
Proposed contract: `tasks.md`, version 1; awaiting agreement before implementation.
Acceptance: Return the agreed fields, including an empty-list response. Report the endpoint checks and implementation commit when ready.
Next: Service replies; the integrator records the agreed contract before implementation.
