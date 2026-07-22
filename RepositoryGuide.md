# Repository Guide

> Master handbook for the NotesSamurai production system. Read this first if you are new to the repository — it explains how everything fits together and where to go next. This document does not duplicate content from other files; it references them.

---

## 1. Repository Philosophy

NotesSamurai is an AI-assisted creative studio, not a channel with uploads. The repository is the studio: every song is a production run through a fixed pipeline, not a one-off asset. The documentation exists so that creative identity, technical process, and production history persist independently of any single contributor, tool, or AI model.

The system is designed around one assumption: consistency compounds. A protagonist that never changes, a color script that never drifts, a workflow that never varies — these let quality increase over time instead of resetting with every new song. See `Master.md` and `StyleGuide.md` for what stays constant; this guide explains how the repository is organized to protect that constancy.

---

## 2. Repository Structure

```
/docs/
/projects/
/templates/
/workflow/
/assets/
/archive/
```

**`/docs/`** — Studio-wide identity and process documentation that applies to every project: `Master.md`, `StyleGuide.md`, `RepositoryGuide.md`, `README.md`. Nothing project-specific lives here.

**`/projects/`** — One subfolder per song (e.g. `/projects/UrbanEdge/`). Contains that song's `README_Project.md`, storyboard, prompt pack, generation log, editing notes, and final exports. Everything specific to a single production lives here and nowhere else.

**`/templates/`** — Blank, reusable copies of every per-song document (`ProductionChecklist.md`, `AssetList.md`, `PromptPack.md`, `GenerationLog.md`, `EditingNotes.md`, `ReleaseChecklist.md`, `YouTubeMetadata.md`, `README_Project.md`). Copy from here into a new `/projects/<Song>/` folder — never edit templates to fit one song.

**`/workflow/`** — Process-level references: the standard production workflow, naming conventions, commit conventions. Supports the studio's operations rather than any one song's creative content.

**`/assets/`** — Reusable, cross-project assets tracked in `AssetList.md`: approved character sheets, recurring locations, logos, transitions. Project-specific assets stay inside their `/projects/<Song>/` folder instead.

**`/archive/`** — Completed, released productions moved out of active `/projects/` once `ReleaseChecklist.md` is fully checked. Read-only in practice; historical reference only.

---

## 3. Documentation Hierarchy

Documents are read in this order — each layer depends on the one above it:

```
README.md
   ↓
StyleGuide.md
   ↓
Master.md
   ↓
Project README (README_Project.md)
   ↓
Production Documents
(ProductionChecklist.md, AssetList.md, PromptPack.md,
 GenerationLog.md, EditingNotes.md, ReleaseChecklist.md,
 YouTubeMetadata.md)
```

- **`README.md`** — entry point to the repository itself. Read first, always.
- **`StyleGuide.md`** — the studio's creative identity: philosophy, emotional arc, symbol meanings. Read before any creative decision.
- **`Master.md`** — the technical visual bible: art style, character lock, prompt structure, negative prompts. Read before any prompt is written.
- **`README_Project.md`** — the specific song's summary and status. Read before touching that song's production files.
- **Production Documents** — working files used during active production of a single song. Read/updated continuously during that song's pipeline.

No production document should be read or trusted in isolation from the layers above it.

---

## 4. Standard Production Workflow

```
Song Idea
   ↓
Lyrics
   ↓
Story Analysis
   ↓
Storyboard
   ↓
Production Planning
   ↓
Prompt Preparation
   ↓
Image Generation
   ↓
Editing
   ↓
Quality Control
   ↓
Release
   ↓
Archive
```

- **Song Idea → Lyrics** — creative origin, captured in the song's `README_Project.md`.
- **Story Analysis → Storyboard** — theme and lyrics mapped into a scene plan, validated against `StyleGuide.md` and `Master.md`.
- **Production Planning** — `ProductionChecklist.md` run in full before generation begins.
- **Prompt Preparation** — scenes converted into structured entries in `PromptPack.md`.
- **Image Generation** — attempts tracked in `GenerationLog.md` until each scene is approved.
- **Editing** — approved assets assembled per `EditingNotes.md` in Premiere Pro.
- **Quality Control → Release** — `ReleaseChecklist.md` and `YouTubeMetadata.md` completed in full.
- **Archive** — project folder moved to `/archive/`, `README_Project.md` updated to reflect final status.

No stage should be skipped. A stage may be fast, but it must leave a record in the corresponding document.

---

## 5. Folder Naming Convention

Project folders use the song title in PascalCase, no spaces, no punctuation:

```
UrbanEdge
CrosswalkOfTomorrow
BetweenNightAndMorning
```

- One folder per song, matching the song's working title.
- No abbreviations at the folder level — abbreviations belong to file-level Scene IDs (see Section 6).
- Consistency here matters because folder names are referenced across `AssetList.md`, `GenerationLog.md`, and cross-project links. A renamed folder breaks every reference to it.

---

## 6. File Naming Convention

| Asset Type | Convention | Example |
|---|---|---|
| Storyboard | `<SongTitle>_finalsceneplan.md` | `UrbanEdge_finalsceneplan.md` |
| Scene ID (used across Prompt/Generation/Editing docs) | `<Initials>-<SceneNumber>` | `UE-01`, `UE-02` |
| Prompt files | Entries inside `PromptPack.md`, keyed by Scene ID | `UE-06` |
| Artwork | `<Initials>-<SceneNumber>_v<OutputVersion>` | `UE-06_v2` |
| Exports | `<Initials>_Export_<Resolution>` | `UE_Export_4K` |
| Premiere project | `<Initials>_Premiere.prproj` | `UE_Premiere.prproj` |
| Audio | `<Initials>_Master.wav` | `UE_Master.wav` |
| Version history | `<Initials>-v<Major>.<Minor>` | `UE-v1.0`, `UE-v1.1` |

