# Style Quality Rubric

Use this to judge whether a prompt or generated image has reduced AI feel.

Score each axis 1-5:

- **1**: weak or visibly wrong
- **3**: acceptable but generic
- **5**: strong, specific, and style-consistent

## Universal Rubric

### Medium Truth

Does the image look like it was made with the chosen medium?

5 means the medium has real process evidence: paper grain, ink layer, brush behavior, lens limits, pixel grid, material roughness, cel shadow logic, etc.

Common failures:

- watercolor with glossy HDR
- pixel art with blurred gradients
- cel anime with 3D hair rendering
- vector art with random painterly texture

### Style Hierarchy

Is there one dominant style with clear modifiers?

5 means the base medium is obvious and secondary styles only affect palette, motif, mood, or composition.

Common failures:

- many style names blended into one generic look
- no clear base medium
- contradictory lighting models

### Physical / Production Plausibility

Do anatomy, objects, contact, gravity, material, and production constraints make sense?

5 means body mechanics, object contact, shadows, material thickness, and tool/process limits are believable.

Common failures:

- floating feet or props
- broken hands
- fabric ignoring pose
- impossible reflections
- print style with infinite colors

### Detail Control

Is detail placed where it matters?

5 means detail density supports the composition without reducing construction quality in secondary areas. The focal point can be sharper or more detailed, but visible background and non-focus elements still remain believable.

Common failures:

- micro-detail everywhere
- cluttered background
- overdesigned costume
- detail hiding anatomy or silhouette

### Background / Non-Focus Quality

Do secondary figures, props, architecture, environmental objects, and other non-focus areas remain plausible?

5 means the background receives the same quality scrutiny as the focal subject: background people have natural posture and scene-appropriate action, objects keep recognizable function and material logic, architecture follows perspective, signage/text does not become fake symbols, and realistic scenes contain rich lived-in environmental detail.

Common failures:

- main subject is polished but background people have malformed limbs
- chairs, cups, vehicles, buildings, or stairs melt into impossible shapes
- background perspective contradicts the floor plane or horizon
- fake text/logos appear in signs or posters
- secondary characters perform bizarre actions unrelated to the scene

### Light / Value Logic

Does lighting or value match the style?

5 means the light model is consistent: photographic, cel, paint, print, vector, or 3D.

Common failures:

- fake rim lights
- HDR glow in flat print
- airbrushed gradients in cel color
- black mush in moody scenes

### Composition / Use Fit

Does the composition match the intended use?

5 means avatar, poster, wallpaper, thumbnail, product shot, sprite, etc. remain readable at final size.

Common failures:

- no safe space for text
- tiny focal subject
- unreadable thumbnail
- wallpaper clutter under app icons
- product not visible enough

### Anti-AI Specificity

Are the anti-AI constraints specific rather than generic?

5 means the prompt blocks the exact failure modes of the selected style.

Common failures:

- "no AI look" only
- "high quality, masterpiece"
- negative prompt full of unrelated terms

## Score Interpretation

- **35-40**: strong. Generate or keep.
- **27-34**: usable. Fix the lowest two axes.
- **19-26**: generic or unstable. Rewrite with a clearer base medium.
- **8-18**: likely AI soup. Reclassify style from scratch.

## Medium-Specific Checks

### Photography

Check:

- real light source
- plausible lens/exposure behavior
- skin/material texture
- contact shadows
- believable background

Red flags:

- perfect skin
- unreal reflections
- fake cinematic glow
- floating props

### Hand-Drawn Anime

Check:

- clean line logic
- flat local colors
- deliberate shadow shapes
- readable key pose
- character/background layer relationship

Red flags:

- glossy 3D hair
- airbrushed gradients
- random rim lights
- anatomy hidden by effects

### Manga / Ink

Check:

- confident contour
- black fill design
- screentone or hatch discipline
- readable panels/silhouette

Red flags:

- gray mush
- random hatching
- fake text
- unreadable hands

### Watercolor

Check:

- transparent washes
- pigment behavior
- paper grain
- reserved highlights
- soft/hard edge variation

Red flags:

- plastic gradients
- no paper behavior
- over-black shadows
- digitally perfect blur

### Gouache / Poster Color

Check:

- opaque matte color
- visible brush masses
- simplified shapes
- layered flat planes

Red flags:

- wet oil shine
- too much micro-detail
- photoreal rendering

### Oil Paint

Check:

- brush direction
- lost-and-found edges
- value structure
- canvas or paint behavior

Red flags:

- uniform AI brush filter
- photographic sharpness everywhere
- random impasto

### Printmaking

Check:

- limited ink logic
- registration behavior
- paper texture
- flat separations

Red flags:

- unlimited colors
- smooth gradients
- fake distress
- unreadable tiny text

### Vector / UI Illustration

Check:

- clean paths
- consistent geometry
- limited palette
- clear hierarchy

Red flags:

- random gradient blobs
- inconsistent icons
- fake UI text
- unnecessary texture

### Pixel Art

Check:

- consistent pixel grid
- limited palette
- readable clusters
- no blur

Red flags:

- pseudo-pixel noise
- anti-aliased gradients
- inconsistent pixel sizes

### 3D Render

Check:

- material roughness
- believable geometry
- grounded shadows
- scale cues

Red flags:

- melted geometry
- glossy everything
- texture with no UV logic
- floating objects

### Technical Illustration

Check:

- consistent perspective or projection
- line weight hierarchy
- callout-safe spacing
- part accuracy

Red flags:

- fake labels
- mixed perspective
- impossible assembly
- decorative shadows

## Before/After Report Template

```yaml
style_validation:
  target_style: "<style family>"
  intended_use: "<use case>"
  before_score:
    medium_truth: 0
    style_hierarchy: 0
    production_plausibility: 0
    detail_control: 0
    background_non_focus_quality: 0
    light_value_logic: 0
    composition_use_fit: 0
    anti_ai_specificity: 0
    total: 0
  after_score:
    medium_truth: 0
    style_hierarchy: 0
    production_plausibility: 0
    detail_control: 0
    background_non_focus_quality: 0
    light_value_logic: 0
    composition_use_fit: 0
    anti_ai_specificity: 0
    total: 0
  top_remaining_failures:
    - "<failure>"
  next_prompt_fix:
    - "<specific fix>"
```

## Rewrite Rule

When a score is low, rewrite only the failing axes.

Examples:

- Low medium truth -> add process evidence.
- Low style hierarchy -> remove secondary styles.
- Low plausibility -> add anatomy/contact/material constraints.
- Low detail control -> specify focal-only detail.
- Low light logic -> choose one light model.
- Low use fit -> add aspect ratio and safe-space constraints.
