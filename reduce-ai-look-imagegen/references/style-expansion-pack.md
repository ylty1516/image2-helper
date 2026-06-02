# Style Expansion Pack

Use this after `style-taxonomy.md` when the requested style needs finer classification.

## Historical Art And Design Movements

Use movement names carefully. Do not claim a perfect historical replica unless the user wants an educational reconstruction. Translate the movement into visual mechanics.

### Impressionist Painting

Use for fleeting light, outdoor atmosphere, and painterly everyday scenes.

Prompt cues:

```text
visible broken brushstrokes, light-first color, outdoor atmosphere, loose edges, ordinary subject, movement in the paint surface, no photographic sharpness
```

Avoid:

```text
smooth digital oil filter, black-heavy shadows, hyper-detailed outlines, static photo realism
```

### Post-Impressionist / Color Structure

Use for more deliberate color planes and expressive structure than Impressionism.

Prompt cues:

```text
visible brush structure, simplified forms, subjective color, patterned strokes, strong contour or planar organization where appropriate
```

Avoid:

```text
random color noise, generic painterly filter, photoreal lighting under thick brush texture
```

### Expressionist Painting

Use for emotional distortion and inner mood.

Prompt cues:

```text
distorted forms serving emotion, heightened color, anxious or forceful brushwork, compressed space, expressive contour, mood over accuracy
```

Avoid:

```text
pretty color chaos, random warped anatomy, glossy digital gradients, decorative distortion without emotional purpose
```

### Surrealist Image

Use for dream logic and symbolic juxtaposition.

Prompt cues:

```text
dreamlike spatial logic, precise unexpected juxtaposition, ordinary objects in impossible relation, calm uncanny lighting, symbolic transformation
```

Avoid:

```text
random weird objects, AI hallucination clutter, fake mystery fog, meaningless melting effects
```

### Cubist / Fragmented Planes

Use for fractured viewpoint and planar abstraction.

Prompt cues:

```text
multiple viewpoints, faceted planes, compressed space, geometric simplification, limited earth or muted palette, figure-ground ambiguity
```

Avoid:

```text
broken low-poly 3D, random shards, glossy facets, unreadable subject
```

### Futurist / Speed And Motion

Use for movement, machines, urban energy.

Prompt cues:

```text
repeated motion forms, diagonal force lines, mechanical rhythm, urban speed, dynamic overlap, aggressive forward movement
```

Avoid:

```text
generic sci-fi glow, random speed streaks, illegible clutter, motion blur replacing composition
```

### Art Nouveau

Use for ornamental, botanical, elegant graphic design.

Prompt cues:

```text
flowing organic line, botanical ornament, elongated forms, decorative border logic, flat color areas, integrated hand-lettering-safe space
```

Avoid:

```text
random vines, fake ornate text, over-rendered 3D metal, cluttered symmetry
```

### Art Deco

Use for luxury, speed, geometry, 1920s/1930s modernity.

Prompt cues:

```text
sleek geometric forms, stepped symmetry, sunburst or fan motifs, streamlined shapes, metallic accents, polished but flat graphic ornament
```

Avoid:

```text
generic gold everywhere, random triangles, fake small lettering, glossy casino look
```

### Bauhaus

Use for functional modernist design and geometric clarity.

Prompt cues:

```text
functional geometry, primary color accents, black-white structure, sans-serif clarity, simple shapes, form follows function, no excess ornament
```

Avoid:

```text
random red yellow blue decoration, fake museum poster text, trendy minimalism without structure
```

### De Stijl

Use for strict abstract grid design.

Prompt cues:

```text
orthogonal grid, rectangles only, primary colors with black white gray, asymmetrical balance, flat planes, strict spacing
```

Avoid:

```text
diagonal shapes, gradients, busy decoration, arbitrary color blocks
```

### Constructivist Poster

Use for propaganda-like graphic energy without actual propaganda claims.

Prompt cues:

```text
diagonal composition, photomontage feel, bold red-black-cream palette, industrial geometry, strong sans-serif blocks, urgency and material organization
```

Avoid:

```text
fake Cyrillic text, random political symbols, modern glossy gradients, unreadable typography
```

