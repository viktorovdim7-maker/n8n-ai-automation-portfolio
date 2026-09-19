# Case Study: E-commerce Automation on a VPS

## Goal

Reduce manual work in a small e-commerce operation by moving repetitive research, content preparation, API calls and publication-related steps into a server-side automation pipeline.

## Environment

- Linux VPS
- Docker
- n8n workflow orchestration
- OpenAI API
- Etsy seller API
- Printful-connected fulfilment flow
- JSON/REST integrations

## Work performed

### 1. API and credential debugging

The system needed several external services to cooperate reliably. The practical work included checking authentication paths, validating request payloads, inspecting API responses and separating configuration problems from application logic problems.

### 2. Server-side execution

The project was designed so routine operations could run on the VPS rather than depending on a local laptop being awake. This required organizing the project for Linux/Docker execution and making failures observable through logs.

### 3. Workflow decomposition

Instead of one opaque script, the process was broken into stages:

1. collect/receive candidate data;
2. validate and normalize fields;
3. enrich or generate structured content;
4. prepare marketplace-ready payloads;
5. call external APIs;
6. verify the response;
7. log success/failure for the next run.

### 4. Reliability work

A recurring engineering problem was the difference between "the API call returned" and "the business task actually succeeded". The workflow therefore needs explicit verification, useful error messages and retry-safe behavior.

## What this demonstrates

This case is useful because it combines the same skills that appear in many client automation tasks:

- connecting multiple APIs;
- handling JSON transformations;
- debugging authentication and request errors;
- deploying automations on a VPS;
- separating manual approval steps from autonomous steps;
- keeping secrets out of source control;
- verifying business outcomes rather than assuming success from a 2xx response.

## Privacy and security

This public repository does **not** contain production credentials, customer information, private API responses, server addresses or marketplace secrets. Examples are intentionally sanitized.

## Current status

The production project is an ongoing engineering case rather than a finished commercial product. This portfolio focuses on the technical patterns and problem-solving methods that can be reused for client work.
