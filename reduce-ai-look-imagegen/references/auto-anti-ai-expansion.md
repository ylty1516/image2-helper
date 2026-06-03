# Auto Image Quality Expansion

Use this for every image-generation phrase before calling imagegen. The goal is to silently enrich the final generation prompt with compact quality-control constraints while preserving the user's original intent. Lowering AI look is one important module, but this file is equally responsible for format preservation, intent completion, fuzzy-word repair, composition, perspective, physical logic, style clarity, consistency, and background integrity.

## Core Behavior

Always add a minimal preflight layer for visible-space logic, format preservation, style clarity, and obvious fuzzy wording. When trigger words appear, add the matching compact support layer in the background. Do not ask the user to provide missing craft terms. Translate vague requests into visual mechanics.

Default route:

```text
user phrase -> preserve format/subject/style -> add universal quality preflight -> detect trigger words -> add 0-2 focused category patches -> repair top 0-2 fuzzy words -> produce/generate with the enriched prompt
```

If the user asks for the final prompt, show the enriched prompt. If the user asks only for an image, use the enriched prompt silently and keep chat explanation short.

## Trigger Detection

No trigger words are required for minimal preflight. First scan `INDEX.md` for quick trigger/search words. Then load the focused reference only if the trigger is specific.

Always-on minimal preflight:

```text
Preserve the requested format, subject, style, aspect ratio, and required props. Add perspective lock when space is visible, physical contact/material logic, focal hierarchy, and scene/background integrity when relevant. Repair only the strongest vague taste words.
```

High-priority quality triggers:

- AI味, ai味, 一眼AI, 降AI, 去AI感, less AI, de-AI, too AI
- 自动补全, 后台补充, 模糊词修缮, prompt enrichment, fuzzy taste words
- 透视, 透视错误, 地平线, 消失点, 比例不对, 尺度混乱, horizon, vanishing point, perspective, ground plane, scale mismatch, occlusion
- 二次元人物融入现实, 动漫人物进现实, 角色进屏幕, 显示器, 手机屏幕, 桌面场景, AR角色, hologram, anime character in real photo, monitor, phone display, screen integration
- 手绘感, 真人画师, 动画感, hand-drawn, cel, genga, linework
- 赛博, 霓虹, 蓝紫, cyber anime, neon, fake code, floating UI, crystal
- 动漫壁纸感, 天空太AI, 新海模板, 风景壁纸, spectacular sky, rooftop, station, torii
- 史诗奇幻, 奇幻风景, 奇幻壁纸, 冰雪王国, 熔岩城堡, 浮岛, 天空城, 极光, 月亮, 瀑布群, epic landscape, fantasy panorama, lava fortress, ice kingdom, floating islands
- 镜面反光, 反光太满, wet pavement, mirror gloss, puddle
- 背景假, 假招牌, unreadable signs, fake signage, props melt
- 太满, 太碎, 细节堆满, no focal hierarchy, meaningless micro-detail
- 人物像贴上去, generic wistful pose, grounded feet, contact shadows

Fuzzy taste triggers:

- 高级感, 氛围感, 故事感, 电影感, 真实感, 干净, 精致, 可爱, 梦幻, 透明感, 质感, 细节感, 日系, 二次元, 赛博朋克, 未来感, 复古
- premium, atmospheric, story-rich, cinematic, realistic, clean, detailed, dreamy, cute, transparent, texture quality

## Expansion Rules

1. Preserve the user's format, subject, required style, and required props.
2. Add no more than two focused category patches unless the user requests deep refinement.
3. Repair no more than two fuzzy words by converting them into concrete light/color, composition, material/process, and subject-behavior cues.
4. Add the global perspective layer whenever the image has visible space, objects, architecture, landscape, products, people in a scene, or props on a surface.
5. Prefer positive construction cues before negative avoid cues.
6. Use avoids only for the top likely failures.
7. Do not add unrelated props, story symbols, text, logos, or named artist/studio copying.
8. If text/signage is not exact and necessary, make it blank, abstract, or non-readable by design.

## Global Perspective Layer

Use this compact layer for every generated image with visible space:

```text
Perspective geometry: one camera height, one horizon line, one coherent perspective system, aligned ground/floor/water/table planes, believable scale anchors, contact shadows, overlap order, foreshortening, and depth falloff.
```

If the prompt is already long, use the shorter form:

```text
Perspective lock: one camera height, coherent horizon/vanishing system, grounded contact, believable scale and occlusion.
```

## Background Support Layer

Append a compact support layer like this:

```text
Quality support: [medium/process evidence], [focal hierarchy], [motivated light/material logic], [grounded pose/contact/scene integrity]. Avoid [top 2-3 matched failure modes].
```

For general anti-AI polish:

```text
Anti-AI support: real medium/process evidence, controlled highlight shapes, grounded contact shadows, plausible anatomy/material response, and no meaningless micro-detail. Avoid generic AI gloss, over-symmetry, fake luxury polish, and impossible contact points.
```

For anime:

```text
Anime quality support: clean animation contours, flat local color fields, selective hard-edged cel shadows, hand-painted background masses, restrained compositing, grounded character contact, and scene details with real function. Avoid glossy 3D hair/skin, random rim light, fake text, mirror gloss everywhere, and meaningless micro-detail.
```

