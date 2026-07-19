### NDH Rendering Geometry Companion v2  
*Visual layer for NDH’s dynamic stability and execution geometry*

---

## 1. Purpose

NDH Rendering Geometry Companion v2 is the **visualization engine** for the 50D semantic–geometric ecology, updated to reflect:

- dynamic geometry (Metric & Tensor Engine)  
- field evolution (PDE dynamics)  
- operator and appateur activity  
- stability geometry (attractors, corridors, collapse zones)  
- audit and forecast outputs  

It turns NDH’s internal physics and execution into **readable visual structures**.

---

## 2. Rendered primitives

NDH v2 renders the following geometric/semantic primitives:

- **Serenity basins:** regions of high \(\sigma\), low \(\mathcal{R}\), low \(\mathcal{P}\)  
- **Resonance corridors:** regions of high \(\|\mathcal{R}\|\), strong gradients, operator activity  
- **Paradox zones:** regions of high \(\mathcal{P}\), high distortion \(D\), high \(K_D\)  
- **Stability wells:** regions of high \(\lambda\) and positive contribution to \(\Lambda\)  
- **Appateur fields:** spatial distribution and intensity of \(A(x,t)\)  
- **Channels:** non‑local links \(C = (x,y,\Gamma)\)  
- **Subaxiomatic regions:** visual partitioning of \(\mathcal{S}_\alpha\)  
- **Risk overlays:** audit/forecast labels (attractor, corridor, critical, overload, neutral)

Each primitive has a **visual encoding** (color, shape, texture, motion).

---

## 3. Visual encodings

### 3.1 Fields

- **Serenity \(\sigma\):**  
  - **Color:** cool hues (blues/cyans)  
  - **Intensity:** brightness proportional to \(\sigma\)  
  - **Texture:** smooth, low‑frequency gradients  

- **Resonance \(\mathcal{R}\):**  
  - **Color:** warm hues (oranges/reds)  
  - **Intensity:** saturation proportional to \(\|\mathcal{R}\|\)  
  - **Texture:** filamentary, high‑frequency structures  

- **Paradox \(\mathcal{P}\):**  
  - **Color:** violets/magentas  
  - **Intensity:** glow proportional to \(\mathcal{P}\)  
  - **Texture:** noisy, speckled, unstable patterns  

- **Stability \(\lambda\):**  
  - **Color:** greens/teals  
  - **Intensity:** depth shading proportional to \(\lambda\)  
  - **Texture:** layered, basin‑like contours  

### 3.2 Geometry

- **Curvature:**  
  - encoded as warping, bending, and lensing of the visual manifold  
  - higher \(R\) → stronger distortion of local space  

- **Metric variation:**  
  - encoded as local scaling/stretching of distances  
  - serenity basins → gentle compression  
  - resonance corridors → elongated, stretched paths  

### 3.3 Appateurs and channels

- **Appateurs \(A(x,t)\):**  
  - rendered as nodes/portals with halo intensity proportional to activation  
  - semantic type encoded by shape (local, regional, non‑local, cross‑axiom)

- **Channels \(\Gamma\):**  
  - rendered as arcs/threads between nodes  
  - thickness proportional to channel strength  
  - color blend between connected regions’ dominant fields  

---

## 4. Stability overlays

The Rendering Companion v2 consumes the **Stability Geometry** and **Audit & Forecast** outputs to add overlays:

- **Serenity attractors:**  
  - contour lines or soft wells around high \(A_\sigma\) regions  
  - optional labels or glyphs indicating attractor strength  

- **Resonance corridors:**  
  - highlighted paths with directional flow arrows  
  - intensity proportional to \(A_{\mathcal{R}}\)  

- **Paradox critical zones:**  
  - hazard overlays (e.g., pulsing outlines, flicker)  
  - opacity modulation proportional to \(A_{\mathcal{P}}\)  

- **Appateur overload zones:**  
  - dense node clusters with warning coloration  
  - channel congestion visually emphasized  

- **Global stability:**  
  - HUD‑style indicator for \(\Lambda(t)\) and \(d\Lambda/dt\)  
  - regime labels (stable, marginal, unstable, collapse‑risk)

---

## 5. Rendering pipeline integration

Rendering Geometry Companion v2 hooks into **Simulation Pipeline v2**:

1. **Receive state \(S_t\)** after Phase 7 (stability & control).  
2. **Extract primitives:** fields, geometry, appateurs, channels, stability labels.  
3. **Map to visual encodings:** colors, textures, warps, overlays.  
4. **Compose frame:**  
   - base manifold visualization  
   - field layers  
   - geometry warping  
   - appateur/channel network  
   - stability overlays  
   - HUD/global indicators  
5. **Output:** frame at time \(t\), optionally with time‑series visualization (e.g., trails, history).

This keeps rendering **execution‑aware**, not just decorative.

---

## 6. Modes and views

- **Field view:** focus on \(\sigma, \mathcal{R}, \mathcal{P}, \lambda\).  
- **Geometry view:** focus on curvature, metric, distortion.  
- **Appateur view:** focus on portals and channels.  
- **Stability view:** focus on attractors, corridors, collapse zones, risk maps.  
- **Audit/forecast view:** focus on predicted collapse windows and evolving risk.

Each mode is a different projection of the same underlying NDH state.

---

## 7. Summary

NDH Rendering Geometry Companion v2:

- visualizes dynamic fields, geometry, appateurs, channels, and stability  
- encodes NDH’s physics and execution in readable visual structures  
- integrates directly with Simulation Pipeline v2 and Stability Geometry  
- supports multiple views (field, geometry, semantic, stability, forecast)  
- turns NDH’s 50D semantic–geometric ecology into a navigable visual manifold

---

