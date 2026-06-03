---
name: excalidraw-diagram
description: >-
  Creates Excalidraw diagram JSON (.excalidraw) that argues visually—workflows,
  architectures, protocols—with evidence artifacts and mandatory PNG validation.
  Use when the user wants diagrams, flowcharts, system sketches, Excalidraw files,
  or visual explanations; mentions Excalidraw; or needs editable diagram source plus preview.
paths:
  - "**/*.excalidraw"
---

# Excalidraw Diagram

Generate `.excalidraw` files that **argue visually**, not just label boxes. The shape should carry meaning; removing all text should still suggest the structure (**isomorphism test**).

**Brand colors:** Read [references/color-palette.md](references/color-palette.md) before every diagram and use it for all fills, strokes, and text.

**Setup:** If the renderer is not installed, follow [Setup](#setup) below or ask the user to approve setup once.

## When to Use

- User asks for a diagram, architecture sketch, flowchart, or visual explanation  
- Working with or creating `*.excalidraw` files  
- Technical teaching diagrams that need real names, payloads, or code snippets  

## Quick Workflow

1. **Assess depth** — simple/conceptual vs comprehensive/technical → [design-methodology.md](references/design-methodology.md)  
2. **Research** (if technical) — real APIs, events, formats; no generic placeholders  
3. **Plan** — patterns per concept → [visual-patterns.md](references/visual-patterns.md)  
4. **Write JSON** — section-by-section if large → [large-diagrams.md](references/large-diagrams.md)  
5. **Render & fix** — loop until PNG passes → [Render & validate](#render--validate-mandatory)  
6. **Checklist** → [quality-checklist.md](references/quality-checklist.md)  

## JSON Essentials

```json
{
  "type": "excalidraw",
  "version": 2,
  "source": "https://excalidraw.com",
  "elements": [],
  "appState": { "viewBackgroundColor": "#ffffff", "gridSize": 20 },
  "files": {}
}
```

**Text rule:** `text` and `originalText` contain **only readable words** (no HTML/markdown).

```json
{
  "text": "Start",
  "originalText": "Start",
  "fontSize": 16,
  "fontFamily": 3,
  "textAlign": "center",
  "verticalAlign": "middle"
}
```

**Templates:** [element-templates.md](references/element-templates.md)  
**Schema details:** [json-schema.md](references/json-schema.md)  

Use descriptive string element IDs (e.g. `api_rect`, `flow_arrow_1`). Namespace random seeds by section when building large files.

## Render & Validate (Mandatory)

You cannot judge layout from JSON alone. After generating or editing:

### Render

From the **skill root** (folder containing this `SKILL.md`):

```bash
cd scripts
uv run python render_excalidraw.py <path-to-file.excalidraw>
```

Writes `<same-name>.png` beside the `.excalidraw` file. **Read the PNG** with the Read tool.

### Loop

1. Render and view the PNG  
2. **Vision check** — structure matches plan; patterns and hierarchy correct; evidence readable  
3. **Defect check** — clipped text, overlaps, arrows through shapes, wrong targets, uneven spacing, illegible size, lopsided layout  
4. **Fix** JSON — coordinates, container width, arrow `points`, label positions  
5. Re-render; repeat until [quality-checklist.md](references/quality-checklist.md) passes (typically 2–4 passes)

Stop only when you would show the diagram without caveats.

## Setup

First time in this skill's `scripts/` directory:

```bash
cd scripts
uv sync
uv run playwright install chromium
```

Requires Python ≥3.11 and [uv](https://github.com/astral-sh/uv). The render script and `render_template.html` must stay in the same `scripts/` folder.

## Reference Index

| Topic | File |
|-------|------|
| Depth, research, evidence, containers | [design-methodology.md](references/design-methodology.md) |
| Fan-out, timeline, shapes | [visual-patterns.md](references/visual-patterns.md) |
| Section-by-section builds | [large-diagrams.md](references/large-diagrams.md) |
| Pre-delivery checklist | [quality-checklist.md](references/quality-checklist.md) |
| Colors / brand | [color-palette.md](references/color-palette.md) |
| Element JSON snippets | [element-templates.md](references/element-templates.md) |
| Excalidraw format | [json-schema.md](references/json-schema.md) |

## Additional Resources

- Cursor skills: https://cursor.com/docs/skills.md  
- Agent Skills standard: https://agentskills.io  
