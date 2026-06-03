# Reference Index

Use this file only when you need a quick map of the reference folder.

## Fast Routes

| Need | File |
|---|---|
| Any image generation request: universal lightweight preflight before imagegen | `auto-anti-ai-expansion.md` |
| Quick quality repair or compact rewrite | `fast-path.md` |
| Auto-add image quality constraints and repair fuzzy words in a generation phrase | `auto-anti-ai-expansion.md` |
| Lower token use without quality loss | `quality-preserving-speed.md` |
| Decide whether this skill should run | `routing-and-triggering.md` |

## Quick Quality-Control Trigger Words

Use this section as a fast search map. If the user's wording or inspected image matches one row, load the listed file first.

| Category | Trigger/search words | Load |
|---|---|---|
| General AI feel | AI味, ai味, 太AI, 一眼AI, fake, generic, template, default beauty, plastic, glossy, oily, 3D感, 赛博糖水 | `failure-feedback-fixes.md` |
| Perspective/spatial geometry | 透视, 透视错误, 空间歪, 地平线, 消失点, 地面漂浮, 比例不对, 尺度混乱, horizon, vanishing point, perspective, ground plane, floor plane, floating feet, scale mismatch, occlusion | `perspective-geometry.md` |
| Anime character real-scene/screen integration | 二次元人物融入现实, 动漫人物进现实, 纸片人现实, 角色进屏幕, 屏幕里的人物, 显示器, 手机屏幕, 桌面场景, AR角色, hologram, anime character in real photo, anime in real scene, monitor, phone display, screen integration | `anime-character-real-scene-integration.md` |
| Hand-drawn anime repair | 手绘感, 真人画师, 动画感, cel, genga, douga, linework, cel shadow, flat color, hand-painted, not hand-drawn enough | `anime-handdrawn-look.md` |
| Cyber/neon anime template | 赛博, 霓虹, 蓝紫, cyber anime, neon, floating UI, fake code, crystal, shards, butterflies, constellation, micro-detail, glow everywhere | `anime-handdrawn-look.md` then `failure-feedback-fixes.md` |
| Anime wallpaper sky/scenery | 动漫壁纸感, 天空太AI, 新海模板, 风景壁纸, 夕阳, 彩虹, 雪景, 屋顶, 海边车站, 神社, torii, rooftop, station, spectacular sky, mirror reflections | `anime-handdrawn-look.md` then `background-integrity.md` |
| Epic fantasy landscape wallpaper | 史诗奇幻, 奇幻风景, 奇幻壁纸, 冰雪王国, 熔岩城堡, 浮岛, 天空城, 极光, 月亮, 瀑布群, lava fortress, ice kingdom, floating islands, fantasy panorama, epic landscape, generic epic landscape | `style-expansion-pack.md` then `background-integrity.md` |
| Background/place logic | 背景假, 场景不真实, 假招牌, unreadable signs, fake signage, props melt, architecture, perspective, station hardware, railing, roof supports | `background-integrity.md` |
| Reflection/material over-polish | 镜面反光, 反光太满, 地面太亮, wet pavement, mirror gloss, puddle, tile seams, surface roughness, wet/dry patches, material logic | `background-integrity.md` then `failure-feedback-fixes.md` |
| Detail/focal hierarchy | 太满, 太碎, 细节堆满, no focal hierarchy, equal detail density, cluttered, meaningless micro-detail, no quiet area, no negative space | `failure-feedback-fixes.md` then `mainstream-style-composition.md` |
| Character belongs to scene | 人物像贴上去, 姿势空, generic wistful pose, grounded feet, weight, contact, wind response, rain response, story beat | `prompt-recipes.md` then `background-integrity.md` |
| Auto fuzzy-word repair | 自动补全, 后台补充, 模糊词修缮, fuzzy taste words, prompt enrichment, compact expansion | `auto-anti-ai-expansion.md` then `fuzzy-word-precision-library.md` |

## Current Quality-Control Categories

### 1. Generic Polish / Plastic Finish

Problem:

- generic quality words create default beauty, smooth gradients, glossy skin/hair, and no production constraints

Use language:

```text
Replace generic polish with a real medium/process artifact: controlled line weight, visible paper/paint/scan texture, flat local color or material-specific roughness, restrained highlight shapes, and grounded contact shadows.
```

### 2. Perspective / Spatial Geometry

Problem:

- AI often invents different horizons, vanishing points, ground planes, object scales, and occlusion orders inside one image

Use language:

```text
Lock one camera height, one horizon line, and one coherent perspective system. Align floor/ground/water/table planes, architecture, props, figures, contact shadows, scale anchors, overlap order, foreshortening, and depth falloff.
```

### 3. Anime Character Real-Scene / Screen Integration

Problem:

- anime character looks pasted onto a real photo, room, desktop, phone, monitor, or AR scene because scale, light, shadow, edge softness, reflection, and occlusion do not match

Use language:

```text
Lock the existing real background plate first: preserve all objects, positions, crop, perspective, exposure, color temperature, original light, original shadows, highlights, reflections, clutter, texture, grain, and compression. Do not clean, relight, repaint, stylize, replace, add, remove, or move anything in the background. Then match the anime character layer to the real scene camera, scale, light response, contact/occlusion, edge softness, and grain.
```

### 4. Over-Decorated Cyber Anime

Problem:

- blue-purple neon, fake UI/code, crystals, glow trails, and sparkle detail cover every layer equally

Use language:

```text
Keep one focal hierarchy and limit glow to 2-3 motivated sources. Remove decorative floating UI, fake code, random crystals, petals, constellations, and meaningless micro-detail. Use readable anime linework, designed hair masses, neutral dark anchors, and selective cyan/violet accents.
```

### 5. Anime Wallpaper Sky / Scenic Poster

Problem:

- dramatic sky, sunset/rainbow/stars/snow/birds/reflections, and iconic scenery props are stacked into a beautiful but template-like wallpaper

Use language:

```text
Use one observed place and one weather/light event. Paint broad hand-made cloud masses with selective edge light and quiet negative areas. Make reflections local and broken by puddle edges, tile seams, grime, roughness, and wet/dry patches. Keep props functional, signs blank or accurate, and characters grounded in a specific story beat.
```

### 6. Background And Prop Integrity

Problem:

- background objects, signage, station/shrine/rooftop hardware, railings, benches, bicycles, plants, and architecture become decorative filler

Use language:

```text
Give every visible background object a real function, scale, construction, material, contact point, and perspective logic. Simplify distant details with paint, not with melted forms or fake text.
```

### 7. Epic Fantasy World Logic

Problem:

- fantasy landscapes stack castle/aurora/moon/lava/waterfall/floating-island spectacle without scale, terrain, light, or architecture logic

Use language:

```text
Use one worldbuilding hook and one terrain/light logic. Give architecture entrances, paths, supports, defenses, scale references, material wear, and cultural consistency. Make water, lava, ice, cliffs, and floating land obey a clear internal rule. Use atmospheric perspective and avoid equal detail density across the entire panorama.
```

### 8. Detail Density / Composition Discipline

Problem:

- every part is equally detailed, bright, reflective, or dramatic, so the image feels generated rather than composed

Use language:

```text
Reserve high detail for the focal face/hands/main prop; simplify secondary surfaces; preserve quiet areas and readable silhouettes; remove decorative effects that do not support the story.
```

### 9. Character-Scene Integration

Problem:

- character looks inserted into a pretty background, with generic wistful posture and weak physical contact

Use language:

```text
Make the character belong to the scene: grounded feet, believable weight, contact shadows, clothing/hair responding to wind/rain/snow, gaze and posture tied to one concrete story beat.
```

## Repair Modules

| Need | File |
|---|---|
| Background/non-focus objects, secondary figures, malformed crowds, broken architecture | `background-integrity.md` |
| Extra props, prompt-image mismatch, expression/action or viewpoint/environment mismatch | `inconsistency-cleanup.md` |
| User says too AI, too glossy, bad hands, fake, busy, not premium | `failure-feedback-fixes.md` |
| Pose/action correction, realism pass, reusable recipes | `prompt-recipes.md` |
| Anime battle, weapon clash, magic combat, martial arts, monster fight | `combat-action-anime.md` |
| Anime character inside real photo, monitor, phone, desktop, AR, display, or room scene | `anime-character-real-scene-integration.md` |

## Style And Intent Modules

| Need | File |
|---|---|
| Fuzzy words, hard format lock, user purpose parsing | `intent-and-fuzzy-language.md` |
| Deep fuzzy taste-word translation and personal preference wording | `fuzzy-word-precision-library.md` |
| Anime, cel, genga/layout, hand-painted backgrounds | `anime-handdrawn-look.md` |
| Better composition, framing, mainstream style defaults | `mainstream-style-composition.md` |
| Choose style by output use case | `style-selection-and-use-cases.md` |
| Broad style taxonomy | `style-taxonomy.md` |
| Niche/historical/craft/technical styles | `style-expansion-pack.md` |
| Mixed/conflicting styles | `style-blending-rules.md` |
| Ready prompt skeletons | `style-prompt-cookbook.md` |
| Score before/after quality | `style-quality-rubric.md` |

## Loading Rule

Load one file first. Add a second file only when the task has a separate risk.

Examples:

- "anime quality repair, too glossy or too generic" -> `fast-path.md` + `anime-handdrawn-look.md`
- "anime battle looks flashy but action is unclear" -> `combat-action-anime.md`
- "maid skin has an unwanted staff" -> `inconsistency-cleanup.md`
- "main character is good but the background people/props/buildings look fake" -> `background-integrity.md`
- "anime girl coming out of my monitor" -> `anime-character-real-scene-integration.md`
- "faster image2 with same quality" -> `quality-preserving-speed.md`
- "game menu more story-rich but buttons clear" -> `mainstream-style-composition.md`
- "make it more premium, relaxed, story-rich, lived-in, or transparent" -> `intent-and-fuzzy-language.md` then `fuzzy-word-precision-library.md` if needed
