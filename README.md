# image2-helper

`image2-helper` is a Codex skill package for making AI image generation more intentional, less synthetic, and easier to route.

It contains the deployable skill:

```text
reduce-ai-look-imagegen/
```

The skill is designed for prompts and image-editing workflows where a user says things like:

- "lower the AI feel"
- "make it less fake / oily / plastic"
- "make this pose more natural"
- "this looks too 3D"
- "turn my vague taste words into a real image prompt"
- "keep this as a four-panel comic, do not turn it into a poster"

For ordinary image generation, it intentionally routes away from itself and lets your normal image tool run first.

## What It Helps With

| Problem | What the skill does |
|---|---|
| The image feels AI-generated | Converts vague quality words into concrete medium/process cues |
| The user only says "premium" or "atmospheric" | Translates fuzzy taste words into color, light, texture, composition, and material choices |
| The output format is important | Locks formats like four-panel comic, logo, icon, poster, game menu, character sheet, and packaging |
| Hands or body poses look wrong | Adds pose/action reasoning: joint range, weight support, contact points, clothing/hair gravity |
| Anime looks glossy or 3D | Rewrites toward hand-drawn cel/anime production language |
| Styles are mixed together | Resolves conflicts such as watercolor + cyberpunk or pixel art + cinematic |
| Token use is getting high | Uses a fast path and loads only one reference file when possible |

## Install

Copy the skill folder into your Codex skills directory:

```powershell
Copy-Item -Recurse .\reduce-ai-look-imagegen "$env:USERPROFILE\.codex\skills\reduce-ai-look-imagegen"
```

Then restart Codex or open a new thread so the skill can be discovered.

## Quick Use

Use the skill explicitly when you want anti-AI refinement:

```text
Use $reduce-ai-look-imagegen to rewrite this image prompt so it feels less AI-generated:
an anime girl standing in a city, cinematic, high quality
```

Example request:

```text
Use $reduce-ai-look-imagegen to keep this as a four-panel comic, but make it feel more atmospheric and less AI-generated.
```

Example output direction:

```text
Create a four-panel comic page with four clearly separated panels in reading order.
Keep a consistent character design across all panels.
Use a setup, development, turn, payoff rhythm.
Style: clean manga linework, controlled screentone, simple atmospheric backgrounds.
Avoid: single-poster composition, fake dialogue text, changing character design, glossy AI gradients.
```

## Trigger Routing

The skill has two channels:

### 1. Anti-AI / Refinement

Use `reduce-ai-look-imagegen` when the user asks for:

- lower AI feel
- more natural / realistic / hand-drawn
- pose, hand, or anatomy correction
- prompt diagnosis
- style correction
- fuzzy taste-word translation
- before/after scoring

### 2. Ordinary Image Generation

If the user only says:

```text
Generate an image of ...
Draw a poster of ...
Make a wallpaper ...
```

then use your normal image generation skill/tool first. This skill should not be forced into every image request.

## Low-Token Design

This project includes a fast path:

```text
reduce-ai-look-imagegen/references/fast-path.md
```

The skill is written to:

- route ordinary image generation away from extra prompt analysis
- load `fast-path.md` for simple anti-AI prompt rewrites
- load only one specialized reference file when possible
- keep normal image prompts under about 120 words
- use no more than 3 anti-AI constraints by default
- avoid long diagnostics before generation

## File Map

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

## Key References

- `fast-path.md` - cheapest route for common requests
- `routing-and-triggering.md` - when to use this skill versus ordinary imagegen
- `intent-and-fuzzy-language.md` - maps vague user words into real visual instructions
- `failure-feedback-fixes.md` - turns feedback like "too oily" or "bad hands" into prompt patches
- `anime-handdrawn-look.md` - hand-drawn anime, cel color, genga/layout, painted background language
- `style-blending-rules.md` - prevents style soup
- `style-quality-rubric.md` - scores whether AI feel was actually reduced

## Validate

If you have Codex's skill creator validation script:

```powershell
$env:PYTHONUTF8 = '1'
$target = Join-Path $env:TEMP 'codex_pyyaml_validate'
if (-not (Test-Path -LiteralPath $target)) { py -m pip install --target $target PyYAML -q }
$env:PYTHONPATH = $target
py "$env:USERPROFILE\.codex\skills\.system\skill-creator\scripts\quick_validate.py" ".\reduce-ai-look-imagegen"
```

Expected:

```text
Skill is valid!
```

## Example: Fuzzy Word Translation

User says:

```text
Make it more premium and less AI.
```

The skill translates this into:

```text
Use precise negative space, restrained palette, credible material texture, quiet lighting, fewer objects, controlled reflections, no fake luxury logo, no glossy AI finish.
```

User says:

```text
Make it feel like a four-panel comic, but more cinematic.
```

The skill keeps the hard format:

```text
Four clearly separated panels remain mandatory. Cinematic mood may affect lighting, framing, and value structure inside the panels, but the result must not become a single splash illustration.
```

## Maintainer Notes

Read this first when continuing the project:

```text
reduce-ai-look-imagegen/00_NEXT_AI_READ_FIRST.md
```

The project is intentionally reference-heavy but runtime-light: large style libraries are loaded only when needed.

## License

MIT. See [LICENSE](LICENSE).
