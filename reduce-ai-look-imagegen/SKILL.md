---
name: reduce-ai-look-imagegen
description: Universal image-generation preflight and prompt quality controller. Improve prompts before imagegen for intent completion, fuzzy-word repair, style choice, composition/framing, perspective/scale/ground-plane logic, pose/hand/action clarity, anatomy, object contact, background/prop integrity, prompt-image consistency, unwanted object prevention, anime-character real-scene/screen integration, token efficiency, and lower-AI/less generic results. Use for any image generation or image editing request before calling imagegen.
---

# Imagegen Preflight Quality Controller

## Prime Directive

Act as a lean image-generation router and prompt quality controller. Preserve the user's intent while improving every important generation layer: format, subject, style, composition, perspective, physical logic, scene integrity, consistency, token efficiency, and anti-AI polish control.

Default path:

```text
image request -> lightweight preflight -> load the smallest useful reference -> write one compact prompt/edit instruction -> call imagegen/edit tool when available
```

Do not load the full reference library. Do not print long diagnostics before generation unless the user asks for analysis.

## Trigger Channels

Use this skill for:

- any image generation or image editing request as a lightweight preflight before imagegen
- intent completion, prompt enrichment, fuzzy-word repair, and hard format preservation
- style selection, style translation, style mixing, and visual taste clarification
- composition/framing/layout improvement
- lower-AI / less fake / less glossy / less plastic / less 3D results
- prompt rewrite, image diagnosis, before/after scoring, or style correction
- pose, hand, action, anatomy, object contact, or perspective repair
- horizon, vanishing point, floor/ground plane, scale, occlusion, or spatial geometry repair
- anime battle/action clarity, weapon clash, spell combat, martial arts, or monster-fight repair
- extra/unwanted props, prompt-image mismatch, expression/action mismatch, viewpoint/environment mismatch
- malformed background objects, secondary figures, crowds, architecture, props, or non-focus details
- anime character integrated into a real photo, room, desktop, phone, monitor, screen, AR, or display scene
- fuzzy taste words such as premium, atmospheric, story-rich, cinematic, cute, clean, realistic, hand-drawn
- lower token use or faster image prompting without quality loss

If the user only asks for ordinary image creation, use this skill as a compact preflight layer, then route to the available image generation skill/tool. Keep the preflight minimal unless the user asks for refinement, diagnosis, anti-AI, composition, pose, perspective, background integrity, consistency, style translation, or a special integration case.

Use host-native / Plus-style image generation or editing when available. Do not call API-key CLIs or third-party image APIs unless the user explicitly asks for that workflow.

## Quality Floor

A compact prompt must still keep:

```yaml
format: "hard output format and aspect ratio"
subject: "identity, action, role, required props"
style: "one base medium/style with concrete production cues"
composition: "focal anchor, crop, viewer path, or safe area when relevant"
light_color: "one motivated light/value/color model"
perspective_geometry: "one camera height, horizon line, perspective system, ground/floor plane, scale anchors, contact/occlusion logic when visible"
physical_logic: "pose/contact/material/perspective constraint"
scene_integrity: "background receives the same quality scrutiny as the focal subject; secondary figures, props, architecture, and non-focus actions remain rich and plausible"
source_background_lock: "for edits/composites using an existing real photo or background plate, preserve the background exactly: crop, objects, positions, perspective, exposure, color, shadows, highlights, reflections, clutter, noise, and existing light must not change"
guards: "top 2-3 task-specific failure modes"
```

Never save tokens by deleting hard format, subject identity, required style/medium, composition/safe area, perspective geometry for visible spaces, physical logic, background/non-focus quality, or the most likely failure guards.

## Fast Workflow

1. Classify the request: generation, edit, prompt rewrite, image diagnosis, style selection, consistency cleanup, composition pass, or speed/token pass.
2. For any generation phrase, load `references/auto-anti-ai-expansion.md` and silently enrich the prompt before generation; use deeper references only when triggers or risks require them.
3. Pick the route from the matrix below.
4. Load only the selected reference. If still ambiguous, load one additional focused reference.
5. Produce the shortest output that preserves the quality floor.
6. When generating or editing images, save outputs under the configured `F:\Codex_Save_Library` folders.

