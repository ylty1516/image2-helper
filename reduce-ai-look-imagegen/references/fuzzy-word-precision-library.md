# Fuzzy Word Precision Library

Use this when the user gives vague taste words and the result would otherwise become generic, over-polished, or style-wrong. This is a precision library, not a synonym list.

Load this file after `intent-and-fuzzy-language.md` when:

- the prompt contains several vague taste words
- the user asks to "make it more X" without clear visual decisions
- the image must match an individual user's preference quickly
- the first output missed the user's intended vibe

## Core Rule

Turn each vague word into 3 to 5 concrete visual decisions:

```yaml
precision_expansion:
  format_lock: "do not change the requested output structure"
  visual_function: "what the word should do in the image"
  light_color: "specific light, value, color, or contrast behavior"
  composition: "framing, spacing, depth, focal path, or safe area"
  material_process: "medium, texture, material, camera, or rendering evidence"
  subject_behavior: "pose, gaze, expression, action, or social logic"
  avoid: "2-3 likely wrong interpretations"
```

Do not expand every word in the user prompt. Pick the two highest-impact vague words and convert only those unless the user asks for a full profile.

## Fast Disambiguation

| Vague word | Usually means | Concrete conversion | Avoid |
|---|---|---|---|
| 高级感 / premium | restraint and credible taste | precise negative space, fewer objects, restrained palette, real material behavior, quiet light | gold everywhere, fake luxury logo, glossy surfaces |
| 奢华 / luxurious | abundance and expensive material | rich material contrast, polished but believable metal/glass/fabric, layered decor with hierarchy | clutter, fake brands, over-shiny everything |
| 氛围感 / atmospheric | mood from light and air | motivated light, visible air depth, foreground-midground-background layering, weather or time cue | fog hiding weak structure, random bokeh |
| 故事感 / story-rich | implied before/after | specific story moment, environmental clues, gaze/action direction, object with consequence | random symbolic props, static beauty shot |
| 电影感 / cinematic | narrative frame and value control | motivated practical light, lens perspective, layered blocking, value hierarchy | orange-teal default, fake flare |
| 松弛感 / relaxed | natural ease | relaxed posture, breathable spacing, casual folds, ordinary imperfect object placement | sloppy anatomy, messy clutter |
| 张力 / tension | pressure or conflict | asymmetry, diagonal force, compressed space, opposing gaze/action, selective contrast | random action effects, visual noise |
| 冲击力 / impact | immediate read | strong silhouette, bold value contrast, simple focal hook, scale contrast | detail everywhere, no hierarchy |
| 治愈 / healing | safety and warmth | warm practical light, soft tactile surfaces, small routine detail, gentle posture | candy overload, uncanny smile |
| 生活感 / lived-in | ordinary believable use | used objects, slight wear, real placement logic, non-staged clutter | dirty chaos, empty showroom |
| 真实感 / realistic | physical and camera plausibility | lens/exposure limits, contact shadows, scale cues, material texture, natural anatomy | HDR clarity, perfect skin |
| 胶片感 / film look | analog color/exposure | highlight rolloff, midtone grain, muted color crossover, slight halation | fake scratches, uniform noise |
| 手绘感 / hand-drawn | human mark-making | controlled line weight, paper grain, brush/pencil pressure, handmade edge variation | smooth AI gradients |
| 质感 / texture quality | material credibility | surface response, thickness, edge wear, tactile variation, contact marks | random noise overlay |
| 细节感 / detailed | purposeful information | focal detail hierarchy, readable object functions, varied but logical small parts | micro-detail everywhere |
| 干净 / clean | hierarchy and control | limited palette, clear spacing, consistent edges, simplified secondary surfaces | sterile void, no texture |
| 极简 / minimal | intentional reduction | one focal idea, strong negative space, limited geometry, precise alignment | unfinished emptiness |
| 空灵 / ethereal | light quiet otherworldliness | pale value range, translucent layers, soft depth, delicate edges | overexposure, random sparkles |
| 透明感 / clarity | clean light and air | controlled pale palette, translucent material behavior, soft reflections, enough contrast | washed-out whites |
| 梦幻 / dreamy | memory-like softness | soft value transitions, sparse symbolic props, gentle haze with depth | over-blur, fantasy clutter |
| 少女感 / girlish softness | delicate youthful styling | soft palette, airy spacing, age-appropriate fabric/accessory detail | sexualized framing |
| 少年感 / boyish youth | fresh direct energy | casual posture, wind or motion cue, sporty silhouette, natural expression | stiff idol pose |
| 可爱 / cute | safe readable charm | rounded shapes, clear expression, simplified detail, strong silhouette | creepy doll eyes |
| 软萌 / soft cute | gentle round cuteness | plush-like shape, low contrast, soft edges, small gesture | plastic toy gloss |
| 酷 / cool | attitude or sharpness | confident pose, sharper silhouette, controlled contrast, bold accent | sunglasses by default |
| 冷淡 / aloof | emotional distance | reserved expression, cool palette, wider spacing, reduced gesture | lifeless blank face |
| 热血 / passionate | active motivation | forward motion, warm accents, dynamic body line, visible effort | random flames |
| 史诗感 / epic | scale and stakes | large scale reference, wide/low viewpoint, layered depth, central silhouette | fantasy clutter |
| 压迫感 / oppressive | weight and constraint | low ceiling, looming mass, compressed spacing, heavy value blocks | black mush |
| 孤独感 / lonely | social or spatial isolation | single figure, negative space, distance cues, muted sound/color feeling | empty without story |
| 赛博 / cyberpunk | neon noir urban tech | wet reflections, practical neon, dense city layers, shadowed faces | neon everywhere |
| 科幻感 / sci-fi | speculative technology logic | functional future objects, clean interfaces, scale cues, material systems | random glowing parts |
| 未来感 / futuristic | forward-looking design | streamlined geometry, translucent tech, controlled lighting, new material logic | generic blue glow |
| 复古 / retro | era-specific production | chosen decade/medium palette, process cue, typography-safe space | generic beige filter |
| Y2K | early digital futurism | chrome bubbles, translucent plastic, candy color, rounded UI forms | modern app gradient |
| 蒸汽波 / vaporwave | artificial retro nostalgia | pastel magenta-cyan, grid horizon, classical/computer motif if relevant | random Japanese text |
| 国风 / Chinese-inspired | specific Chinese medium or design cue | ink wash, gongbi, folk print, modern Chinese graphic, or costume fantasy as selected | fake Chinese text, dragon dumping |
| 古风 / historical Chinese fantasy | historical mood, costume, setting | era-consistent silhouette, fabric layers, architecture/material cue | mixed dynasty costume soup |
| 日系 / Japanese-style | broad seasonal or anime/lifestyle cue | infer anime, clean lifestyle, minimal design, or quiet seasonal mood from use case | random kana/torii |
| 韩系 / Korean-style | clean trend, soft polish, webtoon, or lifestyle | choose fashion/lifestyle/manhwa/product route, soft color, clean composition | generic idol face |
| 二次元 / anime-style | anime/manga rendering | clean contour, flat local color, cel shadow logic, readable silhouette | glossy 3D hair |
| 赛璐璐 / cel | animation color logic | hard-edged shadow blocks, flat color, simple highlights, painted background layer | airbrush gradients |
| 厚涂 / painterly | brush mass and value shaping | broad brush masses, visible stroke direction, lost edges, focal texture | AI brush filter |
| 水彩感 / watercolor | transparent pigment behavior | washes, paper grain, reserved highlights, soft/hard edge variation | plastic gradients |
| 油画感 / oil paint | paint body and edges | brush direction, canvas/paint behavior, value structure, lost-and-found edges | photo with paint filter |
| 美式漫画 / American comic | bold graphic ink | black fills, strong contour, flat separations, halftone if needed | fake comic dots |
| 韩漫 / manhwa | vertical webtoon logic | clean character rendering, readable acting, speech-safe space, selective gradients | fake dialogue |
| 乙女 / otome | romance visual-novel appeal | expressive gaze, elegant details, soft tension, UI-safe negative space | over-sexualization |
| 设定感 / concept design | visible world rules | functional silhouette, material logic, scale cue, callout-safe areas | meaningless glowing parts |
| Logo感 / brand mark | scalable identity | simple geometry, clear silhouette, limited colors, strong negative space | illustration scene |
| 图标感 / icon feel | small-size readability | centered simple symbol, consistent stroke/fill, limited detail | tiny text, scenic depth |

