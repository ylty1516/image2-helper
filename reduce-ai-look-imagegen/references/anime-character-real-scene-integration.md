# Anime Character Real-Scene Integration

Use this when the user wants a 2D/anime character to appear inside a real or photographed environment, desktop setup, room, phone/computer display, AR-like scene, product photo, live-action plate, or any image where an illustrated character must convincingly share physical space with real objects.

## Core Problem

AI often makes the character look pasted onto the scene: the anime layer is clean and luminous, while the real environment has different camera perspective, exposure, shadow softness, reflection behavior, lens blur, and material texture. The result feels like a sticker, screenshot, or compositing error instead of a character occupying the same world.

## Immutable Background Plate Rule

When the user provides a real photo, room, desktop, phone shot, screen photo, product shot, or any existing background plate, the background is locked. Preserve every background pixel as much as the edit tool allows.

Hard rule:

- do not change the crop, camera angle, perspective, lens distortion, depth of field, exposure, white balance, color temperature, existing light, existing shadows, highlights, reflections, glass glare, texture, grain, compression, clutter, dust, dirt, or noise
- do not add, remove, replace, clean up, repaint, sharpen, blur, denoise, relight, recolor, stylize, straighten, upscale, or rearrange background objects
- do not move furniture, props, wires, screens, clothes, books, cups, doors, windows, walls, signs, railing, desk items, floor marks, or existing reflections
- only the inserted/edited character layer may change; character color, edge softness, exposure, and shadow design must adapt to the locked background
- if contact shadow or occlusion is required, keep it as a tiny localized character-contact effect and never alter the room's original global lighting or existing object shadows

Prompt lock:

```text
Background plate lock: preserve the existing real background exactly, including all objects, object positions, crop, camera perspective, exposure, white balance, color temperature, original light, original shadows, highlights, reflections, clutter, texture, grain, and compression. Do not clean, relight, repaint, stylize, replace, blur, sharpen, denoise, rearrange, add, remove, or move anything in the background. The anime character must adapt to the background; the background must not adapt to the character.
```

## Tool / Workflow Rule

If exact background preservation matters, a prompt-only whole-image edit is not reliable enough. It can still re-render the room, change lighting, move small objects, alter clutter, or smooth photo noise.

Preferred workflow:

1. Keep the original background photo as the final base layer.
2. Mark the physical anchors before generation: seat plane, desk/keyboard plane, floor plane, chair back/legs, hand target, pelvis/thigh support, foot target, and foreground occluders.
3. Mark the background lighting map before generation: main light source, fill light, bright side, shadow side, occluders, contact-shadow zones, exposure range, color temperature, bounce color, and screen/desk/window glow.
4. Generate or extract only the anime character as a transparent/cutout layer that already matches the physical anchors and lighting map.
5. Locally composite the character layer onto the original photo.
6. Adjust only the character layer: scale, position, edge softness, color response, internal light/shadow, and local contact/occlusion.
7. Do not add global cast shadows, relight the room, clean the desk, move props, or rewrite the background.
8. When practical, compare the final output against the original photo and confirm pixels outside the character/overlay bounding box remain unchanged.

Only use whole-image generative edit as an exploratory preview, not as the final delivery, when the user says the real background must not change at all.

## Physical Anchor Rule

Background locking does not make a composite believable by itself. Before generating the character layer, identify the exact contact and occlusion anchors in the photo.

For a seated-at-desk scene, decide:

- seat plane: where the pelvis/thighs actually rest, and what part of the chair back remains visible
- desk/keyboard plane: where the hands should land, and whether wrists/forearms should be hidden by the desk edge or keyboard
- leg/foot path: where knees bend, how legs pass under the desk, and where shoes contact the floor or chair foot area
- occlusion order: which chair rails, desk edges, ladder bars, monitor, keyboard, or foreground objects should cover parts of the character
- support logic: the body weight must be carried by chair/floor/desk contacts, not floating in the blank space between them

Prompt patch:

```text
Physical anchors: generate the character layer only after matching the real chair seat plane, desk/keyboard plane, floor plane, and occlusion order. The pelvis and thighs must visibly rest on the chair; hands must align to the real keyboard/laptop plane; legs must pass naturally under the desk; shoes must have a believable floor/chair-foot target; existing chair rails, desk edge, ladder, keyboard, or monitor may occlude the character. Avoid floating pelvis, hands hovering above the keyboard, knees clipping the desk, feet with no target, and body scale that ignores the chair.
```

## Background Lighting Map Rule

Before generating the character layer, read the photo's actual lighting instead of asking for generic indoor light.

Decide:

- main source: lamp, monitor, window, ceiling light, desk light, or phone flash direction
- lit side: which side of the character should receive stronger light
- shadow side: which side must stay muted or occluded
- contact-shadow zones: under thighs/skirt, between back and chair, under forearms/hands, under shoes, behind hair/shoulder where close to objects
- bounce color: wood desk warmth, wall gray, monitor blue, curtain color, floor color, or nearby fabric color
- exposure range: whether highlights are clipped, soft, dim, noisy, warm, cool, or mixed

Prompt patch:

```text
Lighting map: match the locked background's real light. Identify the main light source, fill light, lit side, shadow side, occluders, contact-shadow zones, bounce color, color temperature, and exposure range before generating the character layer. Put brighter values only on the side facing the room/desk light; keep the opposite side muted and lower contrast. Add local bounce from the wood desk and nearby wall/fabric only on the character layer. Avoid independent anime rim light, uniform cel lighting, face lit from the wrong side, highlights brighter than the room, and shadows that contradict the locked photo.
```

## AI-Looking Failure Modes

- character has no physical contact point with the desk, floor, chair, screen edge, hand, or prop
- feet, hair, clothes, or accessories ignore the scene's ground plane and perspective
- anime character uses a different camera angle than the real photo plate
- character scale does not match nearby objects such as keyboard, mug, phone, monitor, books, bed, window, or chair
- no cast shadow, ambient occlusion, reflected color, or occlusion where the character overlaps real objects
- lighting direction differs: room light from one side, character rim/highlights from another
- character edges are too clean, too sharp, too glowing, or too high-resolution compared with the camera plate
- skin/hair/clothes keep pure cel colors while the environment has lens noise, exposure rolloff, color temperature, and compression
- screen/display scenes ignore screen physics: bezel occlusion, glass reflection, pixel grid, bloom, moire, viewing angle, and brightness falloff
- AR/hologram effects float without a source device, surface anchor, reflection, or shadow logic

## Human-Artist / Good Composite Comparison

- the camera plate determines the character's scale, perspective, lens softness, and crop
- one contact anchor is clear: feet on floor, hand on desk, body behind monitor edge, reflection on glass, shadow on wall, or occlusion behind foreground object
- the character receives the same main light direction, color temperature, shadow softness, and exposure range as the environment
- edges are integrated: slight blur, grain, compression, color spill, rim only where motivated, and no perfect sticker outline
- nearby real objects affect the character through occlusion, bounce light, reflection, and contact shadow
- if the character is on a screen, the image is visibly emitted by the display surface rather than existing as a flat pasted poster

## Prompt Patch

```text
Anime-real integration: make the anime character share the real scene's camera plate while preserving the background plate exactly. Match one camera height, lens perspective, horizon/ground plane, scale anchors, and crop. Define physical anchors before generation: seat/floor/desk/screen plane, hand/foot/body contact, support logic, and occlusion order. Define the background lighting map before generation: main light, fill light, lit side, shadow side, contact-shadow zones, bounce color, color temperature, and exposure range. Match the room's existing light and physical contacts by changing the character layer only, not the background. Integrate character edges with slight camera softness, grain/compression, local color spill, and foreground occlusion. Avoid sticker-like cutout edges, floating character, hands hovering above target objects, mismatched scale, separate lighting, pure cel colors unaffected by the room, background relighting, moved objects, cleaned clutter, changed shadows, or any background repainting.
```

## Screen / Display Prompt Patch

Use when the anime character is inside or emerging from a phone, tablet, monitor, TV, projection, livestream, desktop wallpaper, or AR display.

```text
Screen integration: the character is constrained by the display surface and camera view while the existing background/screen photo remains unchanged. Align the character to the screen plane, bezel, viewing angle, pixel grid, glass reflection, brightness falloff, and screen bloom by adapting the character layer. Let the existing bezel or foreground objects occlude parts of the character where appropriate. If the character emerges from the screen, define the crossing point and occlusion at the bezel without moving the bezel, changing room lighting, rewriting reflections, or altering existing screen/glass/background details. Avoid pasted flat wallpaper, impossible depth through the screen, clean sticker edges, unreadable fake UI text, background relighting, object changes, and glow that edits the original room.
```

## Physical Checklist

Before generating, silently decide:

- real plate type: photo, phone shot, webcam frame, desktop scene, room, street, product shot, monitor display, AR projection
- locked background elements: crop, objects, positions, exposure, color temperature, original light/shadows/reflections, clutter, texture, grain, compression
- character state: printed image, screen image, AR/hologram, miniature figure, life-size person, or stylized overlay
- anchor: floor, desk, chair, hand, screen bezel, phone glass, wall, shadow, reflection, or foreground occlusion
- physical anchor map: seat/desk/floor/screen planes, hand targets, foot targets, support points, occlusion order, and scale anchors
- lighting map: main light, fill light, lit side, shadow side, contact-shadow zones, bounce color, exposure range, color temperature
- camera: height, lens softness, perspective, crop, depth of field, noise/compression
- light: main direction, color temperature, screen glow, bounce light, rim only if motivated
- material interaction: cast shadow, contact shadow, reflection, glass glare, pixel grid, fabric/object occlusion
- style blending: keep anime identity but adapt exposure, edge softness, and color response to the real plate

## Compact Add-On

```text
2D-to-real integration: preserve the existing real background exactly, including objects and original light/shadow/reflection behavior. Match the character to the real scene camera, perspective, scale, light direction, color temperature, shadow softness, contact/occlusion, edge softness, and lens grain by changing the character layer only. Give the anime character one clear physical anchor in the scene. Avoid floating sticker cutout, mismatched lighting, wrong scale, pure cel colors unaffected by the environment, moved background objects, changed room lighting, and background repainting.
```