### Mid-Century Modern Illustration

Use for 1950s/60s editorial, advertising, and interiors.

Prompt cues:

```text
simplified figures, atomic shapes, warm muted palette, textured paper, geometric furniture silhouettes, playful asymmetry
```

Avoid:

```text
generic retro beige, fake distressed overlay, AI corporate illustration, too many nostalgic props
```

### Pop Art

Use for mass-media, advertising, comic, and consumer imagery.

Prompt cues:

```text
bold commercial color, sharp-edged graphic shapes, halftone or screenprint logic, repeated consumer imagery, witty mass-media framing
```

Avoid:

```text
copyrighted logos unless provided, fake brand text, muddy painterly shadows, random comic dots
```

### Memphis / Postmodern 80s

Use for playful design, pattern, and product/interior looks.

Prompt cues:

```text
bold geometric shapes, squiggles, zigzags, laminate-like flat color, playful asymmetry, clashing but controlled palette
```

Avoid:

```text
corporate vector blandness, random confetti, uncontrolled color chaos, 3D gloss unless product-specific
```

### Brutalist Graphic / Architecture-Inspired

Use for severe posters, architecture, UI moodboards, and editorial layouts.

Prompt cues:

```text
raw concrete texture, heavy type blocks, stark grid, exposed structure, monochrome or limited color, uncompromising scale
```

Avoid:

```text
generic gray minimalism, unreadable tiny text, fake concrete overlay, soft luxury lighting
```

## Commercial Entertainment Art

### Concept Art

Use for game/film worldbuilding and preproduction images.

Prompt cues:

```text
design problem visible, clear scale reference, functional silhouettes, callout-ready details, atmosphere supporting the idea, not final poster polish
```

Avoid:

```text
generic epic landscape, unreadable kitbash, random glowing runes, photobash seams
```

### Epic Fantasy Landscape / Concept Wallpaper Tells

Use when a fantasy landscape looks spectacular but AI-made: ice kingdoms, lava citadels, floating islands, endless waterfalls, ruined temples, aurora skies, impossible castles, glowing rivers, or panoramic world vistas.

Likely causes:

- too many spectacle motifs stacked at once: castle, ruins, mountains, aurora, moon, waterfalls, clouds, floating islands, lava, ocean, glowing crystals
- worldbuilding has no design problem or function; architecture is decorative silhouette instead of a usable place
- scale is inconsistent: tiny bridges, huge towers, repeated ruins, waterfalls, cliffs, and cities do not share a believable size system
- terrain geology is ornamental: mountains, ice, lava, cliffs, and waterfalls are arranged for drama rather than physical cause and erosion
- light sources conflict or overperform: moon, sunset, lava, aurora, god rays, glowing water, and rim lights all illuminate the scene
- detail density is equally high across foreground, midground, and far distance, creating a generated "epic wallpaper" feel
- repeated gothic towers, arches, bridges, spires, ruins, and floating rocks look kitbashed without cultural/material logic

Human-artist comparison:

- the world has one readable concept hook and a few supporting details, not every fantasy landmark at once
- architecture implies use: entrances, paths, supports, defenses, bridges, scale references, and material wear
- terrain follows a physical logic: gravity, erosion, water source and drainage, volcanic flow, ice formation, snow accumulation
- atmosphere simplifies distance; far elements lose detail and value contrast instead of staying equally sharp
- light has hierarchy: one dominant source plus controlled secondary glow where the material justifies it
- composition contains rest areas and large value shapes so the eye can travel through the world

Prompt patch:

```text
Reduce the generic epic-fantasy wallpaper feel. Build one clear worldbuilding hook and one terrain/light logic instead of stacking every spectacle motif. Give castles, ruins, bridges, roads, towers, and settlements usable construction, scale references, entrances, supports, material wear, and cultural consistency. Make terrain physically motivated: water has a source and drainage path, lava follows gravity and heat effects, ice/snow accumulates on plausible surfaces, floating land masses have an intentional rule if present. Use one dominant light source with limited material-based secondary glow; simplify far distance with atmosphere and broad value shapes. Avoid random spires, repeated ruins, impossible waterfalls, unreadable kitbash, glowing cracks everywhere, equal detail density, and castle/aurora/moon/lava/waterfall/floating-island spectacle all at once.
```

