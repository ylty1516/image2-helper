# Style Blending Rules

Use this when the user mixes style names or asks for a hybrid look.

## Core Rule

Every image needs one dominant rendering logic. Treat other styles as modifiers.

Use this hierarchy:

1. **Base medium**: how the image is physically or digitally made.
2. **Structure**: composition, line, shape, camera, or layout logic.
3. **Color/light model**: how value, shadow, and palette behave.
4. **Surface finish**: paper, scan, print, grain, paint, pixels, glass, fabric.
5. **Mood/genre modifier**: cyberpunk, cozy, luxury, gothic, retro, etc.

If two requested styles conflict, keep the base medium honest and translate the second style into palette, subject, composition, or motif.

## Blend Formula

```text
Base medium: [one medium/process].
Subject/use: [what the image is for].
Structure: [composition/layout/line/camera].
Modifier: [one style or genre translated into palette/motifs].
Finish: [medium-specific texture].
Avoid: [conflicts that would break the base medium].
```

## Conflict Resolver

### Watercolor + Cyberpunk

Keep watercolor as the base. Convert cyberpunk into subject and color.

Use:

```text
transparent watercolor city scene, neon signs suggested through layered magenta and cyan washes, pigment blooms in rainy reflections, paper grain visible, softened edges
```

Avoid:

```text
HDR neon glow, glossy 3D reflections, razor-sharp signage, heavy black gradients
```

### Pixel Art + Cinematic

Keep pixel art as the base. Convert cinematic into composition and palette.

Use:

```text
fixed pixel grid, limited palette, dramatic silhouette staging, foreground/midground/background readable in tile clusters, no anti-aliased blur
```

Avoid:

```text
depth-of-field blur, smooth lens flare, painted gradients, inconsistent pixel sizes
```

### Cel Anime + Oil Painting

Choose one base. Usually keep cel anime and borrow oil painting only as background mood or color temperature.

Use:

```text
clean cel character layer with flat colors and hard shadows, background uses painterly color temperature shifts and visible brush masses, no impasto on the character
```

Avoid:

```text
thick oil texture on anime eyes, airbrushed gradients, glossy 3D hair
```

### Vector + Photoreal Product

Choose whether it is a diagram or a product render.

If vector is base:

```text
flat vector product diagram, simplified material icons, clean paths, limited palette, consistent stroke, no photoreal reflections
```

If photo/render is base:

```text
real product material with vector overlay labels or icon accents, grounded reflections, simplified UI callout shapes
```

Avoid:

```text
half-photoreal half-flat object surfaces with no boundary
```

### Risograph + Luxury

Keep risograph as print process. Convert luxury into spacing, restraint, and palette.

Use:

```text
two-ink risograph poster, warm paper, precise negative space, restrained metallic-evoking ochre ink, grainy stencil texture, slight registration offset
```

Avoid:

```text
gold foil realism, glossy reflections, smooth gradients, many ink colors
```

### Gouache + Minimal UI

Keep gouache as illustration base and UI as composition/grid.

Use:

```text
opaque gouache interface illustration, simplified panels as painted color blocks, matte brush texture, consistent spacing, no tiny readable UI text
```

Avoid:

```text
crisp app screenshots, real interface text, glassmorphism blur
```

### Clay + Anime Character

Keep clay as physical model. Convert anime into character proportions and expression.

Use:

```text
hand-shaped clay figure with anime-inspired proportions, visible fingerprints, practical miniature lighting, simple painted eyes, fabric or paper set pieces
```

Avoid:

```text
smooth CGI anime skin, hair made of impossible fine strands, glossy plastic finish
```

### Noir + Children's Book

Keep children's book if the target is age-friendly. Convert noir into light contrast and mystery, not danger.

Use:

```text
children's picture book illustration with gentle noir-inspired shadows, warm lamplight, curious expression, simplified shapes, tactile paper texture
```

Avoid:

```text
violent crime mood, adult glamour lighting, frightening realism
```

## Style Soup Warnings

Prompts become AI-looking when they contain:

- more than two base media
- multiple eras with no hierarchy
- "ultra detailed" plus a medium that needs simplification
- photoreal lens terms inside flat print or vector styles
- hand-drawn terms plus glossy 3D material language
- too many genre words: cyberpunk, fantasy, gothic, dreamy, luxury, cute, cinematic all at once

Fix by asking: "What is the image made of?" Then demote everything else into palette, motif, lighting, or composition.

## Detail Density Control

Set detail density by style:

- **Low detail**: vector, icon, sticker, pixel sprite, logo, enamel pin.
- **Selective detail**: anime still, gouache, risograph, children's book, editorial illustration.
- **Rich detail**: oil painting, botanical plate, concept art, product photo.
- **Structured detail**: technical diagram, patent drawing, map, architecture.

Add this when the model overdoes detail:

```text
Detail density: selective detail only at the focal point; simplify secondary surfaces; keep background shapes broad and readable.
```

## Light Model Control

Choose one light model:

- **Photo light**: real source, exposure, lens, shadow falloff.
- **Cel light**: flat colors and hard shadow shapes.
- **Paint light**: value masses and brush temperature.
- **Print light**: flat ink separations, no actual glow unless simulated with ink.
- **Vector light**: simple shadow tokens or none.
- **3D light**: material roughness, reflection, ambient occlusion.

Never combine all light models in one prompt.

## Texture Control

Texture should come from the medium, not an overlay.

Better:

```text
paper grain visible where watercolor wash thins near the edge
```

Weaker:

```text
add paper texture
```

Better:

```text
risograph ink grain appears inside the magenta layer, with slight registration offset at the blue edge
```

Weaker:

```text
vintage grainy texture
```

## Text Handling

When exact text matters, use a design tool after image generation unless the image model is known to handle typography well.

In prompts:

- Say "blank title-safe area" when text can be added later.
- Say "no invented text" for posters, packaging, labels, signage, UI, maps, and diagrams.
- Use "exact text only" when the user provides exact wording.

## Hybrid Prompt Template

```text
Create a [base medium] image, [aspect ratio].
Subject: [subject and action].
Structure: [layout/camera/line/composition].
Style modifier: [secondary style translated into palette, motif, or mood].
Light/color: [one light model].
Texture/finish: [medium-specific texture].
Detail density: [low/selective/rich/structured].
Text: [none/exact text/blank safe area].
Avoid: [style conflicts and AI-looking failure modes].
```

## Fast Examples

Weak:

```text
anime watercolor oil painting cyberpunk masterpiece, ultra detailed, cinematic, realistic lighting
```

Stronger:

```text
hand-drawn anime still with watercolor background treatment: clean cel character contours, flat local colors and hard-edged shadows, rainy city background painted with transparent magenta/cyan washes and visible paper grain, practical neon suggested through color bleeding, selective detail at the face and umbrella. Avoid glossy 3D hair, oil impasto, HDR bloom, fake signage, and photoreal lens blur.
```

Weak:

```text
luxury risograph product photo with 3D realistic reflections
```

Stronger:

```text
two-ink risograph product poster: simplified perfume bottle silhouette, warm off-white paper, black and muted gold ink layers, slight registration offset, grainy stencil texture, precise luxury spacing, blank logo-safe area. Avoid photoreal glass reflections, gradients, fake brand text, and glossy 3D lighting.
```
