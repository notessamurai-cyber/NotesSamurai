# NotesSamurai — Visual Bible (Master.md)

> Version: 1.0
> Purpose: Single source of truth for all AI-generated imagery in the NotesSamurai project.
> Usage: Reference this file before generating any artwork. Copy the Prompt Template section and fill in variables for each new scene.

---

# Visual Philosophy

NotesSamurai lives in the quiet space between everyday Japanese urban life and inner emotional clarity. The visual identity is contemplative, cinematic, and grounded — beauty found in commutes, rooftops, rain-slicked crosswalks, and the first light of morning. Every image should feel like a single frame pulled from a feature film: emotionally charged but restrained, never cartoonish, never busy. The city is not a backdrop — it is a character, breathing through weather and light.

Core pillars:
- **Stillness in motion** — calm subjects inside a living, moving city.
- **Light as emotion** — time of day and light quality carry the feeling, not exaggerated expressions.
- **Realism with soul** — semi-realistic anime rendering, not stylized comic simplification.
- **Consistency over novelty** — the same character, the same city, the same rules, every time.

---

# Art Style

- Anime cinematic illustration — feature-film quality, not TV-anime flatness.
- Makoto Shinkai inspiration: hyper-detailed skies, light shafts, reflective surfaces, emotional atmosphere.
- Persona series UI atmosphere: bold contrast, graphic confidence, stylish urban energy — used as *mood accent*, not literal UI overlays.
- Modern Japanese urban aesthetic: real-world architecture, signage, transit systems.
- Semi-realistic rendering: realistic proportions and lighting physics, anime-style facial simplification.
- Highly detailed environments: texture in wet asphalt, glass reflections, fabric folds, signage grime.
- Emotionally driven compositions: every frame should suggest a feeling before a story.

**Explicitly avoid:** flat manga shading, chibi proportions, western comic linework, 3D-render plastic look, photorealistic human skin.

---

# Character Design Rules

## Default Protagonist

| Attribute | Specification |
|---|---|
| Age | Late teens to early twenties (visually ambiguous, mature-youthful) |
| Hair | Dark, slightly messy, wind/rain-responsive strands, natural movement |
| Eyes | Sharp, expressive, subdued realistic color (not oversized anime eyes) |
| Outfit | Modern Japanese streetwear — school-adjacent or casual urban layers, muted tones with one accent color |
| Expression | Calm, introspective, rarely overtly emotional — subtlety over exaggeration |
| Silhouette | Lean, upright, recognizable in backlight/rim-light silhouette alone |
| Accessories | Minimal — one signature item (e.g., bag strap, earphones, wristwatch) kept identical across all scenes |

**Consistency Lock:** Hair style, outfit silhouette, accessory, and color accent must remain identical in every generated image unless a scene explicitly calls for a documented variant (e.g., "rain-soaked" or "uniform version"). Any variant must be logged and added to this file as an approved exception.

---

# Environment Rules

**Setting:** Urban Japan — contemporary, real-world, lived-in.

**Approved elements:**
- Rain, wet reflections
- Neon signage (used sparingly, motivated by real shopfronts/vending machines)
- Morning light, sunrise
- Blue hour, golden hour
- Purple-hour transitional skies
- Realistic modern architecture (train stations, apartment blocks, convenience stores, overpasses)
- Roads, crosswalks
- Train stations, train interiors/platforms
- Rooftops overlooking skyline
- City skyline silhouettes

**Strictly forbidden:**
- No fantasy elements
- No medieval architecture or clothing
- No sci-fi armor, mechs, or futuristic tech beyond present-day Japan
- No magical effects unrelated to natural light phenomena

---

# Color Script

The emotional color arc of the project, used to time-code any sequence or story order:

```
Night → Blue Hour → Purple → Orange → Golden Sunrise
```

