# Prompt Recipes

Use these recipes only when the request benefits from more precision than the core workflow.

## Universal Anti-AI Pass

Checklist:

- Replace abstract style adjectives with physical evidence.
- Add one real production constraint: lens, sensor, paper, print process, lighting rig, scan, render engine, or handmade medium.
- Add one plausible imperfection: uneven shadow, small scuff, skin pore texture, compression, handling mark, dust, fabric wrinkle, imperfect crop, or slight motion blur.
- Clarify object contact and scale.
- Remove contradictory style tags.
- Keep negative constraints short.

Template:

```text
Create a [format], [aspect ratio].
Subject: [specific subject].
Scene: [specific place/action/time].
Production: [camera/medium/process constraint].
Light: [motivated light and exposure behavior].
Physical details: [materials, wear, contact points, scale].
Composition: [framing and hierarchy].
Finish: [color grade or output texture].
Avoid: plastic surfaces, over-symmetry, generic AI gloss, impossible anatomy, floating objects, fake text/logos.
```

## Existing Image Realism Pass

Use this when the user provides an image that already exists and wants less AI feel without changing the concept.

Diagnosis checklist:

- Which parts must be preserved exactly?
- Which parts look synthetic because of texture, light, anatomy, object contact, or composition?
- Which fixes can be done by post-processing?
- Which fixes require actual image editing or regeneration?

Edit prompt:

```text
Edit the provided image while preserving the subject identity, pose, framing, outfit/product shape, and original scene layout.
Reduce synthetic AI finish by adding motivated exposure behavior, grounded contact shadows, restrained grain, believable material texture, small natural imperfections, and less glossy smoothing.
Change only the surface realism and photographic/design finish.
Do not change the subject, body shape, pose, outfit coverage, layout, or important objects.
Avoid waxy skin, plastic material, over-bright whites, fake bokeh, floating objects, and overprocessed HDR.
```

Post-processing proof limits:

- Can reduce sterile polish, over-bright whites, and smooth digital finish.
- Can make a result feel more photographed through grain, tone rolloff, edge softness, and color restraint.
- Cannot reliably fix anatomy, identity, object logic, or deep prompt mismatch.

## Pose And Action Correction

Use this when a person, humanoid character, animal-like character, or action scene looks wrong because the pose is exaggerated, anatomically impossible, unsupported, or unclear.

### Diagnosis checklist

- **Body line**: Do the head, neck, shoulders, spine, pelvis, knees, and feet form a believable chain?
- **Joint range**: Are elbows, wrists, knees, ankles, neck, waist, or fingers bent past normal range?
- **Weight support**: Which limb, hip, seat, floor, wall, or prop carries the body weight?
- **Center of gravity**: Would the figure fall over if this were a real body?
- **Contact and pressure**: Do feet touch the floor plane? Do hands actually grip or press? Does a seated body compress into the seat?
- **Scale and foreshortening**: Are near-camera limbs enlarged in a plausible way?
- **Action intent**: Is the subject jumping, leaning, reaching, dancing, fighting, sitting, or resting in a readable way?
- **Clothing and hair response**: Do folds, straps, hems, sleeves, hair, and loose accessories follow the movement and gravity?

### Edit prompt

```text
Edit the provided image to correct the physically implausible pose while preserving the subject identity, face, outfit, scene, camera angle, lighting, and original emotional intent.
Fix only the action mechanics: natural joint range, believable spine and pelvis alignment, clear weight support, grounded feet or seated contact, realistic hand/finger placement, and object contact.
Make clothing folds, hair, straps, and accessories respond to the corrected pose and gravity.
Keep the pose expressive but physically possible.
Do not change the character design, body type, outfit coverage, background, or framing.
Do not make the pose more sexualized, more violent, or more exaggerated.
Avoid broken joints, twisted limbs, floating hands or feet, impossible balance, and unclear object interaction.
```

### Generation prompt addition

```text
Pose logic: physically possible action with clear weight support, natural joint range, readable body line from head through pelvis and limbs, grounded contact points, believable hand/finger placement, and clothing/hair following gravity.
```

### Fast rewrite examples

Bad:

```text
dynamic girl jumping pose, dramatic angle, beautiful hands
```

Better:

