# n8n & AI Automation Portfolio

Practical automation work focused on **n8n, REST APIs, webhooks, OpenAI API, Linux/VPS and Docker**.

I build and repair workflows that turn repetitive business processes into reliable automations. My focus is not just connecting nodes — it is getting the workflow to a verifiable working result, handling edge cases, and keeping credentials and sensitive data out of public code.

## What I can help with

- Diagnose and repair broken n8n workflows
- Build API and webhook integrations
- Connect AI models to business workflows
- Transform and validate JSON/data between services
- Automate lead intake, routing and response preparation
- Run automations on Linux/VPS with Docker
- Add retries, error paths and operational logging

## Real project case study

This repository is based on a real automation project for an e-commerce workflow running on a VPS.

The project work includes:

- n8n workflow orchestration
- OpenAI API integration
- Etsy seller API integration
- Printful-connected fulfilment workflow
- Docker/Linux deployment on a remote VPS
- JSON/API debugging and data transformation
- Moving from manual operations toward server-side automation

The production system is still being hardened, so this portfolio only publishes **sanitized examples** and architecture notes. No API keys, credentials, customer data or private production configuration are included.

See:

- [Case study](docs/CASE_STUDY.md)
- [Architecture](docs/ARCHITECTURE.md)
- [Sanitized n8n example](workflows/lead-triage-sanitized.json)

## Example workflow: fast lead triage

The included workflow demonstrates a common paid automation task:

`Webhook → validate payload → classify lead → prepare structured output → return response`

It is intentionally credential-free and safe to publish. In a client project, the classification step can be replaced with OpenAI, a CRM, a database, email, Slack, Telegram or another API.

## How I work

1. Define the expected result.
2. Inspect the existing workflow or API surface.
3. Reproduce the failure or build the smallest working path.
4. Add validation and error handling.
5. Test with realistic payloads.
6. Deliver a working workflow plus short handoff notes.

## Availability

Open to **paid trials, urgent workflow repairs, fixed-price automation tasks and longer-term n8n / AI automation work**.

Primary tools: `n8n` · `OpenAI API` · `REST` · `Webhooks` · `Docker` · `Linux/VPS` · `JSON`
