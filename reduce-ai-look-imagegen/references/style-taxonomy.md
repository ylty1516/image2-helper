# Visual Style Taxonomy

Use this reference to choose and describe a style with less AI feel. Prefer medium/process language over generic quality words.

## Selection Rule

Pick at most two style families:

1. **Base medium**: photo, cel anime, watercolor, gouache, oil paint, ink, print, vector, pixel, 3D render.
2. **Mood or genre modifier**: cozy, noir, luxury, cyberpunk, solarpunk, retro, editorial, documentary.

Do not stack many style labels. Translate labels into production evidence: line, color, shadow, surface, composition, printing, lens, or material behavior.

## Photography Families

### Documentary / Street Photo

Use for natural, unposed, human, everyday scenes.

Prompt cues:

```text
available light, imperfect framing, real gesture, layered background, contact shadows, slight motion softness, ordinary clothing texture, natural color response
```

Avoid:

```text
perfect model pose, studio glow, fake cinematic haze, beauty-retouch skin, symmetrical scene cleanup
```

### Editorial / Fashion Photo

Use for polished but believable portraits, fashion, and magazine-like images.

Prompt cues:

```text
controlled styling, intentional negative space, wardrobe fabric tension, visible makeup texture, purposeful pose, real studio modifier shadows, restrained retouching
```

Avoid:

```text
plastic skin, impossible fabric, over-sharp eyes, glossy AI face, unmotivated rim light
```

### Cinematic Still

Use for narrative moments rather than just "cool lighting."

Prompt cues:

```text
story moment, motivated practical light, frame-within-frame composition, restrained palette, foreground obstruction, lens falloff, believable set dressing
```

Avoid:

```text
orange teal by default, excessive bloom, fake anamorphic flare, empty dramatic pose
```

### Analog Film / Snapshot

Use for nostalgic, casual, or imperfect human images.

Prompt cues:

```text
film-like highlight rolloff, muted color crossover, visible grain, small focus miss, flash falloff, slight dust or scan marks, print-like contrast
```

Avoid:

```text
uniform digital noise, fake heavy scratches, HDR clarity, sterile perfect whites
```

### Product / Catalog Photo

Use for sellable objects, packaging, devices, cosmetics, food packaging.

Prompt cues:

```text
true material transitions, scale cue, grounded contact shadow, realistic reflection shape, packaging print limits, minor manufacturing marks
```

Avoid:

```text
floating object, fake brand marks, impossible reflections, glass with no thickness, too-clean showroom void
```

## Anime And Comics Families

### Hand-Drawn Cel Anime

Use `anime-handdrawn-look.md` for detailed instructions.

Short cues:

```text
layout-driven staging, clean animation contours, flat local colors, hard-edged cel shadows, simple highlights, painted background layer
```

Avoid:

```text
glossy 3D hair, airbrushed skin, random rim lights, overloaded micro-detail
```

### Manga Ink / Screentone

Use for black-and-white manga panels, character art, action, and printed pages.

Prompt cues:

```text
clean ink contours, confident black fills, screentone shading, speed lines only where action needs them, panel-aware composition, readable silhouette
```

Avoid:

```text
gray mush, random hatching, unreadable hands, fake text, excessive gradient tones
```

### Webtoon / Manhwa

Use for vertical-scroll romance, action, fantasy, or glossy comic panels.

Prompt cues:

```text
vertical composition, clean character rendering, simplified background panels, selective gradients, readable facial acting, clear speech-safe negative space
```

Avoid:

```text
over-rendered hair shine, same-face syndrome, cluttered panel, fake speech text, anatomy hidden by effects
```

### Retro 80s/90s Anime

Use for older animation feel without naming a studio.

Prompt cues:

```text
painted cel look, thicker contour lines, limited palette, analog compositing softness, subtle film dust, bolder shadow shapes, simpler background detail
```

Avoid:

```text
modern glossy gradients, 3D camera depth blur, ultra-clean vector linework, neon effects everywhere
```

### Pop Comic / Halftone

Use for bold posterized comic imagery.

Prompt cues:

```text
bold ink outlines, flat color separations, halftone dots, strong graphic shapes, limited palette, print registration feel
```

Avoid:

```text
fake random dots, painterly gradients, over-detailed faces, muddy print texture
```

## Painting And Drawing Families

### Watercolor

Use for soft, transparent, atmospheric illustrations.

Prompt cues:

```text
transparent washes, paper grain, pigment blooms, reserved white highlights, soft edge variation, layered light color
```

Avoid:

```text
opaque plastic gradients, perfect digital blur, over-black outlines unless mixed-media
```

### Gouache / Poster Color

Use for hand-painted illustration, anime backgrounds, editorial art, cozy scenes.

Prompt cues:

```text
opaque matte color, visible brush masses, simplified shapes, layered flat planes, softened dry-brush edges, poster-like color harmony
```

Avoid:

```text
wet oil shine, photoreal rendering, infinite micro-detail, glossy lighting
```

### Oil Paint

Use for painterly portraits, classical scenes, textured still life.

Prompt cues:

```text
layered brushwork, impasto only where needed, glazing, lost-and-found edges, canvas texture, warm/cool paint temperature shifts
```

Avoid:

```text
uniform AI brush filter, over-smoothed skin, random palette knife marks, photographic sharpness everywhere
```

### Acrylic / Poster Illustration

Use for bold contemporary painting and graphic editorial looks.

Prompt cues:

```text
opaque blocks, crisp masked edges mixed with brush texture, saturated but controlled palette, graphic silhouettes
```

Avoid:

```text
generic digital airbrush, muddy shadows, unrelated decorative strokes
```

### Ink Wash / Sumi-Inspired

Use for restrained brush art, landscape, animals, poetic scenes.

Prompt cues:

```text
economical brush strokes, ink density variation, absorbent paper texture, empty space, controlled bleed, simplified silhouette
```

Avoid:

```text
over-detailed linework, gray digital fog, decorative symbols without purpose
```

### Graphite / Colored Pencil

Use for sketchbook studies, character concepts, intimate drawings.

Prompt cues:

```text
visible pencil pressure, layered hatching, paper tooth, construction marks when appropriate, softened smudged transitions
```

Avoid:

```text
perfect vector edges, fake pencil texture overlay, fully rendered 3D shading
```

### Charcoal / Pastel

Use for expressive portraits, gesture, moody studies.

Prompt cues:

```text
powdery texture, broad value masses, smudged edges, eraser lifts, paper tooth, expressive gesture
```

Avoid:

```text
tiny perfect details everywhere, glossy highlights, clean digital gradients
```

## Printmaking And Poster Families

### Ukiyo-e / Japanese Woodblock-Inspired

Use for flat print design, landscapes, folklore, stylized figures. Avoid direct artist imitation.

Prompt cues:

```text
woodblock print structure, crisp contour, flat color planes, visible paper fiber, slight registration variation, patterned fabric shapes, decorative composition
```

Avoid:

```text
fake kanji, photoreal depth, glossy anime lighting, random Japanese motifs
```

### Linocut / Woodcut

Use for bold handmade print looks.

Prompt cues:

```text
relief print, carved negative spaces, bold black shapes, rough cut marks, limited ink palette, paper impression, imperfect edges
```

Avoid:

```text
smooth vector imitation, tiny impossible carving detail, gradients, fake distressed overlay only
```

### Screenprint

Use for posters, merch graphics, bold editorial images.

Prompt cues:

```text
separate ink layers, flat spot colors, slight registration offset, stencil-like edges, limited palette, paper ink texture
```

Avoid:

```text
unlimited gradients, glossy digital lighting, random grunge texture
```

### Risograph / Zine

Use for indie posters, zines, playful editorial graphics.

Prompt cues:

```text
limited fluorescent inks, grainy stencil texture, overprinted color, slight misregistration, paper warmth, simple graphic shapes
```

Avoid:

```text
perfect CMYK print, smooth gradients, photoreal lighting, too many colors
```

### Vintage Lithograph / Travel Poster

Use for location posters, retro ads, tourism, food or product nostalgia.

Prompt cues:

```text
large simplified color planes, stylized perspective, hand-lettering-safe layout, soft print wear, limited palette, clear foreground/midground/background
```

Avoid:

```text
fake small text, AI typography, photo-real detail, generic beige nostalgia
```

## Digital Illustration And Design Families

### Flat Vector

Use for UI, explainer, brand, app, editorial diagrams.

Prompt cues:

```text
simple geometric shapes, clean paths, limited palette, consistent corner radius, no texture unless specified, clear hierarchy
```

Avoid:

```text
random gradients, inconsistent icon style, fake 3D shadows, over-decorated backgrounds
```

### Editorial Geometric

Use for conceptual magazine or article illustration.

Prompt cues:

```text
visual metaphor, simplified bodies, bold shape language, restrained texture, intentional negative space, limited colors
```

Avoid:

```text
generic corporate people, meaningless floating shapes, gradient blobs, clutter
```

### Isometric Technical

Use for software, architecture, systems, maps, diagrams.

Prompt cues:

```text
consistent isometric angle, aligned grid, clear object hierarchy, simplified labels or no text, uniform stroke, controlled shadows
```

Avoid:

```text
mixed perspectives, fake tiny text, impossible architecture, decorative complexity
```

### Pixel Art

Use for games, icons, retro scenes, sprites.

Prompt cues:

```text
fixed pixel grid, limited palette, deliberate clusters, no anti-aliased blur, readable silhouette, sprite-scale constraints
```

Avoid:

```text
AI pseudo-pixels, smooth gradients, random noise, inconsistent pixel size
```

### Low-Poly / Stylized 3D

Use for game props, environments, toy-like 3D.

Prompt cues:

```text
visible polygon planes, simplified geometry, consistent material roughness, ambient occlusion, clear silhouettes, game-asset lighting
```

Avoid:

```text
accidental melted geometry, photoreal textures on low-poly forms, glossy everything
```

### Clay / Stop-Motion Look

Use for tactile character scenes, product shorts, cozy animation.

Prompt cues:

```text
hand-shaped clay surfaces, fingerprints, tiny dents, practical miniature lighting, felt/fabric props, shallow set depth
```

Avoid:

```text
perfect plastic 3D, impossible smoothness, CGI gloss, fake handmade texture overlay
```

## Genre Modifiers

Use these as modifiers, not complete styles.

### Cyberpunk / Neon Noir

Prompt cues:

```text
wet reflective surfaces, mixed signage light, dense urban layering, practical neon sources, shadowed faces, controlled color contrast
```

Avoid:

```text
neon everywhere, unreadable signage, random holograms, purple-blue gradient soup
```

### Solarpunk

Prompt cues:

```text
human-scale green infrastructure, warm daylight, repairable materials, plants integrated with architecture, optimistic but functional design
```

Avoid:

```text
generic fantasy garden city, impossible engineering, all-green palette
```

### Cozy Slice Of Life

Prompt cues:

```text
small domestic details, warm practical light, imperfect object placement, quiet gesture, soft but not blurry texture
```

Avoid:

```text
sterile cafe set, fake steam, over-saturated warmth, clutter without hierarchy
```

### Minimal Luxury

Prompt cues:

```text
material restraint, precise spacing, tactile surfaces, controlled reflections, few objects, expensive but quiet finish
```

Avoid:

```text
empty white void, generic gold accents, glossy stock render, unreadable logo text
```

### Dark Fantasy / Gothic

Prompt cues:

```text
aged stone, candle or moonlight logic, layered costume weight, worn metal, fog with depth, ritual composition
```

Avoid:

```text
spikes everywhere, random symbols, black mush, over-rendered armor shine
```

## Rewrite Pattern

Weak:

```text
beautiful stylish illustration, high quality, detailed, cinematic
```

Strong:

```text
[base medium] with [process-specific marks], [limited palette or material behavior], [composition logic], [texture/finish], [one genre modifier if needed]. Avoid [top 3 AI-looking failure modes for that family].
```

Example:

```text
risograph-style editorial poster with two fluorescent ink layers, grainy stencil texture, slight registration offset, simple graphic silhouettes, warm off-white paper, restrained negative space. Avoid smooth gradients, fake tiny text, glossy 3D lighting, and random distressed overlays.
```

## Expansion Reference

Use `style-expansion-pack.md` for more granular categories:

- historical art and design movements
- commercial entertainment art
- craft and material looks
- scientific and technical illustration
- retro internet and screen aesthetics
- culturally specific or tradition-inspired styles that require extra care

Use `style-blending-rules.md` when the user combines several styles, moods, eras, or media and the prompt needs a consistent hierarchy.

Use `style-selection-and-use-cases.md` when the style should be chosen from the user's goal, platform, output format, audience, or taste words.

Use `style-quality-rubric.md` after drafting or generating to score whether the style is coherent and low-AI.

Use `style-prompt-cookbook.md` for copy-ready prompt skeletons.

Use `failure-feedback-fixes.md` to translate user critique into the next prompt revision.

Use `intent-and-fuzzy-language.md` before style selection when the user's words may describe format, purpose, mood, audience, or quality rather than a literal style.