- **Night** — deep navy/black, isolated warm light sources (windows, vending machines, streetlamps)
- **Blue Hour** — cool desaturated blues, quiet stillness, low contrast
- **Purple** — transitional dusk/dawn tones, ambiguous time, soft gradients
- **Orange** — warming light, rising energy, longer shadows
- **Golden Sunrise** — full warm saturation, hope/resolution tone, high-key highlights

Every scene should be assignable to one stage of this script. Do not mix stages within a single frame.

---

# Lighting Rules

- Natural cinematic lighting only — motivated by visible or implied light sources.
- Rain reflections on ground, glass, and metal surfaces mandatory in wet scenes.
- Volumetric light (light shafts through fog, dust, or rain) encouraged at dawn/dusk.
- Soft bloom on highlights — gentle, not overexposed.
- Lens flare permitted **only** when emotionally motivated (e.g., sun breaking through after rain) — not decorative, not constant.

---

# Camera Rules

Approved shot types (choose one per artwork, matched to emotional intent):

- Wide Shot — establishing scale, isolation, or environment dominance
- Medium Shot — character presence with context
- Close Up — emotional focus, internal moment
- Over Shoulder — perspective, anticipation, connection
- Bird Eye — scale, pattern, distance from self
- Low Angle — power, awe, architecture dominance
- Tracking Shot — implied movement, journey feeling
- Drone Shot — skyline, geographic establishing

---

# Motion Guidelines

All artwork must be generated as a **single static frame** designed to support post-production motion in Premiere Pro. Compose with headroom and depth layers to enable:

- Slow zoom (in or out)
- Slow pan (horizontal drift)
- Ken Burns effect (combined zoom + pan)
- Parallax (foreground/midground/background separation)
- Cross dissolve (compatible edge framing for scene transitions)

**Rule:** No excessive motion implied within the artwork itself (no motion blur, no dynamic action poses unless the scene specifically requires it). Stillness in the frame preserves flexibility in the edit.

---

# Prompt Structure

Reusable template — copy and fill in brackets for every new generation:

```
[SCENE]
Brief one-line description of the moment being depicted.

[SUBJECT]
Default protagonist (see Character Design Rules) — note pose, action, and expression for this specific scene.

[ENVIRONMENT]
Location from approved Environment Rules list. Include specific details (station name-type, street type, weather state).

[MOOD]
One or two emotional keywords (e.g., "quiet resolve," "nostalgic calm," "anticipatory stillness").

[CAMERA]
One approved shot type from Camera Rules.

[LIGHTING]
Time-of-day stage from Color Script + lighting behavior from Lighting Rules.

[COMPOSITION]
Framing notes — rule of thirds, negative space, depth layering for parallax support.

[COLOR]
Dominant palette matched to Color Script stage.

[DETAILS]
Texture and atmosphere specifics — rain droplets, steam, reflections, signage, fabric movement.

[NEGATIVE PROMPT]
See Negative Prompt section below.
```

---

# Negative Prompt

Standard exclusion list — append to every generation:

```
low quality, extra limbs, wrong anatomy, text, logo, watermark, low resolution,
blurry, duplicate character, different outfit, wrong color palette,
manga shading, chibi proportions, 3D render look, fantasy elements,
medieval architecture, sci-fi armor, mecha, oversaturated colors,
flat lighting, cartoon outline, western comic style
```

---

# Aspect Ratio

- **Standard:** 16:9
- **Target resolution:** 3840 x 2160 (4K)

All compositions should be framed with 16:9 in mind from the start — no cropping fixes after generation.

---

# Export Notes

- Final output must always read as a **finished anime illustration**, not a sketch, not a storyboard panel, not a manga page, not a comic panel.
- No panel borders, speech bubbles, or comic paneling of any kind.
- Every image is a standalone cinematic frame — complete, polished, ready for direct use in video editing without further illustration work.
- File naming and versioning convention (recommended): `NS_[SceneNumber]_[ColorStage]_[ShotType].png`

---

*End of Master.md — NotesSamurai Visual Bible. Update this file only through deliberate revision; all generations should stay traceable back to these rules.*
