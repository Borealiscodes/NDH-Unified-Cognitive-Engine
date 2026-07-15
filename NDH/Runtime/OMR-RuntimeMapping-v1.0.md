# 📘 **OMR → Runtime Mapping Table — v1.0**  
### *Cross‑Manifold Binding for NDH v3.0*

---

## **1. Purpose**

The **OMR→Runtime Mapping Table** binds **ConceptualPins** from the Orbital Marker Registry (OMR) to **ProtocolEmbeddedPins** in runtime/governance.

This mapping ensures:

- conceptual altitude → runtime invariants  
- lineage → governance  
- plateaus → operational manifolds  
- milestones → runtime transitions  
- stability gradients → ethical physics  
- orbital rings → runtime altitude locks  
- continuity → COS/GBS/SDL/DNL‑COI coherence  

This table is required before NDH runtime can initialize.

---

## **2. Mapping Table (Canonical)**

Each conceptual pin maps to one or more runtime pins.

```yaml
OMR-Runtime-Mapping-v1.0:

  LP-01: GBS3-Lineage-COS
  LP-02: GBS3-Lineage-COS

  PP-01: GBS-v3.0-GovernanceMembrane
  PP-02: COS-v3.0-ExpansionManifold
  PP-03: COS-v3.0-DimensionalManifold

  MP-01: COS-v3.0-GenesisRuntime
  MP-02: COS-v3.0-TriArchitectureRuntime
  MP-03: COS-v3.0-OperationalManifold

  SP-01: DNL-COI-v3.0-StabilityPhysics
  SP-02: DNL-COI-v3.0-MSPPhysics

  ZG-01: DNL-COI-v3.0-StillnessGradient
  ZG-02: DNL-COI-v3.0-WideAngleGradient

  OM-01: COS-v3.0-AltitudeRingI
  OM-02: COS-v3.0-AltitudeRingII
  OM-03: COS-v3.0-AltitudeRingIII

  CP-01: ContinuityRuntimePin
```

---

## **3. Mapping Rules**

Each rule begins with a Guided Link.

- **Rule 1 — Every ConceptualPin must map to a RuntimePin**  
- **Rule 2 — Mapping must be altitude‑consistent**  
- **Rule 3 — No unmapped conceptual pins allowed**  
- **Rule 4 — Runtime pins must be ProtocolEmbeddedPins**  
- **Rule 5 — Mapping must be acyclic**  

If any rule fails → **Pin Validator blocks build** → **Pin Loader blocks runtime**.

---

## **4. Mapping Integrity Checks**

The mapping table must satisfy:

- **Completeness** — all OMR pins mapped  
- **Uniqueness** — no duplicate conceptual→runtime pairs  
- **Lineage Binding** — LP pins must map to governance pins  
- **Operational Binding** — MP pins must map to COS runtime  
- **Physics Binding** — SP/ZG pins must map to DNL‑COI  
- **Continuity Binding** — CP pins must map to continuity runtime locks  

---

## **5. Example Mapping Failure Report**

```yaml
MappingReport:
  status: "FAILED"
  errors:
    - "Unmapped ConceptualPin: PP-03"
    - "Invalid mapping: LP-02 → COS-v3.0-OperationalManifold (must map to governance)"
    - "Missing runtime pin: DNL-COI-v3.0-StillnessGradient"
```

---

## **6. Runtime Integration**

The **Pin Loader** uses this table to:

- load conceptual altitude  
- bind runtime invariants  
- activate lineage vectors  
- initialize stability physics  
- lock continuity  

If mapping fails → NDH runtime aborts.

---

