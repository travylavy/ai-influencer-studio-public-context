# Public Context Boundary

This repository is deliberately small.

It exists to give AI sessions and reviewers enough safe context to understand the project direction without granting access to private source material.

## Included

- High-level architecture summary
- Workflow A public contract summary
- Safety and governance summary
- Current build status
- Current context handoff

## Excluded

- Private active repo source tree
- Raw AI system files
- Raw character files
- Workbook data
- Vault data
- Generated media
- Local machine paths
- Environment files
- n8n database files
- n8n credential stores
- Private prompt assets
- Private operational details
- Branch export indexes and file maps

## Safe Placeholder Language

This repo may use words such as "secret", "token", "credential", or environment variable names only as safety and governance placeholders. It must not contain actual values.

## Authority Rule

The private repository remains the implementation source of truth. This public context repo is only a sanitized summary.
