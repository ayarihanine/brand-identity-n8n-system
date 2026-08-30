# Contributing

Thank you for helping improve the Brand Identity Builder. This repository contains an n8n workflow export and the Freshy Matcha visual reference package. Contributions should preserve both workflow reliability and presentation quality.

## Before opening a change

Read the [README](README.md) and [Workflow Operations Guide](docs/WORKFLOW_OPERATIONS.md). Make sure the proposed change has a clear purpose, does not expose credentials, and does not alter production-specific identifiers without documenting the impact.

## Workflow changes

When changing the n8n export, validate that the JSON remains well-formed and that node names, connections, expressions, credentials, and downstream field mappings remain coherent. Describe the affected branch and include the test path used to verify it.

## Visual changes

Keep the Freshy Matcha system consistent with its documented typography, color palette, editorial tone, and natural product photography. Use descriptive filenames and update the asset manifest when adding or replacing visual material.

## Commit style

Use concise imperative commit messages. Prefer focused commits such as `Document workflow operations`, `Refresh brand application board`, or `Fix approval branch mapping`.

## Pull request checklist

| Check | Requirement |
| --- | --- |
| Scope | The change has a focused purpose and does not include unrelated generated files. |
| Validation | JSON, Markdown links, and relevant media files have been checked locally. |
| Security | No API keys, passwords, OAuth tokens, private URLs, or customer data are included. |
| Documentation | User-facing workflow or asset changes are reflected in the documentation. |
| Reviewability | The description explains what changed, why it changed, and how it was tested. |
