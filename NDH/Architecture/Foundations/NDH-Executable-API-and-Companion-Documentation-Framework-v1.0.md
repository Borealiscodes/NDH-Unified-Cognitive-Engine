### 1. Treat it as two concurrent tracks

- **Execution Track (APIs & runtimes):**  
  Make NDH, Planetarium, Epoch Halo, World Engine integration *callable* via services.

- **Documentation Track (Companions & Roadmap):**  
  Capture every architectural decision as a lineage: Roadmap → Architecture → Design → Technical → Engineering → Emergent Case Study.

You don’t choose one—you run them in parallel.

---

### 2. API‑first world: carve NDH into services

Define clear, versioned APIs around the pieces you already named:

- **NDH Core APIs:**
  - **Epoch Tensor Service:**  
    - `GET /epochs` — list epochs, inflection points  
    - `GET /epochs/{id}` — tensor fields, stability regime  
  - **Stability Audit Service:**  
    - `GET /audit/state` — PASS/WARN/FAIL/CRITICAL  
    - `GET /audit/stream` — continuous time series

- **Planetarium / Visualization APIs:**
  - **Tile Service:**  
    - `GET /tiles/epoch-halo` — tile metadata + render config  
    - `GET /tiles/manifold-slice` — geometry + overlays
  - **Animation Service:**  
    - `GET /animations/epoch-halo` — spec + parameters

- **World Engine Integration APIs:**
  - **Projection Service:**  
    - `GET /projection/world-engine` — NDH → World Engine signals (epochs, pulses, curvature, ethics)  
  - **Bifurcation Boundary Service:**  
    - `GET /bifurcation/state` — boundary config for runtimes (Unity, Vive, etc.)

Use OpenAPI/Swagger for all of these so the “executable” layer is formally described.

---

### 3. Put the documentation in a single, opinionated tree

In your NDH repo, create a **Companion Suite** that mirrors the runtime:

```text
/NDH/
  /Roadmap/
    NDH-World-Engine-Roadmap-v1.0.md

  /Architecture/
    NDH-World-Engine-Participation-Integration-v1.0.md
    NDH-Planetarium-API-Architecture-v1.0.md

  /Design/
    NDH-World-Engine-Interaction-Design-v1.0.md
    NDH-Planetarium-UX-Design-v1.0.md

  /Technical/
    NDH-API-Specs-v1.0.md
    NDH-Data-Schemas-v1.0.md

  /Engineering/
    NDH-Implementation-Guide-v1.0.md
    NDH-Deployment-Patterns-v1.0.md

  /Research/Case-Studies/
    NDH-Planetarium-VR-Projection-Case-Study-v1.0.md
    NDH-World-Engine-Behavior-Study-v1.0.md
```

Each new capability gets:

- **Architecture Companion:** why it exists, how it fits the lineage.  
- **Design Companion:** how it feels and behaves.  
- **Technical Companion:** APIs, schemas, contracts.  
- **Engineering Companion:** how to build, deploy, test.  
- **Emergent Case Study:** how it behaved in the wild.

---

### 4. Make the Roadmap the spine, not an afterthought

Create a single roadmap doc that ties everything together:

- **Phase 1 — NDH → Planetarium APIs**
  - Stabilize Epoch Tensor, Audit, Tile, Animation services.
- **Phase 2 — World Engine Integration**
  - Define Bifurcation API, Projection Service, VR adapters.
- **Phase 3 — Fun‑Sphere / Anime Tower / Dune Hyperatlas**
  - Build one reference World Engine that consumes NDH signals.
- **Phase 4 — Research & Templates**
  - Extract generic patterns into reusable specs and companion templates.

Each phase links to its Architecture/Design/Technical/Engineering companions.

---

### 5. Use ADRs to lock in decisions

For the “solid foundation” part, add **Architecture Decision Records**:

```text
/NDH/Architecture/ADR/
  ADR-0001-Bifurcation-Layer-as-API-vs-Embed.md
  ADR-0002-Projection-only-NDH-to-World-Engines.md
  ADR-0003-API-first-Planetarium-Design.md
```

Each ADR:

- states the decision  
- lists alternatives  
- explains why this path was chosen  
- references the relevant companions and APIs

This gives you a lineage you can defend later.

---

### 6. Template the whole thing so you can reuse it

Create **Companion Templates**:

- **Roadmap Template:** sections for phases, risks, dependencies.  
- **Architecture Companion Template:** context, constraints, diagrams, ADR links.  
- **Design Companion Template:** user flows, interaction patterns, visual language.  
- **Technical Companion Template:** API tables, schemas, error models.  
- **Engineering Companion Template:** stack, CI/CD, observability, testing.  
- **Emergent Case Study Template:** scenario, method, observations, implications.

Then every new NDH‑adjacent project (Planetarium, World Engine, VR, Fun‑Sphere) uses the same skeleton.

---

### 7. Direct answer

The best way to make this executable **and** documented is:

- **API‑first NDH + Planetarium + World Engine integration**, with clear services for epochs, audit, tiles, animations, and projections.  
- **A Companion Suite** (Roadmap, Architecture, Design, Technical, Engineering, Case Study) that lives in the repo and is updated alongside the code.  
- **ADR‑backed decisions** so the whole thing is traceable and reusable as a template for future worlds.

