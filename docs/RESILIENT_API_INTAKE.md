# Resilient API Intake Example

This sanitized n8n workflow demonstrates a more realistic automation pattern than a single linear demo.

## Flow

`Webhook → validate/normalize → route by business rule → prepare deterministic output → respond`

It demonstrates:

- input validation before downstream work;
- normalization of user-supplied fields;
- branching based on a business rule;
- a stable external ID carried through the workflow;
- an idempotency key pattern for retry-safe downstream integrations;
- separate response paths for high- and normal-priority work;
- no credentials or private infrastructure details in source control.

The example deliberately stops before a real CRM, email provider, marketplace or paid AI API. In a client workflow, those nodes can be inserted after routing while preserving the validation and idempotency pattern.

## Test payload

```json
{
  "externalId": "demo-1001",
  "email": "customer@example.com",
  "message": "Urgent: please review this today"
}
```

Expected classification: `high`.

A non-urgent message follows the normal path.

## Security

This is a portfolio-safe example. It contains no production credentials, customer data, server addresses or private API responses.
