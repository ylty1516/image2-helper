# Visual Case: Background / Non-Focus Quality

## User Goal

The user wants the background to receive the same quality support as the main character. The focal subject can remain compositionally primary, but the background must not become a lower-quality filler layer.

## Why It Matters

AI images often polish the main subject while leaving the rest of the scene with malformed people, melted objects, fake signs, impossible stairs, or empty decorative clutter. This breaks realism even when the main character looks good.

## Visual Map

![Background integrity map](./background-integrity-map.svg)

## Quality Rule

```text
The focal subject may lead the composition, but all visible background and non-focus details receive the same quality scrutiny: plausible structure, material, action, perspective, light, contact, and context-rich detail.
```

## Copy-Ready Prompt Add-On

```text
Scene integrity: the focal subject remains compositionally primary, but the background is generated with equal quality support: rich, realistic, structurally plausible objects and secondary figures, aligned to the same perspective and light, with no melted props, malformed crowd figures, fake text, or bizarre unrelated actions.
```

## Typical Failure Patch

Bad prompt direction:

```text
Make the character detailed and keep the background simple.
```

Better prompt direction:

```text
Keep the character as the focal anchor, but give the entire environment the same quality standard: believable background people, real object functions, coherent architecture, consistent light and contact shadows, and rich lived-in material detail.
```

## What Changed In The Skill

- `SKILL.md` now treats background/non-focus quality as part of the quality floor.
- `references/background-integrity.md` provides focused checks and prompt blocks.
- `references/fast-path.md` and `references/quality-preserving-speed.md` preserve background quality even in compact prompts.
- `references/style-quality-rubric.md` scores background/non-focus quality as its own axis.
