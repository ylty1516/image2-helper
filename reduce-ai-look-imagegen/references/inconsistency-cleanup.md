# Inconsistency Cleanup

Use this when a first AI-generated image includes unreasonable or unwanted elements that conflict with the user's prompt.

This module is not only about "AI look." It fixes prompt-image mismatch and visual logic errors before returning the image or edit prompt to the user.

## Core Rule

Compare the generated image against the user's requested concept. Remove or correct anything that does not serve the concept, role, action, camera, environment, or mood.

Most fixes are subtractive:

- remove extra props
- simplify role-breaking details
- align emotion with action
- align gaze with target
- align camera with environment
- align lighting and reflections with the scene

## Five-Layer Consistency Check

### 1. Concept Lock

Question:

```text
Does every major object belong to the user's requested idea?
```

Common failures:

- user asked for a maid skin, image adds a magic staff
- user asked for a healer, image adds a sword
- user asked for a logo, image adds a full scene
- user asked for a four-panel comic, image becomes one poster
- user asked for a product mockup, image hides product behind lifestyle props

Fix:

```text
Remove unrequested props and restore the concept hierarchy. The requested subject must remain the visual priority.
```

### 2. Role Lock

Question:

```text
Does the character still read as the requested role, skin, or identity?
```

Common failures:

- wizard maid skin becomes generic battle wizard
- school uniform character becomes idol costume
- desktop pet mascot becomes full fantasy illustration
- maid elements disappear under armor or magic effects

Fix:

```text
Preserve role-defining clothing, silhouette, color identity, and props. Remove details that switch the role.
```

### 3. Behavior-Expression Match

Question:

```text
Do the face, gesture, body action, and scene emotion agree?
```

Common failures:

- character smiles while falling or fighting
- angry pose with blank gentle expression
- shy expression with aggressive attack pose
- calm menu screen but intense combat stance
- eyes look at viewer while hand points to something off-screen

Fix:

```text
Align expression, gaze, and body gesture with the intended action and emotional beat.
```

### 4. Viewpoint-Environment Match

Question:

```text
Do camera angle, horizon, floor, lighting, reflections, and background scale agree?
```

Common failures:

- character seen from above but floor seen from front
- feet do not meet floor plane
- background perspective contradicts body angle
- reflections show impossible sky/object positions
- light comes from left but shadows fall left too

Fix:

```text
Unify perspective and lighting: one camera height, one horizon logic, one dominant light direction, grounded contact points.
```

### 5. Prop Necessity

Question:

```text
Is each prop required, optional, or harmful?
```

Use:

```yaml
required: keep and make readable
optional: keep only if it supports story/use case
harmful: remove or replace
```

Common harmful props:

- random staff, sword, gun, wings, halo, pet, floating crystal, duplicate bag, extra logo, fake text, random UI marks, decorative chains, unrequested magical effects

Fix:

```text
Remove harmful props. Do not replace them with new props unless the user asked for a replacement.
```

## Cleanup Output Format

When diagnosing an image, output:

```yaml
inconsistency_cleanup:
  prompt_goal: "<what the user asked for>"
  must_preserve:
    - "<identity / pose / outfit / layout / style>"
  remove:
    - "<unwanted object or detail>"
  correct:
    - "<expression/action/viewpoint/environment issue>"
  keep:
    - "<details that support the request>"
  edit_prompt: "<copy-ready image edit prompt>"
```

## Copy-Ready Edit Prompt

```text
Edit the image to match the original prompt more faithfully. Preserve the character identity, main outfit, pose intent, composition, color identity, and requested style. Remove unrequested extra objects or role-breaking props: [list objects]. Correct inconsistencies: [behavior/expression mismatch], [viewpoint/environment mismatch], [lighting/contact issue]. Keep only elements that support [requested concept]. Do not add new props, symbols, text, weapons, pets, wings, halos, or background clutter unless explicitly requested. Return a cleaner image that matches the prompt and keeps the same overall framing.
```

## Prompt Rewrite Pattern

For next-generation prompts, include a concept lock:

```text
Concept lock: [requested role/concept] is the only design priority. Required props: [list]. Do not add unrequested staffs, weapons, pets, wings, halos, logos, fake text, duplicate accessories, or magical effects.
```

For behavior:

```text
Behavior-expression match: expression, gaze, and body gesture must support [emotion/action]. Avoid mismatched smiles, blank stares, aggressive poses in calm scenes, or off-target gaze.
```

For camera:

```text
Viewpoint-environment match: one consistent camera height, horizon, floor plane, light direction, and grounded contact shadows.
```

## Example: Wizard Maid Skin With Unwanted Staff

User goal:

```text
Generate a maid skin for a blue-haired wizard desktop pet.
```

Bad first result:

```text
The character wears a maid outfit but holds a large magic staff, has battle pose effects, and looks like a combat wizard instead of a maid skin.
```

Diagnosis:

```yaml
remove:
  - large magic staff
  - combat spell effects
  - extra floating crystals
correct:
  - expression from battle-ready to gentle service/idle expression
  - hand pose from gripping staff to holding tray, skirt hem, or relaxed idle gesture
keep:
  - blue hair
  - wizard identity hints only as subtle motif
  - maid outfit silhouette
```

Edit prompt:

```text
Edit the character into a clean wizard maid skin. Preserve the blue-haired character identity, chibi desktop-pet proportions, maid outfit, and gentle fantasy color palette. Remove the large magic staff, combat spell effects, floating crystals, and any weapon-like props. Keep only subtle wizard motifs such as a small star hairpin or tiny rune trim on the apron. Change the hands into a relaxed maid idle pose, such as lightly holding the apron or a small tray. Align the expression with a gentle helpful maid mood, not a battle-ready wizard mood. Do not add new weapons, pets, wings, halos, fake text, or extra magical effects.
```

## Example: Expression And Action Mismatch

User goal:

```text
A tired apprentice cleaning the library late at night.
```

Bad first result:

```text
Character smiles brightly while running with a broom, with energetic sparkles everywhere.
```

Edit prompt:

```text
Preserve the apprentice identity, library setting, broom, and late-night scene. Correct the behavior-expression mismatch: make the character quietly tired but focused, with relaxed shoulders, slower cleaning gesture, and soft sleepy eyes. Remove energetic sparkles and running motion effects. Use warm lamplight and settled dust to support a late-night cleaning mood.
```

## Example: Viewpoint And Environment Mismatch

User goal:

```text
A character sitting on a rooftop ledge at sunset.
```

Bad first result:

```text
Character is seen from above, ledge is front-facing, feet float, sunset light and shadows disagree.
```

Edit prompt:

```text
Preserve the character, rooftop sunset concept, outfit, and framing. Correct the viewpoint-environment mismatch: use one consistent camera height, align the rooftop ledge perspective with the character's seated angle, place both hands/hips/feet with clear contact points, and make sunset light come from one direction with matching shadows. Do not add new props or change the scene into a different location.
```
