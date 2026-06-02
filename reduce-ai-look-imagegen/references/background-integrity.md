# Background And Non-Focus Integrity

Use this when the user cares about background quality, non-focus details, secondary figures, environmental logic, distorted objects, weird background people, malformed props, broken architecture, or "the main character is fine but everything else looks AI."

This is a bottom-layer quality rule: the background must receive the same quality scrutiny as the focal subject. A scene only becomes convincing when every visible layer can survive inspection.

## Core Rule

Treat background generation as equal in importance to character generation. The focal subject can still lead the composition, but the background must be real, rich, and logically constructed rather than a disposable filler layer.

For AI image prompts:

```text
Background and secondary details receive equal quality support: real-world structure, plausible objects, coherent perspective, believable secondary figures, consistent light/contact, and context-rich material detail. Depth of field or painterly simplification may reduce sharpness, but not realism, logic, or construction quality.
```

## Integrity Layers

### 1. Environment Geometry

Check:

- horizon and floor plane agree
- architecture follows one perspective system
- doors, windows, stairs, tables, streets, shelves, and vehicles keep believable scale
- background objects do not melt into each other

Prompt cue:

```text
Background integrity: architecture, floor plane, furniture, vehicles, signs, and environmental objects are constructed with the same realism standard as the focal subject, with believable perspective, scale, material detail, and no warped or melted forms.
```

### 2. Secondary Figures

Check:

- background people have believable posture and limb count
- crowds are simplified into readable silhouettes when distant
- visible hands, faces, and gestures are not mutated
- secondary figures interact with the environment naturally

Prompt cue:

```text
Secondary figures: every visible background person receives the same anatomical and behavioral quality check as the main subject, with natural posture, plausible limb count, scene-appropriate gesture, readable clothing logic, and no malformed limbs, duplicate faces, broken hands, or impossible actions.
```

### 3. Props And Objects

Check:

- objects have recognizable function and material
- cups, chairs, books, plants, phones, weapons, bags, lamps, windows, and signage do not have impossible fused shapes
- repeated objects are varied but still coherent
- important small objects do not become fake symbols

Prompt cue:

```text
Background props remain fully designed objects with recognizable function, material, scale, and contact; no distorted handles, fused parts, unreadable invented logos, or impossible materials.
```

### 4. Action And Social Logic

Check:

- background people are not doing bizarre unrelated actions
- expressions and gestures fit the scene mood
- gaze direction and body direction make sense
- crowd behavior matches the location

Prompt cue:

```text
Background action logic: secondary characters and crowd behavior match the scene mood, with natural gestures, gaze direction, and object interaction.
```

### 5. Light, Shadow, And Contact

Check:

- secondary objects share the same light direction
- feet, furniture, vehicles, and props contact the ground or surfaces
- shadows are simplified but not contradictory
- reflections do not invent impossible objects

Prompt cue:

```text
Scene-wide light/contact consistency: all background objects and secondary figures share the same light direction, contact shadows, scale, and surface logic.
```

### 6. Detail Richness And Depth

Check:

- focal subject and background both receive intentional design attention
- realistic images include lived-in background textures, material variation, and usable object detail
- depth of field can soften the background optically, but the underlying objects still make sense
- detail density follows composition, but quality scrutiny does not drop outside the focal point
- detail does not hide anatomy, UI, text area, or the main silhouette

Prompt cue:

```text
Background richness: maintain believable, context-rich background detail with real object functions, lived-in material texture, plausible secondary figures, and coherent environmental storytelling; depth or softness comes from optics/style, not neglected construction.
```

## Photo Reference: Realistic Street Background Audit

Use this when a user provides or requests a realistic street portrait, travel photo, lifestyle photo, city sidewalk scene, cafe street scene, or "real snapshot" look.

The reference street portrait pattern is useful because the main person is close and readable, while the background still contains many reality checks: pedestrians, bicycles, vehicles, trees, storefronts, cafe furniture, pavement, reflections, highlight wash, and edge occlusion.

### What The Background Must Preserve

