# AI Influencer Studio Public Context

This repository is a sanitized public context bundle for AI Influencer Studio. It is designed to help ChatGPT, Claude, Codex, and human collaborators understand the project at a high level without exposing private source material.

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
- `.env` files, credentials, tokens, or API keys
- n8n local user data, SQLite databases, or credential stores
- Generated images, videos, or ComfyUI output
- NSFW/private operational detail

## Current Project Direction

AI Influencer Studio is moving toward deterministic, human-approved runtime workflows where n8n owns routing, state, timing, and Data Store usage for phase-one text interactions.

Workflow A is the first phase-one runtime workflow: a text-only DM response loop using n8n, a first-class `character_id`, OpenAI text response generation, user state updates, and interaction logging.

## Public Context Rule

This repo is a public summary layer only. The private working repository remains the source of implementation truth. If anything here conflicts with the private repo, the private repo wins.

