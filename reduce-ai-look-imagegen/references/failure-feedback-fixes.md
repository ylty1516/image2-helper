# Failure Feedback Fixes

Use this when the user reacts to a generated image. Translate their everyday wording into concrete prompt changes.

## Feedback Translation Table

### "Too AI"

Likely causes:

- generic style stack
- glossy surfaces
- perfect symmetry
- no production constraints
- implausible anatomy or contact

Fix:

```text
Replace generic quality words with medium-specific process cues. Add real tool/camera/print/paint constraints, grounded contact shadows, imperfect material evidence, and style-specific avoid terms.
```

Prompt patch:

```text
Make the result feel like a real [medium/process] artifact: [specific texture], [specific light/value model], [specific production limits]. Avoid generic AI gloss, over-symmetry, meaningless micro-detail, and impossible contact points.
```

### "Pretty but still AI" / "Cyber anime AI look"

Likely causes:

- neon blue-purple palette applied everywhere
- equal sparkle/detail density across the whole image
- decorative floating UI, fake code, crystals, petals, or light trails without purpose
- glossy character, effects, and background all sharing one plastic finish
- generic polished anime face with weak expression or identity

Fix:

```text
Reduce effects and restore human illustration decisions: one focal hierarchy, fewer motivated glow sources, readable line/shadow shapes, designed hair masses, functional props, neutral color anchors, and no fake text.
```

Prompt patch:

```text
Keep the appealing anime polish, but remove the AI-template cyber decoration. Use one clear focal point, selective detail only near the face/hands/main prop, 2-3 motivated glow accents, neutral dark and skin-color anchors, readable cel shadow shapes, and designed hair masses. Remove random floating code, fake UI panels, crystals, petals, constellations, meaningless micro-detail, and uniform blue-purple gloss across skin, hair, clothes, and background.
```

### "Anime wallpaper look" / "Sky looks too AI"

Likely causes:

- spectacular sky, rainbow, sunset, stars, snow, birds, and reflections stacked together
- over-detailed cloud highlights with no quiet broad shapes
- wet ground, rooftops, roads, and platforms reflecting like perfect mirrors
- familiar anime scenery props used as a checklist: seaside station, torii gate, umbrella, bicycle, rooftop rail, sunflowers, lanterns
- generic wistful character pose inserted into a beautiful background
- fake station text, unreadable signs, or invented location labels

Fix:

```text
Turn the scene from an anime wallpaper template into an observed place: one weather event, one story beat, selective sky detail, imperfect local reflections, functional architecture/props, grounded character contact, and no fake text.
```

Prompt patch:

```text
Reduce the anime-wallpaper feel. Use one specific place and one weather/light event instead of stacking sunset, rainbow, stars, snow, birds, and mirror reflections. Paint the sky with broad cloud masses, selective edge light, and quiet negative areas. Make reflections local and broken by puddle edges, tile seams, surface roughness, grime, and wet/dry patches. Give station/shrine/rooftop props functional construction and ordinary wear; leave signs blank unless exact text is provided. Make the character belong to the scene with grounded feet, specific posture, wind/rain response, and a clear story beat. Avoid over-detailed clouds everywhere, blanket orange-pink or blue-violet grading, generic wistful poses, and iconic scenery props used only as decoration.
```

### "Epic fantasy wallpaper" / "Fantasy landscape feels AI"

Likely causes:

- castle, ruins, mountains, aurora, moon, waterfalls, lava, floating islands, glowing crystals, and dramatic clouds stacked together
- terrain and architecture are decorative rather than physically or functionally designed
- scale system is unclear across towers, bridges, cliffs, waterfalls, cities, and mountains
- every distance layer is equally sharp, detailed, glowing, and dramatic
- multiple light sources compete without hierarchy

Fix:

```text
Turn the fantasy panorama into a designed world: one concept hook, one terrain logic, functional architecture, scale references, coherent light hierarchy, atmospheric distance, and controlled detail density.
```

Prompt patch:

```text
Reduce the generic epic-fantasy wallpaper feel. Use one clear worldbuilding hook instead of stacking castle, aurora, moon, lava, waterfalls, floating islands, ruins, and glowing crystals. Give terrain physical cause: erosion, water source and drainage, lava following gravity, ice/snow accumulation, cliff stability. Give architecture function: entrances, paths, bridges, supports, defenses, settlements, scale references, material wear, and cultural consistency. Use one dominant light source with limited material-based secondary glow; simplify far distance with atmosphere and broad value shapes. Avoid random spires, repeated ruins, impossible waterfalls, glowing cracks everywhere, unreadable kitbash, and equal detail density across foreground, midground, and background.
```

### "Too glossy / oily"

Likely causes:

- 3D material language leaking into non-3D styles
- overdone highlights
- airbrushed gradients

Fix:

```text
Use matte finish, flat color fields, rougher material, or print/paint texture. Limit highlights to simple shaped accents.
```

Prompt patch:

```text
Use a matte surface finish with restrained highlight shapes; reduce specular shine and airbrushed gradients; keep shadows controlled by [cel/paint/print/photo] logic.
```

### "Too plastic"

Likely causes:

- skin smoothing
- no pores/fabric/material grain
- uniform reflections

Fix:

```text
Add natural surface variation, material thickness, fabric tension, skin or object texture, and uneven light response.
```

Prompt patch:

```text
Add believable surface variation: natural skin or material texture, fabric tension, tiny scuffs or handling marks where appropriate, and non-uniform light response.
```

### "Too fake"

Likely causes:

- impossible lighting
- object scale mismatch
- unnatural pose
- background and subject do not share a world

Fix:

```text
Anchor the image with scale cues, shared light direction, contact shadows, and a clear physical scene.
```

Prompt patch:

```text
Unify the scene with one motivated light source, clear floor/wall/object contact, believable scale references, and background details that share the same perspective and material logic.
```

### "Anime character looks pasted into reality" / "Screen character feels fake"

Likely causes:

- anime layer uses different camera perspective, scale, or crop than the real scene
- no clear contact point, cast shadow, ambient occlusion, reflection, or foreground occlusion
- light direction, color temperature, exposure, and shadow softness do not match the room or screen
- character edges are too clean/sharp/glowing compared with photo grain, lens softness, or compression
- screen/display physics are missing: bezel occlusion, glass reflection, pixel grid, brightness falloff, and screen glow

Fix:

```text
First lock the existing background plate exactly, including objects, object positions, crop, exposure, color temperature, original light, original shadows, highlights, reflections, clutter, grain, and compression. Then integrate the character into the real camera plate by changing the character layer only: shared perspective, scale anchors, physical contact/occlusion, matching light response, edge softness, lens grain, reflected color, and display-surface physics when a screen is involved.
```

Prompt patch:

```text
Anime-real integration repair: preserve the existing real background exactly: all objects, positions, crop, camera perspective, exposure, color temperature, original light/shadows/highlights/reflections, clutter, texture, grain, and compression. Do not clean, relight, repaint, stylize, replace, blur, sharpen, denoise, rearrange, add, remove, or move anything in the background. Match the character layer to the real scene camera height, lens perspective, horizon/ground plane, scale anchors, crop, light direction, exposure, shadow softness, and material response. Add a clear physical anchor: feet/hand/body contacting or being occluded by a real surface, monitor bezel, phone glass, desk object, wall, or foreground prop. Add only localized character contact/occlusion effects where necessary; do not alter the room's original global lighting or existing object shadows. For screen scenes, align the character to the screen plane, bezel, glass reflection, pixel grid, brightness falloff, and screen glow without changing existing screen/glass/background details. Avoid floating sticker cutout, mismatched lighting, wrong scale, pure cel colors unaffected by the environment, impossible depth through the screen, moved objects, changed room lighting, and any background repainting.
```

### "Perspective is wrong" / "Space feels warped"

Likely causes:

- multiple horizon lines or vanishing systems
- floor, road, water, tabletop, or wall planes tilting in conflicting directions
- objects and figures do not share scale anchors
- feet, wheels, furniture legs, props, or buildings float without contact shadows
- unclear overlap order creates impossible intersections