- **Depth stack**: foreground bicycle/tree/vehicle, midground pedestrians/storefront, and far architecture each stay physically plausible. Depth of field may soften them, but it must not remove structure.
- **Pedestrian anatomy**: distant walkers can be less detailed, but they still need one head, one torso, natural limb count, grounded feet, believable stride, and scene-appropriate gaze/action.
- **Street object mechanics**: bicycles, cars, vans, railings, chairs, stools, doors, windows, and signs must keep real object construction even when cropped or partially hidden.
- **Sidewalk perspective**: curb lines, pavement seams, shopfront edges, tree rows, and walking lane direction should agree with one horizon/floor plane.
- **Cafe/storefront logic**: awnings, pillars, window frames, warm interior lights, reflections, tables, chairs, and planters should remain separate usable objects, not melted decorative blocks.
- **Foliage and tree anchors**: leaves may be soft, but trunks, shrubs, and branches need grounded roots, layered depth, and no fusion with bicycles, people, or building edges.
- **Exposure realism**: bright far buildings or sky may wash out, but not erase all architectural mass, window rhythm, or street continuity.
- **Occlusion discipline**: cropped objects and areas hidden by the subject must continue logically behind the subject; avoid impossible lines, limbs, wheels, or furniture passing through the foreground person.
- **Ordinary lived-in clutter**: keep believable everyday street detail without inventing fantasy props, fake text, random luxury signs, or overdesigned background decoration.

### Street Photo Prompt Cue

```text
Realistic street-background audit: give the sidewalk, pedestrians, storefronts, cafe furniture, bicycles, vehicles, trees, pavement seams, reflections, and far architecture the same realism check as the main subject. Keep depth-of-field softness optical only: all visible background objects still have plausible construction, grounded contact, coherent scale, one perspective system, ordinary lived-in detail, and no melted bikes, fused cafe furniture, malformed walkers, fake signage, or impossible occlusion through the subject.
```

## Common AI Failures

| Failure | Fix |
|---|---|
| main character looks good, background people have broken limbs | give every visible person a full anatomy/gesture plausibility check |
| street/room perspective bends behind the subject | choose one horizon and one floor plane |
| props melt into decorative clutter | preserve recognizable object silhouettes and material logic |
| background text becomes fake symbols | use blank sign shapes or exact provided text; do not invent pseudo-writing |
| distant hands/faces are mutated | keep full head/limb structure and natural pose even when facial detail is low |
| decorative detail covers errors | clarify object relationships and enrich with plausible material detail |
| realistic street background turns into generic blur | audit by zones: sidewalk, pedestrians, storefront, vehicles, bicycles, foliage, pavement, and far architecture |
| cafe chairs/tables/railings fuse into wooden blocks | keep each furniture piece as a separate usable object with legs, contact, scale, and material |
| cropped bicycles or vehicles become impossible fragments | preserve mechanical continuity for wheels, handlebars, frames, doors, windows, and visible contact points |
| bright far background becomes blank white filler | allow exposure wash only while retaining plausible building mass, window rhythm, and street continuity |
| subject occlusion hides background errors | ensure lines, limbs, wheels, furniture, and curb seams continue logically behind the foreground subject |

## Prompt Blocks

### Compact Block

```text
Background integrity: the focal subject and background receive the same quality standard. Secondary figures, props, architecture, floor plane, light direction, material texture, and contact shadows remain richly plausible with no warped objects, malformed people, fake text, or impossible actions.
```

### Edit Prompt Block

```text
Improve the background and non-focus details while preserving the main subject, composition, style, and mood. Treat the background with the same quality standard as the main subject: correct malformed background people, warped objects, broken architecture, impossible perspective, fake text/logos, contradictory light/contact, and empty filler areas. Add context-rich, physically plausible environmental detail where the scene needs realism.
```

### Generation Prompt Add-On

```text
Scene integrity: the focal subject remains compositionally primary, but the background is generated with equal quality support: rich, realistic, structurally plausible objects and secondary figures, aligned to the same perspective and light, with no melted props, malformed crowd figures, fake text, or bizarre unrelated actions.
```

## Examples

### Street Portrait

Bad:

```text
The portrait face is good, but pedestrians behind her have extra limbs, warped faces, and signs become fake symbols.
```

Fix:

```text
Keep the subject as the focal point while giving the street the same realism standard: pedestrians have natural walking posture, believable clothing and limb structure, storefronts have real architectural detail, signs use blank shapes unless exact text is provided, and street objects keep plausible scale and material.
```

### Anime Classroom

Bad:

```text
Main anime character looks clean, but desks bend, windows are inconsistent, and classmates in the back have broken arms.
```

Fix:

```text
Maintain a clean cel character layer while giving the classroom full background construction: desks, windows, chairs, bags, wall details, and classmates follow one perspective grid, with believable school-object design, natural seated/standing poses, and no warped furniture or malformed secondary figures.
```

### Game Menu Background

Bad:

```text
Buttons are readable and the main character is fine, but the city background has impossible stairs, melted buildings, and strange tiny people.
```

Fix:

```text
Keep UI-safe negative space and the main character unchanged. Rebuild the city background with equal care: coherent layered architecture, plausible scale, real street detail, natural small figures, stable perspective, readable material surfaces, and no warped stairs, melted buildings, or fake signs.
```
