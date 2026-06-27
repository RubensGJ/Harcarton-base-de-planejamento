# Repository Guidelines

## Project Structure & Module Organization
This repository is a planning and research base for `haCARthon`, not a packaged application. Keep the top level focused on primary source material and stable reference files.

- `README.md`: repository overview.
- `*.pdf`, `*.txt`, `*.mp4`: official documents, transcripts, and supporting media.
- `.agents/`: role prompts and operating guides used during analysis.
- `relatorios/`: generated analyses and dossier-style outputs.
- `.codex/` and temporary folders such as `.tmp-analysis/`: local tooling state; do not commit them.

When adding new material, prefer this pattern: raw source at the root, derived analysis in `relatorios/`, and agent/process guidance in `.agents/`.

## Build, Test, and Development Commands
There is no build pipeline in this repository. Use lightweight inspection commands instead.

- `rtk powershell -NoProfile -Command "Get-ChildItem -Force"`: quick repository inventory.
- `rtk rg --files`: list tracked files fast.
- `rtk git status`: review pending changes before editing.
- `rtk git log --oneline -5`: inspect recent history and naming style.

If you add automation scripts later, document their exact entrypoints in `README.md` and keep helper outputs outside version control unless they are intentional deliverables.

## Coding Style & Naming Conventions
Prefer concise Markdown with clear headings and direct language. Name reports descriptively with dates when useful, for example `relatorios/dossie-hacarthon-base-2026-06-26.md`.

- Use kebab-case for new Markdown or helper file names.
- Preserve original names for official source files.
- Keep sections short and evidence-based; cite the source document or transcript being summarized.

## Testing Guidelines
There is no formal automated test suite today. Validation is editorial and structural.

- Re-open generated Markdown/HTML and confirm links, headings, and file references.
- For research outputs, cross-check claims against the cited PDF, transcript, or official link.
- Do not add placeholder tests or dummy scripts just to satisfy structure.

## Commit & Pull Request Guidelines
Current history uses short, descriptive commits in Portuguese, for example `Base de planejamento do haCARthon`. Follow that style.

- Keep commits scoped to one logical change.
- In pull requests, explain what was added or reorganized, list affected paths, and mention source documents consulted.
- Include screenshots only when changing rendered HTML or visual artifacts inside `relatorios/`.

## Security & Configuration Tips
Do not commit secrets, private notes, caches, or Codex local state. Respect `.gitignore`, especially `.codex/`, Python cache files, and temporary analysis folders.
