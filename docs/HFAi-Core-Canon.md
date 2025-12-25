# HFAi Core Canon

This document defines how ChatGPT and AI agents should understand, navigate, and use the HFAi-Core repository.

## Purpose
HFAi-Core is the master reference for building, organizing, and evolving all HFAi systems, including websites, AI personas, workflows, and digital products.

## Repository Logic
- This repository is NOT an app.
- It is a knowledge and structure source.
- AI tools should read it as a system blueprint.

## Folder Roles
- /docs → Rules, canon, explanations, and system documentation.
- /projects → Each project lives in its own folder.
- /prompts → Reusable prompts (system, personas, tools).
- /templates → Reusable structures (MD, JSON, checklists).
- /experiments → Temporary or exploratory work.

## AI Usage Rules
- Always respect folder boundaries.
- Never mix unrelated projects.
- Generate new content inside the correct folder.
- Treat this repository as a single source of truth.

## Website Building Rule
When building websites (e.g., HFAi.world):
- Create a dedicated folder under /projects
- All pages, copy, and structure must live there.
- The core repo defines standards, not deployment.

## Deployment Notice
Hosting, domains, and live deployment happen outside GitHub.
This repository provides structure, content, and logic only.
