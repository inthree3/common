# Mock agreement: task list v1

Status: agreed by Client and Service for this fictional example.

`GET /tasks` returns HTTP 200 with:

```json
{"tasks": [{"id": "task-1", "title": "Order paper", "completed": false}]}
```

`id` and `title` are strings; `completed` is a boolean. An empty list is `{"tasks": []}`. Client owns rendering; Service owns the response. Both owners must agree before changing fields or their meanings.
