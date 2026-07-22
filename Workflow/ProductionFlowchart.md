# Production Flowchart

> Visual navigation guide for the NotesSamurai repository. Each diagram below is a Mermaid rendering of a workflow already described in prose elsewhere — `RepositoryGuide.md`, `ProductionFlow.md`, `Master.md`, `StyleGuide.md`. This document does not introduce new rules; it renders existing ones visually.

---

## 1. Repository Structure

```mermaid
flowchart TD
    Root[NotesSamurai Repository]
    Root --> Docs[/docs/]
    Root --> Projects[/projects/]
    Root --> Templates[/templates/]
    Root --> Workflow[/workflow/]
    Root --> Assets[/assets/]
    Root --> Archive[/archive/]

    Docs --> D1[Master.md]
    Docs --> D2[StyleGuide.md]
    Docs --> D3[RepositoryGuide.md]
    Docs --> D4[README.md]

    Projects --> P1[Project Folder per Song]
    P1 --> P1a[Lyrics.md]
    P1 --> P1b[Storyboard.md]
    P1 --> P1c[Production Documents]

    Templates --> T1[Blank per-song document set]
    Assets --> A1[Reusable assets tracked in AssetList.md]
    Archive --> Ar1[Completed, released projects]
```

**Explanation:** `/docs/` governs the whole studio and never varies per song. `/projects/` holds one folder per song, structured identically. `/templates/` supplies the blank starting point for each new project. `/assets/` and `/archive/` support reuse and long-term history respectively. See `RepositoryGuide.md` Section 2 for full folder definitions.

---

## 2. Production Workflow

```mermaid
flowchart TD
    A[Idea] --> B[Songwriting]
    B --> C[Lyrics Documentation]
    C --> D[Creative Analysis]
    D --> E[Storyboard]
    E --> F[Production Planning]
    F --> G[Prompt Development]
    G --> H[AI Review]
    H --> I[Image Generation]
    I --> J[Quality Review]
    J --> K[Premiere Editing]
    K --> L[Rendering]
    L --> M[YouTube Release]
    M --> N[GitHub Archive]
```

**Explanation:** The full pipeline, one stage per node, matching `ProductionFlow.md` exactly. No stage is skipped; each stage's governing document must be complete before the next begins.

---

## 3. Creative Workflow

```mermaid
flowchart LR
    Theme[Theme / Idea] --> Lyrics[Lyrics.md]
    Lyrics --> Analysis[Creative Analysis vs StyleGuide.md]
    Analysis --> Arc{Matches Core Emotion arc?}
    Arc -- No --> Lyrics
    Arc -- Yes --> Storyboard[Storyboard.md]
    Storyboard --> Symbols[Symbol check vs StyleGuide.md Symbol Library]
    Symbols --> Ready[Ready for Production Planning]
```

**Explanation:** The creative loop that happens before any technical production work. A storyboard is not allowed to proceed until the underlying lyrics have been validated against the emotional arc defined in `StyleGuide.md`.

---

## 4. AI Workflow

```mermaid
flowchart LR
    ChatGPT[ChatGPT] -->|Creative Analysis| Storyboard[Storyboard.md]
    Claude[Claude] -->|Documentation| Docs[Pipeline Documents]
    Gemini[Gemini] -->|Creative Review| Storyboard
    ImageModel[Image Generation Model] -->|Scene Artwork| GenLog[GenerationLog.md]
    Premiere[Premiere Pro] -->|Video Production| Render[Final Render]
    Future[Future AI Tools] -.->|Integrates into existing role| ChatGPT
    Future -.-> Claude
    Future -.-> Gemini
    Future -.-> ImageModel
```

**Explanation:** Each tool occupies a fixed role, per `RepositoryGuide.md` Section 10. A new tool joining the pipeline takes over an existing role rather than creating a new one — the dotted lines indicate that substitution path.

---

## 5. Asset Workflow

