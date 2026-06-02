# Intent And Fuzzy Language

Use this before choosing style details when the user request is incomplete, vague, or mixes format, mood, style, and quality words.

For deeper taste-word mapping, stacked fuzzy words, or user-specific wording, load `fuzzy-word-precision-library.md` after this file. Keep this file as the intent and format lock layer.

## Core Rule

First identify what the user is really specifying:

1. **Format**: what the output must structurally be.
2. **Use case**: where it will be used.
3. **Subject/story**: what appears and what happens.
4. **Style/medium**: how it is rendered.
5. **Mood/taste**: how it should feel.
6. **Constraints**: what must be preserved or avoided.

Format beats style. If the user says "four-panel comic," "logo," "icon," "poster," "character sheet," "game UI," "storyboard," or "packaging," do not change that format while chasing a different look.

## Minimum Intent Check

Before generating or rewriting, silently fill this:

```yaml
intent_parse:
  format: "<hard output structure>"
  use_case: "<where it will be used>"
  subject: "<main subject>"
  action_or_story: "<what happens>"
  style_medium: "<rendering family>"
  mood_words: ["<ambiguous taste words>"]
  hard_constraints: ["<must preserve / must avoid>"]
  unknowns: ["<only ask if risky>"]
```

Ask at most one clarification question only when:

- the format is unclear and wrong format would waste the result
- the subject is missing
- a named person/brand/copyright-sensitive reference is central
- two hard constraints conflict

Otherwise infer conservatively and proceed.

## Format Terms Are Hard Constraints

### Four-Panel Comic / 4-Koma / 四格漫画

Meaning:

- four sequential panels
- clear reading order
- simple story beat progression
- setup, development, turn, punchline or emotional payoff

Prompt conversion:

```text
Create a four-panel comic page with four clearly separated panels in reading order. Keep a consistent character design across panels. Each panel shows one story beat: setup, development, turn, payoff. Use [chosen style] only as the rendering treatment; do not collapse the image into a single poster or splash illustration. Leave speech bubbles blank unless exact dialogue is provided.
```

Avoid:

```text
single cinematic scene, random collage, fake unreadable dialogue, changing character design between panels
```

### Manga Page

Meaning:

- panel layout, black-and-white or limited color
- sequential reading flow
- dialogue/caption space

Prompt conversion:

```text
Create a manga page with clear panel gutters, readable sequence flow, consistent characters, ink linework, screentone or black fill discipline, and blank dialogue balloon space unless exact text is provided.
```

### Storyboard

Meaning:

- rough sequential planning frames
- camera/action notes, not polished final art

Prompt conversion:

```text
Create a storyboard sheet with multiple simple frames, clear camera staging, action continuity, rough production drawing feel, and no final-render polish.
```

### Character Sheet

Meaning:

- design reference, not action poster
- front/side/back or expression/pose variants

Prompt conversion:

```text
Create a character design sheet on a neutral background with consistent proportions, front/side/back or selected pose views, readable silhouette, material notes or blank callout space, and no dramatic background.
```

### Game Start Screen / Main Menu

Meaning:

- usable interface plus mood image
- readable buttons
- title/logo area
- background supports story

Prompt conversion:

```text
Create a game main menu screen. Preserve title/logo and readable button hierarchy. Use the background to imply story and worldbuilding, but keep UI contrast, spacing, and click targets clear.
```

### Poster

Meaning:

- one visual hook
- title-safe space
- hierarchy for text

Prompt conversion:

```text
Create a poster composition with one clear visual hook, strong silhouette, title-safe blank area, limited palette, and print-friendly hierarchy. Do not invent small text.
```

### Logo / Icon

Meaning:

- simple symbol, scalable, not an illustration scene

Prompt conversion:

```text
Create a simple scalable mark/icon with strong silhouette, limited colors, consistent geometry, no tiny details, and no fake text.
```

### Sticker / Emoji

Meaning:

- readable at small size
- expression first