For anime character real-scene / screen integration:

```text
Anime-real integration support: match the real scene camera plate, scale anchors, horizon/ground plane, light direction, color temperature, exposure, shadow softness, contact shadow, ambient occlusion, reflected color, edge softness, lens grain/compression, and foreground occlusion. Give the anime character a clear physical anchor such as feet on floor, hand on desk, body behind monitor bezel, reflection on glass, or screen glow on nearby surfaces. Avoid floating sticker cutout, mismatched lighting, wrong scale, pure cel colors unaffected by the room, and clean pasted edges.
```

For cyber/neon anime:

```text
Quality support: one focal hierarchy, 2-3 motivated neon sources, neutral dark anchors, designed hair masses, functional UI/tech props only, readable cel shadow shapes. Avoid fake code, random floating panels, crystals/shards/petals without purpose, uniform blue-purple gloss, and sparkle detail everywhere.
```

For anime scenic wallpaper:

```text
Quality support: one observed place and one weather/light event, broad hand-painted cloud masses, quiet sky areas, imperfect local reflections, functional station/shrine/rooftop objects, blank or accurate signs, and a character grounded in a concrete story beat. Avoid stacked sunset/rainbow/stars/snow/birds spectacle, mirror pavement, over-detailed clouds everywhere, and generic wistful poses.
```

For epic fantasy landscapes:

```text
Quality support: one clear worldbuilding hook, one terrain/light logic, functional architecture with entrances/paths/supports/scale references, physically motivated water/lava/ice/cliffs, atmospheric distance simplification, and controlled detail density. Avoid castle/aurora/moon/lava/waterfall/floating-island spectacle all at once, random spires, repeated ruins, impossible waterfalls, glowing cracks everywhere, unreadable kitbash, and equal detail across the panorama.
```

## Fuzzy Word Repair Pattern

Convert fuzzy words into compact concrete cues:

```text
Interpret "[fuzzy word]" as [visual function]: [light/color], [composition], [material/process], [subject behavior]. Avoid [wrong interpretation].
```

Common repairs:

```text
高级感 -> restraint: precise spacing, fewer objects, restrained palette, credible material behavior, controlled reflections, no fake luxury marks.
氛围感 -> motivated light and air depth: foreground/midground/background layering, weather or time cue, visible atmosphere without hiding weak structure.
故事感 -> one specific before/after moment: gaze/action direction, environmental clue, object with consequence, no random symbolic prop pile.
电影感 -> narrative framing and value hierarchy: motivated practical light, layered blocking, lens/exposure restraint, no default flare or orange-teal grading.
真实感 -> physical plausibility: scale cues, contact shadows, natural anatomy, material texture, exposure limits, no HDR clarity everywhere.
干净 -> controlled hierarchy: limited palette, clear spacing, consistent edges, simplified secondary surfaces, no sterile empty void.
细节感 -> purposeful information: detail concentrated at the focal point, readable object functions, varied but logical small parts, no micro-detail everywhere.
手绘感 -> human mark-making: controlled line weight, paper/paint behavior, simplified handmade shapes, slight edge irregularity, no smooth AI gradients.
```

## Compact Example

User phrase:

```text
生成一张氛围感很强的赛博霓虹动漫少女，蓝紫色，降低AI味
```

Internal expansion:

```text
Create an anime illustration. Subject: a cyber-neon anime girl in a specific urban night setting. Interpret "氛围感" as motivated neon light, air depth, layered foreground/midground/background, and shadowed negative space. Quality support: clean animation contours, flat local color fields, one focal hierarchy around face and hands, 2-3 motivated neon sources, neutral dark anchors, designed hair masses, functional tech props only. Anti-AI support: avoid fake code, random floating UI, crystals/shards without purpose, uniform blue-purple gloss, and sparkle detail everywhere.
```

User phrase:

```text
生成一张动漫女孩从电脑屏幕里探出身体，现实桌面场景
```

Internal expansion:

```text
Create an anime-real mixed scene of an anime girl emerging from a computer monitor into a real desktop setup. Preserve the screen-emergence concept. Anime-real integration support: match the real camera height, screen plane, monitor bezel, viewing angle, desk scale anchors, room light direction, screen glow, contact shadow, ambient occlusion, glass reflection, pixel texture, edge softness, and foreground occlusion. Define the crossing point at the bezel and avoid a flat pasted wallpaper, floating sticker cutout, mismatched scale, and pure cel colors unaffected by the room.
```

User phrase:

```text
日系动漫风景，天空很震撼，雨后站台，电影感，去AI味
```

Internal expansion:

```text
Create a Japanese anime scenic illustration of a rainy station after the storm. Interpret "电影感" as narrative framing, motivated practical light, value hierarchy, and lens/exposure restraint. Quality support: one observed station and one weather/light event, broad hand-painted cloud masses with selective edge light, quiet sky areas, imperfect local puddle reflections broken by tile seams and wet/dry patches, functional station hardware, blank or accurate signs, and a character or prop grounded in one concrete story beat. Avoid stacked rainbow/sunset/stars/birds spectacle, mirror pavement, over-detailed clouds everywhere, fake signage, and generic wallpaper composition.
```
