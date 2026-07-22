# Editing Notes

> Premiere Pro production guide. Organized by scene, one entry per song. Reusable template for every future song's editing pass. Reference `Master.md` Motion Guidelines for permitted motion types and `StyleGuide.md` Editing Philosophy for governing principles.

---

## Scene Entry Template

### Scene ID
<Song>-<SceneNumber>

| Field | Value |
|---|---|
| Duration | Seconds (8-15s range per pacing standard) |
| Timeline Position | Start timecode in the master sequence |
| Camera Motion | Motion type applied in-edit (Slow Zoom / Slow Pan / Ken Burns / Parallax / None) |
| Zoom | In / Out / None — rate and direction |
| Pan | Direction and speed, if any |
| Scale | Start/end scale values if keyframed |
| Position | Start/end frame position if keyframed |
| Transition | Cross Dissolve / Fade to Black / Other — in and out |
| Overlay | Any overlay elements (grain, light leak, particles) — None by default |
| Opacity | Keyframed opacity changes, if any |
| Blend Mode | Layer blend mode, if overlays are used — Normal by default |
| Motion Blur | On/Off — Off/minimal by default per static-frame philosophy; exceptions must be documented |
| Light FX | Lens flare, bloom intensification — must be motivated per `Master.md` Lighting Rules |
| Audio Cue | Relevant lyric line or instrumental beat this scene aligns to |
| Beat Sync | Specific timestamp/beat marker for cut or motion emphasis |
| Subtitle Notes | Lyric text for this scene, language, on/off |
| Color Grading | Grade notes matched to Color Script stage (`Master.md`) |
| Rendering Notes | Export settings, resolution confirmation, scene-specific render concerns |

---

## Governing Principles

- Motion exists only to support emotion — see `StyleGuide.md` Editing Philosophy.
- Default transition is Cross Dissolve; Fade to Black reserved for the final scene only.
- Approved motion set: Slow Zoom, Slow Pan, Ken Burns, Parallax. No excessive or distracting motion.
- Color Grading per scene must track the Color Script (Night → Blue Hour → Purple → Orange → Golden Sunrise) without introducing mismatched stages.
- Every Scene ID here must correspond to the same Scene ID used in `PromptPack.md` and `GenerationLog.md`.

---

## Song Timeline Summary

| Scene ID | Timeline Position | Duration | Transition Out |
|---|---|---|---|
| — | — | — | — |

Use this summary table to verify total runtime and transition continuity before rendering the full sequence.
