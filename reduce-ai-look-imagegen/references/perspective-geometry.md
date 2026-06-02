# Perspective And Spatial Geometry

Use this as a global repair layer for AI-generated images. Apply it whenever an image contains visible space: people in a scene, interiors, architecture, streets, landscapes, product setups, vehicles, furniture, props, floors, stairs, roads, water surfaces, or fantasy environments.

## Core Rule

Every image with visible space needs a camera and perspective contract. Do not let the model invent a different perspective for each object.

Universal prompt add-on:

```text
Perspective geometry: lock one camera height, one horizon line, and one coherent perspective system. Align floor/ground/water planes, roads, rails, stairs, furniture, buildings, props, and figure feet to that system. Preserve believable scale, overlap, foreshortening, contact shadows, and atmospheric depth from foreground to background.
```

## Common AI Perspective Failures

- multiple horizon lines in the same scene
- floor, road, river, platform, or tabletop tilting in incompatible directions
- doors, windows, stairs, tiles, railings, desks, shelves, or bridges using different vanishing points
- people, furniture, vehicles, towers, cliffs, trees, or props changing scale without depth reason
- feet, wheels, chair legs, table legs, props, or buildings floating above the ground plane
- objects intersecting or passing through each other because occlusion order is unclear
- foreground objects too small, far objects too detailed, or near limbs/props without plausible foreshortening
- wide-angle drama added without matching lens distortion across the full scene
- fantasy landscapes with bridges, castles, waterfalls, cliffs, and floating islands that do not share scale or gravity logic

## Human-Artist Comparison

- a human artist usually chooses the camera first: eye-level, low angle, aerial, isometric, orthographic, or wide-angle
- large shapes follow one layout grid before details are added
- foreground, midground, and background have separate scale/detail/value behavior
- object contact is drawn deliberately: feet on floor, chair legs on ground, bridges attached, stairs climbable, water flowing downhill
- stylization may bend perspective, but the bend is consistent and intentional across the whole image

## Perspective Lock Checklist

Before writing or editing a prompt, silently check:

- camera height: eye-level, low angle, high angle, aerial, isometric, or orthographic
- lens/space type: natural lens, wide angle, telephoto compression, animation layout, flat graphic, or stylized map
- horizon line: visible or implied
- vanishing system: one-point, two-point, three-point, isometric, orthographic, or deliberately flat
- ground/floor plane: where feet, wheels, furniture, props, buildings, water, or terrain make contact
- scale anchors: people, doors, windows, trees, vehicles, furniture, stairs, railings, or architectural modules
- occlusion order: what overlaps what, and which edges continue behind objects
- depth falloff: far detail, contrast, saturation, and texture reduce unless the chosen style says otherwise

## Prompt Patches

### General Scene

```text
Perspective lock: use one camera height and horizon line. Keep the floor/ground plane coherent, align objects to one perspective grid, preserve scale anchors, contact shadows, overlap order, and depth falloff. Avoid mixed vanishing points, floating feet/props, warped stairs/railings, impossible object intersections, and far objects rendered with foreground detail.
```

### Anime / Illustration

```text
Layout perspective: treat the image as a planned animation background layout. Choose one camera angle, one horizon line, and one ground plane; align character feet, furniture, buildings, railings, roads, and props to the same layout grid. Use stylized perspective only if it remains consistent across the whole frame.
```

### Interior / Architecture

```text
Architectural perspective: keep verticals, walls, floor seams, ceiling lines, windows, doors, furniture, stairs, shelves, and lamps aligned to one perspective system, with believable scale and contact points. Avoid bent rooms, drifting vanishing points, and furniture that cannot stand on the floor.
```

### Landscape / Fantasy

```text
Landscape perspective: establish foreground, midground, and background scale. Mountains, cliffs, castles, bridges, waterfalls, roads, rivers, floating islands, and settlements share one depth logic, atmospheric perspective, and gravity/terrain rule. Avoid impossible scale jumps, repeated tiny ruins, waterfalls with no source, and equally sharp detail at every distance.
```

### Product / Object Setup

```text
Object perspective: keep the object, tabletop/floor, cast shadow, reflections, and scale cue in one camera perspective. Avoid mismatched ellipses, tilted labels, floating bases, impossible reflections, and inconsistent edge convergence.
```

## Edit Prompt

```text
Edit the image to repair perspective while preserving the subject, style, composition, lighting mood, and important objects. Lock one camera height, horizon line, and coherent perspective system. Correct floor/ground alignment, object scale, contact shadows, overlap order, foreshortening, and architecture/prop convergence. Do not redesign the scene; only make the existing space physically coherent.
```