Prompt conversion:

```text
Create a sticker-style character image with a strong silhouette, thick outline, readable expression, limited internal detail, and a transparent or clean background.
```

### Product Image / Mockup

Meaning:

- product clarity and material truth first

Prompt conversion:

```text
Create a product mockup with clear product shape, true material behavior, scale cue, grounded contact shadow, label-safe areas, and no fake claims or invented brand text.
```

## Format Lock Table

Use this table before style selection.

| User says | Lock as | Never silently turn into |
|---|---|---|
| 四格漫画 / four-panel comic | 4 sequential panels | single poster, single illustration |
| 漫画分镜 / storyboard | sequential rough frames | polished splash art |
| 漫画页 / manga page | panel layout | standalone character art |
| 表情包 / sticker / emoji | small readable expression asset | full background scene |
| 头像 / avatar | readable head/upper-body identity | complex poster |
| 壁纸 / wallpaper | screen-safe composition | text-heavy poster |
| 海报 / poster | single visual hook plus text-safe area | UI screen |
| LOGO / logo | scalable identity mark | detailed illustration |
| 图标 / icon | small symbol | scenic art |
| UI / game menu | usable interface hierarchy | background-only concept art |
| 角色设定 / character sheet | design reference views | action key art |
| 产品图 / product image | product clarity | lifestyle poster hiding product |
| 包装 / packaging | print/label-safe design | fake ad scene |
| 地图 / map | navigable/cartographic logic | landscape painting only |

If the user provides both a locked format and a style, apply the style inside the format.

Example:

```text
"四格漫画，新海诚感" -> four-panel comic structure remains mandatory; luminous sky/rain-reflection mood can affect backgrounds, light, and emotion inside each panel.
```

Bad:

```text
Convert the request into one wide cinematic anime poster.
```

Good:

```text
Create a four-panel comic page. Each panel uses luminous post-rain light, reflective surfaces, and emotional teenage-drama framing, but the four-panel structure and reading order remain clear.
```

## Fuzzy Taste Word Translator

Translate fuzzy words into visual decisions. Use only the relevant rows.

If the user's vague term is not listed here, or if several fuzzy words need to be merged into one stable direction, use `fuzzy-word-precision-library.md`.

### 高级感 / Premium / Sophisticated

Means:

- restraint
- spacing
- material credibility
- less decoration
- fewer colors

Use:

```text
precise negative space, restrained palette, credible material texture, quiet lighting, few objects, controlled reflections, no fake luxury logo
```

Avoid:

```text
gold everywhere, glossy everything, empty white void, fake brand text, random serif typography
```

### 氛围感 / Atmospheric

Means:

- mood from light, air, depth, weather, color, and silence

Use:

```text
motivated light source, visible air depth, foreground/midground/background layering, soft weather cue, restrained color temperature, quiet negative space
```

Avoid:

```text
fog hiding weak composition, random bokeh, overexposed glow, no subject story
```

### 故事感 / Story-Rich

Means:

- the image implies before/after
- props and environment suggest a narrative

Use:

```text
specific story moment, evidence of what just happened, environmental clues, character gaze or gesture with intent, foreground object that hints at conflict or memory
```

Avoid:

```text
generic pose, empty beautiful background, random symbolic props, no action direction
```

### 治愈 / Healing / Comforting

Means:

- safety, warmth, soft routine, gentle light

Use:

```text
warm practical light, soft tactile surfaces, small domestic details, relaxed posture, low-stakes moment, rounded shapes, quiet palette
```

Avoid:

```text
over-sweet candy colors, clutter, intense contrast, uncanny smiles
```

### 可爱 / Cute

Means:

- simplified shapes, readable expression, safe silhouette

Use:

```text
rounded shape language, clear expression, soft palette, simplified detail, small gesture, strong silhouette
```

Avoid:

```text
creepy doll eyes, over-detailed skin, adult glamour pose, random hearts/bows
```

### 日系 / Japanese-Style

