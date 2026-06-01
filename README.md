# image2-helper

一个可部署的 Codex 生图辅助 Skill 项目，用来降低 AI 生图的“AI 感”，并帮助 AI 更准确地理解用户真正想要的画风、格式和用途。

本仓库包含可直接安装的 skill：

```text
reduce-ai-look-imagegen/
```

它适合处理这类需求：

- “降低 AI 感”
- “不要这么假 / 油 / 塑料 / 像 3D”
- “动作、手、姿势不自然，帮我修”
- “我说高级感、氛围感、故事感，你帮我转成真正可用的生图提示词”
- “我要四格漫画，不要被生成成单张海报”
- “帮我判断这张图为什么像 AI”

如果用户只是普通地说“帮我生成一张图”，这个 skill 不会强行接管，而是建议先走普通生图工具。

## 它能解决什么

| 用户问题 | Skill 会做什么 |
|---|---|
| 图片太像 AI | 把空泛词改成具体的媒介、材质、光影、构图语言 |
| 只说“高级感 / 氛围感 / 故事感” | 转换成颜色、光线、材质、空间、叙事线索 |
| 输出格式很重要 | 锁定四格漫画、LOGO、图标、海报、游戏菜单、角色设定、包装等格式 |
| 手、动作、人体不合理 | 检查关节范围、重心、接触点、衣服和头发是否符合重力 |
| 动漫图太油、太 3D | 转换成手绘动画、赛璐璐、线稿、色块、背景绘制语言 |
| 多种画风混在一起 | 避免“风格汤”，先确定主媒介，再加一个修饰风格 |
| token 消耗太高 | 默认走 fast path，只加载最相关的一个参考文件 |

## 安装方法

### 最简单：复制这段提示词给 Codex

把下面这段直接复制到 Codex 里，让 Codex 自动帮你安装：

```text
请帮我安装这个 Codex skill：https://github.com/ylty1516/image2-helper

要求：
1. 克隆或下载这个仓库。
2. 把仓库里的 reduce-ai-look-imagegen 文件夹复制到我的 Codex skills 目录：
   - Windows: C:\Users\我的用户名\.codex\skills\reduce-ai-look-imagegen
   - macOS/Linux: ~/.codex/skills/reduce-ai-look-imagegen
3. 确认最终存在 SKILL.md：
   reduce-ai-look-imagegen/SKILL.md
4. 安装完成后告诉我是否成功。
5. 不要修改 skill 内容。
```

短版：

```text
请从 https://github.com/ylty1516/image2-helper 安装 Codex skill。把 reduce-ai-look-imagegen 文件夹复制到我的 ~/.codex/skills/ 目录下，确保最终路径是 ~/.codex/skills/reduce-ai-look-imagegen/SKILL.md。安装后告诉我结果。
```

### 方法一：用 Git 安装

打开 PowerShell，运行：

```powershell
git clone https://github.com/ylty1516/image2-helper.git
Copy-Item -Recurse .\image2-helper\reduce-ai-look-imagegen "$env:USERPROFILE\.codex\skills\reduce-ai-look-imagegen"
```

然后重启 Codex，或者新开一个 Codex 对话线程。

### 方法二：下载 ZIP 安装

1. 打开仓库页面：<https://github.com/ylty1516/image2-helper>
2. 点击绿色的 `Code` 按钮。
3. 点击 `Download ZIP`。
4. 解压下载好的压缩包。
5. 找到里面的 `reduce-ai-look-imagegen` 文件夹。
6. 把整个 `reduce-ai-look-imagegen` 文件夹复制到你的 Codex skills 目录。

Windows 用户最终路径应该像这样：

```text
C:\Users\你的用户名\.codex\skills\reduce-ai-look-imagegen\SKILL.md
```

macOS / Linux 用户最终路径应该像这样：

```text
~/.codex/skills/reduce-ai-look-imagegen/SKILL.md
```

### Windows 一行安装命令

如果你已经克隆或解压了本仓库，并且当前终端就在仓库根目录，运行：

```powershell
Copy-Item -Recurse .\reduce-ai-look-imagegen "$env:USERPROFILE\.codex\skills\reduce-ai-look-imagegen"
```

### macOS / Linux 一行安装命令

如果你已经克隆或解压了本仓库，并且当前终端就在仓库根目录，运行：

```bash
mkdir -p ~/.codex/skills
cp -R ./reduce-ai-look-imagegen ~/.codex/skills/reduce-ai-look-imagegen
```

### 如何确认安装成功

确认这个文件存在：

```text
Windows:
C:\Users\你的用户名\.codex\skills\reduce-ai-look-imagegen\SKILL.md

macOS / Linux:
~/.codex/skills/reduce-ai-look-imagegen/SKILL.md
```

然后重启 Codex，或新开一个线程，输入：

```text
Use $reduce-ai-look-imagegen to rewrite this prompt so it feels less AI-generated: a glossy anime character poster, cinematic, high quality
```

