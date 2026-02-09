---
name: erduo-skills
description: Uses and runs skills in the erduo-skills repo (daily news report, Gemini watermark remover). Use when working in this repository, when the user asks for a daily news report, to remove Gemini watermarks from images, or when referring to erduo skills.
---

# Erduo Skills

When working in this repo, apply the following.

## Skills in this repo

| Skill | Location | Purpose |
|-------|----------|--------|
| Daily News Report | `skills/daily-news-report/` | Fetches from configured URLs, filters quality tech content, writes Markdown report to `NewsReport/`. |
| Gemini Watermark Remover | `skills/gemini-watermark-remover/` | Removes Gemini image watermark via inverse alpha blend. |

## Config and outputs

- **Daily News Report**: Config in `skills/daily-news-report/sources.json` and `cache.json`. Output: `NewsReport/YYYY-MM-DD-news-report.md`.
- **Gemini Watermark Remover**: Run script with input and output paths; see `skills/gemini-watermark-remover/scripts/remove_watermark.py` and `references/algorithm.md` for details.

## Running from Cursor

1. **Daily news report**: Follow the workflow in `skills/daily-news-report/SKILL.md` (init → fetch/extract → filter → generate report). Use WebFetch or browser tools as described there; output to `NewsReport/`.
2. **Watermark removal**: Execute `python skills/gemini-watermark-remover/scripts/remove_watermark.py <input-image> <output-image>` (ensure Pillow is installed per `scripts/requirements.txt`).

## Conventions

- Use forward slashes in paths (e.g. `skills/daily-news-report/`).
- Do not create or edit skills under `~/.cursor/skills-cursor/`; that is for Cursor’s built-in skills.
