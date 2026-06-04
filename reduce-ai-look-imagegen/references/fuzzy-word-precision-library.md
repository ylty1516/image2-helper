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

## Extended Precision Map

Use this map as a broader vocabulary bank when the first table is too small. It is still a decision tool, not a thesaurus. For each fuzzy term, convert the user's taste word into visual function, light/color, composition, material/process, subject behavior, and avoid cues. Pick only the entries that actually affect the image.

### Mood, Emotion, And Social Temperature

| Vague word | Interpret as | Concrete conversion | Avoid |
|---|---|---|---|
| 安静 / quiet | lowered sensory pressure and reduced social noise | use still posture, fewer competing objects, soft contrast, breathable negative space, muted environmental sound cues, and one gentle light source that lets the subject rest without becoming empty | sterile void, lifeless face, gray sameness |
| 温柔 / gentle | softness with care and low threat | use curved gestures, warm but not sugary light, tactile fabric, rounded spacing, low edge aggression, relaxed hands, and facial expression that suggests attention rather than performance | pink overload, weak anatomy, vacant smile |
| 克制 / restrained | intentional reduction with discipline | keep a narrow palette, one focal hierarchy, limited highlights, simple props, exact alignment, controlled gesture, and material evidence that feels selected rather than expensive for its own sake | underdesigned emptiness, luxury decoration |
| 疏离 / detached | distance with emotional control | widen personal space, reduce direct gesture, cool the palette slightly, keep the gaze off-axis, separate subject from background with value rather than glow, and let the environment imply social distance | dead expression, random blue filter |
| 亲密 / intimate | close human proximity and trust | use closer framing, small shared objects, hand or eye-line relationships, practical warm light, shallow depth from a real lens, and lived-in surface details that make the viewer feel physically near | voyeuristic crop, romantic cliche |
| 清冷 / cool and pure | cool value clarity with emotional reserve | use pale neutral light, sparse composition, crisp local color, cool shadows, smooth but not plastic surfaces, calm pose, and enough dark accents to prevent washed-out whiteness | icy fantasy glow, overexposure |
| 暧昧 / ambiguous tension | unresolved social or emotional signal | use partial eye contact, interrupted gesture, doorway or mirror framing, near-but-not-touching spacing, warm/cool color opposition, and props that imply a before/after moment without explaining everything | random romance props, fake mystery fog |
| 破碎感 / fragile brokenness | vulnerability shown through structure and posture | use off-balance framing, small repair marks, tired hands, slightly lowered gaze, thin light, worn texture, and background gaps that imply loss while keeping anatomy and scene logic intact | melodrama, shattered glass everywhere |
| 生命力 / vitality | visible energy in body and environment | use active posture, lifted chest or forward step, fresh local color, directional daylight, small motion cues, healthy material contrast, and background details that respond to movement | random sparkles, oversaturated greens |
| 野性 / wildness | untamed behavior and raw environment | use asymmetry, wind or dust, rough material, practical dirt, direct stance, incomplete grooming, and lighting that reveals texture without making the subject a fantasy beast unless requested | messy chaos, animal cliches |
| 厌世 / world-weary | tired intelligence and emotional distance | use low-effort posture, heavy eyelids, muted palette, compressed interior space, used objects, soft practical light, and expression that suggests fatigue rather than villainy | edgy black costume, glamorized despair |
| 叛逆 / rebellious | refusal of expected order | use asymmetrical styling, confrontational stance, disrupted alignment, practical street or bedroom context, worn accessories, and controlled accent color that marks defiance without random spikes or slogans | punk costume checklist, fake graffiti |
| 纯真 / innocent | unguarded sincerity and simple desire | use open posture, clear eyes, low-detail background, daylight or gentle practical light, simple clothing construction, and one object that shows honest curiosity or routine | babyish design, creepy doll face |
| 怀旧 / nostalgic | memory shaped by period and use | choose a specific era or medium cue, soften contrast with real exposure rolloff, include worn but functional objects, keep colors slightly faded, and let composition feel remembered rather than staged | generic beige filter, fake scratches |
| 释然 / relieved | tension leaving the body | use exhale posture, loosened shoulders, wider spacing after compression, warm side light, open doorway/window cues, and object placement that implies a problem has just passed | triumphant pose, forced smile |

### Quality, Finish, And Anti-AI Taste