This is too broad. Infer based on context:

- anime/cel if characters
- clean lifestyle photo if real scenes
- minimal product/design if brand/UI
- quiet seasonal mood if illustration

Use:

```text
seasonal cue, clean composition, restrained palette, everyday object detail, quiet emotional tone
```

For anime:

```text
clean animation linework, flat cel colors, hand-painted background feel, readable key pose
```

Avoid:

```text
random kanji/kana, shrine/torii motifs without reason, generic anime gloss, cultural symbol dumping
```

### 新海诚感 / Luminous Contemporary Japanese Animated Film Mood

Do not copy a living director's style directly. Translate to broad traits:

```text
luminous sky, rain-reflection atmosphere, emotional teenage-drama framing, warm rim light, distant train or city detail when story-relevant, transparent air, hand-painted background feel
```

Avoid:

```text
direct named-style claim, overblown clouds everywhere, random lens flare, empty beauty shot with no story
```

### 电影感 / Cinematic

Means:

- narrative frame, lighting motivation, value hierarchy

Use:

```text
story moment, motivated practical light, layered foreground/midground/background, controlled lens perspective, restrained palette
```

Avoid:

```text
orange-teal by default, fake anamorphic flare, fog hiding weak composition
```

### 真实 / Realistic

Means:

- plausible light, material, scale, anatomy, and camera

Use:

```text
motivated light source, natural contact shadows, real material texture, scale cues, lens/exposure limits, believable anatomy
```

Avoid:

```text
HDR clarity, perfect skin, impossible reflection, floating props
```

### 手绘感 / Hand-Drawn

Means:

- visible human mark-making and medium constraints

Use:

```text
controlled line weight, paper grain, brush or pencil pressure, simplified human-made shapes, slight edge irregularity, medium-specific texture
```

Avoid:

```text
smooth AI gradients, fake texture overlay only, glossy 3D rendering
```

### 复古 / Retro

Needs era and medium. If unknown, choose one:

- retro anime cel
- vintage travel poster
- analog photo
- Y2K screen
- mid-century illustration

Use:

```text
era-specific palette, production process, typography-safe space, material aging only where appropriate
```

Avoid:

```text
generic beige filter, random noise, fake old text, mixing every decade
```

### 干净 / Clean

Means:

- hierarchy, controlled detail, consistent spacing

Use:

```text
clear focal hierarchy, consistent spacing, limited palette, simplified secondary surfaces, crisp edges where needed
```

Avoid:

```text
empty sterile scene, no texture, generic corporate vector people
```

### 酷 / Cool

Could mean attitude, color, fashion, tech, or darkness. Infer from subject.

Use:

```text
confident pose, sharper silhouette, controlled contrast, cooler palette or bold accent, fewer cute details
```

Avoid:

```text
random sunglasses, black leather default, neon everywhere, expressionless generic model
```

### 梦幻 / Dreamy

Means:

- soft unreality, gentle transitions, memory-like mood

Use:

```text
soft value transitions, gentle haze with depth, pastel or muted palette, symbolic but sparse props, softened background
```

Avoid:

```text
random sparkles, over-blur, no subject clarity, fantasy clutter
```

### 赛博 / Cyberpunk

Means:

- neon noir urban technology, density, social grit

Use:

```text
wet reflective surfaces, practical neon sources, dense urban layering, shadowed faces, signage-safe abstract light blocks
```

Avoid:

```text
neon everywhere, fake unreadable signage, purple-blue soup, random holograms
```

### 国风 / Chinese-Inspired

Too broad. Ask or infer medium:

- ink wash
- gongbi
- folk print
- costume fantasy
- modern Chinese design

Use:

```text
specific medium/process, regional or historical restraint if known, material texture, blank calligraphy-safe area only if exact text is provided
```

Avoid:

```text
fake Chinese characters, random dragons, generic ornament mix, sacred/cultural symbol dumping
```

### 二次元 / Anime-Style