## Pairwise Clarifiers

Use these when two fuzzy words look similar but should not produce the same prompt.

| If user says | Do this | Do not do this |
|---|---|---|
| 高级感, not 奢华 | reduce and refine | add gold, jewels, luxury logos |
| 生活感, not 杂乱 | add ordinary use evidence | scatter random clutter |
| 氛围感, not 模糊 | build air/light/depth | blur the whole image |
| 故事感, not 道具堆 | imply cause and consequence | add random symbolic props |
| 电影感, not 滤镜感 | control staging and value | add flare and teal-orange only |
| 松弛感, not 懒散 | make posture natural | break anatomy or composition |
| 透明感, not 曝光过度 | keep clean light with contrast | wash out all edges |
| 真实感, not 照片噪声 | enforce physical plausibility | add grain/noise only |
| 可爱, not 幼稚堆料 | use shape and expression | add hearts/bows everywhere |
| 国风, not 符号堆砌 | pick a concrete Chinese medium | add random dragons/clouds/text |

## Output-Use Overrides

The same fuzzy word changes by output use case.

| Use case | Fuzzy word behavior |
|---|---|
| avatar | prioritize face readability, silhouette, expression, small-size contrast |
| wallpaper | preserve icon-safe quiet areas and avoid text clutter |
| poster | build one visual hook plus title-safe space |
| game menu | preserve button-safe negative space and UI contrast |
| comic | keep panel sequence and character continuity before mood |
| product image | translate taste words into material, scale, label-safe layout |
| logo/icon | reduce fuzzy mood into geometry, silhouette, color, and scalability |
| realistic portrait | translate mood into light, lens, environment, posture, and skin/material plausibility |

