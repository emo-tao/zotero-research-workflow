---
name: zotero-research-workflow
description: Guide a Windows Zotero literature workflow across collection, Chinese metadata, selected-text translation, full-PDF translation, notes, and citation export. Use when the user wants to set up, verify, or troubleshoot this plugin combination; do not assume every plugin is required.
---

# Zotero research workflow

Help the user reach an observable Zotero outcome, especially a PDF translation that returns to the correct library item. Treat a running server or installed plugin as a checkpoint, not the final result.

## Route by the actual task

1. Identify the target outcome: collect literature, improve Chinese metadata, translate a passage, translate a complete PDF, write notes, or export citations. Ask for missing system/version information only if it blocks the next step; inspect available local evidence first.
2. Read [plugin-map.md](references/plugin-map.md) to select the smallest relevant component set. Do not install all six extensions for a single narrow task.
3. For installation or end-to-end verification on Windows, read [windows-setup.md](references/windows-setup.md). Check current upstream releases and compatibility before naming an installer or changing dependencies.
4. If a step fails, read [troubleshooting.md](references/troubleshooting.md). Diagnose from the observed error and active interpreter; apply the smallest repair, then rerun the failed check.

## Working rules

- Use the user's selected translation service and existing Zotero library configuration. A local Server does not imply offline translation; state when a configured service may receive PDF content.
- Keep upstream software and this skill distinct. Cite the original plugin, Server, and engine projects from [sources-and-credits.md](../../docs/sources-and-credits.md) when recommending downloads or discussing authorship.
- Use actual installed paths. The source case used a dedicated Python environment because a separate application's old Python appeared first on `PATH`; that path and its package versions are examples, not universal defaults.
- Do not declare success from `uv pip check` alone: it finds dependency conflicts or missing requirements but cannot prove every package is intact or that a PDF can be translated.
- For full-PDF translation, verify a small representative PDF end to end: plugin → Server → engine → translation service → output → correct Zotero item; inspect a few paragraphs, formulas and references. Report the exact passed and failed checkpoints.
- Before changing the user's environment, inspect its current state and preserve existing configuration. Get downloads from the named upstream sources. Avoid exposing tokens, private PDFs or local personal paths in public artifacts.

