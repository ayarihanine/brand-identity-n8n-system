<div align="center">
  <img src="brand/FreshyMatcha-logo.png" alt="Freshy Matcha logo" width="420" />

  # Brand Identity Builder

  **An approval-led n8n system for turning a creative brief into a coherent brand identity and campaign-ready asset package.**

  <p>
    <a href="n8n%20system/Brand%20Identity%20Builder.json">Import the workflow</a> ·
    <a href="docs/WORKFLOW_OPERATIONS.md">Read the operations guide</a> ·
    <a href="brand/">Explore the brand assets</a>
  </p>
</div>

<p align="center">
  <img src="brand/brandstory2.png" alt="Freshy Matcha brand story showing ceremonial matcha products and the mindful ritual positioning" width="100%" />
</p>

> **Fresh in taste. Pure in nature.**
>
> Freshy Matcha is the reference brand for this system: a calm, natural, quietly premium identity built around pure ingredients, mindful rituals, sustainable choices, and intentional design.

## What this project is

**Brand Identity Builder** is a reusable n8n production workflow and visual case study. It guides a customer from an initial brief through proposal approval, AI-assisted identity development, campaign asset generation, human review, and final delivery.

The system is designed for **repeatable creative operations with human control**. Automation removes repetitive coordination work, while approval gates keep the creative direction, generated assets, and delivery decisions visible to the people responsible for quality.

### At a glance

| | |
| --- | --- |
| **Workflow platform** | n8n |
| **Reference brand** | Freshy Matcha |
| **Primary output** | Reviewed brand identity and campaign asset package |
| **Core model** | Brief → proposal → approval → production → review → delivery |
| **Storage and delivery** | Google Drive, email, and environment-specific integrations |
| **Repository type** | Importable workflow export plus visual identity reference package |

## Why the approval model matters

Creative automation should accelerate production without turning judgment into a black box. This workflow records the brief, pauses before production, routes assets through owner and customer review, and supports change requests before final delivery.

That structure creates a clear operating boundary:

1. **The customer describes the brand and selects deliverables.**
2. **The system creates a proposal and waits for approval.**
3. **Approved direction is translated into identity and campaign assets.**
4. **Generated outputs are collected, stored, and reviewed.**
5. **Changes return to the appropriate stage instead of restarting everything.**
6. **Only approved work is delivered.**

## What the workflow handles

| Capability | Result |
| --- | --- |
| **Guided intake** | Captures the brand concept, logo status, existing assets, contact details, and requested deliverables through n8n Forms. |
| **Conditional briefing** | Requests image or video direction only when those deliverables are selected. |
| **Proposal gate** | Sends a creative proposal and pauses the workflow until approval is received. |
| **Identity direction** | Produces structured brand identity guidance from the approved brief. |
| **Campaign production** | Coordinates image prompts, visual generation, video direction, and asset collection. |
| **Review loops** | Supports owner review, customer review, approval, and change requests. |
| **Delivery** | Shares the approved identity document and final campaign assets through the configured delivery flow. |

## Automation architecture

<p align="center">
  <img src="n8n%20system/automationWorkflow.png" alt="Wide n8n Brand Identity Builder workflow architecture map" width="100%" />
</p>

The workflow is organized as a controlled production pipeline rather than a single generation step.

| Stage | Flow |
| --- | --- |
| **Brief** | Brand Identity Form → Deliverables Page → conditional image/video direction pages |
| **Proposal** | Collect Form Data → Save Submission → Generate Proposal → approval email |
| **Create** | Generate Brand Identity → generate image and video prompts → produce selected assets |
| **Prepare** | Collect generated links → upload assets to Google Drive → configure sharing |
| **Review** | Owner review → customer review → change loop or approval |
| **Deliver** | Send the approved identity document and campaign assets to the customer |

## The Freshy Matcha identity

The reference identity balances editorial sophistication with a grounded, natural product world. Deep greens create recognition and premium contrast. Warm neutrals give the system space to breathe. Tactile materials, natural light, leaves, ceramic, stone, bamboo, matcha powder, and product-first compositions make the ritual tangible.

<p align="center">
  <img src="brand/brand1.png" alt="Freshy Matcha light identity board with stationery, packaging, and product applications" width="49%" />
  <img src="brand/brand2.png" alt="Freshy Matcha dark identity board with premium packaging and brand applications" width="49%" />
</p>

| Brand dimension | Direction |
| --- | --- |
| **Positioning** | A mindful matcha ritual for slowing down, recentering, and showing up with intention. |
| **Values** | Pure ingredients, mindful rituals, sustainable choices, and care in every interaction. |
| **Voice** | Calm, confident, warm, intentional, and quietly premium. |
| **Visual language** | Editorial typography, botanical forms, natural light, tactile surfaces, and restrained green contrast. |
| **Applications** | Packaging, stationery, cups, envelopes, seals, social content, environmental touchpoints, and campaign layouts. |

## Campaign system in practice

