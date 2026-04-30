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
- `main` was synced after PR #3.
- Workflow A JSON is importable into a clean n8n validation DB.
- Workflow remains inactive (`active: false`).
- No webhook payload runtime test has been completed yet.
- No credentials were created inside n8n.
- No ManyChat, ComfyUI, or public runtime integration has been completed.

## Current Public Repo State

This repo contains only sanitized docs. It excludes private source tree content, secrets, workbooks, raw assets, n8n databases, local paths, and private operational detail.

## Next Correct Build Step

Resume from Workflow A runtime validation:

1. Use the clean n8n validation setup.
2. Create/map the OpenAI credential in the n8n UI without exposing the API key.
3. Run the controlled test payload.
4. Verify `users` Data Store behavior.
5. Verify `logs` Data Store behavior.

Do not start new build work before this validation step.

## Authority Rule

1. Private repo current `main` = build truth.
2. Public repo `START_HERE_CURRENT_CONTEXT.md` plus public docs = safe summary/context.
3. Old Drive/uploaded files = archive unless explicitly re-promoted.
4. User instruction in the current chat wins when resolving ambiguity.

## Public Context Warning

Do not assume this public repo auto-updates when the private repo changes. Public context must be regenerated intentionally after private changes and leak-scanned before push.

