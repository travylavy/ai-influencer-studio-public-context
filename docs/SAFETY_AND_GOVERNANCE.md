# Safety And Governance Summary

This public context repo intentionally exposes only sanitized, high-level project context. It is not a complete source export and should not be used as an implementation authority over the private repo.

## Change Control

- Do not treat public summary docs as operational approval.
- Do not auto-execute agents or workflows without explicit human approval.
- Do not treat dashboard or mock UI status as proof of live runtime behavior.
- Keep workflow artifacts versioned and rollbackable.

## Data Safety

The following must not be published here:

- Secrets, tokens, credential IDs, API keys, or `.env` values
- Private workbook rows, vault data, or live operational datasets
- Raw character files, private character assets, generated images, or generated video
- Local n8n user folders, SQLite databases, credential stores, or execution logs
- Private local machine paths
- NSFW/private operational detail

## Runtime Safety

- n8n owns phase-one routing, state, timing, and Data Store operations.
- ComfyUI is execution-only and should not be exposed as a public reasoning layer.
- `character_id` must remain present in workflow contracts and logs.
- SFW and NSFW operational boundaries must remain protected.
- Workbook-like data handling should be append-safe and should avoid destructive rewrites.

## Public Context Boundary

This repo may summarize what exists privately, but it must not become a competing source of truth. Future updates should be generated or reviewed from the private repo and should remain high-level and sanitized.

