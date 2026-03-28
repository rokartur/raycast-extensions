---
name: add-new-extension
description: Workflow command scaffold for add-new-extension in raycast-extensions.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-new-extension

Use this workflow when working on **add-new-extension** in `raycast-extensions`.

## Goal

Adds a brand new extension to the repository, including all necessary files, assets, configuration, and documentation.

## Common Files

- `extensions/*/.gitignore`
- `extensions/*/.prettierrc`
- `extensions/*/eslint.config.*`
- `extensions/*/tsconfig.json`
- `extensions/*/package.json`
- `extensions/*/package-lock.json`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Create extension directory under extensions/{extension-name}/
- Add .gitignore, .prettierrc, eslint config, and tsconfig.json files
- Add package.json and package-lock.json
- Add README.md and CHANGELOG.md
- Add assets (icons, images) and metadata screenshots

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.