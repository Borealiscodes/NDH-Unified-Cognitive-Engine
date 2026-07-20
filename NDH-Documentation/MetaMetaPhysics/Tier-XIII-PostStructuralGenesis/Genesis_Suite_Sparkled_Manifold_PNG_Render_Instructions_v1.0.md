# **PNG Rendering Instructions v1.0**  
### *Tier XIII — Sparkled Genesis Manifold Rendering Pipeline*

---

## **Takeaway**  
Render the PNG as a **layered cosmic manifold**: concentric glowing rings, particle‑sparkled flows, and readable labels, using a strict layer order and blending modes to preserve NDH geometry.

---

## **I. Layer Order (Top → Bottom)**

1. **Background Layer**  
2. **Ambient Sparkle Layer**  
3. **Manifold Rings**  
4. **Flow System**  
5. **Flow Sparkles**  
6. **Labels**  
7. **Final Bloom Pass**

This order ensures readability and proper glow propagation.

---

## **II. Background Layer**

- **Gradient:** radial  
- **Center:** #0a0a14  
- **Edge:** #000000  
- **Blend mode:** *normal*  
- **Noise:** 1–2% subtle star‑grain  
- **Purpose:** cosmic depth for manifold rings

---

## **III. Ambient Sparkle Layer**

- **Particles:** 1–3 px circles  
- **Colors:** white, pale cyan  
- **Distribution:** 3–5% density  
- **Blur:** Gaussian 1–2 px  
- **Blend mode:** *screen*  
- **Opacity:** 40%  
- **Purpose:** cosmic ambience without overpowering flows

---

## **IV. Manifold Rings (Core Geometry)**

Render each ring as a separate layer:

### **G‑Core**
- Fill: white‑gold  
- Glow: 4 px  
- Blend: *screen*

### **C‑Band**
- Gradient: cyan → white  
- Glow: 8 px  
- Blend: *screen*

### **M‑Field**
- Gradient: blue‑violet  
- Glow: 10 px  
- Blend: *add*

### **B‑Layer**
- Color: hard red  
- Glow: 4 px  
- Blend: *overlay*  
- Texture: 5% grain

### **O‑Shell**
- Color: pale silver  
- Glow: 12 px  
- Blend: *screen*

---

## **V. Flow System Rendering**

Render flows as **curved Bézier paths** with particle‑enhanced strokes.

### **EG‑13 (G‑Core → C‑Band)**
- Stroke: gold  
- Width: 3 px  
- Glow: 4 px  
- Blend: *add*

### **CG‑13 (C‑Band → M‑Field)**
- Stroke: cyan  
- Width: 3 px  
- Glow: 5 px  
- Blend: *screen*

### **MG‑13 (M‑Field → outer + feedback)**
- Stroke: violet  
- Width: 4 px  
- Glow: 6 px  
- Blend: *add*

### **Continuity Feedback (M‑Field → C‑Band)**
- Stroke: dotted cyan‑white  
- Width: 2 px  
- Blend: *screen*

---

## **VI. Flow Sparkles**

- **Particles:** 1–2 px  
- **Colors:** gold, cyan, violet  
- **Placement:** along flow paths  
- **Motion blur:** 1 px directional  
- **Blend:** *add*  
- **Density:** 20–30% of path length  
- **Purpose:** emphasize movement and genesis dynamics

---

## **VII. Labels**

- **Font:** JetBrains Mono  
- **Color:** white  
- **Glow:** 2 px  
- **Blend:** *screen*  
- **Hierarchy:**  
  - Regions: 32 px  
  - Flows: 28 px  
  - Minor: 24 px  
- **Placement:** outside rings, never overlapping flows

---

## **VIII. Final Bloom Pass**

Apply a global bloom to unify the glow layers.

- **Radius:** 6–10 px  
- **Intensity:** 0.25–0.35  
- **Blend:** *screen*  
- **Mask:** exclude labels for readability  
- **Purpose:** cosmic cohesion + NDH aesthetic

---

## **IX. Export Settings**

- **Format:** PNG  
- **Color profile:** sRGB  
- **Dithering:** off  
- **Compression:** lossless  
- **Target resolution:** 2400 × 2400 px

---

