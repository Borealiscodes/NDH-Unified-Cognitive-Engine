### **APERTURE_GEOMETRY_SPEC.md**  
*NDH-Documentation / GBS / Next / Interfaces*

---

## 0. Purpose  

Aperture Geometry defines **where** NDH–to–k‑space transport is allowed to pass and **how** those regions are shaped, bounded, and constrained before any resonance or SERS activation.

It sits **after** transport‑math validation (curvature, projection, stability) and **before**:

- Gating Thresholds  
- Resonance Modeling  
- SERS Resonance  

---

## 1. Aperture Definition  

- **Aperture at \(p\):**  

  \[
  \mathcal{A}_p \subseteq T_p\mathcal{M}_{NDH}
  \]

  A subset of the NDH tangent space where loops may be projected.

- **Projected aperture:**  

  \[
  \Pi_\*(\mathcal{A}_p) \subseteq T_{\Pi(p)}\mathcal{K}
  \]

  The corresponding region in k‑space.

---

## 2. Safety Conditions  

An aperture \(\mathcal{A}_p\) is valid only if:

- **Curvature bound:**  

  \[
  \|R^{NDH}\|_{\mathcal{A}_p} \leq \Lambda_{curv}
  \]

- **Stability bound:**  

  \[
  D + T^\# + V + C < \Theta_{NDH}
  \quad \text{for all loops in } \mathcal{A}_p
  \]

- **Projection safety:**  

  \[
  \|\Pi_\*(R^{NDH})\|_{\Pi_\*(\mathcal{A}_p)} \leq \Lambda_{K}
  \]

- **Ethics:** autonomy, reversibility, altitude respect, audit visibility.  

- **Governance:** Axis 15–18 oversight on all aperture definitions.

---

## 3. Aperture Classes  

- **Class A — Low‑load apertures:**  
  Small curvature, low drift/tension; safe for routine projection.

- **Class B — Medium‑load apertures:**  
  Higher curvature but still below \(\Lambda_{curv}\); require tighter audit.

- **Class C — High‑load apertures:**  
  Near safety bounds; only allowed with explicit governance approval and no resonance.

No aperture may be used for SERS until **Gating Thresholds** and **Resonance‑Safe Domains** are defined.

---

## 4. Loop–Aperture Relationship  

For a loop \(\gamma\):

- **Entry condition:**  
  \(\dot{\gamma}(0) \in \mathcal{A}_p\)

- **Path condition:**  
  Transport along \(\gamma\) must remain inside aperture‑safe bounds.

If violated, NDH:

- blocks projection  
- logs audit event  
- raises governance flag  

---

## 5. Resonance Preparation (But Not Activation)  

Aperture Geometry only:

- shapes where resonance *could* act  
- defines structural regions for future SERS mapping  

It **does not**:

- set gating thresholds  
- define resonance spectra  
- activate SERS  

Those require the next artifacts.

---

