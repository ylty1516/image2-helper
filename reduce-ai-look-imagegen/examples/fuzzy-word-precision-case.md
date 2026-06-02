# Visual Case: Fuzzy Word Precision

## User Goal

The user wants vague taste words to become accurate image-generation language. The skill should not answer with generic tags such as `masterpiece`, `high quality`, `cinematic`, or `beautiful`.

## Visual Map

![Fuzzy word precision map](./fuzzy-word-precision-map.svg)

## What The Library Adds

- Converts vague taste words into concrete visual decisions.
- Preserves hard output format before mood translation.
- Expands only the highest-impact words to save tokens.
- Blocks common wrong interpretations for each fuzzy term.
- Supports personal taste calibration through compact reusable rules.

## Example Input

```text
让这张图更高级，更有氛围感和故事感，但不要变得很假。
```

## Bad Output

```text
masterpiece, high quality, cinematic, beautiful, premium, atmospheric, ultra detailed
```

This does not explain what should change.

## Better Output

```text
Interpret "premium + atmospheric + story-rich" as restrained everyday narrative mood: precise negative space, motivated dusk light, layered air depth, real material texture, one object implying what just happened, and no gold overload, random fog, fake flare, or symbolic prop pile.
```

## Copy-Ready Prompt Patch

```text
Mood precision: translate vague taste words into visual evidence. Keep the requested format unchanged. Use restrained color, believable material texture, motivated light, layered depth, subject gaze/action with intent, and one environment clue that implies before/after. Avoid generic quality tags, gold overload, random fog, fake flare, and symbolic clutter.
```

## Skill Update

This case is summarized in `references/fuzzy-word-precision-library.md`.