如果 Codex 能识别 `$reduce-ai-look-imagegen`，说明安装成功。

## 快速使用

当你想降低 AI 感时，可以这样说：

```text
Use $reduce-ai-look-imagegen 帮我改写这个生图提示词，让它更少 AI 感：
一个白发动漫少女站在城市街道上，cinematic，高质量
```

如果你要保持格式，比如四格漫画：

```text
Use $reduce-ai-look-imagegen 保持“四格漫画”的格式，但让画面更有氛围感，不要变成单张海报。
```

它会优先锁定格式：

```text
Create a four-panel comic page with four clearly separated panels in reading order.
Keep a consistent character design across all panels.
Use a setup, development, turn, payoff rhythm.
Style: clean manga linework, controlled screentone, simple atmospheric backgrounds.
Avoid: single-poster composition, fake dialogue text, changing character design, glossy AI gradients.
```

## 触发逻辑

这个 skill 有两条通道。

### 1. 降 AI 化 / 优化通道

当用户明确说这些内容时，使用 `reduce-ai-look-imagegen`：

- 降低 AI 感
- 去 AI 味
- 更自然
- 更像手绘
- 更像真实拍摄
- 修手 / 修动作 / 修姿势 / 修人体
- 太油
- 太假
- 太塑料
- 像 3D
- 不高级
- 风格不对
- 帮我优化提示词
- 帮我诊断这张图

### 2. 普通生图通道

如果用户只是说：

```text
帮我生成一张图
画一个头像
做一张壁纸
生成一张海报
```

那就先走普通生图工具。这个 skill 不应该强行接管每一次生图请求。

## 低 token 设计

项目里有一个快速路径文件：

```text
reduce-ai-look-imagegen/references/fast-path.md
```

它会让 AI：

- 普通生图不走本 skill
- 简单降 AI 化只读 `fast-path.md`
- 单一问题只读一个相关 reference
- 普通生图提示词尽量控制在 120 词以内
- 默认只写 3 条以内的反 AI 约束
- 不在生成前输出长篇分析

这样可以减少 image2 / 生图模型的上下文消耗，也能减少思考时间。

## 文件结构

```text
reduce-ai-look-imagegen/
  SKILL.md
  00_NEXT_AI_READ_FIRST.md
  agents/
    openai.yaml
  references/
    fast-path.md
    routing-and-triggering.md
    intent-and-fuzzy-language.md
    failure-feedback-fixes.md
    prompt-recipes.md
    anime-handdrawn-look.md
    style-taxonomy.md
    style-selection-and-use-cases.md
    style-blending-rules.md
    style-expansion-pack.md
    style-prompt-cookbook.md
    style-quality-rubric.md
```

## 重要文件说明

- `SKILL.md`：主 skill 文件，Codex 识别 skill 的入口
- `00_NEXT_AI_READ_FIRST.md`：给下一位维护者或 AI 的快速说明
- `fast-path.md`：低 token 快速路径
- `routing-and-triggering.md`：判断什么时候该用这个 skill
- `intent-and-fuzzy-language.md`：把“高级感、氛围感、故事感”等模糊词转成生图语言
- `failure-feedback-fixes.md`：把“太油、手怪、像 3D”等反馈转成修正提示词
- `anime-handdrawn-look.md`：动漫、赛璐璐、手绘背景、线稿、色块相关规则
- `style-blending-rules.md`：处理混合画风，避免风格冲突
- `style-quality-rubric.md`：判断是否真的降低了 AI 感

## 校验 Skill

如果你本地有 Codex 的 skill creator 校验脚本，可以运行：

```powershell
$env:PYTHONUTF8 = '1'
$target = Join-Path $env:TEMP 'codex_pyyaml_validate'
if (-not (Test-Path -LiteralPath $target)) { py -m pip install --target $target PyYAML -q }
$env:PYTHONPATH = $target
py "$env:USERPROFILE\.codex\skills\.system\skill-creator\scripts\quick_validate.py" ".\reduce-ai-look-imagegen"
```

期望输出：

```text
Skill is valid!
```

## 示例：模糊词转换

用户说：

```text
让它更高级一点，少一点 AI 感。
```

Skill 会转换成类似：

```text
Use precise negative space, restrained palette, credible material texture, quiet lighting, fewer objects, controlled reflections, no fake luxury logo, no glossy AI finish.
```

用户说：

```text
我要四格漫画风格，但更有电影感。
```

Skill 会保留格式：

```text
Four clearly separated panels remain mandatory. Cinematic mood may affect lighting, framing, and value structure inside the panels, but the result must not become a single splash illustration.
```

## 维护说明

如果你要继续扩展这个项目，先读：

```text
reduce-ai-look-imagegen/00_NEXT_AI_READ_FIRST.md
```

这个项目是“参考资料多，但运行时尽量少加载”的设计。不要默认把所有 reference 都塞给模型；应该按任务只读最相关的一份。

## License

MIT. See [LICENSE](LICENSE).