### Key Art / Poster Art

Use for promotional hero images.

Prompt cues:

```text
single clear hook, strong silhouette hierarchy, title-safe negative space, controlled spotlight, readable subject at thumbnail size
```

Avoid:

```text
floating head clutter, fake movie billing text, too many rim lights, no focal hierarchy
```

### Trading Card / TCG Art

Use for fantasy creatures, characters, items, and collectible scenes.

Prompt cues:

```text
central readable subject, dramatic but contained action, border-safe composition, material clarity, effect shapes that do not hide anatomy
```

Avoid:

```text
energy covering every limb, impossible armor, unreadable background, fake card text
```

### Board Game Box Art

Use for tabletop game covers.

Prompt cues:

```text
ensemble clarity, shelf-readable composition, clear theme props, inviting color, visible stakes, logo-safe top area
```

Avoid:

```text
random fantasy crowd, tiny faces everywhere, fake logo text, no visual hierarchy
```

### Children's Picture Book

Use for warm narrative illustration.

Prompt cues:

```text
clear character emotion, simple shape language, tactile medium, readable gesture, gentle exaggeration, page-turn moment
```

Avoid:

```text
over-detailed faces, creepy doll eyes, random whimsy props, adult fashion rendering
```

### Toy Packaging Illustration

Use for collectible figures, cute products, and playsets.

Prompt cues:

```text
bright shelf impact, clean character silhouette, product window-safe layout, playful icon shapes, consistent toy scale
```

Avoid:

```text
fake safety marks, unreadable legal text, glossy chaos, mismatched toy and background scale
```

### Sticker / Mascot

Use for emojis, sticker packs, small merch.

Prompt cues:

```text
bold silhouette, simple face readability, thick clean outline, limited internal detail, transparent or clean background, strong expression
```

Avoid:

```text
tiny texture details, complex lighting, thin hair strands, unreadable expression at small size
```

### Tattoo Flash

Use for tattoo concepts, not medical advice or final stencil guarantee.

Prompt cues:

```text
bold readable silhouette, clean linework, limited shading, skin-safe negative space, balanced black fills, stencil-friendly simplification
```

Avoid:

```text
micro-detail, muddy gradients, fake skin preview only, impossible line density
```

### Fashion Illustration

Use for garment-focused drawings.

Prompt cues:

```text
elongated fashion figure, fabric drape priority, quick confident line, selective wash or marker color, garment silhouette over facial detail
```

Avoid:

```text
realistic body anatomy as the main goal, over-rendered face, fabric with no construction logic
```

### Food Editorial Illustration

Use for menus, magazines, packaging, recipes.

Prompt cues:

```text
appetizing simplified forms, ingredient readability, imperfect edges, warm paper texture, controlled highlights, crumbs or garnish with purpose
```

Avoid:

```text
plastic gloss, impossible steam, random garnish, over-saturated sauce
```

## Craft And Material Looks

### Paper Cut / Layered Paper

Prompt cues:

```text
stacked paper layers, visible cut edges, soft cast shadows between layers, limited flat colors, handmade alignment
```

Avoid:

```text
3D plastic layers, impossible thin curls, random paper texture overlay, too many tiny cutouts
```

### Collage

Prompt cues:

```text
torn or cut paper edges, mixed printed fragments, glue-like overlaps, scale jumps with intention, paper grain, shadow from raised pieces
```

Avoid:

```text
seamless digital montage, random magazine scraps, fake text fragments, inconsistent lighting without purpose
```

### Photomontage

Prompt cues:

```text
assembled photographic fragments, theme-driven juxtaposition, deliberate scale mismatch, cutout edges, unified print finish
```

Avoid:

```text
accidental AI compositing errors, mismatched resolution, random objects without concept
```

### Scrapbook / Journal Page

Prompt cues:

```text
tape, stickers, handwritten-safe blank areas, layered paper, rounded photo corners, date-label space, imperfect alignment
```

Avoid:

```text
fake legible handwriting, cluttered page with no hierarchy, floating scraps
```

### Embroidery

Prompt cues:

```text
thread direction, satin stitches, chain stitch outlines, fabric weave, slight thread shadows, limited stitch colors
```

Avoid:

```text
painted gradients pretending to be thread, impossible tiny stitches, glossy plastic fibers
```

### Patch / Woven Label

Prompt cues:

```text
stitched border, woven thread grid, simplified color separations, merrowed edge, fabric puckering
```

Avoid:

```text
photoreal detail, unreadable tiny text, smooth vector with no thread structure
```

### Quilt / Textile Applique

Prompt cues:

```text
fabric pieces, stitched seams, batting softness, repeated blocks, slight puckering, patterned cotton texture
```

Avoid:

```text
flat poster shapes, impossible fabric scale, random pattern overload
```

### Stained Glass

Prompt cues:

```text
lead came outlines, colored glass pieces, uneven translucency, light passing through, solder joints, simplified shapes
```

Avoid:

```text
glossy 3D gem look, impossible tiny panes, fake cathedral text, no lead structure
```

### Mosaic

Prompt cues:

```text
individual tesserae, grout lines, irregular tile edges, local color built from small pieces, surface unevenness
```

Avoid:

```text
pixel art mistaken for mosaic, smooth gradients, tiles with no grout, too-perfect repetition
```

### Ceramic Glaze

Prompt cues:

```text
clay body thickness, glaze pooling, kiln speckles, hand-thrown asymmetry, foot ring, tiny surface pinholes
```

Avoid:

```text
plastic shine, impossible thin ceramic edges, uniform perfect glaze
```

### Neon Sign

Prompt cues:

```text
bent glass tubing, transformer wires, wall brackets, colored halo on nearby surface, tube gaps where letters break
```

Avoid:

```text
fake vector glow, continuous impossible text, unreadable signage, glow without support structure
```

### Enamel Pin

Prompt cues:

```text
metal outlines, enamel-filled cells, slight raised ridges, glossy but bounded color wells, small pin-scale simplification
```

Avoid:

```text
painted gradients, tiny complex text, no metal separation lines
```

## Scientific And Technical Illustration

### Botanical Plate

Prompt cues:

```text
accurate plant morphology, whole specimen plus detail studies, consistent light direction, scale marks or blank label space, watercolor or ink clarity
```

Avoid:

```text
decorative flower fantasy, wrong leaf arrangement, fake Latin text, random insects unless requested
```

### Zoological / Natural History Plate

Prompt cues:

```text
species-specific anatomy, profile or diagnostic pose, neutral background, fine ink or watercolor detail, scale consistency
```

Avoid:

```text
fantasy hybrid unless requested, glamour lighting, wrong limb count, fake labels
```

### Medical / Anatomical Illustration

Prompt cues:

```text
clear anatomical hierarchy, simplified but accurate forms, clean labels or label-free callout space, neutral lighting, educational composition
```

Avoid:

```text
gore for drama, fake labels, impossible anatomy, decorative lighting
```

### Patent Drawing

Prompt cues:

```text
black line technical drawing, numbered callout-safe parts, orthographic or exploded views, no shading except simple hatching, clean white background
```

Avoid:

```text
fake patent text, perspective glamour render, decorative shadows
```

### Blueprint / Architectural Plan

Prompt cues:

```text
orthographic plan or elevation, consistent line weights, grid, dimension-safe spaces, cyan/blueprint or black-on-white drafting finish
```

Avoid:

```text
impossible floor plan, fake tiny labels, mixed perspective
```

### Exploded Diagram

Prompt cues:

```text
parts separated along clear axes, aligned spacing, consistent perspective, visible assembly order, callout-safe negative space
```

Avoid:

```text
floating random parts, mismatched scale, fake labels, decorative explosion
```

### Map / Cartographic Illustration

Prompt cues:

```text
consistent projection or stylized map logic, legible icon hierarchy, terrain texture, route clarity, compass or scale only if meaningful
```

Avoid:

```text
fake place names, impossible geography, over-decorated borders, unreadable tiny text
```

## Retro Internet And Screen Aesthetics

### Vaporwave

Prompt cues:

```text
pastel magenta-cyan palette, classical statue or retro computer motifs, grid horizon, sunset disk, intentionally synthetic nostalgia
```

