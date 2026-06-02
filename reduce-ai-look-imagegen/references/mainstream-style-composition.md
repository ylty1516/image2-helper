# Mainstream Style And Composition

Use this when the user asks for mainstream styles, better composition, stronger framing, cover/poster/wallpaper/game UI layout, visual hierarchy, or "make it look more professional" without naming a precise style.

This reference fixes a common AI-image failure: prompts choose a style label but do not decide how the image is composed. Composition must be chosen before decorative style words.

## Composition-First Rule

Before writing style cues, silently lock these fields:

```yaml
format: "<poster / wallpaper / avatar / game menu / comic panel / character sheet / product image / social thumbnail>"
aspect_ratio: "<square / vertical / horizontal / wide / mobile>"
focal_anchor: "<face / object / title area / action / product / scene depth>"
viewer_path: "<where the eye enters, where it lands, where it exits>"
safe_area: "<space for UI/text/icons/crop, if needed>"
depth_plan: "<flat graphic / foreground-midground-background / deep perspective / orthographic>"
detail_density: "<high only at focal point; simplified secondary areas>"
```

Then choose one composition architecture and one style family.

## Core Composition Architectures

### 1. Centered Iconic

Use for logos, icons, avatars, stickers, product hero shots, game items, simple covers.

Prompt cues:

```text
centered focal subject, clean silhouette, even breathing room, stable symmetry, simplified background, readable at thumbnail size
```

Avoid:

```text
busy background, tiny accessories, cropped silhouette, fake text, random decorative glow
```

### 2. Rule-Of-Thirds Narrative

Use for portraits, cinematic stills, landscapes, environmental character art, street/photo scenes.

Prompt cues:

```text
subject placed on one third, horizon on upper or lower third, negative space in the direction of gaze or motion, secondary element balancing the frame
```

Avoid:

```text
dead-center subject by accident, empty unused space, horizon cutting through the head, background detail competing with the face
```

### 3. Leading-Line Depth

Use for streets, hallways, trains, roads, rivers, fantasy corridors, sci-fi interiors, adventure scenes.

Prompt cues:

```text
foreground lines guide the eye toward the subject, one vanishing direction, layered depth, readable scale cues, grounded contact shadows
```

Avoid:

```text
multiple conflicting vanishing points, decorative lines that do not point anywhere, floating feet, background perspective fighting the body angle
```

### 4. Frame-Within-Frame

Use for cinematic, mystery, romance, quiet story moments, windows, doors, mirrors, screens, arches.

Prompt cues:

```text
subject framed by doorway/window/foreground shape, partial obstruction, motivated light entering through the frame, clear focal separation
```

Avoid:

```text
random border decoration, frame hiding the face, symmetrical tunnel with no story point, fake lens flare replacing composition
```

### 5. Diagonal Action

Use for sports, battle, dance, chase scenes, dynamic posters, action manga, game splash art.

Prompt cues:

```text
diagonal body line, opposing force direction, clear start/end of action, motion space ahead of the subject, effects kept behind the silhouette
```

Avoid:

```text
effects covering joints, impossible twist, action cropped at hands/feet, speed lines everywhere
```

### 6. Triangular Stability

Use for group portraits, fantasy party art, product arrangements, food still life, editorial layouts.

Prompt cues:

```text
three-point visual structure, clear primary-secondary-tertiary hierarchy, stable base, detail concentrated near the apex or focal object
```

Avoid:

```text
all subjects equal size, random object scatter, no primary focal point, overlapping faces
```

### 7. Negative-Space Premium

Use for premium product images, fashion/editorial portraits, posters, album covers, app wallpapers, brand imagery.

Prompt cues:

```text
large intentional blank area, precise focal placement, restrained palette, quiet value contrast, few objects, space reserved for title or UI
```

Avoid:

```text
empty void with no design intent, fake luxury logo, glossy everything, decorative filler in every corner
```

### 8. Layered Foreground-Midground-Background

Use for story-rich images, environmental art, anime backgrounds, cinematic scenes, concept art, wallpapers.

