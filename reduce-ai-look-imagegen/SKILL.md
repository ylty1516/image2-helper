---
name: reduce-ai-look-imagegen
description: Improve image generation/editing prompts to reduce synthetic AI feel, generic polish, anatomy/action errors, visual inconsistency, unwanted extra objects, weak composition, style mismatch, or vague taste-word confusion. Use when the user asks for lower AI feel, de-AI, remove AI look, more natural/hand-drawn/realistic, better composition/framing, pose/hand/body correction, inconsistency cleanup, remove unreasonable extras, fix prompt-image mismatch, fix behavior/expression/viewpoint/environment mismatch, prompt refinement, image diagnosis, before/after scoring, or fuzzy taste-word translation; also when the result is too AI, oily, fake, plastic, 3D-looking, generic, not premium, inconsistent, has extra props, badly composed, or style-wrong. For ordinary image generation without anti-AI/refinement/composition/pose/inconsistency/style-translation needs, route to imagegen instead.
---

# Reduce AI Look Imagegen

## Core Rule

Default to the fastest sufficient path. Do not load the large reference files unless the request truly needs them. For most tasks, use `references/fast-path.md` and produce one compact image prompt.

This skill has two trigger channels:

1. **Explicit anti-AI/refinement channel**: Use this skill when the user asks to reduce AI feel, fix implausible anatomy/action, remove unreasonable extras, fix prompt-image mismatch, translate vague taste words, improve a prompt, diagnose a generated image, or make a result less glossy/generic/fake.
2. **Ordinary image generation channel**: If the user simply asks to generate an image and does not mention anti-AI, realism repair, pose/action correction, style diagnosis, or prompt refinement, call the available image-generation skill/tool instead, such as `plus-imagegen`, `gpt-image`, or the host-native image tool. Do not force this skill into ordinary generation unless its routing help is needed.

Use the host-native image generation or image editing tool when available. Do not call `gpt-image`, `OPENAI_API_KEY`, `OPENAI_BASE_URL`, or third-party image APIs unless the user explicitly asks for an API or CLI workflow.

This skill is for Codex/ChatGPT Plus-style hosted image generation and editing. If the native image tool is unavailable, explain that the Plus-style generation path cannot run in this runtime and provide a prompt-only deliverable or ask whether to switch to an API/CLI path.

## Workflow

1. Route the request with the two trigger channels above.
2. If this skill is needed, choose a processing budget:
   - **Fast path**: ordinary anti-AI prompt rewrite, one style, no complex diagnosis. Use `references/fast-path.md` only.
   - **Focused path**: one clear problem such as pose, anime gloss, fuzzy wording, or style mixing. Load only the single most relevant reference.
   - **Deep path**: complex before/after analysis, reusable profile, broad style taxonomy work, or repeated failed generations. Load multiple references only when necessary.
3. Classify the request as new image generation, image editing, style variation, realism pass, or prompt rewrite.
4. Identify the likely AI-feel risks before writing the final prompt:
   - over-smooth skin, plastic texture, waxy faces
   - symmetrical lighting, perfect surfaces, generic beauty retouching
   - impossible hands, vague object relationships, floating props
   - extra objects that violate the requested concept, such as unwanted weapons, props, logos, pets, wings, halos, or background items
   - behavior/expression mismatch, viewpoint/environment mismatch, or role/costume mismatch
   - anatomically implausible poses, broken joint angles, unclear weight balance
   - weak composition, no focal hierarchy, random crop, or wrong safe area for the output format
   - overloaded style words, cinematic cliches, shallow depth-of-field everywhere
   - sterile backgrounds, fake film grain, too-clean product renders
   - unreadable text, hallucinated logos, mismatched typography
   - anime images that look like glossy 3D renders instead of drawn cels or painted backgrounds
5. Replace generic polish with grounded production details:
   - real camera or medium constraints
   - motivated light sources and imperfect shadow behavior
   - tactile materials, wear, dust, compression, or handling marks when appropriate
   - plausible body pose, object contact, scale, and gravity
   - corrected action logic: joint range, load-bearing limb, gaze direction, grip, and contact points
   - consistency cleanup: remove extras, align expression with action, align viewpoint with environment, preserve only user-requested props
   - composition planning: focal anchor, viewer path, depth layers, crop safety, and output-specific safe areas
   - hand-drawn production cues when the target is anime or illustration
   - specific but restrained color, lens, layout, and post-processing choices
