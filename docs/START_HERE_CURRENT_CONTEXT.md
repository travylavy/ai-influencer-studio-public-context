# Start Here: Current Context

Read this first in future ChatGPT, Claude, Codex, or collaborator sessions.

## Repositories

- Private build/source-of-truth repo: `travylavy/codex-ai-influencer-studio`
- Public context repo: `travylavy/ai-influencer-studio-public-context`

This public repo is a sanitized context snapshot only. It is not a full mirror, not runtime source, and not the private source of truth.

## Legacy Source Warning

Old Google Drive files, uploaded source files, and older exports are historical archive material and may be stale. Do not use them as current authority unless the user explicitly re-promotes them in the current chat.

## Current Private Repo State

- PR #2 merged: repo-shape/source-of-truth reconciliation.
- PR #3 merged: Workflow A n8n importability fix.
- PR #4 merged: private repo public-context handoff pointer.
- PR #6 merged: Workflow A local MSI/n8n validation.
- PR #7 merged: private post-merge Workflow A status wording.
- Workflow A local MSI/n8n validation passed and PR #6 was merged to private main.
- Workflow remains inactive (`active: false`).
- Text-only DM loop validation succeeded locally.
- OpenAI Chat call succeeded.
- users/logs persistence succeeded through n8n-native Data Table-compatible local runtime.
- `character_id` was preserved.
- Response shape remained `{ "text": "...", "image_url": null }`.
- No ManyChat, ComfyUI, image generation, or public runtime integration has been validated.

## Current Public Repo State

This repo contains only sanitized docs. It excludes private source tree content, secrets, workbooks, raw assets, n8n databases, local paths, and private operational detail.

## Next Correct Build Step

Review the merged Workflow A local validation milestone and decide the next approved workstream. The prefixed local webhook URL behavior remains a review item before production-like use.

Do not start ManyChat, ComfyUI, image generation, Workflow B, production deployment, or public-runtime work without explicit approval.

## Authority Rule

1. Private repo current `main` = build truth.
2. Public repo `START_HERE_CURRENT_CONTEXT.md` plus public docs = safe summary/context.
3. Old Drive/uploaded files = archive unless explicitly re-promoted.
4. User instruction in the current chat wins when resolving ambiguity.

## Public Context Warning

Do not assume every private change is reflected here until the public-context sync workflow has completed successfully. Public context is generated from controlled templates and leak-scanned before push.