Prompt cues:

```text
clear foreground object, midground subject, background world clue, atmosphere separating depth layers, detail falls off with distance
```

Avoid:

```text
flat collage depth, foreground clutter, background sharper than the subject, fog hiding weak staging
```

### 9. Grid / Editorial Layout

Use for posters, magazine spreads, product boards, UI mockups, moodboards, infographics, packaging.

Prompt cues:

```text
clear grid, aligned edges, consistent spacing, title-safe area, strong typographic or object hierarchy, limited color system
```

Avoid:

```text
fake small text, random alignment, decorative boxes everywhere, too many fonts, unclear reading order
```

### 10. Sequential Panel Layout

Use for four-panel comics, manga pages, storyboards, webtoon beats, tutorial images.

Prompt cues:

```text
separate panels, clear reading order, consistent character design, each panel has one beat, background simplified to support action
```

Avoid:

```text
single splash illustration, panels with changing character identity, fake dialogue text, decorative borders replacing story progression
```

### 11. Orthographic / Isometric Clarity

Use for game assets, maps, pixel art, technical drawings, character sheets, item sheets.

Prompt cues:

```text
consistent orthographic or isometric angle, no lens distortion, readable silhouette, aligned parts, neutral or gameplay-safe background
```

Avoid:

```text
dramatic perspective hiding design, inconsistent scale, unusable crop, background overpowering asset readability
```

## Mainstream Style Families With Composition Defaults

### Photography

| Style | Default composition | Use when |
|---|---|---|
| Documentary / street | rule-of-thirds narrative, imperfect framing, layered background | human, everyday, natural |
| Editorial / fashion | negative-space premium or centered iconic | polished portrait, wardrobe, magazine feel |
| Cinematic still | frame-within-frame or layered depth | story moment, movie-like mood |
| Product / catalog | centered iconic or triangular stability | object clarity, sellable product |
| Food / interior | triangular stability, negative space, top-down or 45-degree view | menu, lifestyle, room detail |
| Sports / action | diagonal action with motion space | movement, speed, force |

### Anime / Comic

| Style | Default composition | Use when |
|---|---|---|
| Hand-drawn cel anime | layout-driven key pose, layered background | anime still, character scene |
| Manga ink / screentone | sequential panel or diagonal action | black-and-white action/story |
| Webtoon / manhwa | vertical sequential layout, speech-safe space | scroll storytelling |
| Visual novel key art | character layer plus UI-safe negative space | game menu, romance, character focus |
| Chibi / sticker | centered iconic with strong silhouette | emoji, sticker, mascot |
| Retro anime frame | simple staged mid-shot, analog compositing space | nostalgic held frame |

### Game / Entertainment

| Style | Default composition | Use when |
|---|---|---|
| Game key art / splash | diagonal action or triangular hero grouping | high-impact promotional image |
| Game main menu | UI-safe negative space with story background | readable buttons plus worldbuilding |
| Character concept sheet | orthographic clarity, neutral background | design documentation |
| Trading card / gacha card | centered iconic with contained effects | collectible character/item |
| Pixel / isometric game asset | orthographic/isometric clarity | usable asset or map |
| Environment concept art | layered foreground-midground-background | worldbuilding, location mood |

### Graphic / Design

| Style | Default composition | Use when |
|---|---|---|
| Poster | single visual hook, title-safe negative space | event, film, product, campaign |
| Album / book cover | centered metaphor or rule-of-thirds narrative | cover art, emotional symbol |
| Thumbnail / social ad | centered iconic, high contrast, large shapes | small-screen readability |
| Logo / icon | centered iconic, simple geometry | scalable mark |
| Packaging | grid/editorial layout, product-safe hierarchy | label, box, cosmetic, food |
| Infographic / diagram | grid hierarchy, callout-safe spacing | information clarity |

### Illustration / Painting

