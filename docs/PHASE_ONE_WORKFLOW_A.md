# Phase-One Workflow A Summary

Workflow A is the phase-one text-only DM response loop.

## Status

Workflow A local MSI/n8n validation passed and PR #6 was merged to private main. Workflow A remains inactive and is not live, production-deployed, ManyChat validated, ComfyUI validated, image-generation validated, or public-runtime validated.

Current public-safe artifact signals:

- workflow name: `workflow_dm_text_response_v1`
- workflow id: `workflowAResponseV1`
- active flag: `false`
- node count: `20`

Public-safe validation evidence:

- text-only DM loop validated locally
- OpenAI Chat call succeeded
- users/logs persistence succeeded through n8n-native Data Table-compatible local runtime
- `character_id` was preserved
- response shape remained `{ "text": "...", "image_url": null }`
- workflow remained inactive
- no ManyChat, ComfyUI, or image generation was validated

## Scope

In scope:

- Incoming webhook payload normalization
- First-class `character_id`
- n8n-native users persistence lookup, create, and update
- Basic state and flag calculation
- Delay calculation
- OpenAI text response node
- Response cleanup and fallback
- Interaction log record creation
- n8n-native logs persistence insert
- Final response shape with text and `image_url`

Out of scope:

- ManyChat live routing
- ComfyUI image generation
- Hermes
- Google Drive upload
- Monetization logic
- Dashboard or Mission Control as runtime authority

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

Workflow A has local MSI/n8n validation evidence for the controlled text-only DM path. This does not mean the workflow is production-ready or live. The prefixed local webhook URL behavior remains a review item before production-like use, and future hardening should still cover malformed payloads, repeat-user behavior, fallback behavior, and production webhook path review.
