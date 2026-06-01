# Visual Case: Composition-First Style Routing

This example demonstrates the mainstream-style-composition module.

## User Goal

```text
Make this game start page feel more story-rich, but keep the buttons clear.
```

## Why The Old Prompt Fails

Weak prompt:

```text
Make it more cinematic, beautiful, high quality, with story atmosphere.
```

Likely failure:

```text
- The background becomes busy behind the buttons.
- The character turns into generic key art.
- UI readability is lost.
- "Cinematic" becomes bloom, fog, and random lens flare instead of actual framing.
```

## Visual Routing Map

![Composition-first style routing](./composition-style-map.png)

## Composition Diagnosis

```yaml
composition_lock:
  format: "game main menu"
  aspect_ratio: "wide desktop"
  hard_constraints:
    - readable title/logo
    - readable buttons and click targets
    - no busy texture behind UI
  focal_anchor:
    - character/story clue on the left third
    - button-safe negative space on the right
  depth_plan:
    - foreground object hinting at story
    - midground character or key location
    - background sky/city/world detail
  detail_density:
    - richer detail near character/story clue
    - quiet value grouping behind buttons
```

## Copy-Ready Prompt Segment

```text
Composition: game main menu layout, character and world clue on the left third, readable button-safe negative space on the right, layered foreground/midground/background depth, title/logo-safe top-left area, calm value grouping behind UI. Use visual-novel key art logic with an anime painted background feel. Keep UI contrast and spacing clear; do not place high-detail texture, fake text, or bright effects behind buttons.
```

## What Changed In The Skill

- Added `references/mainstream-style-composition.md`.
- Added composition/framing trigger language to `SKILL.md`.
- Added a reference selection row for composition and mainstream style completion.
- Added compact fast-path wording for "better composition."
- Added visual evidence for how the module routes intent into composition locks.