| Style | Default composition | Use when |
|---|---|---|
| Watercolor | negative-space premium or light layered depth | gentle, airy, handmade |
| Gouache / poster color | simplified planes, strong foreground/background | editorial, cozy, anime background |
| Oil / painterly | value-mass hierarchy, triangular stability | portrait, fantasy, classic drama |
| Woodblock / print | flat decorative composition, controlled pattern | traditional, poster, craft |
| Risograph / screenprint | graphic grid or centered metaphor | editorial poster, zine, indie |
| Vector editorial | grid/editorial layout, bold shape hierarchy | article art, SaaS, explainer |
| Children's book / cute flat | centered readable action, simplified setting | soft story, approachable character |

## Composition Translation For Fuzzy Requests

| User phrase | Translate to composition |
|---|---|
| 更有构图 | choose one focal anchor, one viewer path, one depth plan |
| 更高级 | negative-space premium, few objects, precise spacing |
| 更有故事感 | layered foreground-midground-background, off-frame gaze, one clue of before/after |
| 更电影感 | frame-within-frame, motivated practical light, foreground obstruction, restrained palette |
| 更震撼 | low viewpoint, diagonal action or triangular hero grouping, strong value mass |
| 更干净 | clear focal hierarchy, simplified secondary areas, consistent spacing |
| 更适合壁纸 | wide/mobile safe areas, no important detail under icons, calm value grouping |
| 更适合封面 | single hook, title-safe area, readable silhouette at thumbnail size |
| 更适合头像 | centered face, readable eyes/expression, simple background, strong crop safety |
| 更适合游戏菜单 | story background plus button-safe negative space, title/logo hierarchy |

## Prompt Blocks

### Compact Composition Block

```text
Composition: [architecture], [focal anchor] placed [center/third/foreground], viewer's eye moves from [entry] to [subject] to [secondary clue], [safe area], detail concentrated at the focal point and simplified elsewhere.
```

### Deep Composition Block

```text
Composition plan: [format/aspect ratio]. Focal hierarchy: primary [subject], secondary [supporting object], tertiary [background clue]. Camera/framing: [shot size, angle, crop]. Viewer path: [leading line/gaze/motion direction]. Depth: [flat/layered/deep/isometric]. Safe area: [title/UI/crop]. Detail density: sharpest and richest only at [focal point], quieter shapes elsewhere.
```

### Edit Prompt Block

```text
Improve the composition while preserving the subject identity, requested style, and main scene. Keep one clear focal anchor, remove or simplify secondary clutter, align the crop with the intended format, reserve required safe space for UI/text if needed, and use [composition architecture] to guide the viewer's eye. Do not change the concept, role, or required props.
```

## Anti-AI Composition Checklist

Before returning a prompt, check:

- Is there one clear focal anchor?
- Does the composition match the requested output format?
- Is detail density controlled instead of spread everywhere?
- Is negative space intentional, not empty by accident?
- Do foreground, midground, and background share perspective and lighting?
- Do background/secondary figures, props, architecture, and non-focus details receive the same quality scrutiny as the focal subject?
- Does the crop preserve hands, feet, props, logo/title safe areas, and action direction?
- Are effects behind or around the silhouette instead of hiding anatomy?
- If the image is for UI, are buttons/text/logo areas readable?

## Fast Examples

### Game Start Page With Story

```text
Composition: game main menu layout, character and world clue on the left third, readable button-safe negative space on the right, layered sky/city/foreground object depth, title/logo-safe top-left area, calm value grouping behind UI.
```

### Four-Panel Comic With Cinematic Mood

```text
Composition: four clearly separated panels in reading order. Each panel uses one story beat, controlled close/medium/wide shot variation, consistent character design, and simple backgrounds that support the emotional turn. Do not merge into a single poster.
```

### Premium Product Poster

```text
Composition: negative-space premium layout with product anchored slightly below center, title-safe blank area above, one soft shadow grounding the object, restrained secondary prop only if it explains scale or material.
```

### Anime Wallpaper

```text
Composition: wide layered background, character on one third, large calm sky or interior negative space for desktop icons, foreground object hinting at story, hand-painted background detail falling off into distance.
```
