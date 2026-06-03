# Excalidraw Diagram Skill (Cursor)

A [Cursor Agent Skill](https://cursor.com/docs/skills.md) that generates Excalidraw diagrams from natural language—not generic box grids, but layouts where **structure carries the argument**. Includes a Playwright render loop so the agent can inspect PNG output and fix layout issues before delivery.

Based on [excalidraw-diagram-skill-cursor](https://github.com/konashevich/excalidraw-diagram-skill-cursor) (Agent Skills / [agentskills.io](https://agentskills.io) compatible).

## What It Does

- **Visual arguments** — fan-out, timelines, convergence, trees; varied patterns per concept  
- **Evidence artifacts** — real code, JSON, event names on technical diagrams  
- **Render validation** — `.excalidraw` → PNG via headless Chromium; agent reviews and iterates  
- **Brand palette** — edit one file: `references/color-palette.md`  

## Install (Cursor)

### Option A: Use this repo in your project

Clone into your project (or add as submodule). Cursor auto-discovers:

```text
your-project/
└── .cursor/skills/excalidraw-diagram/
    ├── SKILL.md
    ├── references/
    └── scripts/
```

Restart Cursor or open **Settings → Rules → Agent Decides** to confirm `excalidraw-diagram` appears.

### Option B: User-level (all projects)

```bash
git clone https://github.com/konashevich/excalidraw-diagram-skill-cursor.git
cp -r excalidraw-diagram-skill-cursor/.cursor/skills/excalidraw-diagram ~/.cursor/skills/excalidraw-diagram
```

Also supported: `~/.agents/skills/excalidraw-diagram/`

### Option C: GitHub remote rule

**Settings → Rules → Project Rules → Add Rule → Remote Rule (Github)** — paste this repository URL.

## Renderer setup

**Ask the agent:** *"Set up the excalidraw-diagram skill renderer."*

**Or manually:**

```bash
cd .cursor/skills/excalidraw-diagram/scripts   # or ~/.cursor/skills/excalidraw-diagram/scripts
uv sync
uv run playwright install chromium
```

Requires Python ≥3.11 and [uv](https://github.com/astral-sh/uv).

## Usage

In Cursor Agent chat:

> Create an Excalidraw diagram showing how webhooks flow from a payment provider to our order service and database.

Or invoke explicitly: `/excalidraw-diagram`

The skill also surfaces automatically when working on `*.excalidraw` files (`paths` in frontmatter).

## Customize colors

Edit `.cursor/skills/excalidraw-diagram/references/color-palette.md`.

## Layout

```text
.cursor/skills/excalidraw-diagram/
├── SKILL.md                 # Workflow + render loop (read first)
├── references/
│   ├── color-palette.md     # Brand colors (edit for your style)
│   ├── design-methodology.md
│   ├── visual-patterns.md
│   ├── large-diagrams.md
│   ├── quality-checklist.md
│   ├── element-templates.md
│   └── json-schema.md
└── scripts/
    ├── render_excalidraw.py
    ├── render_template.html
    └── pyproject.toml
```

## Docs

- [Cursor Agent Skills](https://cursor.com/docs/skills.md)  
- [Agent Skills standard](https://agentskills.io)  
