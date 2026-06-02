# Anime Hand-Drawn Look

Use this reference when improving anime, manga, cel animation, or hand-painted background prompts so they feel less AI-generated.

## Core Principle

Do not ask for "more anime quality." Ask for a believable animation production artifact: a layout-driven drawing, clean line layer, flat cel color layer, painted background layer, and restrained compositing layer.

## AI-Looking Anime Failure Modes

- glossy 3D skin and hair highlights
- soft airbrushed gradients everywhere
- random rim lights that do not match the scene
- too many tiny costume ornaments or hair strands
- line art that changes thickness without purpose
- character and background rendered with the same plastic finish
- photographic bokeh, HDR glow, and lens effects fighting cel color
- painterly mush where animation needs clear silhouettes
- hands, feet, and props that do not read as animation key poses

### Over-Decorated Neon / Cyber Anime Tells

Use this diagnosis when an anime image looks impressive but still feels AI-made, especially with blue-purple cyberpunk, crystals, floating UI, code, butterflies, galaxies, or transparent effects.

Likely causes:

- every area has the same high-detail sparkle, so there is no human-made focal hierarchy
- blue/purple/cyan glow covers skin, hair, clothes, background, and props with one uniform finish
- random floating code, fake UI panels, constellations, shards, petals, or crystals decorate the image without story function
- unreadable pseudo-text and pseudo-code are used as texture instead of designed graphic elements
- hair, costume straps, jewelry, glass, and light trails contain too many tiny strands and ornaments
- faces become generic polished anime beauty: smooth skin, huge glossy eyes, weak expression specificity
- character layer, effects layer, and background layer share the same luminous plastic rendering

Human-artist comparison:

- detail is selective; the focal face, hands, or prop gets the most design attention while secondary areas simplify
- effects have a source, direction, opacity, and rhythm instead of being evenly sprinkled
- linework and shadow shapes stay readable under the lighting
- props, UI, symbols, and costume pieces have a clear function or are removed
- color temperature has anchors: neutral darks, local skin color, material color, and only a few deliberate glow accents
- imperfections come from process: visible brush/line decisions, slight asymmetry, texture, and purposeful omissions

Prompt patch:

```text
Reduce the over-decorated AI cyber-anime finish. Keep one clear focal hierarchy: face and hands first, main silhouette second, background third. Limit glow to 2-3 motivated sources with visible direction and falloff; remove decorative floating code, random crystals, petals, constellations, and UI panels that do not serve the scene. Use readable hand-drawn anime linework, flatter cel color, selective hard-edged shadow shapes, neutral dark anchors, and a few restrained cyan/violet accents. Keep hair as designed masses with selected strands, not hundreds of glowing threads. No fake text, no meaningless micro-detail, no uniform blue-purple gloss across every material.
```

### Spectacular Sky / Scenic Anime Poster Tells

Use this diagnosis when an anime landscape looks like a beautiful sunset, rooftop, seaside station, bus stop, shrine, rainbow, snow, or cloud poster but still feels AI-made.

Likely causes:

- the sky carries maximum drama: giant cumulonimbus, glowing sunset, rainbow, stars, snow, birds, or wet reflections all competing at once
- cloud edges have uniform glittery highlight detail instead of believable weather structure and broad hand-painted masses
- every surface is treated like a mirror: platforms, rooftops, stones, roads, and puddles reflect the sky with the same glossy coating
- iconic anime scenery props feel like a checklist: seaside station, torii gate, lantern, umbrella, bicycle, sunflowers, rooftop rail, distant city, dramatic sky
- characters are generic wistful silhouettes placed inside a background rather than people with scene-specific weight, gesture, and purpose
- signage and location text are half-legible pseudo-Japanese or pseudo-station graphics
- color grading uses blanket orange-pink sunset or blue-violet twilight across all materials, leaving no local color or neutral anchors
- foreground, midground, and sky are all over-rendered, so the picture reads as an algorithmic "anime wallpaper" instead of an observed scene

Human-artist comparison:

- sky drama is designed around one weather moment; quiet areas and broad cloud masses are allowed to stay simple
- reflections are selective, broken by tile seams, puddle edges, wet/dry patches, grime, and surface roughness
- a location has ordinary specificity: usable station hardware, believable railings, accurate roof supports, real plant growth, functional signs
- characters have weight and intent: feet contact the ground, clothes react to wind/rain, gaze and posture imply a concrete beat
- composition sacrifices some prettiness for story, readability, and believable place memory
- text is either accurately designed, intentionally blank, or simplified as non-readable graphic blocks

