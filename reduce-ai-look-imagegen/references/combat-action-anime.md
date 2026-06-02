# Combat Action Anime Anti-AI

Use this when the user asks for anime battle illustration, sword duel, martial arts clash, magic combat, monster fight, cyber weapon clash, game splash action, or when an action image feels AI-generated because it is spectacular but hard to read.

This reference compares common AI battle-image behavior against strong human-directed action illustration principles. Do not copy any living artist. Use the general craft ideas: readable action, force, staging, silhouette, cause/effect, and controlled detail.

## Core Diagnosis

AI battle images often look impressive at first glance because they maximize:

- glow
- sparks
- debris
- fabric/hair flow
- weapon trails
- floating particles
- high-contrast detail everywhere

But they feel AI-made when the action lacks:

- a readable attack intention
- a precise contact or near-contact point
- believable body mechanics
- clear force direction
- foreground/midground/background separation
- damage and environment reaction caused by the action
- quiet zones that let the viewer read the pose

## Human-Directed Action Rule

Before adding effects, lock the action skeleton:

```yaml
combat_action_skeleton:
  attacker: "who initiates the action"
  defender: "who receives, blocks, dodges, counters, or resists"
  action_verb: "slash / thrust / block / parry / punch / kick / cast / grapple / evade"
  contact_point: "weapon-to-weapon, fist-to-guard, spell-to-shield, claw-to-ground, near miss"
  force_vector: "where energy travels through body and scene"
  body_support: "feet, stance, jump arc, grip, hip/shoulder twist"
  reaction: "hair, fabric, debris, expression, recoil, environment damage"
  quiet_zone: "area kept simple so the action can be read"
```

Effects support the skeleton. Effects must not replace the skeleton.

## Common AI Flavor In Combat Images

| AI-feeling cause | Why it feels fake | Human-directed fix |
|---|---|---|
| Effects hide the joints | The viewer cannot tell how the body attacks or defends | keep elbows, wrists, shoulders, hips, knees, feet, and grip readable |
| Every area has the same detail intensity | The eye cannot find the real action beat | create one primary clash point, one secondary reaction, and quieter surrounding detail |
| Attack trails do not follow body mechanics | Energy looks pasted on instead of caused by motion | align trails with weapon arc, hand path, hip twist, and follow-through |
| No before/after moment | It is a poster pose, not a fight frame | imply the previous beat and next beat through recoil, debris direction, stance, or gaze |
| Characters float without support | Dynamic angle becomes weightless | show planted foot, jump arc, braced knee, wall/floor contact, or clear airborne momentum |
| Monster/weapon scale is unclear | Huge forms become decorative clouds | include scale anchors, overlap, ground contact, shadow, or damage radius |
| Glow is brighter than the action | Light pollution replaces drawing decisions | reserve the brightest value for the contact point and keep nearby silhouettes readable |
| Hair, cloth, and debris move in random directions | Motion feels generated instead of animated | make all secondary motion follow the same impact vector or wind source |
| Background destruction is decorative | Ruins/fire/debris do not tell what happened | make damage originate from the clash, landing, blast path, or creature movement |
| Camera angle is dramatic but not staged | Low/wide angle hides body relation | choose a camera that shows attacker, defender, contact point, and escape/motion space |

## Four-Image Pattern Notes

Use these as abstract diagnosis patterns, not as source-specific criticism.

### Magic Duel With Effect Wall

AI-feeling risk:

- magic circle becomes the true subject while the caster's stance and pressure are secondary
- spell geometry is extremely clean, but hand pressure, shoulder line, and recoil are less emphasized
- floating debris and runes compete with the contact point

Prompt patch:

```text
Magic duel action clarity: the caster's shoulder, elbow, wrist, palm pressure, braced stance, and recoil visibly drive the shield or spell. Keep the magic circle readable but secondary to the body mechanics and contact point. Debris and runes follow the blast vector instead of filling the whole image.
```

### Dragon Fight With Spectacle Over Mechanics

AI-feeling risk:

- dragon scale detail, fire, sparks, and claws dominate before the attack path is understood
- the hero's jump/weapon thrust may feel weightless if no arc, grip, or landing logic is clear
- flames and debris can cover the real distance between fighter and dragon

Prompt patch:

```text
Monster-fight mechanics: show the hero's jump arc, two-hand grip, hip twist, weapon line, and intended strike path toward a precise dragon target. The dragon reacts with head angle, claw reach, wing tension, and damage radius. Fire and sparks illuminate the action but do not hide the body line or weapon contact.
```

### Cyber Weapon Clash With Contact Overload

AI-feeling risk:

- crossing neon beams and sparks create a bright knot that hides blade positions and hand grips
- both faces are polished, but the duel's push-pull force may be unclear
- background city detail competes with the clash instead of framing it

Prompt patch:

```text
Weapon clash readability: define the exact blade-to-blade contact point, opposing push directions, hand grips, wrist angles, and foot/hip support for both fighters. Keep the brightest spark at the contact point only, with rain reflections and city lights subdued enough to preserve silhouettes.
```

### Martial Arts Clash With Stronger Action Read

Why it feels closer to hand-directed action:

- bodies overlap with a readable attack/defense relationship
- arms, hands, expressions, and cloth motion converge around one impact beat
- the alley background frames the fight instead of becoming the fight

Preserve:

```text
Keep the visible attack/defense relationship, clear limb silhouettes, contact or near-contact beat, facial intent, cloth direction, and environment reaction around the impact.
```

## Combat Prompt Blocks

### Compact Block

```text
Combat action clarity: one readable attack/defense beat, exact contact or near-contact point, clear force vector, physically possible stance/jump/grip, visible joints and silhouettes, hair/cloth/debris following the same impact direction, effects kept behind or around the anatomy, and one quiet zone for readability.
```

### Edit Prompt Block

```text
Reduce AI-feeling spectacle while preserving the character designs, scene, style, and battle concept. Rebuild the action skeleton: define attacker, defender, action verb, contact point, force direction, stance or jump support, hand/weapon grip, and reaction. Move glow, sparks, debris, hair, cloth, and background destruction so they support the impact vector instead of covering joints, faces, weapons, or silhouettes. Keep one bright impact point and simplify surrounding noise.
```

### Generation Prompt Add-On

```text
Staged anime combat: the image reads as one human-directed action frame, not a decorative effect collage. The viewer can identify who attacks, who defends, where contact happens, which direction the force travels, how each body is supported, what reacts to the impact, and which areas stay quiet for readability.
```

## Action Clarity Checklist

Before finalizing a battle prompt, check:

- Can the viewer name the action verb in one second?
- Is there one primary clash/contact point?
- Are hands, wrists, elbows, shoulders, hips, knees, and feet readable enough?
- Does the weapon/spell trail follow the body motion?
- Does hair/cloth/debris share a coherent force direction?
- Is there a quiet area around the pose so anatomy can be read?
- Does background damage originate from the action?
- Is the brightest value reserved for the impact, not spread everywhere?
- Does the camera show both attacker/defender relation and motion space?

## Avoid

```text
glow wall hiding anatomy, sparks everywhere, random debris, unreadable crossed weapons, floating bodies, unclear attacker/defender, detail intensity everywhere, monster as black-purple cloud, fire covering the strike path, fake runes/text replacing action, hair and cloth moving in unrelated directions
```