| Vague word | Interpret as | Concrete conversion | Avoid |
|---|---|---|---|
| 不那么AI / less AI | process evidence and fewer default artifacts | specify the actual medium or camera behavior, restrained detail hierarchy, imperfect but logical background, motivated light, natural edge variation, and no decorative filler that has no physical or story reason | glossy skin, random bokeh, ornate clutter |
| 自然 / natural | plausible cause-and-effect in pose, light, and setting | use relaxed joints, real contact shadows, uneven but coherent environment detail, ordinary material wear, available light, and small asymmetries that support the subject | sloppy composition, broken anatomy |
| 高完成度 / polished | solved design without over-rendering | use clear silhouette, finished edges where focal, simplified secondary areas, consistent light model, deliberate palette, and readable small shapes that still obey material function | micro-detail everywhere, plastic gloss |
| 耐看 / lasting appeal | quiet hierarchy that survives repeated viewing | use balanced value structure, specific but not noisy details, stable composition, subtle material variation, and one memorable focal decision instead of many competing hooks | instant gimmick, trend overload |
| 有品味 / tasteful | selective choices with cultural restraint | use fewer better objects, correct proportions, careful spacing, honest material, soft but controlled light, and avoid symbols of status unless the user explicitly asks for luxury | logo flexing, gold trim, showroom staging |
| 精致 / refined | small decisions resolved with care | use clean edges where needed, tuned spacing, believable seams, well-placed highlights, tidy but used objects, and local detail that clarifies construction rather than decorating the whole image | sterile perfection, jewelry overload |
| 扎实 / solid | structural confidence | use strong underlying shapes, grounded perspective, clear contact, weight-bearing pose, material thickness, correct shadow placement, and composition that does not rely on haze to hide weak construction | soft mush, floating objects |
| 松散 / loose | relaxed craft or layout, not careless error | use broader brush marks or open spacing, fewer hard edges, natural gesture, readable big shapes, and controlled unfinished areas that still preserve anatomy and perspective | accidental distortion, unfinished face |
| 锐利 / sharp | decisive edge and contrast hierarchy | use selected crisp contours, high-value focal contrast, angular silhouette, clean graphic accents, and a clear direction of attention while keeping non-focal areas calmer | sharpened everything, harsh skin |
| 细腻 / delicate | subtle transitions and small-scale care | use fine edge variation, low-contrast detail near the focal area, gentle texture, controlled color shifts, and precise hands/eyes/material seams without turning the whole image into lace | fuzzy blur, excessive micro-ornament |
| 粗粝 / gritty | honest roughness from material or environment | use worn surfaces, hard practical light, visible dirt or grain where motivated, lower polish, tactile edges, and social context that explains the roughness | random grunge overlay, ugly noise |
| 干练 / crisp professional | efficient visual decisions | use clean silhouette, decisive crop, limited palette, functional props, confident posture, and lighting that separates subject from background without glamour haze | corporate stock smile, sterile office |
| 松弛高级 / relaxed premium | ease plus restraint | combine natural posture, breathable spacing, quiet palette, real fabric folds, limited objects, and soft practical light; keep the scene lived-in but edited by taste | luxury logos, messy bedroom chaos |
| 低饱和 / low saturation | controlled color pressure | lower chroma while preserving value separation, keep one or two local color anchors, maintain skin/material identity, and use contrast or texture to avoid flat gray | muddy colors, dead skin |
| 干净通透 / clean clarity | air, light, and readable form | use clear value separation, pale but not blown highlights, transparent material logic, soft reflections, limited background clutter, and enough dark notes to hold structure | overexposed white, no shadows |

### Light, Color, And Atmosphere Words

| Vague word | Interpret as | Concrete conversion | Avoid |
|---|---|---|---|
| 暖 / warm | emotional warmth from source and material | use practical lamp, late sun, wood bounce, warm skin midtones, soft shadow edge, and muted cool counter-notes so warmth feels motivated | orange wash, yellow skin |
| 冷 / cold | temperature, distance, or environment pressure | use blue-gray shadow, pale daylight, hard air, reduced saturation, controlled skin color, and material cues like glass, tile, metal, or winter fabric | cyan filter over everything |
| 明亮 / bright | high key visibility with structure | raise exposure while preserving shadow anchors, use clean highlights, open composition, and accurate material response; keep subject readable without deleting edge contrast | blown whites, floating subject |
| 昏暗 / dim | low-light realism | use practical source falloff, visible noise/grain, deep but separated shadows, small highlight islands, and posture or setting that explains limited light | black mush, fake vignette |
| 逆光 / backlit | light source behind subject with readable front | use rim only where light can touch, soft front fill or bounce, controlled silhouette, exposure rolloff, and background brightness that explains the backlight | glowing outline everywhere |
| 微光 / faint glow | subtle motivated light | use small screens, candles, neon spill, moon reflection, or lamp leakage; keep glow local, let it fade with distance, and preserve surrounding darkness | fantasy aura, random particles |
| 朦胧 / hazy | air depth with retained construction | use atmospheric perspective, softened distant edges, visible near-plane sharpness, and haze that follows light direction and depth rather than covering the subject | blur filter, low-detail face |
| 清晨感 / early morning | low-contrast fresh start | use cool ambient light, low sun angle, long soft shadows, pale sky reflection, quiet routine props, and slightly sleepy posture or environment | generic sunrise orange |
| 黄昏感 / dusk mood | transition between day and night | use warm horizon or practical lights, cooler shadows, layered silhouettes, reflective surfaces, and a value structure that feels like time changing | orange-purple cliche |
| 雨后 / after rain | wet surfaces and cleaned air | use ground reflections, darker porous materials, softened sky light, water beads, slightly lifted saturation, and practical footprints or umbrellas if relevant | rain streaks everywhere |
| 夏日感 / summer | heat, daylight, and seasonal behavior | use hard sun or humid shade, brighter local color, relaxed clothing fabric, sweat or condensation only if useful, and environment cues like fans, leaves, tiles, or open windows | beach props by default |
| 冬日感 / winter | cold air and insulated behavior | use low sun, muted sky, heavy fabric, visible breath only when plausible, cool shadows, warm interior contrast, and slower posture | snow everywhere, blue skin |
| 霓虹感 / neon mood | practical colored light in darkness | use visible neon source, wet or glossy surfaces, localized color spill, dark neutral anchors, and faces partially shadowed so color has function | neon over every surface |
| 月光感 / moonlit | cool night visibility from a real sky source | use pale blue-gray top light, low saturation, dark value anchors, soft reflective edges, and warm artificial contrast only where a lamp exists | bright daytime night |
| 通透光 / luminous air | clear illuminated volume | use soft high-key exposure, translucent material, gentle reflections, light-toned background, and controlled shadow detail that keeps forms readable | washed-out edges, angelic glow |

### Composition, Framing, And Camera Words

