# Production Flow

> Explains the complete NotesSamurai production workflow, stage by stage, from idea to archive. This document describes *what happens and why* at each stage; it does not restate the contents of the documents produced at each stage. See `RepositoryGuide.md` Section 4 for the condensed flow diagram and `ProductionFlowchart.md` for the visual Mermaid version of this same pipeline.

---

## Idea

Origin of a song concept — theme, mood, and initial direction. Captured informally until it has enough shape to begin `Lyrics.md`.

**Objective:** Establish a theme consistent with `StyleGuide.md` Brand Philosophy before any documentation begins.

---

## Songwriting

Lyrics are written and refined outside the repository until stable enough to document.

**Objective:** Produce a lyric set that expresses the Core Emotion progression defined in `StyleGuide.md`.

---

## Lyrics Documentation

Finalized lyrics (and translations, if multilingual) are recorded in the song's `Lyrics.md`.

**Objective:** Create the authoritative lyric reference that every later stage — storyboard, prompts, editing, subtitles — will point back to.

---

## Creative Analysis

The lyrics are read against `StyleGuide.md` to identify narrative purpose, emotional tone, and symbol usage per section.

**Objective:** Confirm the song's arc matches Beginning → Conflict → Decision → Transformation → Hope before scene planning begins.

---

## Storyboard

Scenes are planned and documented in the song's `Storyboard.md`, each scene linked to a lyric section from `Lyrics.md`.

**Objective:** Translate the emotional arc into a concrete, efficient sequence of scenes with defined camera, lighting, and color per `Master.md`.

---

## Production Planning

The full `ProductionChecklist.md` is run against the storyboard before any generation begins.

**Objective:** Catch story, visual, consistency, and pacing issues while they are still cheap to fix.

---

## Prompt Development

Each approved scene is expanded into a structured entry in `PromptPack.md`.

**Objective:** Produce generation-ready prompts that follow `Master.md` Prompt Structure and Negative Prompt standards.

---

## AI Review

Prompts and storyboard logic receive a second-opinion creative pass, per the AI role structure in `RepositoryGuide.md` Section 10.

**Objective:** Catch continuity or interpretation issues before spending generation attempts.

---

## Image Generation

Scenes are generated and every attempt is logged in `GenerationLog.md` until each scene reaches `Approved: Yes`.

**Objective:** Produce final, approved artwork for every scene with full iteration history preserved.

---

## Quality Review

Approved artwork is checked against `ProductionChecklist.md` Sections 2-9 (Visual, Character, Emotional, Pacing, Camera, Color, Symbol, Prompt validation) as a full-set pass, not just per-scene.

**Objective:** Confirm the complete scene set holds together as one consistent visual story before editing begins.

---

## Premiere Editing

Approved assets are assembled in Premiere Pro following the song's `EditingNotes.md`.

**Objective:** Apply motion, transitions, color grading, and audio sync without introducing motion or effects outside `Master.md` Motion Guidelines.

---

## Rendering

Final export is produced at the target resolution and aspect ratio.

**Objective:** Deliver a render that passes `ReleaseChecklist.md` Video and Quality Control sections.

---

## YouTube Release

Metadata is finalized in `YouTubeMetadata.md` and the full `ReleaseChecklist.md` is completed before publishing.

**Objective:** Publish with complete, consistent metadata and cross-platform copy.

---

## GitHub Archive

The completed project folder is moved to `/archive/` per `RepositoryGuide.md` Section 11, and `README_Project.md` is updated to reflect final status.

**Objective:** Preserve the full production history and free `/projects/` for active work, without losing any documentation.

---

## Stage Dependency Note

No stage should begin before the prior stage's governing document is complete. A storyboard should not be written against unfinished lyrics; prompts should not be developed against an unapproved storyboard. This ordering is what keeps rework rare.
