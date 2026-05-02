# AI Influencer Studio Public Context

## Start Here

Future ChatGPT, Claude, Codex, and collaborator sessions should read [`docs/START_HERE_CURRENT_CONTEXT.md`](docs/START_HERE_CURRENT_CONTEXT.md) first.

This repository is a sanitized public context bundle for AI Influencer Studio. It is designed to help AI sessions and human collaborators understand the project at a high level without exposing private source material.

This is not the active private build repository. It does not contain runtime secrets, private workbooks, raw character assets, local n8n data, generated media, or private operational files.

## What This Repo Contains

- High-level architecture overview
- Phase-one Workflow A summary
- Safety and governance summary
- Current build status
- Public boundary and exclusion rules

## What This Repo Does Not Contain

- Private repository source tree
- Raw character files or assets
- Private workbook or vault data
- Environment files, credentials, tokens, or API keys
- n8n local user data, database files, or credential stores
- Generated images, videos, or ComfyUI output
- Private operational detail

## Current Project Direction

AI Influencer Studio is moving toward deterministic, human-approved runtime workflows where n8n owns routing, state, timing, and n8n-native persistence for phase-one text interactions.

Workflow A is the first phase-one runtime workflow: a text-only DM response loop using n8n, a first-class `character_id`, OpenAI text response generation, user state updates, and interaction logging.

Workflow A local MSI/n8n validation passed and PR #6 was merged to private main. Workflow A payload-validation gate was merged to private main. Workflow A remains inactive and is not live, production-deployed, ManyChat validated, ComfyUI validated, image-generation validated, or public-runtime validated.

The payload-validation gate checks required inbound fields before OpenAI and before users/logs persistence. Missing, null, or blank required fields return a safe text-only JSON response with `image_url: null`.

## Public Context Rule

This repo is a public summary layer only. The private working repository remains the source of implementation truth. If anything here conflicts with the private repo, the private repo wins.