| Vague word | Interpret as | Concrete conversion | Avoid |
|---|---|---|---|
| 大气 / grand and open | scale with breathing room | use wider framing, clear foreground-midground-background, large negative space, low or elevated viewpoint chosen for scale, and one strong subject anchor | empty panorama, tiny unreadable subject |
| 紧凑 / compact | efficient compression | use closer crop, overlapping shapes, compressed prop placement, clear priority, and controlled edges so density feels intentional and readable | cramped confusion, cut-off anatomy |
| 纵深感 / depth | spatial layering | use foreground occluder, midground subject, background scale reference, atmospheric perspective, floor or ground plane cues, and value/color separation by distance | fake blur only |
| 层次感 / layered | readable hierarchy across planes | separate planes by value, edge sharpness, scale, and overlap; assign a role to each layer and keep secondary details constructed | decoration stack, no focal path |
| 留白 / negative space | purposeful empty area | reserve calm space for gaze, text, icon safety, or emotional distance; keep the empty area textured enough to belong to the same medium | blank accident, dead corner |
| 视觉中心 / focal center | controlled first read | use contrast, edge detail, gaze direction, light island, or shape framing to make one dominant point before secondary details | multiple equal focal points |
| 动势 / motion energy | directional body or object force | use diagonal line, trailing fabric, shifted balance, motion blur only where physically plausible, and clear contact or force origin | random speed lines |
| 镜头感 / camera presence | lens-informed image | specify focal length feel, camera height, depth of field, exposure limits, crop behavior, distortion when relevant, and natural sensor noise for photos | fake cinematic filter |
| 抓拍感 / candid | unstaged moment | use imperfect timing, real gesture, partial occlusion, non-centered framing, available light, and background people or objects behaving independently | awkward broken pose |
| 海报感 / poster-like | one readable promise | use bold silhouette, simple value block, title-safe area, clear subject scale, memorable color accent, and minimal small detail | fake typography, cluttered scene |
| 封面感 / cover-worthy | iconic but usable layout | use strong face/object hook, editorial crop, negative space for text, controlled background, and high readability at thumbnail size | full narrative overload |
| 电影剧照 / film still | narrative frame from a larger scene | use blocking, motivated practical light, lens perspective, off-screen implication, environmental clues, and value hierarchy that suggests before/after action | teal-orange preset only |
| 鸟瞰 / top-down feel | readable overhead structure | use visible top planes, flattened depth, clean object relationships, and cast shadows that follow the overhead camera rather than a side-view character pose | impossible mixed perspective |
| 低机位 / low angle | power, scale, or vulnerability | use rising verticals, visible underside planes, foreground dominance, horizon below subject, and lighting that supports the chosen drama | heroic distortion by default |
| 近距离 / close-up | physical proximity and detail priority | use tighter crop, shallow depth if photo, skin/material texture, small expression changes, and background simplification without deleting context | beauty-retouch plastic |

### Material, Surface, And Object Words

| Vague word | Interpret as | Concrete conversion | Avoid |
|---|---|---|---|
| 金属感 / metallic | reflective material with thickness | use controlled highlight bands, edge wear, reflected environment color, bevels, weight, and contact shadows; distinguish brushed, polished, oxidized, or painted metal | chrome on everything |
| 玻璃感 / glassy | transparency plus reflection | use refracted edges, double highlights, background distortion through glass, dust or fingerprints if real, and correct opacity variation by thickness | invisible object, plastic shine |
| 陶瓷感 / ceramic | fired smooth material | use subtle glaze pooling, hard cool highlights, tiny imperfections, weight at the base, and contact shadow that shows thickness | mirror gloss, paper-thin edges |
| 木质感 / wood texture | grain and warm structural material | use directional grain following form, varied knots, worn edges, matte-to-satin reflection, and contact with screws, joints, or seams where relevant | flat brown fill |
| 织物感 / fabric | flexible woven material | use fold tension, seam logic, weave scale, thickness, compression at contact points, and different behavior for cotton, silk, wool, denim, or synthetic cloth | painted-on clothing |
| 皮革感 / leather | animal or synthetic hide behavior | use creases from use, edge stitching, uneven sheen, thickness, compression, and color variation near folds and corners | glossy black plastic |
| 纸感 / paper | fiber, bend, and print limits | use matte texture, slight warping, torn or folded edges, ink absorption, shadow from thickness, and scale-appropriate grain | smooth digital rectangle |
| 胶片颗粒 / film grain | analog texture tied to exposure | use midtone grain, highlight rolloff, subtle color crossover, and grain size consistent with format; keep it integrated with the image | uniform noise overlay |
| 湿润感 / wetness | liquid behavior on surfaces | use specular highlights, darkened porous material, beads or streaks following gravity, reflections on flat surfaces, and local contact marks | slime everywhere |
| 蓬松 / fluffy | volume from fibers or hair | use soft edge breakup, layered strands or pile, compress contact areas, directional light catching tips, and shadow pockets inside volume | cotton ball blob |
| 柔软 / soft material | compressible tactile response | use rounded folds, pressure marks, sag, contact flattening, low sheen, and body/object weight visibly changing the material | airbrushed smoothness |
| 坚硬 / hard material | rigid resistance | use crisp edges, stable planes, strong contact shadow, minimal deformation, and impact marks only where force is plausible | brittle shards everywhere |
| 透明材质 / transparent material | see-through object with optical rules | use refraction, reflection, edge density, internal caustic or shadow only if motivated, and background visibility changing by thickness | pure ghost overlay |
| 旧物感 / aged object | time and use evidence | use worn edges, faded labels without fake text, dust in recesses, repair marks, patina, and placement that shows the object is still functional | random dirt, broken junk |
| 手作感 / handmade | human construction marks | use slight asymmetry, tool marks, uneven but intentional edge, material thickness, stitching, brush pressure, or carved variation that serves the object | childish mistakes |

### Character, Pose, Expression, And Body Language