The visual package extends the identity into a consistent content system rather than isolated mockups. The social grid below demonstrates how the same voice can move between product photography, ritual education, seasonal storytelling, and concise editorial messaging.

<p align="center">
  <img src="brand/06_social_media_grid.png" alt="Freshy Matcha six-panel social media campaign grid" width="49%" />
  <img src="brand/brandstory2_improved.png" alt="Freshy Matcha extended brand story and product presentation board" width="49%" />
</p>

The `brand/` directory also includes stationery, desk objects, wearables, accessories, environment concepts, packaging scenes, signage, and additional campaign directions. These assets make the repository useful both as a workflow demonstration and as a complete visual reference set.

## Commercial film

The repository includes an animated preview and the original MP4 commercial. The preview is convenient inside GitHub; the MP4 is the source presentation format with native playback and audio.

<p align="center">
  <a href="brand/Freshy_Matcha_advertisement_design_202608291218.mp4">
    <img src="brand/Freshy_Matcha_advertisement_preview.gif" alt="Animated preview of the Freshy Matcha commercial; click to open the original MP4" width="760" />
  </a>
</p>

<p align="center"><strong>Click the preview to open the original commercial.</strong></p>

## Repository map

| Location | Purpose |
| --- | --- |
| [`n8n system/Brand Identity Builder.json`](n8n%20system/Brand%20Identity%20Builder.json) | Importable n8n workflow export. |
| [`n8n system/automationWorkflow.png`](n8n%20system/automationWorkflow.png) | Workflow architecture reference. |
| [`brand/`](brand/) | Freshy Matcha identity, applications, campaign visuals, and commercial assets. |
| [`docs/WORKFLOW_OPERATIONS.md`](docs/WORKFLOW_OPERATIONS.md) | Deployment, integration, testing, and production checklist. |
| [`docs/ASSET_GUIDE.md`](docs/ASSET_GUIDE.md) | Visual asset inventory and reuse guidance. |
| [`BEHANCE_PROJECT.md`](BEHANCE_PROJECT.md) | Case-study narrative and publishing sequence. |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | Contribution and review standards. |
| [`SECURITY.md`](SECURITY.md) | Credential, data, and public-sharing policy. |

## Setup and deployment

This repository contains an **n8n workflow export**, not a turnkey hosted service. Credentials, folders, approval URLs, email settings, generation providers, and storage policies belong to the target n8n workspace.

### Requirements

Use an n8n instance with permission to import workflows, SMTP access for transactional email, Google Drive access for storage and sharing, the AI credentials expected by the workflow nodes, and an available n8n Data Table for submission history.

### Import safely

1. Import [`Brand Identity Builder.json`](n8n%20system/Brand%20Identity%20Builder.json) into a non-production n8n workspace.
2. Replace exported credential mappings with credentials owned by the target workspace.
3. Confirm the submission Data Table and its mapped columns.
4. Review AI generation nodes, HTTP Request endpoints, email routing, approval URLs, and Google Drive destinations.
5. Test with non-production recipients and storage before activation.
6. Activate the workflow only after proposal, review, change-request, and delivery paths have been tested end to end.

### Integration map

| Integration | Responsibility | Operator configuration |
| --- | --- | --- |
| **n8n Forms** | Collects the brief, deliverables, and optional creative direction. | Form paths, fields, and response URLs. |
| **OpenAI / Google Gemini** | Supports AI-assisted identity, prompt, or image generation where configured. | Credentials, models, request settings, and output fields. |
| **Google Drive** | Stores generated assets and applies sharing rules. | OAuth credential, folders, and sharing policy. |
| **SMTP** | Sends proposals, review updates, change requests, and delivery messages. | Sender identity, recipients, and routing. |
| **n8n Data Table** | Stores submitted brief data and status context. | Table identifier and matching columns. |
| **HTTP Request** | Connects external generation or delivery services. | Endpoint, authentication, payload, and response mapping. |

For the complete deployment sequence and production checklist, read the [Workflow Operations Guide](docs/WORKFLOW_OPERATIONS.md).

## Security boundary

Keep API keys, SMTP passwords, OAuth tokens, and private workspace identifiers inside n8n credentials. Do not commit secrets to the repository or place them in workflow expressions. Separate test and production folders, verify public-sharing behavior before delivery, and review approval links before activating the workflow.

See [`SECURITY.md`](SECURITY.md) for the repository’s security and public-sharing policy.

## References

[1]: n8n%20system/Brand%20Identity%20Builder.json "Importable Brand Identity Builder n8n workflow"
[2]: n8n%20system/automationWorkflow.png "Brand Identity Builder workflow architecture"
[3]: brand/ "Freshy Matcha visual identity and campaign asset package"
[4]: brand/Freshy_Matcha_advertisement_design_202608291218.mp4 "Freshy Matcha original commercial film"

<div align="center">
  <sub>Built for thoughtful, repeatable brand production.</sub>
</div>


## Visual direction

