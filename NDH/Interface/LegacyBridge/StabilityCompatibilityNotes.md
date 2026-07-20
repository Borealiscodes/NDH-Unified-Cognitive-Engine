# NDH Interface Layer — Stability Compatibility Notes
# Location: /NDH/Interface/LegacyBridge/StabilityCompatibilityNotes.md
# Purpose:
#   Document which legacy NDH constructs remain compatible with the new Stability
#   Geometry Manifold, which require reinterpretation, and which are deprecated.
#   This file ensures safe cross-repo referencing without violating manifold
#   boundaries or stability geometry constraints.

## Header
Version: 1.0
Manifold: LegacyBridge
Scope: Compatibility Assessment
Boundary: NonDual
Status: Active

---

## 1. Fully Compatible Legacy Constructs
These constructs align naturally with stability geometry and require no structural
changes. They may be referenced directly through the interface layer.

### 1.1 Quiet Apex
- **Status:** Canonical
- **Reason:** Quiet Apex remains the highest-stability attractor.
- **Manifold Role:** Upstream attractor feeding Serenity.bsfn.
- **Mapping:** QuietApex.op

### 1.2 DriftAlign (conceptual)
- **Status:** Compatible with reinterpretation
- **Reason:** Aligns with StabilityMetric.AlignDrift.
- **Manifold Role:** Drift correction within stability geometry.

### 1.3 Normalization (conceptual)
- **Status:** Compatible with reinterpretation
- **Reason:** Maps cleanly to EnergyFunctional.NormalizeState.

---

## 2. Partially Compatible Constructs
These constructs require reinterpretation within the manifold but remain usable
through interface-layer translation.

### 2.1 Resolve()
- **Legacy Role:** Collapse unstable states.
- **Manifold Interpretation:** StabilityMetric.Settle()
- **Notes:** Deprecated as an operator; retained conceptually.

### 2.2 Anchor()
- **Legacy Role:** Ground oscillatory states.
- **Manifold Interpretation:** ResonanceField.Clamp()
- **Notes:** Operator replaced; conceptual behavior preserved.

### 2.3 Calm()
- **Legacy Role:** Emotional amplitude reduction.
- **Manifold Interpretation:** Serenity.Apply()
- **Notes:** Calmness becomes a basin-function output.

---

## 3. Deprecated Constructs
These constructs do not map cleanly into stability geometry and should not be
used in new development. They remain in the legacy repo for historical context.

### 3.1 OperatorCascade
- **Reason:** Replaced by StabilityFlow.Sequence.
- **Notes:** Cascades violate manifold curvature constraints.

### 3.2 EmotionalResolution (legacy form)
- **Reason:** Replaced by Serenity.Output.
- **Notes:** Legacy emotional scalar models are not geometry-aligned.

### 3.3 SoftLanding (legacy heuristic)
- **Reason:** Replaced by BasinEntry → Serenity.
- **Notes:** Legacy heuristics lack basin-awareness.

---

## 4. Stability Geometry Dependencies
The following constructs exist only in the new repo and must never be duplicated
in the old repo:

- **StabilityMetric**
- **ResonanceField**
- **EnergyFunctional**
- **Serenity.bsfn**
- **StabilityFlow.Sequence**

All references must pass through the interface layer.

---

## 5. Boundary Rules
- Legacy constructs may be *interpreted* but not *imported* into the new repo.
- Basin functions must never appear in the old repo.
- All Serenity interactions must use SerenityReference.map.
- Directional flow is strictly: Legacy → Interface → Manifold.

---

## End of File