| Vague word | Interpret as | Concrete conversion | Avoid |
|---|---|---|---|
| 灵动 / lively grace | small active movement and responsive expression | use shifted weight, angled shoulders, loose hair or fabric motion, bright but not exaggerated eyes, and a pose that can continue into the next beat | stiff idol pose |
| 慵懒 / languid | relaxed weight and slow tempo | use supported posture, lowered shoulders, bent wrist, soft gaze, loose fabric folds, warm or dim practical light, and objects within easy reach | broken spine, sleepy cliche |
| 英气 / heroic poise | confident upright structure | use clean jaw/shoulder silhouette, steady gaze, decisive stance, functional costume, controlled wind or cape motion, and value contrast supporting authority | armor overload, masculine stereotype |
| 娇俏 / playful delicate charm | light teasing expression | use small head tilt, lifted brows or smile, quick hand gesture, airy spacing, fresh local color, and clothing/accessory details that stay age-appropriate | sexualized framing |
| 乖巧 / well-behaved sweetness | cooperative calm | use neat posture, hands placed deliberately, soft eye contact, tidy clothing, low-conflict background, and warm but restrained color | doll passivity, fake innocence |
| 病娇 / obsessive sweetness | unstable affection and control | use sweet styling with one unsettling contradiction: tight grip, too-close gaze, shadowed object, or controlled smile; keep it psychological rather than gore-heavy unless requested | gore for drama, empty anime trope |
| 破防 / emotionally shaken | composure interrupted | use interrupted gesture, wet eyes or tense mouth, uneven breathing posture, displaced object, and framing that keeps the reaction readable | exaggerated crying face |
| 压迫力 / intimidating presence | controlled dominance | use low angle or compressed space, large silhouette, shadow mass, still posture, direct gaze, and surrounding objects scaled to show presence | random monsters, black mush |
| 亲和力 / approachable | social safety | use open hands, relaxed shoulders, direct but soft gaze, accessible clothing/material, warm practical light, and environment that allows approach | customer-service stock smile |
| 专注 / focused | attention locked to task | use eye-line to object, hand-object contact, reduced background distractions, practical task light, and body lean that makes the action physically believable | blank stare, fake productivity |
| 疲惫 / tired | physical energy loss | use slumped but anatomically plausible posture, duller eye highlight, loosened clothing, practical low light, used objects, and slower composition rhythm | zombie face, ugliness only |
| 紧张 / nervous | restrained internal pressure | use small closed gestures, raised shoulders, hand grip, compressed spacing, off-center framing, and selective contrast near face or hands | chaotic action, random sweat drops |
| 自信 / confident | ease with command | use stable stance, balanced gaze, open torso, deliberate hand placement, clean silhouette, and lighting that reveals rather than flatters excessively | arrogance cliche, power pose only |
| 神秘 / mysterious | partial information with coherent clues | use occlusion, shadow, off-axis gaze, symbolic but specific object, limited palette, and a clear focal anchor that prevents confusion | random hood, smoke everywhere |
| 天真烂漫 / bright innocent energy | open joy and simple motion | use spontaneous gesture, daylight, rounded composition, natural smile, simple props with clear use, and environment that supports play or curiosity | infantilization, candy clutter |

### Environment, Background, And Lived-In Detail

| Vague word | Interpret as | Concrete conversion | Avoid |
|---|---|---|---|
| 烟火气 / everyday human warmth | visible routines and small domestic traces | use cooking steam, used cups, folded cloth, worn table edges, practical lighting, and objects placed where a real person would leave them | dirty chaos, festival cliches |
| 市井感 / street life | ordinary public activity | use functional storefronts, layered pedestrians with plausible posture, signs as shapes not fake text, weathered surfaces, and local light/shadow logic | malformed crowds, random lanterns |
| 居家感 / homey | private comfort | use soft furniture compression, personal items, warm lamps, imperfect tidiness, fabric textures, and scale cues that make the space usable | showroom catalog, messy dump |
| 工作感 / work-focused | task-driven environment | use tools in reachable order, focused lighting, ergonomic body/object relation, screens or papers with unreadable but plausible structure, and clutter grouped by function | random office props |
| 学院感 / campus mood | study life and youth routine | use books, desks, notice boards, bikes, uniforms or casual layers if relevant, daylight through windows, and social spacing that feels educational | fantasy school symbols |
| 宿舍感 / dorm life | compact shared living | use bunk beds, desks, storage, hanging clothes, wires, cups, small lamps, cramped scale anchors, and honest clutter that does not change background structure | dirty room stereotype |
| 都市感 / urban | dense built environment | use layered architecture, signage-safe shapes, traffic or window light, reflections, human scale, and vertical/horizontal rhythm that shows city function | skyline wallpaper only |
| 废土感 / post-apocalyptic | survival after breakdown | use repaired objects, dust, scarcity, improvised shelter, broken infrastructure with physical cause, and muted color broken by functional signal colors | random skulls, orange dust filter |
| 森系 / forest-like | organic enclosure and soft green life | use layered foliage, dappled light, natural material, moss or bark texture, irregular spacing, and subject behavior that belongs in the environment | green wash, fairy sparkles |
| 海边感 / seaside | salt air, horizon, and weather | use sky-water value relation, wind on fabric/hair, wet sand or concrete, practical coastal objects, and color shaped by humidity | shells everywhere, postcard sunset |
| 工业感 / industrial | machinery and raw utility | use metal beams, exposed joints, concrete, bolts, cables, safety color accents, directional hard light, and scale cues that show function | random pipes, cyberpunk glow |
| 实验室感 / laboratory | controlled testing environment | use clean surfaces, labeled shapes without fake readable text, glass/metal/plastic material contrast, task lighting, and objects arranged by procedure | sci-fi blue tubes everywhere |
| 废弃感 / abandoned | time without maintenance | use dust patterns, water stains, broken but physically plausible objects, faded color, plants only where growth makes sense, and light entering through real openings | haunted-house cliche |
| 舞台感 / staged performance | visible presentation space | use spotlight logic, audience or wing implication, strong silhouette, costume contact with body, and controlled background darkness or set design | random curtains, impossible light |
| 陈列感 / curated display | objects arranged for viewing | use aligned surfaces, label-safe space, consistent object spacing, soft display light, and material contrast that lets each item read clearly | museum emptiness, fake tiny labels |

