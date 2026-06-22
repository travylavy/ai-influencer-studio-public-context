# Current Build Status

## Repository Shape

The private Codex working repository has been reconciled from an old branch-export and audit mirror into the active working repo layout. Old exported branch snapshot folders were removed from the active root, while historical material remains preserved through Git history and source refs.

Private main source signal at generation time: `5996e81`.

## Recent Private Repo Milestones

- PR #2 merged: repo-shape and source-of-truth reconciliation.
- PR #3 merged: Workflow A n8n importability fix.
- PR #4 merged: private repo public-context handoff pointer.
- PR #10 merged: Workflow A hardening evidence preserved in private main.
- PR #9 merged: Workflow A payload-validation gate.

## Workflow A

Workflow A is the current phase-one runtime focus.

Completed:

- Private repo cleanup and source-of-truth reconciliation
- Workflow A candidate files promoted into the active private repo
- Local n8n foundation setup
- Clean n8n validation folder setup
- n8n 2.18.5 importability gate passed after a one-line workflow ID fix
- PR #6 merged Workflow A local MSI/n8n validation into private main
- PR #7 updated private post-merge status wording
- PR #10 recorded local hardening evidence and the missing-message risk
- PR #9 merged the Workflow A payload-validation gate into private main
- text-only DM loop validated locally
- OpenAI Chat call succeeded
- users/logs persistence succeeded through n8n-native Data Table-compatible local runtime
- `character_id` was preserved
- response shape remained `{ "text": "...", "image_url": null }`
- missing-message hardening found that required-field validation was needed before OpenAI and before users/logs persistence
- payload-validation gate now validates `user_id`, `platform`, `character_id`, and `message`
- missing, null, or blank required fields return safe JSON with `image_url: null`
- invalid payloads do not call OpenAI
- invalid payloads do not create/update users
- invalid payloads do not write a normal interaction log
- valid text-DM behavior remains preserved
- Workflow remains text-only
- Workflow remains inactive by default

Pending:

- production webhook path review because local validation used a prefixed local n8n URL
- extended malformed-payload variants and regression hardening
- fallback behavior hardening
- any decision about production activation
- ManyChat validation
- ComfyUI validation
- image-generation validation
- public-runtime validation

## Public Context Repo Status

This repo is a sanitized context bundle only. It does not include private source code, runtime credentials, local n8n data, character assets, workbook rows, or generated media.
