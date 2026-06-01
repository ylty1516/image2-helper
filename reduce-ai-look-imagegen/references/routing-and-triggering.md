# Routing And Triggering

Use this reference before applying the skill when the user's request could be ordinary image generation.

## Two Trigger Channels

### Channel 1: Explicit Anti-AI / Refinement

Use `reduce-ai-look-imagegen` when the user says or implies:

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

### Channel 2: Ordinary Image Generation

If the user only asks for a new image, such as:

- 帮我生成一张图
- 画一个角色
- 做一张海报
- 生成头像
- 出一张壁纸
- 画四格漫画
- 做游戏开始页

and does not ask for anti-AI reduction, quality diagnosis, style correction, or prompt refinement, route to the available image-generation skill/tool first:

- `plus-imagegen` for Codex/ChatGPT hosted image generation
- `gpt-image` when the user explicitly wants that CLI/API workflow
- host-native image tool when available

Do not let this skill override the user's requested format or become the default for every image task.

## Routing Decision

Use this quick decision:

```text
Does the user primarily want image creation?
  Yes -> Did they explicitly ask for lower AI feel, repair, diagnosis, or prompt refinement?
    Yes -> Use reduce-ai-look-imagegen, then generate/edit if needed.
    No -> Use image generation skill/tool directly.
  No -> If they ask for prompt/style/quality analysis, use reduce-ai-look-imagegen.
```

## Combined Use

Sometimes use both:

1. Use `reduce-ai-look-imagegen` to parse intent and build a low-AI prompt.
2. Use `plus-imagegen` or the native image tool to generate the image.

Only do this when anti-AI or style-translation is actually part of the user's request.

## Examples

User:

```text
帮我生成一张水彩猫咪头像
```

Route:

```text
Ordinary image generation. Use imagegen skill/tool. Do not invoke reduce-ai-look-imagegen unless the user complains about the result.
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
Ordinary generation with a hard format constraint. Use imagegen. If prompt planning is needed, use intent parsing only to preserve four panels.
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
