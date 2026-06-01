# Style Selection And Use Cases

Use this when the user has a goal but not a precise style.

## Fast Style Interview

Ask at most three questions. Prefer choices that reveal tradeoffs.

1. What is the image for: avatar, poster, wallpaper, product, character design, game asset, social post, thumbnail, sticker, book/album cover, or reference board?
2. Should it feel more: realistic, hand-drawn, graphic, painterly, cute, premium, raw, cinematic, cozy, retro, or experimental?
3. What should it absolutely avoid: AI gloss, childishness, cheap stock look, over-sexualization, clutter, fake text, wrong anatomy, too much detail, or generic anime face?

If the user is impatient, infer from context and proceed.

## Taste Word Translator

Translate vague words into operational style choices.

### "Premium"

Usually means restraint, material credibility, spacing, and fewer effects.

Use:

```text
controlled negative space, precise material behavior, restrained palette, few objects, grounded shadows, quiet finish
```

Avoid:

```text
gold accents by default, glossy everything, fake luxury logo, empty white void
```

### "Cute"

Usually means simplified proportion, clear expression, safe silhouette, and warmth.

Use:

```text
rounded shape language, readable expression, soft palette, simplified detail, tactile surface, small gesture
```

Avoid:

```text
creepy doll eyes, over-detailed skin, adult glamour pose, random bows and hearts
```

### "Realistic"

Usually means credible light, material, scale, anatomy, and camera behavior.

Use:

```text
motivated light source, natural contact shadows, plausible scale, real material texture, lens/exposure limits
```

Avoid:

```text
HDR clarity, perfect skin, impossible reflections, floating props
```

### "Cinematic"

Usually means narrative framing, light motivation, and visual hierarchy.

Use:

```text
story moment, motivated practical light, foreground/midground/background layering, restrained palette, set dressing with purpose
```

Avoid:

```text
orange-teal by default, fake anamorphic flare, empty dramatic pose, fog hiding weak composition
```

### "Clean"

Usually means hierarchy and controlled detail, not sterile blankness.

Use:

```text
clear focal hierarchy, simplified secondary surfaces, consistent spacing, limited palette, crisp edges where needed
```

Avoid:

```text
empty scene, plastic surfaces, no texture, generic corporate vector people
```

### "Moody"

Usually means value structure and emotional temperature.

Use:

```text
low-key value grouping, selective highlights, cool/warm tension, negative space, quiet expression
```

Avoid:

```text
black mush, random fog, neon everywhere, unreadable subject
```

### "High Detail"

Usually means meaningful detail, not detail everywhere.

Use:

```text
rich detail at the focal point, simplified secondary areas, material-specific texture, readable silhouette
```

Avoid:

```text
micro-detail noise, overdesigned costume, unreadable background, AI filigree
```

### "Anime But Not AI"

Usually means animation production logic.

Use:

```text
layout-driven pose, clean contour, flat cel color, deliberate shadow shapes, painted background, restrained effects
```

Avoid:

```text
glossy 3D hair, airbrushed skin, random rim lights, hyper-detailed eyes
```

## Use-Case Recipes

### Avatar / Profile Image

Best families:

- editorial portrait
- sticker/mascot
- cel anime portrait
- clay/stop-motion character
- flat vector icon

Prompt priorities:

```text
readable face at small size, clean silhouette, controlled background, strong expression, simple color identity
```

Avoid:

```text
tiny accessories, busy background, unreadable eyes, fake text, over-detailed hair
```

### Phone Wallpaper

Best families:

- cinematic still
- anime background
- watercolor/gouache scene
- solarpunk/cozy landscape
- abstract print

Prompt priorities:

```text
vertical composition, top/bottom safe areas, strong atmosphere, no important detail under app icons, clean value grouping
```

Avoid:

```text
central tiny subject, text, cluttered top area, extreme contrast behind icons
```

### Desktop Wallpaper

Best families:

- cinematic landscape
- painted background
- analog film scene
- technical/isometric scene
- fantasy concept environment

Prompt priorities:

```text
wide composition, left/right breathing room, layered depth, one clear focal zone, detail visible at large scale
```

Avoid:

```text
poster text, overbusy full-frame detail, fake lens dirt, no quiet space
```

### Poster

Best families:

- screenprint
- risograph
- vintage travel poster
- art deco
- constructivist
- key art

Prompt priorities:

```text
single visual hook, clear hierarchy, title-safe area, limited palette, strong silhouette
```

Avoid:

```text
fake small text, too many focal points, illegible typography, random texture
```

### Album Cover

Best families:

- analog photo
- surrealist image
- collage
- minimal luxury
- vaporwave/synthwave
- expressionist painting

Prompt priorities:

```text
square composition, strong mood, central metaphor, text-safe negative space, recognizable thumbnail
```

Avoid:

```text
literal generic music symbols, fake artist name text, clutter, low-contrast thumbnail
```

### Book Cover

Best families:

- literary photo
- gouache illustration
- collage
- art nouveau/deco
- dark fantasy
- children's picture book

Prompt priorities:

```text
title-safe top area, strong central symbol, genre-readable mood, controlled negative space, print-friendly palette
```

Avoid:

```text
fake title text, too many characters, tiny plot details, AI fantasy clutter
```

### Social Ad / Product Promo

Best families:

- product/catalog photo
- minimal luxury
- flat vector
- editorial geometric
- screenprint poster

Prompt priorities:

```text
product clarity, benefit visual, blank copy area, realistic material, clean hierarchy, platform-safe crop
```

Avoid:

```text
fake logos, fake small claims, floating product, impossible reflections, cluttered copy area
```

### Thumbnail

Best families:

- bold editorial
- pop comic
- cel anime expression
- product hero
- graphic poster

Prompt priorities:

```text
one readable emotion or object, large shapes, high value contrast, simple background, no tiny text
```

Avoid:

```text
busy details, subtle mood only, small face, fake labels, low contrast
```

### Sticker / Emoji Pack

Best families:

- sticker/mascot
- chibi cel anime
- enamel pin
- clay mini figure
- flat vector

Prompt priorities:

```text
transparent or clean background, thick outline, exaggerated readable expression, limited detail, strong silhouette
```

Avoid:

```text
thin hair strands, complex lighting, tiny props, realism that disappears at small size
```

### Character Design Sheet

Best families:

- cel anime design
- game concept art
- fashion illustration
- toy design
- graphite/colored pencil concept

Prompt priorities:

```text
front/side/back or clear pose set, consistent proportions, material notes, readable silhouette, simple neutral background
```

Avoid:

```text
changing costume between views, dynamic pose hiding design, fake labels, over-rendered background
```

### Live2D / Sprite Reference

Best families:

- cel anime
- clean game character
- flat shaded mascot

Prompt priorities:

```text
front-facing neutral pose, separated readable hair and clothing shapes, symmetrical enough for rigging, clean edges, no extreme perspective
```

Avoid:

```text
crossed limbs, heavy occlusion, messy hair masses, complex transparent fabrics, motion blur
```

### Game Sprite

Best families:

- pixel art
- clean cel asset
- low-poly concept
- sticker/mascot

Prompt priorities:

```text
readable silhouette at target size, limited palette, clear action state, consistent viewing angle, no unnecessary micro-detail
```

Avoid:

```text
painted texture at sprite scale, complex anatomy hidden by effects, inconsistent pixel grid
```

### Game Environment Concept

Best families:

- concept art
- gouache painted background
- isometric technical
- low-poly
- cinematic landscape

Prompt priorities:

```text
navigation-readable space, scale reference, functional landmarks, material zones, mood supporting gameplay
```

Avoid:

```text
generic epic scene, no playable layout, random glowing props, unreadable architecture
```

### Product Mockup

Best families:

- product/catalog photo
- soft 3D render
- minimal luxury
- screenprint packaging

Prompt priorities:

```text
true material thickness, scale cue, grounded shadow, label-safe blank area, realistic reflection, packaging print limits
```

Avoid:

```text
fake readable claims, impossible glass, floating packaging, no crease/fold logic
```

### Packaging Illustration

Best families:

- screenprint
- flat vector
- food editorial illustration
- toy packaging
- vintage lithograph

Prompt priorities:

```text
shelf impact, print-safe palette, barcode/nutrition-safe blank zones if needed, clear product flavor or theme, limited text placeholders
```

Avoid:

```text
fake legal text, fake brand, too many ingredients, unreadable typography
```

### UI / App Illustration

Best families:

- flat vector
- editorial geometric
- isometric technical
- gouache UI illustration

Prompt priorities:

```text
clear hierarchy, consistent component style, no invented UI text, accessible contrast, simple metaphor
```

Avoid:

```text
fake app screenshot, unreadable microcopy, gradient blobs, inconsistent icon style
```

## Style Decision Tree

If the user wants:

- more emotional truth -> documentary photo, analog film, expressionist, children's book, gouache
- more commercial polish -> editorial photo, product photo, minimal luxury, art deco, vector
- more hand-made warmth -> gouache, watercolor, paper cut, embroidery, clay, risograph
- more graphic impact -> screenprint, pop comic, constructivist, flat vector, poster
- more worldbuilding -> concept art, cinematic still, painted anime background, map, isometric
- more small-size readability -> sticker, mascot, icon, pixel art, enamel pin
- more technical credibility -> patent drawing, exploded diagram, blueprint, botanical/medical plate

Then apply `style-taxonomy.md` or `style-expansion-pack.md` for the exact style family.

## Anti-AI Use-Case Check

Before finalizing a prompt, check:

- Is the focal point readable at the final size?
- Did the prompt reserve space for text if text will be added later?
- Does the chosen style match the use case?
- Are style constraints specific to the medium?
- Is there one light model and one material logic?
- Are anatomy, pose, and object contact plausible?