Avoid:

```text
random Japanese text, purple-blue soup, glossy generic cyberpunk, too many memes
```

### Synthwave

Prompt cues:

```text
dark horizon grid, neon magenta and cyan, 1980s sports car or skyline silhouette, sunset stripes, chrome type-safe space
```

Avoid:

```text
neon everywhere, no focal silhouette, fake unreadable typography
```

### Y2K Gloss

Prompt cues:

```text
chrome bubbles, translucent plastic, candy colors, early digital shine, rounded UI forms, starbursts used sparingly
```

Avoid:

```text
modern app gradient polish, unreadable chrome text, everything reflective
```

### Frutiger Aero

Prompt cues:

```text
clear water, glassy UI surfaces, green-blue optimism, soft sky gradients, translucent bubbles, early-2000s tech cleanliness
```

Avoid:

```text
generic stock eco imagery, too much blur, modern flat design, fake interface text
```

### 90s Web / Zine Digital

Prompt cues:

```text
low-resolution web graphics, tiled background, visible buttons, chunky pixel icons, scanned collage bits, intentional amateur layout
```

Avoid:

```text
unreadable fake text walls, random clip art, modern responsive polish
```

### VHS / CRT Screen

Prompt cues:

```text
scanlines, phosphor glow, tracking noise, slight chroma bleed, rounded screen corners, interlaced softness
```

Avoid:

```text
heavy glitch hiding the subject, random RGB split, modern sharp UI
```

## Tradition-Inspired Style Care

Use these only when relevant and avoid treating cultures as decoration.

Rules:

- Prefer "inspired by [medium/process]" over "authentic [culture]."
- Avoid fake writing, sacred symbols, ceremonial objects, or religious imagery unless the user specifically provides context.
- Use material and craft language: paper, ink, textile, ceramic, carving, dye, print process.
- If exact cultural accuracy matters, ask for references or region/period before generating.

### Chinese Ink Wash Inspired

Prompt cues:

```text
brush-and-ink landscape logic, varied ink density, rice paper absorbency, empty space, mist suggested by unpainted paper, calligraphy-safe blank area only if text is provided
```

Avoid:

```text
fake Chinese characters, random dragons, over-detailed digital mountains, gray fog filter
```

### Gongbi-Inspired Fine Line Painting

Prompt cues:

```text
fine controlled linework, mineral-like color washes, delicate patterning, precise flora/fauna detail, silk or paper texture
```

Avoid:

```text
generic fantasy Asian ornament, fake seals, glossy anime rendering
```

### Islamic Geometric-Inspired Pattern

Prompt cues:

```text
compass-and-straightedge geometry, repeating star polygons, interlaced symmetry, tile or manuscript border material, limited mineral palette
```

Avoid:

```text
fake Arabic script, random sacred motifs, broken symmetry, AI filler ornament
```

### Medieval Manuscript / Illuminated Page

Prompt cues:

```text
vellum texture, decorated initials, marginalia, flat gold-leaf areas, rubrication, hand-ruled layout, limited medieval palette
```

Avoid:

```text
fake Latin text, modern fantasy realism, random monsters without page logic
```

### Folk Poster / Festival Print

Prompt cues:

```text
regional craft-inspired motifs, flat folk color, handmade print texture, symmetrical or border-based composition, simplified figures
```

Avoid:

```text
generic ethnic pattern mix, sacred symbols without context, fake language text
```

## Micro-Classifier

When the user gives a style phrase, map it quickly:

- "dreamy painterly" -> watercolor, gouache, impressionist, or soft digital painting. Ask or choose based on subject.
- "retro poster" -> screenprint, lithograph travel poster, art deco, mid-century, or constructivist.
- "premium product" -> editorial photo, catalog photo, minimal luxury, or soft 3D render.
- "cute character" -> sticker/mascot, children's book, toy package, chibi anime, or clay.
- "dark cool" -> noir photo, dark fantasy, gothic poster, cinematic still, or expressionist.
- "technical clean" -> patent drawing, exploded diagram, isometric technical, blueprint, or flat vector.

Always convert the chosen map into process cues and avoid terms.
