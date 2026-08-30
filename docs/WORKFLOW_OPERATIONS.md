# Workflow Operations Guide

This guide explains how to move the **Brand Identity Builder** workflow from import to a controlled test run. The workflow export is stored at [`../n8n system/Brand Identity Builder.json`](../n8n%20system/Brand%20Identity%20Builder.json).

## Purpose

The workflow turns a creative brief into a reviewed brand identity and campaign package. It collects structured input, asks for additional direction only when required, creates a proposal, waits for approval, coordinates image and video generation, stores assets, and routes them through owner and customer review before delivery.

## Workflow contract

| Input | Description |
| --- | --- |
| `brand_name` | Name of the brand being developed. |
| `brand_concept` | Description of the offer, audience, values, and desired feeling. |
| `logo_status` | Whether a logo is needed, needs refinement, or is already approved. |
| `existing_assets` | Optional notes about existing visuals, colors, or fonts. |
| `email` | Customer email used for approval and delivery communication. |
| `deliverables` | One or more requested outputs: identity document, campaign images, mood board, social carousels, or brand videos. |
| `image_direction` | Optional visual direction shown when image-based deliverables are selected. |
| `video_direction` | Optional motion direction shown when brand videos are selected. |

## Integration map

| Integration | Workflow responsibility | Configuration required |
| --- | --- | --- |
| **n8n Forms** | Collects the brief, deliverables, image direction, and video direction. | Form paths, fields, and response URLs. |
| **OpenAI** | Supports AI-assisted identity and prompt generation where configured. | n8n OpenAI credential and model settings. |
| **Google Gemini** | Supports image or creative generation where configured. | n8n Gemini credential and model settings. |
| **Google Drive** | Stores generated images and videos and can share approved assets. | OAuth credential, destination folders, and sharing policy. |
| **SMTP** | Sends proposals, review updates, change requests, and final delivery messages. | SMTP credential, sender identity, and recipient routing. |
| **n8n Data Table** | Stores submitted brief data and status context. | Data Table identifier and matching columns. |
| **HTTP Request** | Connects to external generation or delivery services. | Endpoint, authentication, payload, and response mapping. |

## Recommended deployment sequence

### 1. Import

Import the JSON export into a non-production n8n workspace first. Do not assume credential IDs, Data Table IDs, folder IDs, webhook paths, or approval URLs are portable between workspaces.

### 2. Rebind credentials

Replace every exported credential reference with a credential owned by the target workspace. Keep secrets inside n8n’s credential manager; do not place API keys, SMTP passwords, or OAuth tokens in workflow expressions or repository files.

### 3. Confirm storage

Create or select the submission Data Table and verify that its columns match the fields written by the `Save Submission` node. Create separate Google Drive folders for test and production outputs, and review whether public sharing is permitted for the generated assets.

### 4. Verify generation services

Review each OpenAI, Google Gemini, and HTTP Request node. Confirm that the selected model or endpoint is available, the request body matches the service contract, and the response fields used by downstream nodes are present.

### 5. Test the approval path

Submit a test brief that requests a small set of deliverables. Verify that the proposal is sent before any production work begins, that approval links resolve correctly, and that a change request returns to the intended review loop.

### 6. Test final delivery

Complete an owner review and customer review with test recipients. Confirm that approved assets are uploaded to the expected location, that the final identity email contains the correct links, and that no internal credentials or private metadata are exposed.

## Production checklist

| Check | Expected result |
| --- | --- |
| Form submission | A complete brief is captured and stored once. |
| Conditional branches | Image and video direction pages appear only when needed. |
| Proposal gate | Generation does not begin before proposal approval. |
| Asset collection | Generated links are collected without losing the associated brand context. |
| Drive handling | Files land in the correct folder with intentional sharing permissions. |
| Review loops | Owner and customer changes return to the correct stage. |
| Email delivery | Messages use the intended sender, recipient, and approval URLs. |
| Error recovery | Failed external calls can be identified and retried without duplicating delivery. |
| Security | Secrets remain in n8n credentials and production data is separated from tests. |

## Operational boundary

The repository contains a workflow export, not a turnkey hosted service. Deployment remains environment-specific because credentials, storage destinations, external generation providers, email settings, and approval URLs belong to the operator’s n8n workspace.
