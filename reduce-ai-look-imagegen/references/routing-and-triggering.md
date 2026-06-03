# Routing And Triggering

Use this reference before applying the skill when routing an image generation or image editing request.

## Core Rule

Use `reduce-ai-look-imagegen` for every image generation request as a lightweight preflight before calling imagegen. The skill is not only an anti-AI filter; it is the default image prompt quality controller.

It should preserve and improve:

- user intent, hard format, subject, aspect ratio, required props, and requested style
- composition, framing, focal hierarchy, and output safe areas
- perspective, horizon, vanishing system, scale anchors, ground/floor plane, contact, and occlusion
- pose, hands, anatomy, action clarity, object interaction, and material behavior
- background, secondary figures, props, architecture, signage, and non-focus details
- style choice, style translation, fuzzy wording, and token efficiency
- lower-AI polish control when relevant

## Two Use Levels

### Level 1: Universal Lightweight Preflight

Use this for ordinary image generation when the user simply says things like:

- 帮我生成一张图
- 画一个角色
- 做一张海报
- 生成头像
- 出一张壁纸
- 画四格漫画
- 做游戏开始页

Minimal preflight should:

- preserve the requested format, subject, aspect ratio, style, and required props
- add perspective/ground-plane/contact/scale logic when visible space exists
- add background/scene integrity when non-focus details are visible
- repair only the strongest vague taste words
- avoid adding unrelated story symbols, props, logos, or text
- keep explanation short or silent when the user only wants an image

### Level 2: Focused Quality Pass

Use a deeper focused pass when the user says or implies:

- 降低AI感, 去AI味, 不要像AI
- 更自然, 更像真实拍摄, 更像手绘
- 修动作, 修手, 修人体, 姿势怪
- 透视错误, 空间歪, 比例不对, 地面漂浮
- 背景假, 道具假, 招牌假, 人物像贴上去
- 风格不对, 不高级, 太油, 太假, 太塑料, 太3D
- 二次元人物融入现实, 动漫人物进现实, 角色进屏幕, 手机屏幕, 显示器, AR角色
- 帮我优化提示词, 帮我诊断这张图, 把模糊词转换成真正提示词

Also use it when the user provides an existing image and asks for critique, refinement, style correction, edit instructions, or a better prompt.

## Routing Decision

Use this quick decision:

```text
Does the user primarily want image creation or image editing?
  Yes -> Use reduce-ai-look-imagegen as preflight.
    If the request is ordinary -> load auto-anti-ai-expansion only, then generate/edit.
    If quality risk is explicit -> load the focused reference selected by SKILL.md or INDEX.md.
  No -> If they ask for prompt/style/quality analysis, use reduce-ai-look-imagegen.
```

## Combined Use

For image generation:

1. Use `reduce-ai-look-imagegen` to parse intent and build a stronger compact prompt.
2. Use `plus-imagegen`, `imagegen`, or the host-native image tool to generate the image.

This applies to all image generation requests, but the preflight should stay compact for ordinary requests.

## Examples

User:

```text
帮我生成一张水彩猫咪头像
```

Route:

```text
Ordinary image generation. Use reduce-ai-look-imagegen as a minimal preflight to preserve watercolor medium and avatar format, add contact/material logic if relevant, then call imagegen.
```

User:

```text
帮我生成一张水彩猫咪头像，但不要AI味，要像真的手绘
```

Route:

```text
Use reduce-ai-look-imagegen to translate "真的手绘" into watercolor process cues, then generate with imagegen.
```

User:

```text
生成四格漫画风格
```

Route:

```text
Ordinary generation with a hard format constraint. Use reduce-ai-look-imagegen as preflight to preserve four panels and reading order, then call imagegen.
```

User:

```text
生成四格漫画风格，但是别变成单张AI插画，动作要自然
```

Route:

```text
Use reduce-ai-look-imagegen because the user explicitly asks for format preservation and natural action correction, then generate with imagegen.
```

User:

```text
生成一个动漫少女从电脑屏幕里伸出来，现实桌面照片感
```

Route:

```text
Use reduce-ai-look-imagegen plus anime-character-real-scene-integration.md before imagegen. Lock screen plane, bezel occlusion, glass reflection, scale anchors, light direction, screen glow, contact shadow, edge softness, and camera grain.
```

User:

```text
这张图太像AI了，帮我改一个
```

Route:

```text
Use reduce-ai-look-imagegen directly with failure-feedback-fixes.md.
```
