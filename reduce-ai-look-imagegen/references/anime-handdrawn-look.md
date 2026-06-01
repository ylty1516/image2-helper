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
