# Asset List

> Master asset database for NotesSamurai. Tracks every reusable and project-specific visual asset across all songs.
> Update this file whenever a new asset is created, reused, or retired. Reference `Master.md` for design rules governing each category.

---

## Metadata Fields

Every asset entry uses this schema:

| Field | Description |
|---|---|
| ID | Unique asset identifier (e.g. `CHAR-001`, `LOC-014`) |
| Name | Short descriptive name |
| Category | One of the categories below |
| Reusable | Reusable / Project-Specific |
| Priority | High / Medium / Low |
| Status | Concept / In Progress / Approved / Retired |
| First Used | Song/project where first generated |
| Reuse Notes | Guidance for reusing this asset in future songs |

---

## Characters

| ID | Name | Reusable | Priority | Status | First Used | Reuse Notes |
|---|---|---|---|---|---|---|
| CHAR-001 | Default Protagonist | Reusable | High | Approved | — | Locked per `Master.md` Character Design Rules. Do not redesign between songs. |

## Locations

| ID | Name | Reusable | Priority | Status | First Used | Reuse Notes |
|---|---|---|---|---|---|---|
| LOC-001 | City Intersection (Night) | Reusable | High | — | — | Standard establishing location for opening scenes. |
| LOC-002 | Narrow Street w/ Neon | Reusable | Medium | — | — | Use for searching/transitional beats. |
| LOC-003 | Train Station Platform | Reusable | High | — | — | Flexible across Blue Hour and Golden Hour variants. |
| LOC-004 | Rooftop (City Overlook) | Reusable | High | — | — | Primary location for resolve/climax scenes. |
| LOC-005 | Elevated Pedestrian Bridge | Reusable | Medium | — | — | Use for decision-point scenes. |
| LOC-006 | Crosswalk | Reusable | Medium | — | — | Use for hope/threshold beats. |

## Props

| ID | Name | Reusable | Priority | Status | First Used | Reuse Notes |
|---|---|---|---|---|---|---|
| PROP-001 | Signature Accessory (Character-locked) | Reusable | High | Approved | — | Must appear identically per `Master.md` Character Design Rules. |
| PROP-002 | Umbrella (unused/carried) | Project-Specific | Low | — | — | Optional, evaluate per song before reuse. |

## Environment

| ID | Name | Reusable | Priority | Status | First Used | Reuse Notes |
|---|---|---|---|---|---|---|
| ENV-001 | Urban Architecture Backdrop | Reusable | High | — | — | Base skyline silhouette set, reusable across songs. |
| ENV-002 | Wet Asphalt Surface | Reusable | High | — | — | Standard rain-scene ground texture. |

## Weather

| ID | Name | Reusable | Priority | Status | First Used | Reuse Notes |
|---|---|---|---|---|---|---|
| WX-001 | Light Rain | Reusable | High | — | — | Default weather state for Night/Blue Hour scenes. |
| WX-002 | Heavy Rain | Reusable | Medium | — | — | Use for conflict/momentum scenes only. |
| WX-003 | Clearing Rain | Reusable | Medium | — | — | Use for hope-transition scenes. |
| WX-004 | Clear Morning | Reusable | High | — | — | Default for Golden Sunrise scenes. |

## Lighting

| ID | Name | Reusable | Priority | Status | First Used | Reuse Notes |
|---|---|---|---|---|---|---|
| LIGHT-001 | Streetlamp Bloom | Reusable | High | — | — | Standard night lighting accent. |
| LIGHT-002 | Neon Reflection | Reusable | Medium | — | — | Use sparingly per `Master.md` Environment Rules. |
| LIGHT-003 | Volumetric Sunrise Rays | Reusable | High | — | — | Reserved for climax/finale scenes. |
| LIGHT-004 | Motivated Lens Flare | Reusable | Medium | — | — | Only when emotionally appropriate per `Master.md` Lighting Rules. |

## FX

| ID | Name | Reusable | Priority | Status | First Used | Reuse Notes |
|---|---|---|---|---|---|---|
| FX-001 | Rain Streak Overlay | Reusable | High | — | — | Applied in Premiere, not baked into illustration unless static rain texture is needed. |
| FX-002 | Drifting Light Particles | Reusable | Medium | — | — | Use for loss-to-hope transition scenes. |

## Typography

| ID | Name | Reusable | Priority | Status | First Used | Reuse Notes |
|---|---|---|---|---|---|---|
| TYPE-001 | Title Card Font Set | Reusable | High | — | — | Minimal/elegant per `StyleGuide.md` Typography. |
| TYPE-002 | Lyric Subtitle Style | Reusable | High | — | — | No excessive animation. |

## Logos

| ID | Name | Reusable | Priority | Status | First Used | Reuse Notes |
|---|---|---|---|---|---|---|
| LOGO-001 | NotesSamurai Wordmark | Reusable | High | Approved | — | Used on end screens and thumbnails only, never in-frame illustration. |

## Transitions

| ID | Name | Reusable | Priority | Status | First Used | Reuse Notes |
|---|---|---|---|---|---|---|
| TRANS-001 | Cross Dissolve (Standard) | Reusable | High | Approved | — | Default scene-to-scene transition per `Master.md` Motion Guidelines. |
| TRANS-002 | Fade to Black (Outro Only) | Reusable | High | Approved | — | Reserved for final scene of each song. |

---

## Reusable Assets Summary

Assets marked `Reusable` should be checked against this list before generating a new equivalent asset for a new song. Prefer reuse over regeneration.

## Project Specific Assets Summary

Assets marked `Project-Specific` are not guaranteed to transfer between songs and should be re-evaluated per project.