The README now treats the brand library like a presentation: a few strong visual statements lead the story, while the complete production archive remains available below without overwhelming the page.

### Selected identity spreads

<p align="center">
  <img src="brand/brand1_improved.png" alt="Freshy Matcha expanded light identity and packaging board" width="88%" />
</p>

<p align="center"><strong>Identity system · packaging, stationery, and touchpoints</strong></p>

<p align="center">
  <img src="brand/freshymatcha_brandstory_clean_product_led.png" alt="Freshy Matcha clean product-led brand story board" width="48%" />
  <img src="brand/freshy.png" alt="Freshy Matcha tall visual identity presentation board" width="48%" />
</p>

<p align="center">
  <img src="brand/05_environment.png" alt="Freshy Matcha branded environment and spatial applications" width="88%" />
</p>

<p align="center"><strong>Brand world · a calm identity carried into space</strong></p>

<p align="center">
  <img src="brand/freshy_matcha_idea_02_empty_tea_bar.png" alt="Freshy Matcha empty tea bar interior concept" width="88%" />
</p>

<p align="center"><strong>Spatial direction · retail as a mindful ritual</strong></p>

<p align="center">
  <img src="brand/freshy_matcha_hero_exterior_refined.png" alt="Freshy Matcha refined exterior hero scene" width="48%" />
  <img src="brand/freshy_matcha_original_brand_world.png" alt="Freshy Matcha original brand world presentation" width="48%" />
</p>

<details>
<summary><strong>Browse the complete production asset archive</strong> · 29 additional visual assets</summary>

### Identity foundations

<p align="center">
  <img src="brand/logos.png" alt="Freshy Matcha logo exploration and lockup board" width="48%" />
  <img src="brand/freshy_matcha_typography_only.png" alt="Freshy Matcha typography and editorial layout reference" width="48%" />
</p>

### Physical applications

<p align="center">
  <img src="brand/01_stationery_suite.png" alt="Freshy Matcha stationery suite applications" width="48%" />
  <img src="brand/02_desk_objects.png" alt="Freshy Matcha desk objects and workday touchpoints" width="48%" />
</p>

<p align="center">
  <img src="brand/03_wearables.png" alt="Freshy Matcha wearable brand applications" width="48%" />
  <img src="brand/04_accessories.png" alt="Freshy Matcha accessories and branded objects" width="48%" />
</p>

### Retail and packaging concepts

<p align="center">
  <img src="brand/freshy_matcha_idea_01_packaging_shelf.png" alt="Freshy Matcha packaging shelf concept" width="48%" />
  <img src="brand/freshy_matcha_idea_03_gift_box.png" alt="Freshy Matcha gift box concept" width="48%" />
</p>

<p align="center">
  <img src="brand/freshy_matcha_idea_04_wayfinding_system.png" alt="Freshy Matcha wayfinding system concept" width="48%" />
  <img src="brand/freshy_matcha_idea_05_stationery_pattern.png" alt="Freshy Matcha stationery pattern concept" width="48%" />
</p>

### Standalone applications

<p align="center">
  <img src="brand/freshy_matcha_standalone_01_interior.png" alt="Freshy Matcha standalone interior concept" width="48%" />
  <img src="brand/freshy_matcha_standalone_02_counter_objects.png" alt="Freshy Matcha counter objects and service touchpoints" width="48%" />
</p>

<p align="center">
  <img src="brand/freshy_matcha_standalone_03_wall_signage.png" alt="Freshy Matcha wall signage concept" width="48%" />
  <img src="brand/freshy_matcha_standalone_04_packaging_display.png" alt="Freshy Matcha packaging display concept" width="48%" />
</p>

<p align="center">
  <img src="brand/freshy_matcha_standalone_04_packaging_display(1).png" alt="Freshy Matcha alternate packaging display concept" width="48%" />
  <img src="brand/freshy_matcha_standalone_05_bathroom_detail.png" alt="Freshy Matcha branded bathroom detail concept" width="48%" />
</p>

### Brand-world applications

<p align="center">
  <img src="brand/freshy_matcha_original_01_ritual_station.png" alt="Freshy Matcha ritual station concept" width="48%" />
  <img src="brand/freshy_matcha_original_02_transit_kiosk.png" alt="Freshy Matcha transit kiosk concept" width="48%" />
</p>

<p align="center">
  <img src="brand/freshy_matcha_original_03_delivery_crate_balanced.png" alt="Freshy Matcha balanced delivery crate concept" width="48%" />
  <img src="brand/freshy_matcha_original_04_window_display.png" alt="Freshy Matcha window display concept" width="48%" />
</p>

<p align="center">
  <img src="brand/freshy_matcha_original_05_corporate_gifting_table.png" alt="Freshy Matcha corporate gifting table concept" width="48%" />
</p>

</details>

<div align="center">
  <sub>Curated for first impression. Complete for review. Every visual direction remains in the repository's <code>brand/</code> asset library.</sub>
</div>