6. Write a compact final prompt using the pattern below.
7. Call the native image tool directly for generation or editing.
8. Save or organize generated files under:
   - `F:\Codex_Save_Library\01_Generated_Images` for new text-to-image outputs
   - `F:\Codex_Save_Library\02_Image_Edits` for edited or inpainted images
   - `F:\Codex_Save_Library\04_Final_Exports` for final deliverables
   - `F:\Codex_Save_Library\06_Prompt_Archive` for reusable prompt notes when the prompt itself is the deliverable

## Self-Check Loop

When validating whether this skill helped, compare before and after on concrete visual failure modes instead of asking whether the image is simply "better."

Score these axes from 1-10, where 10 means more AI-looking:

- plastic skin or waxy surfaces
- over-clean lighting and exposure
- generic glossy finish
- impossible anatomy or object contact
- unreasonable pose, joint, balance, or action logic
- extra/unrequested objects or role-breaking props
- behavior/expression/viewpoint/environment mismatch
- weak composition, wrong crop, unclear focal anchor, or missing safe area
- sterile background and missing texture
- overprocessed color or fake HDR

For existing images, first try a native image-editing pass with strict preservation constraints. If the runtime cannot pass the source image into the native editor, make a low-intrusion local proof only: highlight rolloff, slight grain, restrained color correction, edge softness, and contact-shadow emphasis. Mark that result as a post-processing validation, not a full image-editing success.

## Inconsistency Cleanup

Use this module when a first generated image contains something that contradicts the user's request or visual logic.

Check these five consistency layers:

- **Concept lock**: Does every visible prop, costume element, creature, weapon, symbol, and background object belong to the requested concept?
- **Role lock**: Does the character still read as the requested role/skin, such as maid, wizard, student, knight, idol, mascot, product model, or UI asset?
- **Behavior-expression match**: Does the face/emotion match the action and scene? A battle pose should not have a blank selfie smile unless intended; a calm healer should not look aggressive by accident.
- **Viewpoint-environment match**: Do camera angle, horizon, floor plane, lighting direction, reflections, and background scale agree?
- **Prop necessity**: Keep required objects, remove unrequested objects, and downgrade optional objects into background only when they support the story.

For edit prompts, add:

```text
Inconsistency cleanup: compare the image against the original prompt and remove or correct anything that violates the requested concept. Keep only props, costume details, environment elements, and expressions that support the stated role and action. Remove unrequested extra objects such as weapons, staffs, logos, wings, halos, pets, duplicate accessories, or random background items unless explicitly requested. Align expression with behavior, gaze with action, camera viewpoint with environment, and lighting/reflections with the scene.
```

## Pose And Action Reasoning

Use this module whenever an image contains a person, animal-like character, humanoid figure, action pose, hand gesture, dance/fight/sports movement, sitting/lying pose, or object interaction.

First diagnose the pose before rewriting or editing:

- **Skeleton flow**: head, neck, shoulders, spine, pelvis, knees, ankles, elbows, wrists, and fingers should connect through a believable body line.
- **Joint range**: avoid elbows, knees, wrists, necks, waists, and ankles bending past normal range unless the subject is explicitly stylized or nonhuman.
- **Weight and balance**: identify which foot, knee, hip, seat, hand, wall, or object carries the body weight.
- **Contact points**: hands should actually grip, press, rest, or hover with a reason; feet should meet the floor plane; seated bodies should compress into the surface.
- **Action intent**: the pose should match the story: reaching, leaning, jumping, kneeling, holding, fighting, dancing, or resting should have a clear start/end direction.
- **Foreshortening and camera**: extreme limbs near the camera need plausible scale, overlap, shadow, and perspective.
- **Clothing response**: folds, straps, hems, sleeves, and hair should follow the pose and gravity.

When correcting a pose, preserve the character identity, outfit, scene, camera angle, and intended emotion. Change only the anatomy or action mechanics needed to make the pose believable. Do not make the pose more sexualized, revealing, violent, or extreme unless the user explicitly asks and the request is allowed.

For edit prompts, add:

```text
Pose/action correction: adjust the figure into a believable human pose with natural joint range, clear weight support, grounded feet or seated contact, realistic hand placement, and clothing/hair responding to gravity. Preserve identity, outfit, camera angle, scene, and emotional intent. Change only the anatomy, limb placement, and contact points required to fix the implausible action.
```

## Hand-Drawn Anime Reasoning

Use this module when the target is anime, manga, cel-era illustration, modern TV anime, character art, animation stills, or painted anime backgrounds.

Do not rely on named studio or living-artist style copying. Translate references into production traits:

- **Layout/genga intent**: a clear body line, readable silhouette, decisive gesture, and camera-aware staging.
- **Clean line layer**: consistent ink contour, intentional line-weight changes, closed shapes where color fills should stop, and fewer random micro-lines.
- **Cel color layer**: flat local color fields, 2-3 deliberate shadow tones, hard or mostly hard shadow edges, simple highlight shapes, and no photoreal skin gradients.
- **Painted background layer**: gouache/poster-color or watercolor-like brush masses, softened distant detail, atmospheric color harmony, and visible hand-painted simplification.
- **Compositing layer**: characters can be cleaner and flatter than backgrounds; add only mild paper, scan, gate-weave, dust, or photographed-cel softness when it fits.
- **Limited-animation discipline**: make a strong held frame with clear staging instead of cramming every surface with detail.

AI-looking anime usually comes from too many effects at once: glossy 3D lighting, photographic depth of field, over-detailed hair strands, airbrushed skin, tiny meaningless costume details, random rim lights, gradient soup, and background/character rendering that does not belong to the same production.

For hand-drawn anime prompts, add:

```text
Anime production look: layout-driven composition, clean animation linework, flat cel color fields, two-tone shadow blocks, controlled highlight shapes, hand-painted background with poster-color/gouache texture, mild photographed-cel softness, no glossy 3D rendering or overblended gradients.
```

## Prompt Pattern

Use this structure, trimming fields that do not help the request:

```text
Create a [medium/format], [aspect ratio].
Subject: [specific subject with grounded age/material/shape/details].
Scene: [real location, time, action, object relationships].
Production: [camera/medium, lens or design process, realistic constraints].
Light: [motivated light source, shadow behavior, exposure limits].
Texture: [surface detail, small imperfections, physical evidence].
Composition: [shot size, angle, foreground/background, negative space].
Color and finish: [restrained palette, grade, print/render finish].
Action logic: [pose, weight support, hand/foot contact, object interaction, gravity].
Anti-AI constraints: Avoid plastic skin, over-symmetry, glossy generic surfaces, impossible anatomy, broken joints, floating limbs, fake logos, and overprocessed HDR.
```

For hand-drawn anime, replace or supplement the production fields with:

```text
Line and color: clean animation contour, controlled line weight, closed cel shapes, flat local colors, 2-3 hard-edged shadow tones.
Background: hand-painted poster-color/gouache feel, simplified brush masses, atmospheric color harmony, softer distant detail.
Compositing: character cel layer over painted background, mild scan/photographed-cel softness, no glossy 3D lighting, no random micro-detail.
```

For edits, add:

```text
Preserve: [identity, pose, layout, product shape, existing light direction].
Change only: [the requested edits].
Do not alter: [sensitive or important unchanged areas].
```

## Realism Heuristics

Prefer nouns and physical facts over broad adjectives. Replace "beautiful cinematic photo" with concrete conditions such as "35mm documentary photo, window light from camera-left, slightly clipped highlights on the white wall, natural skin texture, relaxed posture."

Use fewer style tags. If a prompt contains many style labels, keep the two or three that affect the image most and convert the rest into visual evidence.

Give the model ordinary constraints. Real images often include uneven hems, tiny reflections, scuffed edges, imperfect alignment, hand pressure on objects, compression artifacts, dust, fingerprints, or minor motion blur. Add only the imperfections that fit the scene.

For people, specify natural asymmetry, believable posture, skin texture, age-appropriate features, hand placement, and contact points. Avoid "perfect face," "flawless skin," and beauty-retouch wording unless the user asks for that look.

For products, specify manufacturing details, scale references, material transitions, seams, surface wear, real packaging print behavior, and plausible reflections. Avoid empty studio gloss unless the user wants a polished catalog render.

For illustrations, reduce AI feel through coherent art direction rather than fake photorealism: consistent line weight, limited palette, purposeful composition, medium-specific marks, and clear subject hierarchy.

## Reference Loading

Read `references/fast-path.md` first for most anti-AI prompt rewrites. If it is enough, do not load other references.

Read `references/inconsistency-cleanup.md` when the image or prompt contains extra unwanted objects, role/costume mismatches, behavior/expression mismatch, viewpoint/environment mismatch, or prompt-image contradictions.

Read `references/routing-and-triggering.md` when deciding whether this skill should run at all, especially when the user merely asks for image generation without mentioning anti-AI refinement.

Read `references/prompt-recipes.md` when the user asks for a reusable workflow, prompt archive, before/after prompt variants, pose/action correction, or a difficult realism pass involving people, products, interiors, food, typography, anime, manga, cel-style illustration, or painted backgrounds.

