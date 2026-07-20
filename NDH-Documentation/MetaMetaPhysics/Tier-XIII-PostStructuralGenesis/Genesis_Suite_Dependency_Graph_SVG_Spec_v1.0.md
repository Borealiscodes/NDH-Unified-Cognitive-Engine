### SVG specification for Genesis Suite Dependency Graph

Here’s a clean, implementation‑ready spec you (or future‑you) can hand to an SVG generator or code against.

---

#### 1. Canvas

- **Size:**  
  - **Width:** `1200`  
  - **Height:** `900`  
- **Background:** `#ffffff`

---

#### 2. Node definitions

Use rounded rectangles for all nodes, with consistent styling:

- **Common style:**  
  - `rx="10"` (rounded corners)  
  - `fill="#f7f9fc"`  
  - `stroke="#333333"`  
  - `stroke-width="1.5"`  
  - Text: `font-family="monospace"`, `font-size="14"`, `fill="#111111"`

**Node list (with suggested coordinates):**

1. **README**  
   - `id="node_readme"`  
   - `x="450"`, `y="60"`, `width="300"`, `height="70"`  
   - Label: `Genesis Suite README`

2. **Index**  
   - `id="node_index"`  
   - `x="450"`, `y="170"`, `width="300"`, `height="70"`  
   - Label: `Blueprint Suite Genesis Index`

3. **Manifold Map**  
   - `id="node_map"`  
   - `x="80"`, `y="320"`, `width="260"`, `height="70"`  
   - Label: `Genesis Manifold Map`

4. **Flow Diagram**  
   - `id="node_flow"`  
   - `x="470"`, `y="320"`, `width="260"`, `height="70"`  
   - Label: `Genesis Flow Diagram`

5. **Topology Diagram**  
   - `id="node_topology"`  
   - `x="860"`, `y="320"`, `width="260"`, `height="70"`  
   - Label: `Genesis Topology Diagram`

6. **Blueprint Suite**  
   - `id="node_suite"`  
   - `x="450"`, `y="470"`, `width="300"`, `height="80"`  
   - Label: `Blueprint Suite Genesis`

7. **Companion**  
   - `id="node_companion"`  
   - `x="450"`, `y="620"`, `width="300"`, `height="70"`  
   - Label: `Blueprint Suite Companion`

8. **Cross‑Reference Matrix**  
   - `id="node_matrix"`  
   - `x="450"`, `y="760"`, `width="300"`, `height="70"`  
   - Label: `Genesis Suite Cross‑Reference Matrix`

---

#### 3. Edge definitions

Use straight or gently curved arrows with:

- `stroke="#555555"`  
- `stroke-width="1.5"`  
- Arrowheads via `marker-end="url(#arrowhead)"`

**Marker definition (once):**

```xml
<defs>
  <marker id="arrowhead" markerWidth="10" markerHeight="7"
          refX="10" refY="3.5" orient="auto">
    <polygon points="0 0, 10 3.5, 0 7" fill="#555555" />
  </marker>
</defs>
```

**Edges (semantic + approximate coordinates):**

1. **README → Index**

```xml
<line x1="600" y1="130" x2="600" y2="170"
      stroke="#555555" stroke-width="1.5" marker-end="url(#arrowhead)" />
```

2. **Index → Manifold Map**

```xml
<line x1="600" y1="240" x2="210" y2="320"
      stroke="#555555" stroke-width="1.5" marker-end="url(#arrowhead)" />
```

3. **Index → Flow Diagram**

```xml
<line x1="600" y1="240" x2="600" y2="320"
      stroke="#555555" stroke-width="1.5" marker-end="url(#arrowhead)" />
```

4. **Index → Topology Diagram**

```xml
<line x1="600" y1="240" x2="990" y2="320"
      stroke="#555555" stroke-width="1.5" marker-end="url(#arrowhead)" />
```

5. **Manifold Map → Flow Diagram**

```xml
<line x1="340" y1="355" x2="470" y2="355"
      stroke="#555555" stroke-width="1.5" marker-end="url(#arrowhead)" />
```

6. **Manifold Map → Topology Diagram**

```xml
<line x1="340" y1="375" x2="860" y2="375"
      stroke="#555555" stroke-width="1.5" marker-end="url(#arrowhead)" />
```

7. **Flow Diagram → Blueprint Suite**

```xml
<line x1="600" y1="390" x2="600" y2="470"
      stroke="#555555" stroke-width="1.5" marker-end="url(#arrowhead)" />
```

8. **Topology Diagram → Blueprint Suite**

```xml
<line x1="990" y1="390" x2="750" y2="470"
      stroke="#555555" stroke-width="1.5" marker-end="url(#arrowhead)" />
```

9. **Manifold Map → Blueprint Suite**  
(optional explicit edge to show geometry dependency)

```xml
<line x1="210" y1="390" x2="450" y2="470"
      stroke="#777777" stroke-width="1.2" marker-end="url(#arrowhead)" />
```

10. **Blueprint Suite → Companion**

```xml
<line x1="600" y1="550" x2="600" y2="620"
      stroke="#555555" stroke-width="1.5" marker-end="url(#arrowhead)" />
```

11. **All core artifacts → Cross‑Reference Matrix**  
You can either:

- draw separate edges from Map, Flow, Topology, Suite, Companion to Matrix, or  
- use a single vertical edge from Companion to Matrix to represent “depends on all”.

Minimal version:

```xml
<line x1="600" y1="690" x2="600" y2="760"
      stroke="#555555" stroke-width="1.5" marker-end="url(#arrowhead)" />
```

---

#### 4. Layering and groups

Wrap related elements in `<g>` groups for clarity:

- `id="group_core_artifacts"` for Map, Flow, Topology  
- `id="group_suite"` for Suite + Companion  
- `id="group_meta"` for README + Index + Matrix

This makes future edits and styling easier.

---

