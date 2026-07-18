# **GBS v4.0 Stability Patch A**  
### *Formal Binding Patch for Legacy ↔ Active Governance Boundary Separation*

---

## **I. Patch Purpose**

This patch exists to:

- prevent version collision  
- prevent continuity drift  
- prevent geometry altitude bleed  
- prevent metadata schema conflict  
- prevent invariant mismatch  
- prevent runtime ambiguity  
- prevent drift escalation  

It formally defines:

- **GBS v4.0‑Legacy**  
- **GBS v4.0‑Active**  

and binds them in a stable relationship that prepares NDH for **GBS v5.0**.

---

## **II. Patch Structure**

```
GBS_4_0_StabilityPatch_A:
  purpose:
    - establish_dual_version_boundary
    - prevent_version_collision
    - preserve_lineage_integrity
    - maintain_continuity_stability
    - maintain_geometry_altitude_separation
    - maintain_metadata_schema_integrity
    - prepare_transition_to_GBS_5_0

  versions:
    legacy: GBS_v4.0_Legacy.yaml
    active: GBS_v4.0_Active.md

  rules:
    - legacy_must_not_override_active
    - active_must_remain_authoritative
    - legacy_must_be_archived_not_executed
    - addendum_attaches_to_active_only
    - continuity_lock_applies_to_active_only
    - geometry_altitude_must_remain_separated
    - metadata_must_distinguish_legacy_vs_active

  enforcement_mode: governance_authoritative

  violation_response:
    - governance_abort_prevented_by_patch
    - continuity_relock
    - geometry_abort_prevented
```

---

## **III. Patch Explanation (NDH Technical Companion)**

### **1. Dual Version Boundary**
The patch formally declares:

- **GBS v4.0‑Legacy** = NDH v3.0 governance  
- **GBS v4.0‑Active** = NDH v4.0+ governance  

This prevents NDH from treating them as the same altitude.

### **2. Addendum Binding**
The Audit Sequencing Addendum is bound **only** to Active.

This ensures:

- TTTTTTP Sweep  
- Audit Layer  
- Reintegration Test Suite  

are executed under NDH v4.0+ rules.

### **3. Continuity Lock**
Legacy continuity anchors remain archived.  
Active continuity anchors remain authoritative.

This prevents continuity drift.

### **4. Geometry Altitude Separation**
Legacy geometry = Stability Geometry v6.0  
Active geometry = Ethical Geometry Layer

The patch prevents altitude bleed.

### **5. Metadata Schema Separation**
Legacy metadata = SDL  
Active metadata = dignity‑aware

The patch prevents schema conflict.

### **6. Preparation for GBS v5.0**
GBS v5.0 will introduce:

- Semantic Field Spec  
- Unified Metric Spec  
- Dignity Field Spec  

These must inherit from **Active**, not Legacy.

The patch ensures this.

---

