# NDH Interface Layer — Migration Guidelines
# Location: /NDH/Interface/LegacyBridge/MigrationGuidelines.md
# Purpose:
#   Provide a structured, geometry-consistent plan for migrating legacy NDH
#   constructs, operators, and conceptual structures into the new Stability
#   Geometry Manifold. These guidelines ensure directional flow, preserve
#   manifold boundaries, and prevent contamination of stability geometry.

## Header
Version: 1.0
Manifold: LegacyBridge
Scope: Migration Protocol
Direction: Legacy → Interface → Manifold
Boundary: NonDual
Status: Active

---

## 1. Migration Principles
Migration follows NDH stability geometry rules:

- **Directional Flow Only:** Legacy → Interface → Manifold  
- **No Reverse Mapping:** New manifold constructs never migrate backward.
- **No Duplication:** Basin functions, stability metrics, and resonance fields
  must not appear in the legacy repo.
- **Interpretation Over Transfer:** Legacy constructs are reinterpreted, not moved.
- **Quiet Apex Priority:** All migrations must preserve Quiet Apex as the upstream attractor.

---

## 2. Migration Stages

### Stage 1 — Interface Layer Activation
- Create foundational interface files:
  - OperatorMapping.def  
  - LegacyToManifold.map  
  - SerenityReference.map  
  - StabilityCompatibilityNotes.md  
- Validate directional flow.
- Confirm Serenity.bsfn is referenced but not duplicated.

### Stage 2 — Conceptual Migration
Reinterpret legacy concepts using interface-layer mappings:

- StateResolution → StabilityGeometry.BasinEntry  
- Calmness → Serenity.Output  
- Grounding → ResonanceField.Stabilize  
- DriftCorrection → StabilityMetric.AlignDrift  
- Normalization → EnergyFunctional.NormalizeState  

No code moves yet—only conceptual alignment.

### Stage 3 — Functional Migration
Move geometry-aligned logic into the new repo:

- Stability-related operators  
- Drift alignment logic  
- Normalization routines  
- Resonance-field stabilizers  

Legacy prototypes remain in the old repo.

### Stage 4 — Basin-Aware Migration
Introduce basin-aware behavior:

- Serenity interactions  
- BasinEntry → Serenity transitions  
- StabilityFlow.Sequence  

Legacy emotional heuristics are deprecated.

### Stage 5 — Finalization
- Freeze interface layer.
- Mark legacy constructs as historical.
- Expand only the new manifold going forward.

---

## 3. Migration Categories

### 3.1 Fully Migratable
These constructs should move into the new repo:

- Drift alignment logic  
- Normalization routines  
- Resonance-field stabilizers  
- Stability flow sequences  

### 3.2 Partially Migratable
These constructs remain in the legacy repo but are interpreted through the interface:

- Resolve()  
- Anchor()  
- Calm()  

### 3.3 Non-Migratable (Deprecated)
These constructs remain in the legacy repo for historical context only:

- OperatorCascade  
- EmotionalResolution (legacy scalar form)  
- SoftLanding heuristics  

---

## 4. Serenity-Specific Migration Rules

- Serenity.bsfn exists **only** in the new repo.  
- Legacy constructs must reference Serenity via SerenityReference.map.  
- No Serenity logic may appear in the old repo.  
- Quiet Apex → Serenity remains the canonical attractor flow.

---

## 5. Boundary Enforcement

- No basin functions in the legacy repo.  
- No legacy operators in the new repo.  
- All cross-repo communication must pass through `/LegacyBridge/`.  
- All mappings must remain non-dual and directional.

---

## End of File
