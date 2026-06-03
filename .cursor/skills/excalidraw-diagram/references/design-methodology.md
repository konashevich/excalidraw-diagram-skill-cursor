# Design Methodology

Read this when planning a non-trivial or technical diagram.

## Depth Assessment

**Simple/conceptual** — abstract shapes when explaining mental models; audience does not need technical specifics.

**Comprehensive/technical** — concrete examples when diagramming real systems, teaching, or showing integration. **Include evidence artifacts** (below).

## Research Mandate (Technical Diagrams)

Before drawing:

1. Look up actual JSON/data formats, event names, API endpoints
2. Use real terminology, not placeholders

Bad: `Protocol` → `Frontend`  
Good: `AG-UI streams RUN_STARTED, STATE_DELTA` → `createA2UIMessageRenderer()`

## Evidence Artifacts

| Artifact | When | How |
|----------|------|-----|
| Code snippets | APIs, integrations | Dark rect + syntax-colored text (see color-palette) |
| Data/JSON | Schemas, payloads | Dark rect + colored text |
| Event sequences | Protocols, workflows | Timeline (line + dots + labels) |
| UI mockups | Real output | Nested rectangles |
| Real input content | What goes into a system | Visible sample in a rectangle |

Show what things **look like**, not only what they are called.

## Multi-Zoom Architecture

1. **Summary flow** — pipeline at a glance (top or bottom)
2. **Section boundaries** — labeled regions grouping related parts
3. **Detail inside sections** — artifacts, snippets, concrete examples

## Container vs Free-Floating Text

Default to **free-floating text**. Use containers only when: focal point, grouping, arrow target, shape carries meaning (diamond), or distinct system "thing".

**Container test**: Would free-floating text work? If yes, remove the box.

## Bad vs Good

| Bad (displaying) | Good (arguing) |
|------------------|----------------|
| Equal labeled boxes | Shape mirrors behavior |
| Card grid | Structure matches concept |
| Icons on text | Shape IS the meaning |
| Everything boxed | Selective containers |

| Simple | Comprehensive |
|--------|----------------|
| `Input` → `Process` → `Output` | Real input/output formats shown |
| Box labeled `API` | Box + sample request/response |
| `Events` label | Timeline with real event names |
| ~30s to explain | ~2–3 min of teaching content |

## Design Process (Before JSON)

0. **Depth** — simple vs comprehensive; if comprehensive, research first  
1. **Understand** — what each concept *does*; relationships; what viewers must *see*  
2. **Map patterns** — see [visual-patterns.md](visual-patterns.md)  
3. **Variety** — each major concept uses a different pattern; no uniform grids  
4. **Sketch flow** — clear visual story for the eye  
5. **Generate JSON** — section-by-section for large diagrams ([large-diagrams.md](large-diagrams.md))  
6. **Render & validate** — mandatory loop in SKILL.md

## Color and Layout

- All colors: [color-palette.md](color-palette.md) only — do not invent colors  
- `roughness: 0`, `opacity: 100` for professional diagrams  
- `fontFamily: 3` for all text  
- Hierarchy: hero 300×150, primary 180×90, secondary 120×60, small 60×40  
- Whitespace signals importance (200px+ around hero)  
- **Connections required** — if A relates to B, draw an arrow  
- **<30%** of text elements inside containers
