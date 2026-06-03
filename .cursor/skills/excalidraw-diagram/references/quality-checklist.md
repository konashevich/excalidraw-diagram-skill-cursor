# Quality Checklist

Use after planning and again after the render loop.

## Depth & Evidence (technical diagrams)

1. Research done — real specs, formats, names  
2. Evidence artifacts present  
3. Multi-zoom — summary + sections + detail  
4. Concrete over abstract labels  
5. Educational — viewer learns something specific  

## Conceptual

6. **Isomorphism** — structure alone suggests the concept  
7. **Argument** — diagram shows what prose cannot  
8. **Variety** — distinct pattern per major concept  
9. No uniform card grids  

## Containers & typography

10. Minimal containers — could any box be free-floating text?  
11. Timelines/trees use lines + text  
12. Font size/color hierarchy without boxes  

## Structural

13. Every relationship has arrow or line  
14. Clear eye path (often left→right or top→bottom)  
15. Scale/isolation show importance  

## Technical JSON

16. `text` / `originalText` contain only readable words (no markup in `text`)  
17. `fontFamily: 3`  
18. `roughness: 0` unless hand-drawn style requested  
19. `opacity: 100` everywhere  
20. <30% of text inside containers  

## Visual validation (required)

21. Rendered to PNG and inspected with Read tool  
22. No clipped or overlapping text  
23. Consistent spacing  
24. Arrows land correctly, no careless crossings  
25. Legible at export size  
26. Balanced composition — no huge voids or overcrowding  
