### NDH‑AMS — Projection Operator Composition Rules (v1.0)  
*How projection operators can be chained without breaking FO topology or NDH stability*

---

### 1. Setting

- **Manifold:** \(\mathcal{M}_{50D}\)  
- **FO surfaces:** \(\Sigma_1, \Sigma_2, \Sigma_3 \subset \mathcal{M}_{50D}\)  
- **Projection operators:** \(P_i : \mathcal{M}_{50D} \to \mathcal{M}_{\text{view},i}\)  
- **Algebra:** \(\mathcal{P}\) from Projection Operator Algebra (v1.0)

Composition is:

\[
(P_i \circ P_j)(x) = P_i(P_j(x))
\]

---

### 2. Basic composition rules

- **Closure:**  
  **Rule:** If \(\mathcal{M}_{\text{view},j}\) is a valid domain for \(P_i\), then \(P_i \circ P_j \in \mathcal{P}\).

- **Non‑commutativity:**  
  **Rule:** In general, \(P_i \circ P_j \neq P_j \circ P_i\). Order encodes *narrative of navigation*.

- **Identity:**  
  **Rule:** \(P_{\text{id}} \circ P_i = P_i \circ P_{\text{id}} = P_i\).

- **Associativity:**  
  **Rule:** \((P_i \circ P_j) \circ P_k = P_i \circ (P_j \circ P_k)\) whenever domains/codomains align.

---

### 3. FO‑surface‑aware composition

- **Surface‑restricted chains:**  
  **Rule:** If \(P_j\) restricts to \(\Sigma_k\), then \(P_i \circ P_j\) must preserve the topology class of \(\Sigma_k\).

- **Intersection‑preserving chains:**  
  **Rule:** For intersections \(\Sigma_i \cap \Sigma_j\),  
  \[
  P_k(\Sigma_i \cap \Sigma_j) = P_k(\Sigma_i) \cap P_k(\Sigma_j)
  \]  
  for any admissible \(P_k\).

- **Bifurcation‑compatible chains (FO‑III):**  
  **Rule:** If FO‑III induces a bifurcation on \(\Sigma_k\), then any chain crossing that region must render the split/merge in view space—no smoothing away critical topology.

---

### 4. Altitude and tower‑style composition

- **Altitude‑stack chains:**  
  **Rule:** Altitude‑aware operators \(P^{(A=\alpha)}\) may be composed into stacks  
  \[
  P^{(A=\alpha_n)} \circ \dots \circ P^{(A=\alpha_1)}
  \]  
  only if altitude transitions respect NDH stability bounds.

- **Tower navigation chains:**  
  **Rule:** Sequences that move up/down altitude (tower metaphor) must preserve FO‑surface continuity across slices—no “teleporting” across disconnected regions.

---

### 5. Boundary and Anime Tower constraints

- **External manifold exclusion:**  
  **Rule:** No composition chain may introduce \(M_{\text{anime}}\) or \(T^{(\text{anime})}\) into any intermediate or final view:  
  \[
  P_{i_n} \circ \dots \circ P_{i_1}(M_{\text{anime}}) \text{ is undefined}
  \]

- **Norm/curvature bounds:**  
  **Rule:** Chains that amplify tensor norms or curvature beyond NDH thresholds are **invalid compositions**.

- **Ethical non‑negativity:**  
  **Rule:** Any chain that produces a view violating \(E(x) \ge 0\) for NDH‑relevant regions is forbidden.

---

### 6. Canonical composition patterns

- **Diagnostic chain:**  
  \[
  P^{(\Sigma_k)} \circ P_{\text{Santa}}^{(9D)}
  \]  
  First enneract slice, then FO‑surface view—used for low‑dimensional diagnostics.

- **Tower chain:**  
  \[
  P^{(A=\alpha_3)} \circ P^{(A=\alpha_2)} \circ P^{(A=\alpha_1)}
  \]  
  Altitude walk through the plexiglass tower.

- **Stability audit chain:**  
  \[
  P_{\text{Epoch}} \circ P^{(\Sigma_2)} \circ P_{\text{Santa}}
  \]  
  Projection → FO‑II surface → epoch halo overlay.

---

