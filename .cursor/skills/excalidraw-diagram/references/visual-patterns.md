# Visual Pattern Library

Match structure to meaning. For multi-concept diagrams, use a **different pattern per major concept**.

## Patterns

| If the concept… | Pattern |
|-----------------|---------|
| Spawns many outputs | **Fan-out** — radial arrows from center |
| Combines inputs | **Convergence** — arrows merging to one |
| Has hierarchy | **Tree** — lines + free-floating labels |
| Is a sequence | **Timeline** — line + small dots + labels |
| Loops / iterates | **Spiral/cycle** — arrow back to start |
| Abstract state | **Cloud** — overlapping ellipses |
| Transforms data | **Assembly line** — before → process → after |
| Compares options | **Side-by-side** — parallel with contrast |
| Separates phases | **Gap/break** — whitespace or divider |

### Fan-out
```
        ○
       ↗
  □ → ○
       ↘
        ○
```

### Convergence
```
  ○ ↘
  ○ → □
  ○ ↗
```

### Tree
Use `line` elements for trunk/branches; labels as free-floating text (no boxes).

### Timeline
Vertical or horizontal line; 10–20px ellipse dots; labels beside dots.

### Lines as Structure
Prefer `line` (not arrows) for timelines, tree trunks, section dividers, flow spines.

## Shape Meaning

| Concept | Shape |
|---------|--------|
| Labels, descriptions | none (free-floating text) |
| Start, trigger, input | `ellipse` |
| End, output | `ellipse` |
| Decision | `diamond` |
| Process, action | `rectangle` |
| Abstract state | overlapping `ellipse` |
| Timeline marker | small `ellipse` 10–20px |
| Hierarchy node | lines + text |

Default: no container unless the shape carries meaning.
