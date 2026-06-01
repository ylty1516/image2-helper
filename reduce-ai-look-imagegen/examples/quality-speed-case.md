# Visual Case: Quality-Preserving Speed Mode

This example demonstrates how the skill reduces token use and thinking time without degrading image quality.

## User Goal

```text
Make image prompting faster and use fewer tokens, but keep the same quality or improve it.
```

## Wrong Interpretation

Bad compression:

```text
anime girl, beautiful, cinematic, high quality, less AI
```

Why it fails:

```text
- It is short, but it deletes the actual visual decisions.
- The model has to guess format, composition, medium, lighting, and failure guards.
- It saves tokens by creating ambiguity, which often causes more retries.
```

## Correct Interpretation

The skill now treats speed as routing and information design:

```text
Cut token waste, not quality-critical constraints.
```

![Quality-preserving speed map](./quality-speed-map.png)

## Quality Floor

```yaml
must_keep:
  - hard format and aspect ratio
  - subject identity and required props
  - one base medium/style
  - one composition or safe-area plan
  - one light/value plan
  - one physical/action/material logic constraint
  - top 2-3 failure guards
```

## Speed Routing

```yaml
tier_0:
  use: "ordinary image generation"
  action: "route to imagegen only"
tier_1:
  use: "simple lower-AI rewrite"
  action: "load fast-path.md only"
tier_2:
  use: "one known risk, such as anime gloss, weak composition, extra objects, or fuzzy intent"
  action: "load fast-path.md plus one focused reference"
tier_3:
  use: "repeated failures, reusable profile, complex diagnosis"
  action: "load only 2-3 focused references; quality wins over forced brevity"
```

## Copy-Ready Compact Prompt

```text
Create a hand-drawn anime still, 16:9. Subject: white-haired girl waiting at a rainy tram stop, hands visible on umbrella handle. Style: clean animation contour, flat cel colors, painted background. Composition: character on left third, tram lights leading into depth. Light: cool rain with one warm practical lamp. Avoid glossy 3D hair, airbrushed skin, random rim lights.
```

## What Changed In The Skill

- Added `references/quality-preserving-speed.md`.
- Reframed fast path as quality-preserving speed, not low-effort shortening.
- Added a quality floor to `SKILL.md` and `fast-path.md`.
- Added tiered routing so complex tasks automatically upgrade instead of being forced into a tiny prompt.
- Added a visual case showing what gets kept and what gets cut.
