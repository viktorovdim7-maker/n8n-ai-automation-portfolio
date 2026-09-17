# Architecture Notes

## Reference pattern

```text
External event / schedule
        |
        v
      n8n
        |
        +--> Validate + normalize input
        |
        +--> Business rules / AI enrichment
        |
        +--> REST API / webhook calls
        |
        +--> Verify downstream result
        |
        +--> Log outcome / error path
```

## Design principles

### Keep orchestration separate from credentials

Credentials should live in n8n credential storage, environment variables or a secret manager — never in workflow exports committed to GitHub.

### Validate before expensive work

Reject malformed payloads before calling paid APIs or creating downstream records.

### Prefer structured AI output

When an LLM is used inside an automation, ask for constrained JSON and validate required fields before the workflow continues.

### Make retries safe

A retry should not create duplicate CRM records, duplicate marketplace listings or repeated emails. Use stable external IDs and idempotency checks where the target API supports them.

### Verify business success

A successful HTTP response does not always mean the intended operation happened. Check returned IDs/status fields and, for important operations, query the downstream system again when appropriate.

### Log enough to debug

Record timestamps, workflow stage, external request identifier and sanitized error details. Never log secrets.

## Typical integrations

This pattern can be adapted to:

- lead forms → CRM → notification;
- email → AI extraction → spreadsheet/database;
- e-commerce catalog → AI enrichment → marketplace API;
- support inbox → classification → ticket routing;
- scheduled data sync between SaaS tools;
- webhook-based order and fulfilment workflows.
