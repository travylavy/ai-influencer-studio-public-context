# Phase-One Workflow A Summary

Workflow A is the phase-one text-only DM response loop.

## Status

Workflow A is importable into local n8n 2.18.5 after adding a stable top-level workflow ID. It remains inactive by default. Full webhook payload execution, OpenAI credential mapping, Data Store write verification, and acceptance evidence are still pending.

## Scope

In scope:

- Incoming webhook payload normalization
- First-class `character_id`
- n8n Data Store lookup/create/update for users
- Basic state and flag calculation
- Delay calculation
- OpenAI text response node
- Response cleanup/fallback
- Interaction log record creation
- n8n Data Store log insert
- Final response shape with text and `image_url`

Out of scope:

- ManyChat live routing
- ComfyUI image generation
- Hermes
- Google Drive upload
- Monetization logic
- Dashboard/Mission Control as runtime authority

## Public Contract Summary

Incoming payload:

```json
{
  "user_id": "string",
  "platform": "string",
  "character_id": "string",
  "message": "string"
}
```

User key pattern:

```text
user_id__platform__character_id
```

Outbound payload:

```json
{
  "text": "string",
  "image_url": null
}
```

Log fields:

- `user_id`
- `platform`
- `character_id`
- `input`
- `output`
- `timestamp`
- `image_generated`
- `workflow_status`

## Current Validation Boundary

The workflow import gate has passed locally for n8n 2.18.5. This does not mean the workflow is production-ready. Runtime testing still needs local webhook execution, credential binding, Data Store verification, repeat-user behavior verification, and acceptance evidence.

