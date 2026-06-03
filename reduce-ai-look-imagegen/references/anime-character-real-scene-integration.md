# Anime Character Real-Scene Integration

Use this when the user wants a 2D/anime character to appear inside a real or photographed environment, desktop setup, room, phone/computer display, AR-like scene, product photo, live-action plate, or any image where an illustrated character must convincingly share physical space with real objects.

## Core Problem

AI often makes the character look pasted onto the scene: the anime layer is clean and luminous, while the real environment has different camera perspective, exposure, shadow softness, reflection behavior, lens blur, and material texture. The result feels like a sticker, screenshot, or compositing error instead of a character occupying the same world.

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
Anime-real integration: make the anime character share the real scene's camera plate. Match one camera height, lens perspective, horizon/ground plane, scale anchors, and crop. Give the character a clear physical anchor: feet/hand/body contacting or being occluded by a real surface or object. Match room light direction, color temperature, exposure, shadow softness, ambient occlusion, reflected color, and material response. Integrate edges with slight camera softness, grain/compression, local color spill, and foreground occlusion. Avoid sticker-like cutout edges, floating character, mismatched scale, separate lighting, pure cel colors unaffected by the room, and shadows that do not touch the surface.
```

## Screen / Display Prompt Patch

Use when the anime character is inside or emerging from a phone, tablet, monitor, TV, projection, livestream, desktop wallpaper, or AR display.

```text
Screen integration: the character is constrained by the display surface and camera view. Align the character to the screen plane, bezel, viewing angle, pixel grid, glass reflection, brightness falloff, and screen bloom. Let the bezel or foreground objects occlude parts of the character where appropriate; add subtle moire/pixel texture, reflected room light on glass, and spill light onto nearby surfaces. If the character emerges from the screen, define the crossing point, cast shadow, screen glow source, and occlusion at the bezel. Avoid pasted flat wallpaper, impossible depth through the screen, clean sticker edges, unreadable fake UI text, and glow that ignores the monitor brightness.
```

## Physical Checklist

Before generating, silently decide:

- real plate type: photo, phone shot, webcam frame, desktop scene, room, street, product shot, monitor display, AR projection
- character state: printed image, screen image, AR/hologram, miniature figure, life-size person, or stylized overlay
- anchor: floor, desk, chair, hand, screen bezel, phone glass, wall, shadow, reflection, or foreground occlusion
- camera: height, lens softness, perspective, crop, depth of field, noise/compression
- light: main direction, color temperature, screen glow, bounce light, rim only if motivated
- material interaction: cast shadow, contact shadow, reflection, glass glare, pixel grid, fabric/object occlusion
- style blending: keep anime identity but adapt exposure, edge softness, and color response to the real plate

## Compact Add-On

```text
2D-to-real integration: match the real scene camera, perspective, scale, light direction, color temperature, shadow softness, contact/occlusion, edge softness, and lens grain. Give the anime character one clear physical anchor in the scene. Avoid floating sticker cutout, mismatched lighting, wrong scale, and pure cel colors unaffected by the environment.
```