```text
The character is captured mid-step, not floating: left foot planted on the stair edge, right foot lifting, hips tilted naturally over the supporting leg, arms balancing the motion, fingers relaxed, skirt and hair pulled slightly by the movement.
```

Bad:

```text
cute seated pose, hand near face, full body
```

Better:

```text
The character sits with weight visibly supported by the bench, pelvis and shoulders aligned, one hand resting flat on the seat with slight wrist bend, the other lightly touching the collar, knees angled naturally toward the camera, shoes flat on the floor.
```

## Hand-Drawn Anime And Cel-Look

Use this when the user asks for anime that feels less AI-generated, more hand-drawn, less glossy, less 3D, or closer to animation production art.

Read `anime-handdrawn-look.md` for the full production vocabulary.

Fast checklist:

- Make the composition feel like a layout or held animation frame, not a random poster collage.
- Use clean contours and controlled line weight.
- Use flat local color and 2-3 deliberate hard-edged shadow tones.
- Keep highlights simple and shaped, not sprayed or glossy.
- Let backgrounds be more painterly than characters: poster-color/gouache texture, softened distant detail, color harmony.
- Add mild scan, paper, or photographed-cel softness only when useful.
- Avoid named living artists or direct studio imitation; translate references into production traits.

Prompt addition:

```text
Hand-drawn anime finish: layout-driven staging, clean animation contour, flat local colors, two-tone cel shadow blocks, simple highlight shapes, character cel layer over hand-painted poster-color/gouache background, mild photographed-cel softness, no glossy 3D lighting or airbrushed gradients.
```

## Broader Style Selection

Use `style-taxonomy.md` when the user names a broad style, asks for style options, or mixes several styles together.

Use `style-blending-rules.md` when the prompt contains multiple style families that may conflict.

Rule of thumb:

- Pick one base medium.
- Add at most one mood or genre modifier.
- Convert style labels into process cues.
- Include 3-5 anti-AI constraints specific to that style family.

## Portraits And People

Use:

- natural skin texture, visible pores where appropriate
- slight facial asymmetry
- relaxed shoulders and believable hand placement
- wardrobe wrinkles and fabric tension
- background that explains the light

Avoid:

- flawless skin
- hyper-detailed eyes
- perfect teeth unless requested
- "ultra-realistic masterpiece"
- vague "cinematic model portrait"

Prompt addition:

```text
Human realism: relaxed expression, slight asymmetry, natural skin texture, believable hand placement, clothing wrinkles following the pose, no beauty-retouch plasticity.
```

## Products

Use:

- actual material behavior: brushed metal, molded plastic, coated paper, ceramic glaze, glass thickness
- scale reference or usage context
- plausible reflections and shadows
- packaging print limits, barcode/label areas without fake readable claims unless exact text is provided

Prompt addition:

```text
Product realism: real material transitions, subtle manufacturing marks, grounded contact shadows, plausible reflections, scale cues, no fake brand marks or invented text.
```

## Interiors And Architecture

Use:

- real light sources: window direction, lamp color temperature, exterior bounce
- imperfect lived-in details
- realistic verticals and perspective
- functional clutter with hierarchy

Prompt addition:

```text
Interior realism: straight verticals, motivated daylight and practical lamps, lived-in objects with uneven placement, true contact shadows, no showroom sterility.
```

## Food

Use:

- uneven cuts, crumbs, steam only when physically plausible
- oil sheen, moisture, browning variation
- plate scale and utensil contact

Prompt addition:

```text
Food realism: uneven browning, natural moisture, crumbs and small plating imperfections, real utensil scale, no plastic gloss or impossible garnish.
```

## Typography And Posters

Use exact text only when the user provides it. Keep typography instructions simple and ask for clean legible text. If exact text is critical, recommend generating the image background first and adding typography with a design tool afterward.

Prompt addition:

```text
Typography: use only the exact supplied text, clean readable letterforms, consistent baseline and spacing, no invented small print.
```

## Illustration

For non-photographic outputs, reduce AI feel by specifying a coherent medium rather than fake realism.

Use:

- medium-specific marks: ink bleed, risograph misregistration, graphite pressure, gouache opacity
- limited palette
- consistent line weight
- intentional simplification

Prompt addition:

```text
Illustration discipline: consistent line weight, limited palette, medium-specific texture, clear silhouette hierarchy, no random micro-details.
```
