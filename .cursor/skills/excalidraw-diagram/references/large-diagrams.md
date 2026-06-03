# Large / Comprehensive Diagrams

**Build JSON one section per edit pass.** Do not generate the entire `.excalidraw` file in a single response — quality and token limits both favor section-by-section work.

## Workflow

### Phase 1: Build sections

1. Create base file: `type`, `version`, `appState`, `files`, first section of `elements`
2. Add **one section per edit** — layout and cross-section bindings carefully
3. Use descriptive string IDs (`trigger_rect`, `arrow_fan_left`)
4. Namespace numeric seeds by section (100xxx, 200xxx) to avoid collisions
5. When binding across sections, update earlier elements' `boundElements` in the same edit

### Phase 2: Review whole file

- Cross-section arrows bound on both ends
- Balanced spacing (no cramped vs empty regions)
- All IDs and bindings resolve to existing elements

### Phase 3: Render & validate

Follow the render loop in SKILL.md until the PNG passes vision and defect checks.

## Section boundaries

Plan around visual groupings, e.g.:

- Entry / trigger  
- First decision or routing  
- Main content (often largest)  
- Remaining phases and outputs  

Each section should be understandable on its own plus its cross-links.

## Avoid

- One-shot full-diagram generation  
- Delegating JSON to another agent without this skill's rules  
- Python generator scripts for coordinates — hand-crafted JSON with descriptive IDs is easier to debug
