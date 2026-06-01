# Fast Path

Use this for most requests that need lower AI feel but do not need deep style research.

## 10-Second Route

```text
Ordinary generation only -> use imagegen skill/tool, stop.
Explicit lower-AI/refinement request -> use this fast path.
Existing image critique/edit -> identify 1-3 visible failures, then write edit prompt.
Ambiguous format word -> preserve format first, then style.
Extra/unwanted object or prompt-image mismatch -> use inconsistency cleanup.
```

## Minimal Intent Parse

Silently fill:

```yaml
format: "<hard format>"
subject: "<subject>"
style: "<one base medium>"
mood: "<one modifier>"
fix: "<top anti-AI problem>"
preserve: "<what must not change>"
```

## Compact Prompt Skeleton

Keep this under 120 words unless the user asks for detail:

```text
Create/Edit a [format], [aspect ratio].
Subject: [subject + action].
Style: [one medium/process with 2-3 concrete cues].
Scene: [specific setting or use case].
Light/color: [one motivated light or value model].
Physical logic: [pose/contact/material/scale constraint].
Avoid: [top 3 style-specific AI failure modes].
```

## Common Fast Translations

降低AI感:

```text
Use concrete medium/process evidence, believable contact shadows, natural material texture, and restrained detail. Avoid glossy AI finish, over-symmetry, and impossible anatomy.
```

更像手绘:

```text
controlled line weight, visible paper or paint behavior, simplified hand-made shapes, slight edge irregularity, no smooth AI gradients
```

动漫但不AI:

```text
clean animation contours, flat local colors, hard-edged cel shadows, painted background feel, no glossy 3D hair or random rim light
```

真实自然:

```text
motivated light source, lens/exposure limits, natural contact shadows, believable pose, real material texture
```

高级感:

```text
restrained palette, precise spacing, credible material texture, few objects, controlled reflections, no fake logo/text
```

故事感:

```text
specific story moment, environmental clues, character gaze/gesture with intent, one foreground detail tied to memory or conflict
```

动作自然:

```text
natural joint range, clear weight support, grounded hand/foot contact, clothing and hair following gravity
```

构图更好:

```text
Choose one focal anchor, one composition architecture, one viewer path, and one safe area. Concentrate detail at the focal point, simplify secondary areas, and make the crop match the output format.
```

去不合理元素:

```text
Compare against the original prompt, remove unrequested extra props, preserve required identity/outfit/layout, align expression with action, align viewpoint with environment, and do not add replacement clutter.
```

四格漫画:

```text
four clearly separated panels in reading order, consistent character design, setup-development-turn-payoff rhythm, blank speech bubbles unless exact text is provided
```

游戏开始页:

```text
preserve title/logo and readable buttons, background implies story/world, UI contrast and spacing remain clear
```

## Fast Failure Patch

If user says:

- too glossy -> matte/flat/medium-specific finish, restrained highlights
- too fake -> one light source, scale cues, contact shadows, shared perspective
- too busy -> one focal point, simplify secondary areas
- bad hands -> natural finger grouping, thumb placement, wrist angle, object contact
- pose weird -> body line, support point, joint range, gravity
- bad composition -> focal anchor, viewer path, output-safe crop, controlled negative space
- extra prop -> remove unrequested object, preserve required props only
- expression mismatch -> align face/gaze with action and mood
- viewpoint mismatch -> unify camera height, floor plane, horizon, light direction
- text bad -> no invented text; blank safe area

## Stop Conditions

Do not load deeper references when:

- the request has one obvious style and one obvious fix
- a compact prompt is enough
- the user wants fast generation
- the next step is simply to call imagegen

Load a deeper reference only when the fast path cannot decide the style, format, or failure mode.
