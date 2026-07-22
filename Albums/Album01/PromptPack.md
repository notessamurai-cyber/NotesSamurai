# Prompt Pack

> Master reusable prompt template collection for NotesSamurai. This is a working document, not a final prompt archive — populate one entry per scene per song, using this schema. Final storyboard prompts live in the song's scene plan file (e.g. `finalsceneplan.md`); this file is the structured working version used during iteration.
> Reference `Master.md` for Prompt Structure and Negative Prompt standards.

---

## Template

```
### Scene ID
<Song>-<SceneNumber> (e.g. UrbanEdge-06)

### Purpose
One line — why this image exists.

### Prompt
Primary generation prompt. Illustration description only. No camera movement language.

### Additional Prompt
Optional supplementary detail appended for regeneration/refinement passes.

### Negative Prompt
Standard block from `Master.md`, plus any scene-specific exclusions.

### Continuity Notes
Character/environment consistency requirements referencing prior approved scenes.

### Lighting Notes
Time-of-day stage, light source motivation, bloom/flare guidance per `Master.md` Lighting Rules.

### Composition Notes
Framing, negative space, depth layering for parallax support.

### Color Notes
Color Script stage per `Master.md`.

### Image Generation Notes
Model-specific settings, seed, aspect ratio, resolution target.

### Premiere Notes
Motion plan reference — see `EditingNotes.md` for full detail; summarize only here.

### Approval Status
Draft / In Review / Approved / Rejected

### Prompt Revision History

| Version | Date | Change | Author |
|---|---|---|---|
| v1 | — | Initial draft | — |
```

---

## Usage

- One entry per scene, per song.
- Do not duplicate storyboard prose from the song's scene plan — reference it by Scene ID.
- Increment `Prompt Revision History` on every regeneration attempt; do not overwrite prior versions.
- Cross-reference each entry's Scene ID with the corresponding row in `GenerationLog.md`.
