# Quality-Preserving Speed

Use this when the user wants lower token use, faster thinking, faster image prompt iteration, or "image2 speed" improvements without losing quality.

This module is not about making prompts shorter at any cost. It keeps or improves output quality by spending tokens only on decisions that change the image.

## Core Rule

Reduce tokens by removing low-value reasoning and duplicated style noise, not by removing visual intent.

Keep:

- hard format and aspect ratio
- subject identity and required props
- one base medium/style
- one composition plan
- one light/value plan
- one physical/action/material constraint
- background/non-focus quality when visible
- top 2-3 avoid constraints tied to known failure modes

Cut:

- generic quality tags
- repeated adjectives
- long explanations before generation
- multiple similar style labels
- unsupported artist/studio name stacking
- broad negative lists that do not match the task
- full reference loading when one focused file is enough

## Speed Tiers

### Tier 0: Route-Only

Use when the user only asks for ordinary image generation.

Action:

```text
Route to image generation skill/tool. Do not load reduce-ai-look references.
```

Quality protection:

```text
Do not silently add anti-AI constraints unless the user asked for refinement.
```

### Tier 1: Compact High-Quality Prompt

Use for one clear goal, one style, one likely failure mode.

Budget:

```text
Load fast-path.md only. Final prompt: 70-120 words.
```

Keep these six slots:

```yaml
format: "<what the image is>"
subject: "<identity/action>"
style: "<one base medium + 2 concrete production cues>"
composition: "<focal anchor + crop/safe area>"
light_or_color: "<one motivated model>"
failure_guard: "<top 2-3 avoid terms>"
```

### Tier 2: Focused Reference

Use when one specialized risk matters: pose, extra props, composition, fuzzy wording, anime finish, style conflict, product realism, or typography.

Budget:

```text
Load fast-path.md plus one focused reference. Final prompt: 100-170 words.
```

Quality protection:

```text
Spend extra tokens only on the known risk. Do not load the whole style library.
```

### Tier 3: Deep Pass

Use for high-stakes outputs, repeated failures, image diagnosis, reusable style skill/profile, or multi-format deliverables.

Budget:

```text
Load only the 2-3 references that match separate risks. Use a short diagnosis, then a structured prompt.
```

Quality protection:

```text
Do not force a 120-word prompt when the task has multiple hard constraints. Quality wins over token savings.
```

## Quality Floor

Never compress away these fields:

```yaml
must_keep:
  - output format
  - subject identity
  - required style/medium
  - required action or role
  - required props / forbidden props
  - composition or safe area when the output is UI, poster, cover, wallpaper, comic, icon, or product
  - one physical logic constraint for people, products, hands, contact, or perspective
  - background/non-focus quality when visible background objects, secondary figures, crowds, props, architecture, or signage matter
```

If any `must_keep` field is missing, ask one short question only when guessing would likely break the output. Otherwise infer conservatively.

## Compression Order

When reducing token use, remove content in this order:

1. Chat explanation before the prompt.
2. Generic quality words: masterpiece, high quality, beautiful, ultra detailed, cinematic when it is not translated.
3. Duplicate style adjectives.
4. Long negative prompt lists unrelated to the request.
5. Secondary decorative details.
6. Extra reference files.

Do not remove:

- the hard format
- the focal subject
- the style medium
- the composition plan
- the main light/value logic
- background/non-focus quality when visible
- the top failure guard

## Fast Decision Matrix

| Task signal | Tier | Load |
|---|---:|---|
| ordinary generation | 0 | imagegen only |
| simple "less AI" or "optimize prompt" | 1 | `fast-path.md` |
| "too glossy anime" | 2 | `fast-path.md` + `anime-handdrawn-look.md` |
| extra object / mismatch | 2 | `fast-path.md` + `inconsistency-cleanup.md` |
| weak composition / game UI / cover | 2 | `fast-path.md` + `mainstream-style-composition.md` |
| vague purpose words | 2 | `fast-path.md` + `intent-and-fuzzy-language.md` |
| mixed conflicting styles | 2 | `fast-path.md` + `style-blending-rules.md` |
| repeated failed generations | 3 | 2-3 focused references |
| building reusable skill/profile | 3 | targeted references and archive notes |

## Prompt Pattern

Use this compact pattern for Tier 1-2:

```text
Create/Edit a [format], [aspect ratio].
Subject: [identity + action + required props].
Style: [one base medium] with [2-3 production cues].
Composition: [focal anchor + viewer path or safe area].
Light/color: [one motivated light/value plan].
Logic: [pose/contact/material/perspective constraint].
Avoid: [top 2-3 task-specific failures].
```

This pattern preserves quality because every sentence controls a visible part of the image.

## Bad Compression vs Good Compression

Bad:

```text
anime girl, beautiful, cinematic, high quality, less AI
```

Why bad:

```text
Short but underspecified. It saves tokens by deleting the actual visual decision.
```

Good:

```text
Create a hand-drawn anime still, 16:9. Subject: white-haired girl waiting at a rainy tram stop, relaxed posture, hands visible on umbrella handle. Style: clean animation contour, flat cel colors, painted background. Composition: character on left third, tram lights leading into depth, quiet sky space on right. Light/color: cool rain with one warm practical light. Avoid glossy 3D hair, airbrushed skin, random rim lights.
```

Why good:

```text
Still compact, but it preserves format, subject, medium, composition, light, physical logic, and failure guards.
```

## Response Behavior

When speed matters:

- Do not print a long diagnosis unless asked.
- Give one compact final prompt and, if useful, one sentence explaining the tier.
- Do not show internal reference selection unless the user asks how it worked.
- If the task is complex, say briefly why the prompt is allowed to exceed 120 words.

When the user asks how token reduction works, explain:

```text
It reduces prompt and reasoning waste, not visual specification. It keeps the few constraints that strongly shape the image and drops generic labels, duplicate style words, long analysis, and unrelated negative lists.
```