```mermaid
flowchart TD
    Need[New scene needs an asset] --> Check{Exists in AssetList.md?}
    Check -- Yes --> Reuse[Reuse existing asset]
    Check -- No --> Create[Create new asset]
    Create --> Log[Log new entry in AssetList.md]
    Reuse --> Use[Use in Storyboard / PromptPack]
    Log --> Use
    Use --> Status{Reusable or Project-Specific?}
    Status -- Reusable --> AssetsFolder[/assets/]
    Status -- Project-Specific --> ProjectFolder[/projects/Song/]
```

**Explanation:** Reuse is checked before creation, matching `RepositoryGuide.md` Guiding Principle 4 ("Reuse before recreation"). Every asset's destination folder depends on its reusability classification from `AssetList.md`.

---

## 6. Release Workflow

```mermaid
flowchart TD
    QC[Quality Review Passed] --> Video[Video finalized]
    Video --> Meta[YouTubeMetadata.md completed]
    Meta --> Checklist[ReleaseChecklist.md fully checked]
    Checklist --> Publish[Video Published]
    Publish --> Social[Cross-post: Instagram / X / Discord]
    Social --> ArchiveStep[Move project to /archive/]
    ArchiveStep --> ReadmeUpdate[Update README_Project.md status]
```

**Explanation:** Release cannot begin until Quality Review has passed. Archiving is the final step, not a parallel one — the project stays active in `/projects/` until publishing and cross-posting are both confirmed complete.

---

## 7. Version Control Workflow

```mermaid
gitGraph
    commit id: "docs: initial Master.md"
    commit id: "feat: new project UrbanEdge"
    branch UrbanEdge
    commit id: "feat: storyboard v1"
    commit id: "fix: scene 6 continuity"
    commit id: "assets: rooftop location added"
    commit id: "release: UrbanEdge v1.0"
    checkout main
    merge UrbanEdge
    commit id: "archive: UrbanEdge complete"
```

**Explanation:** Commit prefixes match `RepositoryGuide.md` Section 7 exactly. Each song can be developed on its own branch and merged back once released; the archive commit marks the end of that project's active lifecycle.

---

## 8. Project Lifecycle

```mermaid
stateDiagram-v2
    [*] --> Concept
    Concept --> InProduction: Storyboard approved
    InProduction --> QualityReview: All scenes approved
    QualityReview --> Released: ReleaseChecklist complete
    Released --> Archived: Moved to /archive/
    Archived --> [*]

    InProduction --> InProduction: Revision cycle (GenerationLog)
```

**Explanation:** A project can loop within "In Production" through revision cycles (tracked in `GenerationLog.md`) but cannot move to Quality Review until every scene is approved, and cannot be archived before release.

---

## 9. Folder Relationship

```mermaid
graph LR
    Templates[/templates/] -->|copied into| ProjectFolder[/projects/Song/]
    Docs[/docs/] -->|governs rules for| ProjectFolder
    Assets[/assets/] -->|reused by| ProjectFolder
    ProjectFolder -->|new reusable assets logged to| Assets
    ProjectFolder -->|on completion, moved to| Archive[/archive/]
```

**Explanation:** Templates flow into projects; docs govern projects without being altered by them; assets flow both directions (used by projects, and contributed back to when a project produces something reusable).

---

## 10. Documentation Hierarchy

```mermaid
flowchart TD
    README[README.md] --> StyleGuide[StyleGuide.md]
    StyleGuide --> Master[Master.md]
    Master --> ProjectReadme[README_Project.md]
    ProjectReadme --> ProdDocs[Production Documents]

    ProdDocs --> Checklist[ProductionChecklist.md]
    ProdDocs --> Assets[AssetList.md]
    ProdDocs --> Prompts[PromptPack.md]
    ProdDocs --> GenLog[GenerationLog.md]
    ProdDocs --> Editing[EditingNotes.md]
    ProdDocs --> Release[ReleaseChecklist.md]
    ProdDocs --> Meta[YouTubeMetadata.md]
```

**Explanation:** Matches `RepositoryGuide.md` Section 3. Read top to bottom on first encounter with the repository; production documents at the bottom are only meaningful once everything above them has been read.

---

*End of ProductionFlowchart.md — visual companion to `ProductionFlow.md` and `RepositoryGuide.md`. If a diagram and its prose counterpart ever disagree, the prose document governs; update the diagram to match.*