Prompt patch:

```text
Reduce the anime-wallpaper sky template. Keep one observed place and one weather/light event, not a checklist of dramatic scenery. Build the sky from broad hand-painted cloud masses with selective edge light, believable cloud scale, and quieter negative areas. Make reflections local and imperfect: puddles, tile seams, wet/dry patches, surface roughness, and broken highlights instead of mirror gloss everywhere. Give the foreground objects functional construction and ordinary wear; remove fake station text or leave signage blank. Make the character belong to the scene through grounded feet, specific posture, wind/rain response, and a clear story beat. Preserve local colors and neutral anchors; avoid blanket orange-pink sunset, blue-violet twilight, over-detailed clouds everywhere, generic wistful poses, and iconic anime scenery props used only as decoration.
```

## Hand-Drawn Production Axes

### Layout / Genga

Use for action, body language, and staging.

Prompt cues:

```text
layout-driven staging, readable silhouette, decisive key pose, clear body line, camera-aware spacing, action readable as a held animation frame
```

### Line / Douga

Use for clean anime drawings.

Prompt cues:

```text
clean animation linework, controlled line weight, closed shapes for color fills, simple confident contours, no scratchy random micro-lines
```

For rougher production-art variants:

```text
rough genga pencil lines, construction marks, colored pencil shadow notes, energetic but readable animation sketch
```

### Cel Color

Use for classic or modern cel-style characters.

Prompt cues:

```text
flat local color fields, two-tone cel shadows, hard-edged shadow blocks, simple highlight shapes, limited palette, no photoreal skin gradients
```

### Background Painting

Use for anime environments.

Prompt cues:

```text
hand-painted poster-color/gouache background, simplified brush masses, atmospheric color harmony, softened far detail, visible paint texture, practical light design
```

### Compositing

Use to make the image feel like a frame rather than an over-rendered illustration.

Prompt cues:

```text
character cel layer over painted background, mild photographed-cel softness, subtle paper/scan texture, restrained grain, no HDR bloom, no fake cinematic bokeh
```

## Prompt Template

```text
Create a hand-drawn anime still, [aspect ratio].
Subject: [character/action/object].
Layout: [camera angle, silhouette, action line, foreground/background relationship].
Linework: clean animation contours, controlled line weight, closed cel shapes.
Color: flat local colors, 2-3 hard-edged cel shadow tones, simple highlight shapes.
Background: hand-painted poster-color/gouache feel, simplified brush masses, atmospheric color harmony.
Compositing: character cel layer over painted background, mild scan or photographed-cel softness.
Action logic: physically readable key pose, natural joint range, clear weight/contact points.
Avoid: glossy 3D rendering, photoreal gradients, over-detailed hair, random rim lights, fake HDR, plastic skin, unreadable hands, background/character style mismatch.
```

## Existing Anime Image Edit Prompt

```text
Edit the provided anime-style image to reduce AI gloss while preserving the character identity, pose intent, outfit, scene, composition, and color mood.
Convert the finish toward a believable hand-drawn animation still: cleaner animation contours, flatter local color fields, 2-3 deliberate hard-edged shadow tones, simpler highlight shapes, less airbrushed skin/hair, and a hand-painted background feel with poster-color/gouache texture.
Keep the character layer slightly cleaner and flatter than the background layer.
Correct any implausible pose mechanics only as needed: natural joint range, readable silhouette, grounded contact points, and clothing/hair following gravity.
Do not copy a named studio or artist style. Do not add glossy 3D lighting, photographic bokeh, fake HDR bloom, random micro-detail, or extra costume ornaments.
```

## Quick Before/After Rewrite

Weak:

```text
high quality anime girl, beautiful, cinematic, ultra detailed, soft lighting, masterpiece
```

Stronger:

```text
hand-drawn anime still with layout-driven staging: clean animation contours, flat cel color fields, two-tone hard-edged shadows on the face and uniform, simple highlight shapes in the hair, character cel layer over a softly painted poster-color classroom background, mild photographed-cel softness, no glossy 3D lighting or airbrushed gradients
```

Weak:

```text
anime landscape, beautiful clouds, detailed city, vibrant lighting
```

Stronger:

```text
hand-painted anime background plate: poster-color/gouache texture, broad simplified cloud masses, warm atmospheric color harmony, softened far city detail, foreground shapes painted with clearer edges, practical sunlight direction, no HDR glow or photoreal lens blur
```