### Style, Culture, And Medium Translation

| Vague word | Interpret as | Concrete conversion | Avoid |
|---|---|---|---|
| 新中式 / modern Chinese | contemporary structure with selected Chinese craft cues | use restrained wood/stone/paper/ink references, modern negative space, simple geometry, one cultural motif with function, and no fake calligraphy unless text is not required | dragon dumping, fake seal text |
| 宋韵 / Song-inspired elegance | quiet literati refinement | use pale mineral palette, thin elegant lines, restrained ceramics, garden or architecture cues, ample negative space, and calm posture | generic ancient costume soup |
| 唐风 / Tang-inspired richness | confident historical abundance | use fuller silhouettes, saturated but controlled color, textile weight, architectural scale, and ornament grouped by hierarchy rather than scattered everywhere | random gold, mixed dynasties |
| 水墨 / ink wash | value, water, and brush discipline | use ink density variation, reserved paper, dry/wet brush behavior, simplified forms, and asymmetrical composition with breathing room | gray photo filter, fake calligraphy |
| 工笔 / gongbi | precise line and mineral color | use fine controlled contour, flat decorative color, careful fabric/flower detail, and elegant spacing while avoiding photoreal rendering | over-rendered skin, random patterns |
| 浮世绘 / ukiyo-e | flat print design and line economy | use bold contour, limited ink colors, patterned shapes, cropped composition, paper texture, and period-appropriate graphic rhythm | fake Japanese text |
| 吉卜力感 / gentle animated film mood | hand-painted everyday wonder without copying a brand | use soft painted background, ordinary human routine, warm environmental light, expressive but simple faces, and rich but functional props | direct studio imitation, logo names |
| 新海诚感 / luminous youth drama | contemporary animated-film atmosphere | use sky reflection, rain or window light, youthful emotional distance, sharp architectural perspective, and luminous but motivated color | over-saturated clouds only |
| 复古港风 / retro Hong Kong mood | urban analog color and dense life | use tungsten/neon mix, cramped interiors or streets, film grain, signage as shapes, warm skin, and practical reflections | fake Chinese characters, neon overload |
| 欧美复古 / Western retro | chosen decade and production method | specify magazine flash, 70s film, 80s airbrush, 90s catalog, or early digital look; match clothing, color, lens, and layout to that era | generic brown filter |
| 黑白漫画 / monochrome manga | line, tone, and panel clarity | use strong black-white value, screentone logic, speed or emotion marks only where needed, clear silhouette, and panel-safe negative space | gray muddy shading |
| 像素风 / pixel art | grid-based simplification | use fixed pixel scale, limited palette, readable silhouette, tile-aware background, and no anti-aliased painterly gradients | tiny noisy detail |
| 黏土感 / clay style | tactile miniature craft | use hand-shaped forms, fingerprints, small dents, fabric or paper props, practical set lighting, and shallow set depth | smooth 3D toy render |
| 纸雕 / paper cut or paper sculpture | layered paper thickness | use cut edges, cast shadows between layers, fiber texture, limited color sheets, and visible construction depth | vector flatness, impossible curves |
| 版画感 / printmaking | ink transfer and carved shape | use limited color layers, registration offset, carved edges, paper tooth, and simplified shapes with strong value design | digital grunge overlay |

### Commercial, Product, UI, And Design Taste

| Vague word | Interpret as | Concrete conversion | Avoid |
|---|---|---|---|
| 品牌感 / branded | consistent identity system | use repeatable shapes, limited palette, clear product/name safe area, scalable mark logic, material consistency, and hierarchy that could become a campaign | random logo imitation |
| 电商感 / e-commerce ready | product clarity and trust | use clean background, accurate material, readable scale, grounded shadow, label-safe layout, and no extra props that compete with the product | fake text, overstyled scene |
| 种草感 / social commerce appeal | desirable but believable use | show product in real context, hand or environment scale, benefit clue, soft lifestyle light, and authentic imperfections that make the item approachable | influencer clutter, fake reviews |
| 杂志感 / editorial | curated narrative styling | use deliberate crop, typography-safe space, strong visual hook, fashion/product hierarchy, controlled background, and lighting that feels art-directed but not random | fake magazine text |
| 奢侈品感 / luxury goods | scarcity, material, and quiet authority | use precise spacing, premium material response, restrained highlight, deep neutral anchors, high-quality surface detail, and minimal supporting objects | gold overload, fake logos |
| 科技感 / tech-forward | functional clarity and new material logic | use clean interfaces, translucent or matte technical materials, precise lighting, modular geometry, scale cues, and interaction logic | random blue glow, meaningless HUD |
| App感 / app interface | usable product screen | use consistent components, readable hierarchy, real spacing, icon-safe labels if text is needed, and device frame logic when displayed | fake tiny UI, glossy gradients |
| 游戏感 / game-ready | interactive readability | use clear silhouette, role-readable props, camera angle that supports play, material groups, and UI/safe areas if menu or card use is implied | cinematic clutter, unreadable effects |
| 卡牌感 / trading card | collectible framed hierarchy | use central readable subject, border/safe zone, rarity cues through material or light, background depth behind subject, and empty areas for rules/title if needed | fake microtext |
| 潮玩感 / designer toy | manufacturable character object | use simplified volumes, thick edges, stable base, paint separation, material finish, and packaging or scale cue if relevant | impossible thin hair, busy costume |
| 包装感 / package design | shelf-readable object communication | use front-facing hierarchy, label-safe blanks, material thickness, realistic folds or seams, product scale, and restrained decorative system | fake legal text, cluttered mockup |
| 海报宣传感 / promo poster | message-first impact | use one promise, strong subject silhouette, large title-safe field, controlled color accent, and visual evidence of benefit or story | too many subplots, unreadable type |
| 头像感 / avatar-ready | small face recognition | use centered face or head/shoulders, strong silhouette, readable expression, high eye contrast, simple background, and no tiny props | full-body scene, busy background |
| 壁纸感 / wallpaper-ready | attractive background that stays usable | use icon-safe areas, balanced contrast, no fake text, quiet secondary detail, and composition that works behind UI without losing the focal mood | bright clutter everywhere |
| 表情包感 / sticker/emote | instant expression read | use exaggerated but clean face/action, thick outline or transparent-safe edge, limited internal detail, strong silhouette, and expression readable at small size | complex lighting, tiny text |

