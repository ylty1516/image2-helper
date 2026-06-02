# Visual Case: Realistic Street Background Audit

## Source Observation

The reference image is a realistic sidewalk portrait. Its main value for this skill is not a dramatic flaw, but the number of background details that must remain believable for the image to feel real.

The background contains:

- pedestrians walking at different depths
- bicycles and a cropped vehicle on the left
- trees, shrubs, and foreground occlusion
- sidewalk seams and a walking lane receding into depth
- storefronts, awnings, windows, warm interior lights, and cafe furniture on the right
- bright far architecture and mild depth-of-field softness

## What Would Make An AI Version Fail

- Background walkers become vague human-shaped blobs with broken feet or limb count.
- Bicycle wheels, handlebars, frames, and vehicle edges melt into decorative metal lines.
- Cafe chairs, tables, railings, and planters fuse into wooden blocks.
- Sidewalk seams, curb direction, and storefront edges disagree about the floor plane.
- Far buildings become blank white filler instead of plausible washed-out architecture.
- Foliage becomes green noise and fuses with bikes, poles, or people.
- Cropped background objects continue through the foreground person in impossible ways.
- The scene gets over-cleaned, losing the ordinary lived-in street clutter that makes the photo convincing.

## Visual Map

![Street photo background audit](./street-photo-background-audit.svg)

## Copy-Ready Prompt Add-On

```text
Realistic street-background audit: give the sidewalk, pedestrians, storefronts, cafe furniture, bicycles, vehicles, trees, pavement seams, reflections, and far architecture the same realism check as the main subject. Keep depth-of-field softness optical only: all visible background objects still have plausible construction, grounded contact, coherent scale, one perspective system, ordinary lived-in detail, and no melted bikes, fused cafe furniture, malformed walkers, fake signage, or impossible occlusion through the subject.
```

## Edit Prompt For A Failed First Image

```text
Preserve the main portrait, camera angle, daylight mood, and street-photo realism. Repair the background by zones: keep pedestrians anatomically plausible and grounded, rebuild bicycles and vehicles with real mechanical continuity, separate cafe furniture into usable chairs/tables/railings, align sidewalk seams and storefront edges to one floor plane, retain plausible washed-out far architecture, and remove any fake signage, fused props, malformed walkers, or background lines passing through the subject.
```

## Skill Update

This case is summarized in `references/background-integrity.md` under `Photo Reference: Realistic Street Background Audit`.
