# Security Policy

## Scope

This repository contains an n8n workflow export and creative reference assets. It may connect to AI providers, Google Drive, SMTP, external HTTP services, and n8n Data Tables when deployed. The repository itself must never contain live secrets or customer data.

## Reporting a vulnerability

If you discover a security issue in the workflow configuration or documentation, do not publish credentials, private URLs, customer records, or exploit details in a public issue. Contact the repository owner privately with the affected file, a clear description, reproduction steps, and a suggested mitigation.

## Deployment requirements

Store API keys, OAuth tokens, SMTP passwords, webhook secrets, and service credentials in n8n’s credential manager or the deployment platform’s secret store. Replace exported credential mappings after import and review every external endpoint before activation.

Public Google Drive sharing is an explicit workflow capability. Operators should enable it only for assets intended for public delivery and should use separate test and production folders. Remove test files and revoke unintended access after validation.

## Data handling

Use synthetic data during testing. Avoid placing customer emails, brand briefs, private asset URLs, or generated customer deliverables in commits, screenshots, logs, or issue discussions.
