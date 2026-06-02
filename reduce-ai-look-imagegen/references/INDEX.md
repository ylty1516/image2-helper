# Reference Index

Use this file only when you need a quick map of the reference folder.

## Fast Routes

| Need | File |
|---|---|
| Quick lower-AI rewrite | `fast-path.md` |
| Lower token use without quality loss | `quality-preserving-speed.md` |
| Decide whether this skill should run | `routing-and-triggering.md` |

## Repair Modules

| Need | File |
|---|---|
| Background/non-focus objects, secondary figures, malformed crowds, broken architecture | `background-integrity.md` |
| Extra props, prompt-image mismatch, expression/action or viewpoint/environment mismatch | `inconsistency-cleanup.md` |
| User says too AI, too glossy, bad hands, fake, busy, not premium | `failure-feedback-fixes.md` |
| Pose/action correction, realism pass, reusable recipes | `prompt-recipes.md` |
| Anime battle, weapon clash, magic combat, martial arts, monster fight | `combat-action-anime.md` |

## Style And Intent Modules

| Need | File |
|---|---|
| Fuzzy words, hard format lock, user purpose parsing | `intent-and-fuzzy-language.md` |
| Deep fuzzy taste-word translation and personal preference wording | `fuzzy-word-precision-library.md` |
| Anime, cel, genga/layout, hand-painted backgrounds | `anime-handdrawn-look.md` |
| Better composition, framing, mainstream style defaults | `mainstream-style-composition.md` |
| Choose style by output use case | `style-selection-and-use-cases.md` |
| Broad style taxonomy | `style-taxonomy.md` |
| Niche/historical/craft/technical styles | `style-expansion-pack.md` |
| Mixed/conflicting styles | `style-blending-rules.md` |
| Ready prompt skeletons | `style-prompt-cookbook.md` |
| Score before/after quality | `style-quality-rubric.md` |

## Loading Rule

Load one file first. Add a second file only when the task has a separate risk.

Examples:

- "less AI anime, too glossy" -> `fast-path.md` + `anime-handdrawn-look.md`
- "anime battle looks flashy but action is unclear" -> `combat-action-anime.md`
- "maid skin has an unwanted staff" -> `inconsistency-cleanup.md`
- "main character is good but the background people/props/buildings look fake" -> `background-integrity.md`
- "faster image2 with same quality" -> `quality-preserving-speed.md`
- "game menu more story-rich but buttons clear" -> `mainstream-style-composition.md`
- "make it more premium, relaxed, story-rich, lived-in, or transparent" -> `intent-and-fuzzy-language.md` then `fuzzy-word-precision-library.md` if needed