Read `references/anime-handdrawn-look.md` when the request specifically asks for anime hand-drawn feel, cel-era texture, less glossy anime images, genga/layout-informed action, or hand-painted anime backgrounds.

Read `references/style-taxonomy.md` when the user asks to choose, compare, classify, refine, or translate broader visual styles such as photography, painting, printmaking, poster design, manga, webtoon, vector, pixel art, product render, or genre aesthetics.

Read `references/style-expansion-pack.md` when the user asks for more niche style families, historical art/design movements, commercial entertainment art, craft/material looks, scientific illustration, technical diagrams, retro internet aesthetics, or when style-taxonomy needs a finer category.

Read `references/style-blending-rules.md` when a prompt mixes multiple styles, when the output risks becoming generic AI style soup, or when two requested styles have conflicting medium logic such as watercolor plus HDR, pixel art plus shallow depth of field, cel anime plus oil impasto, or vector plus photoreal material texture.

Read `references/style-selection-and-use-cases.md` when the user has not chosen a style, describes taste with vague words like premium/cute/realistic/cinematic/clean, or needs style guidance for a specific output such as avatar, wallpaper, poster, product image, sticker, game asset, character sheet, thumbnail, album cover, or social ad.

Read `references/mainstream-style-composition.md` when the user asks for better composition, framing, layout, cover/poster/wallpaper/game UI composition, mainstream style completion, or a professional-looking result where style choice and composition must be decided together.

Read `references/style-quality-rubric.md` when validating whether a prompt or generated image actually reduced AI feel, comparing before/after results, scoring style consistency, or deciding which failure modes to fix in the next iteration.

Read `references/style-prompt-cookbook.md` when the user wants ready-to-use prompt skeletons, fast variants, or examples for a chosen visual style family.

Read `references/failure-feedback-fixes.md` when the user critiques a result with plain-language feedback such as too AI, too glossy, too fake, too busy, not premium, too childish, too 3D, wrong pose, bad hands, fake text, generic, flat, or not hand-drawn enough.

Read `references/intent-and-fuzzy-language.md` before choosing a style when the user request contains ambiguous wording, incomplete taste words, or format-like terms that must not be overridden, such as four-panel comic, manga page, poster, logo, icon, storyboard, premium, atmospheric, story-rich, healing, cute, Japanese-style, cinematic, realistic, clean, hand-drawn, game UI, or "make it feel better."

When the user specifies an output format, treat it as a hard constraint before style interpretation. For example, "four-panel comic" means preserve a four-panel sequential comic structure; do not turn it into a single poster, cinematic illustration, or unrelated art style unless the user explicitly asks to change format.

## Reference Selection Matrix

Pick the first matching reference and stop unless the task remains ambiguous:

| Task signal | Load |
|---|---|
| ordinary image generation only | no reference; route to imagegen |
| lower AI feel, simple rewrite | `fast-path.md` |
| should this skill run? | `routing-and-triggering.md` |
| extra objects or prompt-image inconsistency | `inconsistency-cleanup.md` |
| vague user wording or format lock | `intent-and-fuzzy-language.md` |
| existing image or prompt critique | `failure-feedback-fixes.md` |
| anime/cel/genga/background | `anime-handdrawn-look.md` |
| composition, framing, mainstream style completion | `mainstream-style-composition.md` |
| mixed/conflicting styles | `style-blending-rules.md` |
| choose style by use case | `style-selection-and-use-cases.md` |
| broad style classification | `style-taxonomy.md` |
| niche/historical/craft/technical style | `style-expansion-pack.md` |
| ready prompt template | `style-prompt-cookbook.md` |
| score before/after | `style-quality-rubric.md` |
| detailed recipe for known domain | `prompt-recipes.md` |

## Token Budget Rules

- Prefer one final prompt under 120 words for normal image generation.
- Use at most 3 anti-AI constraints unless the user asks for detailed prompt engineering.
- Load one reference file at a time; never load the full style library by default.
- Do not print long diagnostics before calling image generation.
- If the user asks for ordinary generation, route to imagegen and skip this skill.
- If the user asks for vague improvement, parse intent first, then load only the relevant focused reference.
- Put long reusable notes in `F:\Codex_Save_Library\06_Prompt_Archive`, not in the chat response.

## Output Style

When the user primarily wants an image, keep the visible explanation short and generate. When the user wants the skill, prompt, or workflow, include:

- the diagnostic notes
- the final Plus-ready prompt
- any preservation or edit constraints
- the saved path if a prompt archive or image output is created
