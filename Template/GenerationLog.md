# Generation Log

> Tracks every AI image generation attempt across all NotesSamurai songs. One row per attempt, not per scene — a scene with three attempts has three rows. Reusable across all AI models and future migrations.
> Reference `PromptPack.md` for prompt versions and `ProductionChecklist.md` Section 10 (Image Generation Readiness) before logging the first attempt for a scene.

---

## Log Table

| Scene ID | Generation Date | AI Model | Prompt Version | Reference Images | Seed | Output Version | Strengths | Weaknesses | Revision Notes | Approved | Final Asset Location |
|---|---|---|---|---|---|---|---|---|---|---|---|
| UrbanEdge-01 | — | — | v1 | — | — | v1 | — | — | — | No/Yes | — |

---

## Field Definitions

| Field | Description |
|---|---|
| Scene ID | Scene identifier matching `PromptPack.md` and the song's storyboard file (e.g. `UrbanEdge-01`) |
| Generation Date | Date of this attempt (YYYY-MM-DD) |
| AI Model | Model/tool used for this attempt — field is model-agnostic to support future migration |
| Prompt Version | Version reference from `PromptPack.md` Prompt Revision History |
| Reference Images | Any input reference images used (character sheet, prior approved scene, style reference) |
| Seed | Generation seed, if the model supports and exposes one — optional |
| Output Version | Sequential version label for this scene's output (v1, v2, v3...), independent of Attempt count if outputs are batched |
| Strengths | What the output got right |
| Weaknesses | What the output got wrong (anatomy, consistency, color, composition, symbol misuse) |
| Revision Notes | What to change on the next attempt, if not approved |
| Approved | Yes / No |
| Final Asset Location | File path or storage location of the approved asset, once selected |

---

## Approval Workflow

1. **Draft Generation** — attempt logged with `Approved: No` by default.
2. **Review** — output checked against `ProductionChecklist.md` (Character Consistency, Color Progression, Symbol Consistency, Prompt Validation).
3. **Decision:**
   - **Approved** — mark `Approved: Yes`, record `Final Asset Location`, close out the scene.
   - **Rejected** — record `Weaknesses` and `Revision Notes`, open a new row for the next attempt.
4. **Finalization** — a scene is production-ready only when exactly one row for that Scene ID carries `Approved: Yes` and a populated `Final Asset Location`.

---

## Process Notes

- Do not delete rejected attempts — they document iteration history and inform future prompt revisions.
- Only one row per Scene ID should carry `Approved: Yes`.
- Model changes mid-production (e.g. migrating to a new AI model) must be logged as a new attempt row, not a silent substitution — preserves traceability.
- Cross-reference every row against the corresponding `PromptPack.md` entry and `ProductionChecklist.md` Section 10 before marking final.