### Failure-Repair Words

| Vague word | Interpret as | Concrete conversion | Avoid |
|---|---|---|---|
| 更像真人 / more human | anatomy, behavior, and camera plausibility | fix joint logic, skin/fabric contact, natural asymmetry, eye focus, micro-expression, scale cues, and real lens/exposure behavior before adding detail | beauty-retouch, hyperreal pores only |
| 更像画的 / more illustrated | visible medium decisions | choose line, brush, print, cel, or paper logic; reduce photographic texture; keep stylized anatomy consistent; and show process evidence in edges, color, or texture | filter on photo |
| 别太油 / less oily | reduce glossy digital finish | lower specular highlights, use matte material response, flatter cel or brush shadows, neutral dark anchors, and fewer wet gradients on skin/hair/clothes | removing all contrast |
| 别太假 / less fake | restore physical cause | add contact, scale, perspective, material thickness, motivated light, plausible background behavior, and remove decorative elements that cannot be explained | noise-only realism |
| 别太满 / less crowded | restore hierarchy | remove or simplify secondary objects, widen spacing, reduce equal-contrast details, keep one focal path, and preserve only props that serve function or story | empty blandness |
| 别太空 / less empty | add meaningful support detail | add functional environment cues, scale anchors, surface texture, small routine objects, and background layers that explain the subject without stealing focus | clutter filling |
| 别太甜 / less sugary | reduce cute color and symbol pressure | lower saturation, remove hearts/bows unless necessary, add neutral anchors, natural expression, and tactile material detail | making it cold or mean |
| 别太暗 / less dark | lift visibility without breaking mood | raise midtones, add motivated fill, preserve shadow shapes, clarify silhouette, and keep a few dark anchors for depth | flat gray exposure |
| 别太亮 / less bright | recover value structure | lower highlight clipping, add shadow planes, keep material whites separated, reduce bloom, and preserve focal light rather than dimming everything equally | muddy underexposure |
| 别太乱 / less messy | reorganize by function | group objects by use, simplify background contrast, keep lived-in evidence, and preserve natural placement logic instead of erasing all personal detail | showroom cleanup |
| 别太网红 / less influencer-like | remove staged trend signals | use less symmetrical posing, fewer trendy props, more functional context, natural light, realistic skin/material, and less caption-ready perfection | ugly snapshot by default |
| 别太商业 / less commercial | reduce sales polish | use ordinary environment, imperfect crop, less retouching, smaller product dominance, real use evidence, and practical light | low-quality photo |
| 别太幼 / less childish | mature shape and palette | reduce oversized cute features, use calmer color, more controlled expression, better material construction, and composition with adult restraint | making it gloomy |
| 别太成熟 / less mature | soften severity | reduce sharp makeup or harsh contrast, use fresher posture, lighter fabric, more open expression, and simpler environment cues | childish costume |
| 别太二次元 / less anime | hybridize with real camera or craft cues | reduce eye size/gloss, add natural proportion, material texture, lens softness, plausible lighting, and background perspective while preserving the requested stylization | full photoreal replacement |

## Compound Fuzzy Phrase Resolver

When the user stacks several fuzzy words, do not expand each row independently. First decide which word controls the emotional goal, which controls the medium/style, which controls the composition, and which controls the failure guard. Then write one compact merged direction.

### Common Compound Intents