Means:

- anime/manga character treatment, not automatically glossy AI.

Use:

```text
clean animation contour, flat local colors, controlled cel shadows, readable silhouette, character/background layer distinction
```

Avoid:

```text
generic same-face anime, glossy 3D hair, over-detailed eyes, random rim light
```

### 质感 / Texture Quality

Usually means material credibility, not more detail everywhere.

Use:

```text
material-specific surface behavior, thickness, edge wear, contact marks, light response, tactile variation at focal areas
```

Avoid:

```text
random noise overlay, glossy everything, micro-detail everywhere
```

### 赛璐璐 / Cel Look

Means:

- flat color and animation shadow logic

Use:

```text
flat local color, clean animation contour, hard-edged shadow blocks, simple highlight shapes, character cel layer over painted background
```

Avoid:

```text
soft airbrush gradients, 3D hair specular, photographic bokeh, random rim lights
```

### 厚涂 / Painterly Thick Digital Painting

Often means visible brush mass and value shaping, not random texture.

Use:

```text
broad brush masses, value grouping, visible stroke direction, color temperature shifts, softened lost edges, focal impasto-like accents
```

Avoid:

```text
uniform AI brush filter, muddy overblending, hard photo detail everywhere
```

### 扁平 / Flat Graphic

Means:

- simplified shape and color hierarchy

Use:

```text
flat color planes, simple geometric shapes, consistent stroke, limited palette, clean hierarchy, no realistic lighting
```

Avoid:

```text
random gradients, fake 3D shadows, texture clutter, inconsistent icon style
```

### Q版 / Chibi

Means:

- exaggerated cute proportion and small-size readability

Use:

```text
large head-to-body ratio, rounded silhouette, simplified limbs, readable expression, thick clean outline, limited detail
```

Avoid:

```text
adult glamour pose, realistic anatomy, creepy doll eyes, tiny costume micro-detail
```

### 氛围光 / Atmospheric Light

Means:

- light that shapes mood and space

Use:

```text
motivated light source, visible air depth, soft bounce light, color temperature contrast, readable shadow falloff
```

Avoid:

```text
random glow, bloom everywhere, unmotivated rim lights, overexposed subject
```

### 史诗感 / Epic

Means:

- scale, stakes, and visual hierarchy

Use:

```text
large scale reference, low or wide viewpoint, layered depth, clear central silhouette, environmental stakes, restrained dramatic light
```

Avoid:

```text
tiny subject lost in detail, random lightning, fantasy clutter, no story stakes
```

### 少女感 / Girlish Softness

Could mean youthful delicacy, gentle color, or romantic detail. Keep it non-sexualized.

Use:

```text
soft palette, delicate fabric or accessory detail, gentle expression, light airy spacing, youthful but age-appropriate styling
```

Avoid:

```text
sexualized framing, exaggerated body focus, random lace overload, doll-like plastic skin
```

### 少年感 / Youthful Boyish Energy

Means:

- fresh, direct, active, less polished

Use:

```text
casual posture, wind or motion cue, clean sporty silhouette, natural expression, bright but not glossy palette
```

Avoid:

```text
over-muscled heroic pose, generic idol face, stiff fashion-model styling
```

### 末世感 / Post-Apocalyptic

Means:

- survival, decay, scarcity, altered environment

Use:

```text
functional worn materials, repaired objects, dust and weathering where contact explains it, sparse resources, environmental damage with cause
```

Avoid:

```text
random rubble, spikes everywhere, orange dust filter, unreadable destruction clutter
```

### 胶片感 / Film Look

Means:

- analog color and exposure behavior

Use:

```text
film-like highlight rolloff, natural grain, muted color crossover, slight halation, print contrast, small focus or exposure imperfection
```

Avoid:

```text
heavy fake scratches, uniform digital noise, HDR clarity, crushed blacks
```

### 蒸汽波 / Vaporwave

Means:

- synthetic retro nostalgia

Use:

```text
pastel magenta-cyan palette, retro computer or classical motif if relevant, grid horizon, sunset disk, intentionally artificial nostalgia
```

Avoid:

```text
random Japanese text, purple-blue soup, too many memes, unreadable chrome text
```

### Y2K

Means:

- early digital gloss, translucent tech, playful futurism

Use:

```text
chrome bubbles, translucent plastic, candy colors, early digital shine, rounded interface forms, sparse starburst accents
```

Avoid:

```text
modern app gradient, everything reflective, cluttered decorations, fake tiny UI text
```

### 美式漫画 / American Comic

Means:

- bold ink, graphic action, halftone/screenprint options

Use:

```text
bold ink outlines, strong black fills, dynamic panel composition, flat color separations, halftone or screenprint texture if desired
```

Avoid:

```text
muddy painterly gradients, random comic dots, fake speech text, anatomy hidden by effects
```

### 韩漫 / Manhwa / Webtoon

Means:

- vertical-scroll comic rendering

Use:

```text
vertical composition, clean character rendering, readable facial acting, simplified backgrounds, speech-safe negative space, selective gradients
```

Avoid:

```text
fake dialogue, over-rendered hair shine, same-face characters, cluttered panels
```

### 乙女 / Otome Romance

Means:

- romance game framing, character appeal, emotional tension

Use:

```text
romance visual-novel composition, expressive gaze, elegant costume details, soft emotional lighting, UI-safe negative space, restrained sparkle accents
```

Avoid:

```text
over-sexualized pose, generic handsome face, random roses, fake dialogue text
```

### Galgame / Visual Novel

Means:

- character-forward screen with UI readability

Use:

```text
visual novel layout, character layer separated from readable background, menu-safe negative space, title/logo hierarchy, emotional setting detail
```

Avoid:

```text
single poster crop that hides UI, busy background behind buttons, fake menu text, inconsistent character scale
```

### Logo感 / Brand Mark Feel

Means:

- simplified, recognizable, scalable identity

Use:

```text
simple silhouette, clear geometry, limited colors, scalable mark, strong negative space, no detailed scene
```

Avoid:

```text
illustration scene, fake text, tiny ornament, gradients unless brand style requires them
```

### 图标感 / Icon Feel

Means:

- small-size readability and consistent UI shape

Use:

```text
simple centered symbol, limited palette, consistent stroke or fill, readable at small size, transparent or simple background
```

Avoid:

```text
complex lighting, tiny details, fake text, perspective-heavy scene
```

### 设定感 / Concept Design Feel

Means:

- world rules and functional design are visible

Use:

```text
functional silhouette, material logic, scale cue, design purpose, callout-safe blank areas, consistent worldbuilding details
```

Avoid:

```text
random ornaments, meaningless glowing parts, no function, unreadable kitbash
```

### 张力 / Tension

Means:

- visual or narrative pressure

Use:

```text
asymmetrical composition, compressed spacing, directional gaze, opposing forces, diagonal body line, selective high contrast
```

Avoid:

```text
random action effects, clutter, stiff pose, no focal conflict
```

### 松弛感 / Effortless Relaxed Feel

Means:

- natural ease, not messy carelessness

Use:

```text
relaxed posture, breathable spacing, casual clothing folds, soft light, imperfect but intentional object placement
```

Avoid:

```text
sloppy anatomy, clutter, blankness, stock-photo smile
```

### 生命力 / Lively Vitality

Means:

- energy from gesture, color, growth, or rhythm

Use:

```text
active gesture, rhythmic shapes, fresh color accents, organic growth cues, light movement, expressive silhouette
```

Avoid:

```text
random particles, oversaturation, chaotic motion lines, no structure
```

### 空灵 / Ethereal

Means:

- lightness, transparency, quiet otherworldliness

Use:

```text
light value range, translucent layers, soft atmospheric depth, sparse composition, delicate edges, quiet color
```

Avoid:

```text
overexposure, random sparkles, no focal point, fog hiding everything
```

### 压迫感 / Oppressive

Means:

- scale, low ceiling, darkness, crowding, or power imbalance

Use:

```text
low viewpoint, heavy overhead forms, compressed negative space, strong value mass, looming scale reference
```

Avoid:

```text
black mush, random horror props, unreadable silhouette
```

### 透明感 / Transparency / Clarity

Means:

- clean light, airy color, reflective or translucent material

Use:

```text
clear light source, pale but controlled palette, translucent material behavior, soft reflection, breathable composition
```

Avoid:

```text
washed-out whites, no contrast, plastic glass, random glow
```

### 颗粒感 / Grain

Means:

- medium-specific grain, not noise everywhere

Use:

```text
film grain in midtones, paper tooth, risograph ink grain, charcoal/pastel powder, or sensor grain depending on medium
```

Avoid:

```text
uniform digital noise overlay, dirt hiding details, fake vintage scratches by default
```

## Ambiguity Decision Tree

If the word sounds like:

- **a container**: four-panel comic, poster, UI, icon -> treat as format.
- **a destination**: wallpaper, avatar, cover, ad -> treat as use case.
- **a medium**: watercolor, pixel, cel, photo -> treat as style base.
- **a feeling**: cozy, premium, atmospheric -> treat as mood modifier.
- **a quality complaint**: too fake, too AI, too glossy -> use `failure-feedback-fixes.md`.
- **a named style/person**: translate into broad traits and avoid direct living-artist copying.

## User Purpose Detection

When the user says "make it better," infer likely purpose from artifact:

- game menu -> improve story world, UI readability, title hierarchy
- character image -> improve identity, pose, anatomy, expression, style consistency
- product image -> improve material, scale, clarity, label safety
- poster -> improve hierarchy, hook, print logic, text-safe space
- comic -> improve panel sequence, character consistency, speech/caption space
- wallpaper -> improve composition safe areas and atmosphere

## Prompt Rewrite Pattern

```text
User said: "<original fuzzy request>"
Interpreted as:
- Format: <hard structure>
- Use case: <destination>
- Style base: <medium/rendering>
- Mood: <translated visual mood>
- Constraints: <preserve/avoid>

Prompt:
Create a <format>, <aspect ratio>.
Subject/story: <specific subject and story beat>.
Style base: <medium-specific process cues>.
Mood translation: <light/color/texture/composition cues>.
Use-case constraints: <readability/safe areas/panel layout/UI hierarchy>.
Anti-AI constraints: <style-specific failure modes>.
```

## Examples

### User: "生成四格漫画风格"

Bad interpretation:

```text
Make a cute anime illustration.
```

Good interpretation:

```text
Create a four-panel comic page with four clearly separated panels in reading order. Use a clean manga/comic rendering style, consistent character design across all panels, and a setup-development-turn-payoff story rhythm. Leave dialogue bubbles blank unless exact text is provided. Avoid collapsing it into one poster image.
```

### User: "更有故事感"

Good conversion:

```text
Add environmental clues that imply before and after: a left-behind object, character gaze toward something off-frame, weather or light suggesting time has passed, and one foreground detail tied to the conflict or memory.
```

### User: "高级一点"

Good conversion:

```text
Reduce decorative noise, use precise negative space, restrained palette, credible material texture, controlled light, fewer objects, and no fake brand/text.
```

### User: "日系治愈"

Good conversion:

```text
Quiet seasonal everyday scene, warm practical light, soft tactile surfaces, restrained palette, small domestic or street detail, relaxed posture, clean composition, no random cultural symbols or fake Japanese text.
```

### User: "像新海诚"

Good conversion:

```text
Use broad contemporary Japanese animated-film traits: luminous sky, transparent post-rain air, reflective surfaces, emotional teenage-drama framing, warm sunlight, distant train/city detail if story-relevant, hand-painted background feel. Do not claim direct named-style imitation.
```