## Compact Rewrite Template

Use this when the answer must stay short:

```text
Interpret "[word]" as [visual function], not [wrong interpretation].
Use: [light/color], [composition], [material/process], [subject behavior].
Avoid: [2-3 likely failures].
```

Example:

```text
Interpret "atmospheric" as motivated dusk light, air depth, layered foreground/midground/background, and quiet negative space, not random fog or bokeh. Avoid glow hiding weak composition, unreadable subject, and fake lens flare.
```

## Multi-Word Merge

When the user stacks fuzzy words, merge them instead of listing every row.

```yaml
user_words: ["高级感", "松弛感", "生活感"]
merged_intent: "restrained everyday realism"
prompt_cues:
  - precise negative space and limited palette
  - relaxed posture and natural clothing folds
  - ordinary used objects placed with real purpose
  - soft practical light, no luxury logos, no showroom emptiness
```

```yaml
user_words: ["故事感", "电影感", "氛围感"]
merged_intent: "narrative cinematic atmosphere"
prompt_cues:
  - one specific before/after story moment
  - motivated practical light and value hierarchy
  - layered depth with environmental clues
  - no random fog, no fake flare, no symbolic prop pile
```

```yaml
user_words: ["可爱", "干净", "图标感"]
merged_intent: "small readable cute icon"
prompt_cues:
  - centered simple symbol or character head
  - rounded silhouette, clear expression, limited palette
  - consistent stroke/fill and no tiny internal detail
  - no full scenic background
```

## Personal Taste Calibration

When learning a specific user's taste, store only compact preference rules:

```yaml
preference_rule:
  user_word: "<the user's vague word>"
  means_for_this_user: "<concrete visual translation>"
  likes:
    - "<repeatable cue>"
  dislikes:
    - "<failure cue>"
  prompt_patch: "<one reusable sentence>"
```

Do not store large interviews or long explanations inside the final prompt. Convert preference memory into short visual rules.