| User phrase | Merged intent | Prompt direction | Guard |
|---|---|---|---|
| 高级松弛生活感 | restrained everyday ease | use natural posture, precise negative space, quiet palette, real fabric folds, ordinary used objects, and warm practical light; keep details selected rather than luxurious | no luxury logos, no showroom emptiness, no messy clutter |
| 电影感氛围感故事感 | narrative atmosphere | define one before/after moment, motivated practical light, layered blocking, environmental clues, and value hierarchy that suggests a larger scene outside the frame | no random fog, no fake flare, no symbolic prop pile |
| 干净通透高级感 | clean restrained clarity | use pale but structured values, limited palette, crisp spacing, translucent or matte material behavior, soft reflections, and a few dark anchors for form | no overexposed white, no sterile void |
| 日系治愈生活感 | quiet seasonal routine | use ordinary domestic or street routine, soft daylight, tactile objects, relaxed gesture, gentle palette, and small weather/season cue | no random kana, no candy overload |
| 韩系干净精致 | soft trendy polish | use clean composition, smooth but not plastic skin/fabric, soft neutral palette, tidy styling, gentle frontal or window light, and strong face readability | no generic idol face, no over-retouching |
| 国风高级感 | specific Chinese craft restraint | choose ink, gongbi, Song-inspired, modern Chinese graphic, or architecture route; use controlled negative space, material cue, and one cultural motif with function | no fake Chinese text, no dragon dumping |
| 古风故事感 | historical narrative beat | use era-consistent costume silhouette, architecture or object clue, directed gaze/action, fabric layer logic, and a scene moment with consequence | no mixed dynasty costume soup |
| 赛博电影感 | neon noir narrative | use visible neon sources, wet reflections, dense city layers, shadowed face, practical tech objects, and camera blocking with tension | no neon everywhere, no meaningless HUD |
| 复古胶片生活感 | analog everyday memory | use era-specific props/clothing, imperfect framing, film highlight rolloff, midtone grain, used objects, and natural body behavior | no fake scratches, no beige-only filter |
| 梦幻空灵少女感 | delicate light fantasy | use pale value range, translucent layers, soft depth, airy spacing, age-appropriate styling, and subtle symbolic props | no overexposure, no sexualized framing |
| 热血史诗感 | motivated high stakes | use clear force direction, large scale reference, central silhouette, warm accent, visible effort, and readable action contact | no random flames, no fantasy clutter |
| 孤独电影感 | cinematic isolation | use single figure, wider negative space, muted color, distant sound/space cues, practical light island, and off-screen implication | no empty frame without story |
| 压迫感废土感 | heavy survival constraint | use low ceiling or looming mass, repaired objects, dust, scarcity, compressed spacing, and muted values with functional signal accents | no orange dust filter only |
| 可爱干净图标感 | small readable cute symbol | use rounded silhouette, simplified expression, centered icon geometry, limited palette, consistent stroke/fill, and transparent or simple background | no full scenic background, no tiny props |
| 潮玩高级感 | designer toy restraint | use simplified manufacturable volumes, premium material finish, stable base, limited colors, precise packaging or scale cue, and quiet display light | no impossible thin hair, no toy clutter |
| 产品科技感高级感 | credible premium technology | use functional geometry, matte/translucent technical material, precise highlight control, scale cue, label-safe layout, and restrained dark/light contrast | no blue glow everywhere, no fake UI text |
| 宿舍生活感真实感 | compact lived-in realism | use bunk/desk/storage scale anchors, wires/cups/clothes/books grouped by function, practical lamp or screen light, contact shadows, and imperfect phone-camera texture | no dirty stereotype, no background cleanup |
| 二次元真实场景融合 | anime identity inside real camera plate | lock background, match camera height/perspective/scale/light, add contact shadows and foreground occlusion, soften anime edges into noise/compression | no sticker cutout, no background repaint |
| 水彩治愈感 | gentle transparent craft | use pigment washes, paper grain, reserved highlights, soft/hard edge variation, warm routine details, and low-threat composition | no plastic gradient, no candy overload |
| 油画史诗感 | painterly scale and value | use strong value structure, large brush masses, lost-and-found edges, scale reference, and restrained dramatic light | no photo paint filter, no detail chaos |

### Resolver Recipe

Use this short decision chain when the phrase is not listed:

```yaml
compound_resolver:
  emotion_word: "sets the viewer's feeling and subject behavior"
  style_word: "sets medium, era, cultural route, or production process"
  quality_word: "sets finish level, restraint, texture, or anti-AI guard"
  space_word: "sets camera, composition, depth, and background behavior"
  repair_word: "sets what to avoid from the user's past failures"
```

Example:

```text
User phrase: "高级、松弛、真实、宿舍感".
Merged direction: restrained lived-in dorm realism. Use natural seated posture, compact bunk-desk scale anchors, quiet warm desk light, ordinary clutter grouped by function, fabric folds and contact shadows, and phone-camera softness. Avoid luxury styling, dirty chaos, showroom cleanup, sticker-like character edges, and relit background.
```

## Domain-Specific Fuzzy Word Overrides

The same fuzzy term changes meaning by domain. Apply these overrides before using the broader tables.

| Domain | If user says | Interpret as | Avoid |
|---|---|---|---|
| portrait | 高级 | restrained styling, controlled skin texture, simple wardrobe, precise negative space, quiet eye light | luxury props, over-retouch |
| room/interior | 高级 | material honesty, spatial order, good proportion, controlled clutter, practical light | hotel showroom, gold decor |
| product | 高级 | accurate material response, label-safe layout, precise shadow, restrained props, premium surface | fake logo, glossy everything |
| anime | 高级 | clean silhouette, disciplined cel shadow, controlled palette, expressive but simple face, no plastic hair | 3D gloss, over-designed costume |
| photo composite | 真实 | camera plate lock, perspective match, scale anchors, contact shadow, edge/noise integration | grain-only realism |
| fantasy landscape | 大气 | clear scale reference, readable landform, atmosphere by depth, controlled light source, foreground anchor | empty wallpaper, giant sky only |
| game asset | 干净 | role readability, silhouette, material groups, UI-safe shape, limited texture noise | bland flat model |
| UI/app | 干净 | hierarchy, spacing, accessible contrast, consistent components, readable labels if needed | empty white screen |
| packaging | 可爱 | shelf-readable mascot/shape, limited colors, clear product window, safe label area | childish clutter |
| comic panel | 电影感 | panel blocking, value contrast, eye-line/action continuity, readable speech-safe area | lens flare, fake widescreen only |
| real street photo | 氛围感 | available light, weather, street activity, layered pedestrians, realistic signage shapes | fog hiding malformed background |
| fashion | 松弛感 | natural pose, fabric drape, casual hand placement, real location, unforced expression | broken posture, messy styling |
| architecture | 未来感 | structural logic, new materials, human scale, consistent joints, purposeful light | random glowing fins |
| food | 质感 | surface moisture, crumb/fiber, steam only if hot, plate contact, color accuracy | plastic shine, fake garnish |
| jewelry | 精致 | small highlight control, metal/stone distinction, macro scale, clean setting, precise shadow | over-sparkle, fake gem fire |
| vehicle | 科技感 | aerodynamic function, panel seams, material contrast, scale, realistic reflections | blue LED lines everywhere |
| poster | 冲击力 | one bold hook, strong silhouette, title-safe contrast, simple color story | equal detail everywhere |
| wallpaper | 治愈 | calm mood, icon-safe quiet areas, gentle value spread, no text, repeat-view comfort | busy cute symbols |
| sticker | 可爱 | thick outline, simple expression, compact pose, transparent-safe silhouette | detailed scenic lighting |
| character design | 设定感 | functional silhouette, role-readable props, material rules, front/back consistency | meaningless ornaments |