## Reference Matrix

Pick the first matching row unless the task clearly has two separate risks:

| Task signal | Load |
|---|---|
| ordinary image generation only | `references/auto-anti-ai-expansion.md`, then route to imagegen |
| generation phrase contains fuzzy taste words, spatial risks, style risks, consistency risks, or anti-AI trigger words | `references/auto-anti-ai-expansion.md` |
| quick trigger/search words for current quality-control categories | `references/INDEX.md` |
| lower AI feel, simple rewrite | `references/fast-path.md` |
| lower token use / faster thinking without quality loss | `references/quality-preserving-speed.md` |
| should this skill run? | `references/routing-and-triggering.md` |
| fuzzy wording or hard format lock | `references/intent-and-fuzzy-language.md` |
| deep fuzzy taste-word translation or personal preference wording | `references/fuzzy-word-precision-library.md` |
| perspective, horizon, vanishing points, floor/ground plane, scale, occlusion, spatial geometry | `references/perspective-geometry.md` |
| malformed background, secondary figures, props, architecture, non-focus detail | `references/background-integrity.md` |
| extra objects, role drift, prompt-image mismatch | `references/inconsistency-cleanup.md` |
| existing image critique or plain-language failure feedback | `references/failure-feedback-fixes.md` |
| pose, hand, action, realism pass, reusable prompt recipe | `references/prompt-recipes.md` |
| anime battle, weapon clash, magic combat, martial arts, monster fight | `references/combat-action-anime.md` |
| anime/cel/genga/hand-painted background | `references/anime-handdrawn-look.md` |
| anime character in real scene, phone, monitor, display, AR, desktop, room, photo composite | `references/anime-character-real-scene-integration.md` |
| epic fantasy landscape, fantasy panorama, ice/lava kingdom, floating islands, concept wallpaper | `references/style-expansion-pack.md` then `references/background-integrity.md` |
| composition, framing, layout, mainstream style completion | `references/mainstream-style-composition.md` |
| choose style by use case | `references/style-selection-and-use-cases.md` |
| broad visual style classification | `references/style-taxonomy.md` |
| niche/historical/craft/technical style | `references/style-expansion-pack.md` |
| mixed or conflicting styles | `references/style-blending-rules.md` |
| ready prompt skeleton | `references/style-prompt-cookbook.md` |
| score before/after quality | `references/style-quality-rubric.md` |

## Compact Prompt Pattern

Use this as the default shape, trimming fields that do not help:

```text
Create/Edit a [format], [aspect ratio].
Subject: [identity + action + required props].
Style: [one base medium/process] with [2-3 concrete cues].
Composition: [focal anchor + crop/viewer path/safe area].
Light/color: [one motivated light or value model].
Perspective: [one camera height + horizon/vanishing system + ground/floor/contact/scale/occlusion logic when visible].
Logic: [pose/contact/material/perspective constraint].
Scene integrity: [background/non-focus details receive equal quality scrutiny when visible].
Avoid: [top 2-3 task-specific failures].
```

For image edits, add:

```text
Preserve: [identity, layout, pose intent, required style].
Change only: [requested fixes].
Do not alter: [important unchanged areas].
```

For real-photo/anime-real composites, make background preservation a hard edit constraint:

```text
Background plate lock: preserve the existing background exactly, including every object, object position, crop, perspective, exposure, color temperature, original shadows, highlights, reflections, clutter, grain, and compression. Do not clean, relight, repaint, stylize, replace, blur, sharpen, denoise, rearrange, add, remove, or move anything in the background. The character must adapt to the background; the background must not adapt to the character.
```

## Output Rules

- If the user wants an image, keep explanation to one short sentence and generate/edit.
- If the user asks how the skill works, include a concise route explanation and the selected reference.
- If the source image cannot be passed to an editor, provide a prompt-only deliverable or clearly label any local proof as post-processing only.
- Keep ordinary prompts around 70-120 words when the quality floor survives; allow 120-170 words for one focused risk; go longer only for deep diagnosis or reusable workflows.
- Put long reusable notes in `F:\Codex_Save_Library\06_Prompt_Archive`, not in chat.