Initials are derived from the song title (e.g. Urban Edge → `UE`) and fixed at project creation — recorded in that song's `README_Project.md` so they never need to be re-derived.

---

## 7. Git Commit Convention

| Prefix | Use For |
|---|---|
| `docs:` | Changes to `/docs/` (Master.md, StyleGuide.md, RepositoryGuide.md, README.md) |
| `feat:` | New song project, new scene, new template |
| `fix:` | Corrections to existing content (prompt fixes, continuity corrections, broken links) |
| `refactor:` | Restructuring without changing meaning (file moves, renames, reorganization) |
| `assets:` | Additions/changes to `/assets/` or `AssetList.md` |
| `release:` | Commits tied to a song's publish event |
| `archive:` | Moving a completed project into `/archive/` |

One prefix per commit. A commit touching both documentation and assets should be split into two commits.

---

## 8. Versioning Strategy

| Version Type | Scope | Incremented When |
|---|---|---|
| Repository Version | Entire repository | Structural changes to `/docs/`, `/templates/`, or workflow |
| Project Version | Single song | Major storyboard or creative direction changes (`UE-v1.0` → `UE-v1.1`) |
| Artwork Version | Single scene | Each new generation attempt (`Output Version` field in `GenerationLog.md`) |
| Prompt Version | Single scene's prompt | Each prompt revision (`Prompt Revision History` in `PromptPack.md`) |
| Release Version | Published output | Each public release of a song, including re-uploads or corrected versions |

Version numbers are never reused. A rejected artwork version stays logged in `GenerationLog.md` rather than being overwritten by the next attempt.

---

## 9. Collaboration Rules

- Never overwrite an asset already marked `Approved: Yes` in `GenerationLog.md`. Generate a new version instead.
- Never modify `StyleGuide.md` or `Master.md` directly to accommodate a single song. If a rule needs to change, it changes for the whole studio, deliberately, with a `docs:` commit.
- Always update `GenerationLog.md` for every generation attempt, approved or not.
- Always document major creative decisions in the song's `README_Project.md` (Known Issues, Lessons Learned) rather than leaving them undocumented in chat history or memory.
- When in doubt about whether something is reusable, check `AssetList.md` before creating a new asset.

---

## 10. AI Workflow

| Role | Responsibility |
|---|---|
| ChatGPT | Creative analysis — theme breakdown, lyric interpretation, early concept work |
| Claude | Documentation — pipeline files, storyboards, structured production documents |
| Gemini | Creative review — second-opinion pass on storyboards and prompts |
| Image Generation Model | Scene artwork, per `PromptPack.md` and logged in `GenerationLog.md` |
| Premiere Pro | Video production, per `EditingNotes.md` |
| Future AI tools | Integrate into the existing role structure above; new tools take on an existing responsibility rather than creating a new one, unless this guide is deliberately updated |

Every AI tool used in production is a role, not a dependency. Swapping the image generation model, for instance, changes the `AI Model` field in `GenerationLog.md` — it does not change `Master.md`, `PromptPack.md` structure, or any other document.

---

## 11. Repository Maintenance

- Archive a project to `/archive/` only after `ReleaseChecklist.md` is fully checked.
- Reuse templates from `/templates/` for every new project rather than copying a prior song's filled-in files.
- Remove duplicate or superseded documents rather than accumulating versions side by side — version history belongs inside a document (revision tables, logs), not as multiple similarly-named files.
- Keep `AssetList.md` synchronized — an asset generated but not logged does not effectively exist for reuse purposes.
- Periodically confirm that `/docs/` files are still accurate before starting a new song; drift here propagates into every project.

---

## 12. Scalability

The structure is built to hold constant as production volume grows:

- **10 songs** — `/projects/` holds ten folders; `/archive/` is mostly empty. Manual tracking in `AssetList.md` remains straightforward.
- **50 songs** — Reuse rates in `AssetList.md` become the primary efficiency lever; prefer existing Locations/Environment/Lighting assets over new generation by default.
- **100 songs** — `/archive/` becomes the majority of the repository. Consider splitting `AssetList.md` by category file if a single table becomes unwieldy, without changing its schema.
- **Future albums** — Group related songs under a shared theme reference inside each `README_Project.md`; no new folder tier is required unless albums need their own shared assets.
- **Multiple artists** — Extend the Character metadata in `AssetList.md` (new `CHAR-00X` entries) rather than forking `Master.md`; the pipeline stays singular even as protagonists multiply.
- **Collaborative productions** — Section 9's collaboration rules are the scaling mechanism — they hold regardless of contributor count.

The pipeline does not change shape as it scales. Only the volume of folders and log entries increases.

---

## 13. Guiding Principles

1. Documentation before generation.
2. Consistency over complexity.
3. Emotion before spectacle.
4. Reuse before recreation.
5. Quality over quantity.
6. Version everything.
7. Keep the workflow simple.
8. Never lose creative history.
9. Every project teaches the next one.
10. Build systems, not shortcuts.

---

*End of RepositoryGuide.md — the operations manual for the NotesSamurai production system. All other documents are referenced here, not repeated. If a rule appears to conflict between this guide and another document, `Master.md` and `StyleGuide.md` govern creative identity; this guide governs process and structure.*
