# Visual Case: Lean Skill Routing

This example documents the project cleanup that makes the skill faster for AI agents to call.

## Before

```text
SKILL.md was about 21.7 KB and contained routing plus many detailed modules.
```

Why that was slower:

```text
- Every skill invocation loaded long instructions.
- Detailed pose/anime/consistency/composition rules lived partly in the default context.
- The AI had more text to scan before choosing the right focused module.
```

## After

```text
SKILL.md is about 6.3 KB and acts as a lean router.
```

What changed:

```text
- SKILL.md keeps only trigger rules, quality floor, route matrix, compact prompt pattern, and output rules.
- Detailed rules stay in references and load only when needed.
- references/INDEX.md gives a quick folder map.
```

![Lean skill routing](./lean-routing-map.png)

## New Call Path

```text
User request
-> SKILL.md lean router
-> one focused reference
-> compact prompt or edit instruction
-> imagegen/edit tool when available
```

## Preserved Capabilities

The cleanup did not remove the existing modules:

```text
fast-path, quality-preserving-speed, inconsistency-cleanup, prompt-recipes,
anime-handdrawn-look, mainstream-style-composition, style taxonomy, style blending,
intent/fuzzy language, feedback fixes, and scoring rubric all remain available.
```

## Practical Result

```text
The default loaded skill body is much smaller, but specialized depth remains available through focused references.
```
