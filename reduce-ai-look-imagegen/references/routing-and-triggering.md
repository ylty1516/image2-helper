# Routing And Triggering

Use this reference before applying the skill when routing an image generation or image editing request.

## Two Use Levels

### Level 1: Universal Image Preflight

Use `reduce-ai-look-imagegen` for every image generation request as a lightweight preflight before calling imagegen.

Minimal preflight should:

- preserve the requested format, subject, aspect ratio, style, and required props
- add perspective/ground-plane/contact/scale logic when visible space exists
- add background/scene integrity when non-focus details are visible
- repair only the strongest vague taste words
- keep explanation short or silent when the user only wants an image

### Level 2: Explicit Anti-AI / Refinement

Use a deeper `reduce-ai-look-imagegen` pass when the user says or implies:

- 降低AI感
- 去AI味
- 不要像AI
- 更自然
- 更像真实拍摄
- 更像手绘
- 修动作
- 修手
- 姿势怪
- 人体不合理
- 太油
- 太假
- 太塑料
- 太3D
- 不高级
- 风格不对
- 这个图哪里怪
- 帮我优化提示词
- 帮我诊断这张图
- 按某个风格但不要AI味
- 把模糊词转换成真正提示词

Also use it when the user provides an existing image and asks for critique, refinement, style correction, or a better edit prompt.

## Ordinary Image Generation

If the user only asks for a new image, such as:

- 帮我生成一张图
- 画一个角色
- 做一张海报
- 生成头像
- 出一张壁纸
- 画四格漫画
- 做游戏开始页

and does not ask for anti-AI reduction, quality diagnosis, style correction, or prompt refinement, still run this skill as a minimal preflight, then route to the available image-generation skill/tool:

- `plus-imagegen` for Codex/ChatGPT hosted image generation
- `gpt-image` when the user explicitly wants that CLI/API workflow
- host-native image tool when available

Do not let this skill override the user's requested format. It is now the default preflight for image tasks, but it should stay compact unless the user asks for deeper refinement.

## Routing Decision

Use this quick decision:

```text
Does the user primarily want image creation?
  Yes -> Use reduce-ai-look-imagegen as preflight.
    If anti-AI/repair/diagnosis/fuzzy/style risk is explicit -> load focused references.
    If not explicit -> use auto-anti-ai-expansion only, then generate/edit.
  No -> If they ask for prompt/style/quality analysis, use reduce-ai-look-imagegen.
```

## Combined Use

Sometimes use both:

1. Use `reduce-ai-look-imagegen` to parse intent and build a low-AI prompt.
2. Use `plus-imagegen` or the native image tool to generate the image.

Do this for all image generation requests, but keep the preflight small for ordinary requests.

## Examples

User:

```text
帮我生成一张水彩猫咪头像
```

Route:

```text
Ordinary image generation. Use reduce-ai-look-imagegen as a minimal preflight to preserve watercolor medium, avatar format, perspective/contact if relevant, then call imagegen.
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
这张图太像AI了，帮我改一下
```

Route:

```text
Use reduce-ai-look-imagegen directly.
```
