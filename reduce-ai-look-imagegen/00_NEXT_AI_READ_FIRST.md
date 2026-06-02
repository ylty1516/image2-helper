# 00 - NEXT AI READ FIRST

This project is a deployable Codex skill named `reduce-ai-look-imagegen`.

Read this file first when taking over the project.

## What This Skill Does

`reduce-ai-look-imagegen` helps Codex improve AI image prompts and image-editing instructions so outputs feel less synthetic, generic, over-polished, anatomically implausible, or "AI-looking."

## Trigger Routing

There are two image-task channels:

1. For any image generation request, use this skill as a lightweight preflight before calling imagegen.
2. If the user explicitly asks for lower AI feel, prompt refinement, image diagnosis, natural pose/action correction, or says the result is too AI/oily/fake/3D/generic, use a deeper focused pass.
3. If the user only asks to generate an image without an anti-AI or refinement goal, keep this skill compact: preserve format/subject/style, add perspective/contact/background integrity where relevant, then route to the available image generation skill/tool such as `plus-imagegen`, `gpt-image`, or the host-native image tool.

Do not make this skill the default path for every image request.

It has grown into a visual style reasoning system. It can:

- diagnose why an image feels AI-generated
- rewrite prompts with stronger medium/process language
- remove unreasonable extra objects and fix prompt-image inconsistency
- correct implausible poses and action logic
- reduce AI flavor in anime battle illustrations by checking action skeleton, force vector, contact point, and effect discipline
- enforce background and non-focus quality with the same scrutiny as the focal subject
- reduce glossy/3D/anime-plastic finish
- classify many visual styles
- improve mainstream style selection through composition-first framing
- choose styles based on use case
- resolve conflicting mixed-style prompts
- score before/after results
- translate user feedback into prompt patches
- turn vague taste words into precise visual decisions and compact preference rules
- reduce token use and thinking time through quality-preserving speed, not low-quality shortening

## Read Order

Start here:

1. `SKILL.md`
2. `references/INDEX.md`
3. the single focused reference selected by `SKILL.md`

Then load specialized references only when needed:

- `references/INDEX.md` for a quick map of the reference folder and current anti-AI trigger/search words
- `references/fast-path.md` for the cheapest route and compact prompts
- `references/auto-anti-ai-expansion.md` for the universal image-generation preflight, silently adding anti-AI constraints and repairing fuzzy taste words
- `references/quality-preserving-speed.md` for lower token use and faster prompting while preserving quality-critical visual constraints
- `references/perspective-geometry.md` for the global camera/horizon/vanishing/ground-plane/scale/occlusion repair layer that every visible-space image should receive
- `references/inconsistency-cleanup.md` for extra props, prompt-image mismatch, expression/action mismatch, and viewpoint/environment mismatch
- `references/background-integrity.md` for rich, realistic background/non-focus quality, secondary figures, props, architecture, scene logic, and realistic street-photo background audits
- `references/anime-handdrawn-look.md` for anime, cel, genga/layout, hand-painted background looks
- `references/combat-action-anime.md` for anime battle, weapon clash, magic combat, martial arts, monster fight, and flashy-but-unclear action repair
- `references/routing-and-triggering.md` for deciding whether this skill should run or whether ordinary image generation should be used
- `references/intent-and-fuzzy-language.md` for user purpose parsing, fuzzy taste words, and hard format locks
- `references/fuzzy-word-precision-library.md` for deeper vague taste-word mapping, stacked fuzzy words, and user-specific preference wording
- `references/style-expansion-pack.md` for niche historical/design/craft/technical styles
- `references/style-blending-rules.md` for hybrid prompts and style conflicts
- `references/style-selection-and-use-cases.md` for choosing styles from output goals
- `references/mainstream-style-composition.md` for composition, framing, mainstream style completion, and output-specific safe areas
- `references/style-prompt-cookbook.md` for ready-to-use prompt skeletons

## Important Design Principles

Do not make prompts rely on vague quality words like:

```text
masterpiece, high quality, ultra detailed, beautiful, cinematic
```

Translate style requests into concrete production evidence:

```text
line behavior, color layer, shadow model, paper/paint/print texture, lens limits, material roughness, contact shadows, action logic, use-case safe areas
```

When a user names a living artist or director, avoid direct style copying. Translate the request into broad traits.

Example:

```text
Do not say: in Makoto Shinkai style.
Say: contemporary Japanese animated-film traits, luminous sky, rain-reflection atmosphere, emotional teenage-drama framing, warm rim light, hand-painted background feel.
```

## Current Folder Meaning

This folder is the portable project copy:

```text
F:\Codex_Save_Library\05_Project_Folders\reduce-ai-look-imagegen
```

The active Codex-discoverable skill lives at:

```text
C:\Users\yyx\.codex\skills\reduce-ai-look-imagegen
```

The latest desktop deployable package should be:

```text
C:\Users\yyx\Desktop\reduce-ai-look-imagegen-deployable.zip
```

## How To Validate

Run:

```powershell
$target = Join-Path $env:TEMP 'codex_pyyaml_validate'
if (-not (Test-Path -LiteralPath $target)) { py -m pip install --target $target PyYAML -q }
$env:PYTHONPATH = $target
py 'C:\Users\yyx\.codex\skills\.system\skill-creator\scripts\quick_validate.py' 'C:\Users\yyx\.codex\skills\reduce-ai-look-imagegen'
```

Expected result:

```text
Skill is valid!
```

Validate the portable copy too when packaging:

```powershell
py 'C:\Users\yyx\.codex\skills\.system\skill-creator\scripts\quick_validate.py' 'F:\Codex_Save_Library\05_Project_Folders\reduce-ai-look-imagegen'
```

## How To Sync Changes

After editing the active skill, sync it to the portable project folder:

```powershell
$src = 'C:\Users\yyx\.codex\skills\reduce-ai-look-imagegen'
$dst = 'F:\Codex_Save_Library\05_Project_Folders\reduce-ai-look-imagegen'
if (Test-Path -LiteralPath $dst) { Remove-Item -LiteralPath $dst -Recurse -Force }
Copy-Item -LiteralPath $src -Destination $dst -Recurse
```

If this handoff file should remain visible, copy it back afterward or keep the project folder as the source of the export package.

## How To Rebuild Desktop ZIP

Use a staging directory and include this handoff file:

```powershell
$src = 'F:\Codex_Save_Library\05_Project_Folders\reduce-ai-look-imagegen'
$desktop = [Environment]::GetFolderPath('Desktop')
$zipPath = Join-Path $desktop 'reduce-ai-look-imagegen-deployable.zip'
if (Test-Path -LiteralPath $zipPath) { Remove-Item -LiteralPath $zipPath -Force }
Compress-Archive -LiteralPath $src -DestinationPath $zipPath -CompressionLevel Optimal
```

## How To Continue Improving

Best next work:

- test with real generated images and fill before/after rubric scores
- add examples for specific game UI screens
- add stronger anime UI/title-screen guidance
- add a tiny set of golden prompts for common targets
- keep SKILL.md short and put detailed material in references

Avoid adding broad lists that do not change prompt behavior. Every new style entry should include:

- when to use it
- concrete process cues
- what to avoid
- how it reduces AI feel

## Current Status

Last known validation:

```text
Skill is valid!
```

The project has been synchronized to the F drive project folder and exported as a desktop ZIP.