## Negative Prompt Guard Bank

Use these compact guards when the user's fuzzy taste is clear but common AI failure patterns are likely. Pick two or three, never the whole bank.

```text
Avoid: generic AI gloss, plastic skin, over-sharp hair strands, random bokeh, fake cinematic flare, unreadable tiny text, meaningless symbols, decorative clutter, wrong scale, floating contact, inconsistent camera angle, relit background, oversaturated glow, muddy shadows, overexposed whites, fake film scratches, uniform noise overlay, copied brand logos, mixed cultural symbols, broken hands, stiff idol pose, empty showroom, dirty chaos, and detail everywhere without hierarchy.
```

## Quick Conversion Snippets

Use these one-sentence conversions when speed matters:

- "高级" -> Interpret as restraint, spacing, material honesty, and controlled light, not gold decoration or luxury branding.
- "氛围" -> Interpret as motivated light, air depth, weather/time cue, and layered space, not fog or blur.
- "故事" -> Interpret as a specific before/after moment with gaze, action, and consequence, not random symbolic props.
- "真实" -> Interpret as physical scale, contact, camera limits, material texture, and natural behavior, not noise or pores alone.
- "干净" -> Interpret as hierarchy, spacing, limited palette, and consistent edge control, not empty sterile space.
- "松弛" -> Interpret as natural posture, breathable composition, ordinary imperfections, and fabric/body ease, not sloppy anatomy.
- "可爱" -> Interpret as readable rounded shape, clear expression, and safe charm, not hearts and bows everywhere.
- "电影" -> Interpret as blocking, value hierarchy, practical light, lens perspective, and off-screen implication, not a color filter.
- "复古" -> Interpret as a chosen era and production process, not a beige/brown filter.
- "科技" -> Interpret as functional future material and interaction logic, not random glowing blue parts.

## Visual Function Presets

Use these presets when a fuzzy word describes what the image should *do* rather than what it should literally contain. They help convert subjective requests into a stable prompt skeleton.

### Make The Image Feel More Expensive

```text
Use fewer objects with better spacing, restrained color, believable material response, accurate shadow contact, controlled highlights, and one confident focal decision. Let the design feel selected and edited. Avoid gold decoration, fake luxury logos, symmetrical showroom staging, glossy plastic surfaces, and detail added only to signal cost.
```

### Make The Image Feel More Human

```text
Prioritize body weight, eye focus, hand-object contact, relaxed asymmetry, ordinary micro-expression, natural clothing tension, and a background that behaves independently. Keep imperfections functional and local. Avoid beauty-retouch perfection, identical facial symmetry, empty polished skin, stiff posing, and adding pores or grain as the only realism cue.
```

### Make The Image Feel More Designed

```text
Define a simple hierarchy: one focal object, one supporting shape family, one accent color, and one material contrast. Align spacing, repeat proportions, simplify secondary details, and keep every decorative element tied to a role. Avoid random ornaments, equal emphasis everywhere, fake text, and stylistic references that fight each other.
```

### Make The Image Feel More Atmospheric

```text
Build atmosphere from light direction, air depth, weather or time cue, value falloff, and layered foreground/midground/background. Keep the subject constructed and readable through the atmosphere. Avoid fog covering weak drawing, random bokeh, global blur, color haze with no source, and glow that ignores objects.
```

### Make The Image Feel More Story-Driven

```text
Choose a specific moment with a visible before or after: interrupted action, object consequence, directed gaze, changed posture, environmental clue, or a relationship between two scene elements. Avoid symbolic prop piles, generic sad beauty shots, unexplained dramatic lighting, and details that do not change the viewer's understanding of the moment.
```

### Make The Image Feel More Believable As A Photo

```text
Use one camera height, one lens behavior, exposure limits, natural depth of field, contact shadows, material scale, imperfect framing, and background details that retain function. Avoid HDR clarity on every plane, fake lens flare, impossible perspective, relit backgrounds, floating objects, and uniform noise pasted over clean rendering.
```

### Make The Image Feel More Like A Finished Illustration

```text
Select one production logic: cel, ink, watercolor, oil, gouache, print, vector, pixel, or clay. Let line, color, texture, edges, and shadow all obey that medium. Finish focal areas with confidence and simplify secondary areas intentionally. Avoid photo filters, inconsistent rendering layers, over-detailed backgrounds, and shiny AI gradients.
```

### Make The Image Feel More Useful For A Product Or Brand

```text
Clarify product scale, material, benefit, label-safe space, shadow grounding, and shelf or screen readability. Use props only when they explain use or audience. Keep the crop and background compatible with later text or UI. Avoid fake microtext, copied logos, overstyled lifestyle clutter, impossible reflections, and props that compete with the product.
```

### Make The Image Feel More Natural In A Real Room

```text
Read the room as a camera plate: floor plane, desk or furniture height, local light sources, clutter grouped by use, fabric compression, object contact, foreground occlusion, and phone-camera softness. Preserve existing background structure when editing. Avoid cleaning the room into a showroom, changing furniture placement, inconsistent scale, and character layers that look pasted on.
```

### Make The Image Feel More Iconic

```text
Reduce the idea to a dominant silhouette, strong value separation, memorable shape rhythm, clear negative space, and one color or material accent. Make it readable at thumbnail size before adding detail. Avoid tiny story props, multiple equal focal points, fake title text, complex background action, and decorative detail that weakens the first read.
```

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
