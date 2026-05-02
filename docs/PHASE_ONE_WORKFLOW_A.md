# Phase-One Workflow A Summary

Workflow A is the phase-one text-only DM response loop.

## Status

Workflow A local MSI/n8n validation passed and PR #6 was merged to private main. Workflow A payload-validation gate was merged to private main. Workflow A remains inactive and is not live, production-deployed, ManyChat validated, ComfyUI validated, image-generation validated, or public-runtime validated.

Current public-safe artifact signals:

- workflow name: `workflow_dm_text_response_v1`
- workflow id: `workflowAResponseV1`
- active flag: `false`
- node count: `23`

Public-safe validation evidence:

- text-only DM loop validated locally
- OpenAI Chat call succeeded
- users/logs persistence succeeded through n8n-native Data Table-compatible local runtime
- `character_id` was preserved
- response shape remained `{ "text": "...", "image_url": null }`
- missing-message hardening identified the need for a pre-OpenAI/pre-persistence validation gate
- payload-validation gate now validates required fields before OpenAI and before users/logs persistence
- required fields are `user_id`, `platform`, `character_id`, and `message`
- missing, null, or blank required fields return a safe text-only JSON response with `image_url: null`
- invalid payloads do not call OpenAI, create/update users, or write a normal interaction log
- valid text-DM behavior remains preserved
- workflow remained inactive
- no ManyChat, ComfyUI, or image generation was validated

## Scope

In scope:

- Incoming webhook payload normalization
- Required payload field validation
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

Invalid required-field response:

```json
{
  "text": "hey, send that again?",
  "image_url": null
}
```

Payload validation boundary:

- Required fields: `user_id`, `platform`, `character_id`, `message`
- Missing, null, or blank required fields are invalid
- Invalid payloads stop before OpenAI
- Invalid payloads do not create/update users
- Invalid payloads do not write a normal interaction log

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

Workflow A has local MSI/n8n validation evidence for the controlled text-only DM path and for the required-field payload-validation gate. This does not mean the workflow is production-ready or live. The prefixed local webhook URL behavior remains a review item before production-like use, and future hardening should still cover extended malformed-payload variants, fallback behavior, and production webhook path review.