Fix:

```text
Lock one camera height, horizon line, perspective system, ground/floor plane, scale anchors, contact shadows, occlusion order, foreshortening, and depth falloff before adding detail.
```

Prompt patch:

```text
Perspective repair: use one camera height, one horizon line, and one coherent perspective system. Align floor/ground/water/table planes, roads, rails, stairs, furniture, buildings, props, and figure feet to that system. Preserve scale anchors, contact shadows, overlap order, believable foreshortening, and atmospheric depth. Avoid mixed vanishing points, floating feet/props, warped stairs/railings, impossible intersections, and far objects rendered with foreground detail.
```

### "Too busy / cluttered"

Likely causes:

- detail everywhere
- no focal hierarchy
- too many props/effects

Fix:

```text
Choose one focal point, simplify secondary areas, and reserve negative space.
```

Prompt patch:

```text
Detail density: rich detail only at the focal point; simplify secondary surfaces; remove decorative props that do not support the story; preserve clean negative space.
```

### "Too empty / boring"

Likely causes:

- no story moment
- no texture or secondary shapes
- flat pose

Fix:

```text
Add one narrative cue, one foreground/background layer, and medium-specific surface detail.
```

Prompt patch:

```text
Add a clear story cue, layered foreground/midground/background shapes, and tactile medium-specific details while keeping the main silhouette readable.
```

### "Not premium"

Likely causes:

- too many effects
- cheap gold/gloss shortcuts
- poor spacing
- fake text/logo

Fix:

```text
Use restraint, precise spacing, material credibility, fewer objects, and no fake branding.
```

Prompt patch:

```text
Make it premium through restraint: precise spacing, quiet palette, credible material texture, controlled reflections, few objects, no fake brand marks or invented small text.
```

### "Too childish"

Likely causes:

- overly rounded shapes
- candy palette
- exaggerated facial proportions
- random cute decorations

Fix:

```text
Reduce decorative cuteness, mature the palette, simplify expression, and improve material/design restraint.
```

Prompt patch:

```text
Mature the design with a restrained palette, cleaner silhouette, fewer cute decorations, subtler expression, and more credible material detail.
```

### "Not cute enough"

Likely causes:

- expression too neutral
- shape language too sharp
- colors too cold
- detail too realistic

Fix:

```text
Round the silhouette, simplify features, warm the palette, strengthen expression.
```

Prompt patch:

```text
Increase cuteness through rounded shape language, readable expression, warm soft palette, simplified facial detail, and a small clear gesture.
```

### "Looks like 3D"

Likely causes:

- smooth gradients
- specular hair/skin
- depth-of-field and rim light
- overly volumetric shading

Fix:

```text
Use flat color, linework, print texture, or paint surface depending on target style.
```

Prompt patch:

```text
Remove 3D render cues: no glossy specular hair, no volumetric rim light, no photoreal depth-of-field. Use [flat cel color / brush texture / print separations / vector shapes] instead.
```

### "Not hand-drawn enough"

Likely causes:

- perfect edges
- digital gradients
- no paper/line/paint evidence

Fix:

```text
Add line weight, imperfect edge behavior, paper/paint/ink evidence, and human simplification.
```

Prompt patch:

```text
Make the image feel hand-drawn through controlled line weight, visible paper or paint behavior, simplified human-made shapes, slight edge irregularity, and no smooth AI gradients.
```

### "Bad hands"

Likely causes:

- no grip/contact logic
- hidden anatomy
- ambiguous finger count

Fix:

```text
Specify hand pose, contact, finger grouping, and object pressure.
```

Prompt patch:

```text
Hands: natural finger grouping, visible thumb placement, believable wrist angle, clear contact with [object/surface], no extra fingers, no melted knuckles.
```

### "Pose is weird"

Likely causes:

- broken joint range
- unclear weight support
- no action intent

Fix:

```text
Define support points, body line, and action direction.
```

Prompt patch:

```text
Pose: physically possible body line, natural joint range, clear weight supported by [foot/seat/hand], grounded contact points, clothing and hair following gravity.
```

### "Face feels generic"

Likely causes:

- default beauty face
- no asymmetry or identity markers
- over-smoothed features

Fix:

```text
Add specific face structure, expression, age/character cues, and reduce beauty retouch.
```

Prompt patch:

```text
Face: specific facial structure, subtle asymmetry, natural expression, age-appropriate features, no generic beauty smoothing or over-enlarged glossy eyes.
```

### "Same-face anime"

Likely causes:

- generic anime prompt
- no facial design rules
- overemphasis on eyes/hair

Fix:

```text
Define silhouette, face shape, eye spacing, brows, nose/mouth simplification, expression, and hairstyle mass.
```

Prompt patch:

```text
Character design: distinctive face silhouette, specific eye spacing and brow shape, simple but individual nose/mouth design, hairstyle as readable masses rather than many strands.
```

### "Text is bad"

Likely causes:

- model invented text
- too much small typography
- no safe area

Fix:

```text
Remove text from generation or use exact text only. Leave blank safe areas.
```

Prompt patch:

```text
Text: no invented text or logos; leave a clean blank title-safe area for typography to be added later.
```

### "Cheap stock image"

Likely causes:

- generic pose
- generic lighting
- fake smiles
- empty concept

Fix:

```text
Add lived-in specifics, real gesture, imperfect framing, and actual context.
```

Prompt patch:

```text
Avoid stock-photo staging: use a specific lived-in setting, natural gesture, imperfect framing, credible wardrobe/object details, and a real story moment.
```

### "Too fantasy generic"

Likely causes:

- random armor/runes/glow
- no culture/material logic
- no practical design

Fix:

```text
Define material culture, function, wear, and limited magic effect.
```

Prompt patch:

```text
Fantasy design: functional materials, visible wear, culturally consistent ornament, limited magic effects with a clear source, no random glowing symbols.
```

### "Too cold"

Likely causes:

- blue-gray palette
- sterile lighting
- no human texture

Fix:

```text
Add warm practical light, tactile material, and small human details.
```

Prompt patch:

```text
Warm the scene with practical light, tactile surfaces, subtle color temperature contrast, and small lived-in details without turning everything orange.
```

### "Too warm / yellow"

Likely causes:

- blanket warm color grade
- no neutral anchors

Fix:

```text
Add neutral whites/grays, cooler shadows, and restrained warmth.
```

Prompt patch:

```text
Use restrained warmth with neutral anchors, cooler shadow notes, and natural skin/material color; avoid blanket yellow-orange grading.
```

### "Too dark"

Likely causes:

- low-key without value hierarchy
- black crush

Fix:

```text
Add selective highlights, readable silhouette, and midtone separation.
```

Prompt patch:

```text
Keep the mood dark but readable: separate silhouette from background, preserve midtone detail, add selective motivated highlights, avoid black mush.
```

### "Too clean"

Likely causes:

- no wear
- perfect surfaces
- sterile background

Fix:

```text
Add use evidence and controlled imperfection.
```

Prompt patch:

```text
Add controlled real-world imperfection: slight wear, dust, fabric wrinkles, fingerprints or scuffs where appropriate, and uneven object placement.
```

### "Too dirty"

Likely causes:

- grunge everywhere
- no material hierarchy

Fix:

```text
Keep patina local and meaningful.
```

Prompt patch:

```text
Use selective patina only where contact or age would create it; keep focal surfaces readable and avoid random grunge overlays.
```

## Revision Flow

1. Quote or paraphrase the user's critique.
2. Translate it into 1-3 likely causes.
3. Apply only the relevant prompt patch.
4. Keep successful parts unchanged.
5. If two critiques conflict, prioritize the newest or ask for a tradeoff.

## Compact Response Pattern

```text
Diagnosis: [plain-language cause].
Keep: [what worked].
Change: [specific visual mechanics].
Next prompt patch: [copy-ready patch].
```
