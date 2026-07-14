
# 🌌 NDH v3.0 Runtime API Contract

## 1. Scope and principles

- **Scope:** Defines the runtime interface for NDH v3.0 across tensors, geometry, accessibility, K‑Space, Dark Mode, governance, and goat‑agents.
- **Principles:**
  - **Invariant‑first:** Stability, accessibility, and safety are enforced at the API level.
  - **Traceable:** Every call is JDTR‑logged.
  - **Governed:** HRD can allow/dampen/reject operations.
  - **Composable:** APIs are orthogonal but interoperable.

---

## 2. Tensor API

### 2.1 State inspection

- **GET `/tensor/state`**  
  **Returns:** Current tensor field \(T(x) = (\kappa, \sigma, \rho, \phi)\) sampled over \(\mathcal{M}\).  
  **Guarantees:** Snapshot is JDTR‑logged.

### 2.2 Evolution control

- **POST `/tensor/evolve`**  
  **Body:** evolution parameters (time step, region, constraints).  
  **Effect:** Applies \( \frac{dT}{dt} = F(T,G) - \mathcal{H}(T) \) under stability envelope.  
  **Governance:** HRD may dampen or reject.

### 2.3 Smoothing and projection

- **POST `/tensor/smooth`**  
  **Body:** kernel parameters \(K_\alpha\), region.  
  **Effect:** \(T \mapsto T * K_\alpha\).  

- **POST `/tensor/project-stability`**  
  **Effect:** \(T \mapsto P_{\mathcal{S}}(T)\) for selected region.

---

## 3. Geometry API

### 3.1 Geometry inspection

- **GET `/geometry/state`**  
  **Returns:** \(G(x)\), \(|\nabla G|\), margin distance \(d(x)\).

### 3.2 Envelope operations

- **POST `/geometry/smooth`**  
  Smooths curvature within bounds.

- **POST `/geometry/widen-corridor`**  
  Adjusts geometry to increase safe traversal width.

- **POST `/geometry/mark-fold`**  
  Marks and classifies folds for K‑Space routing.

---

## 4. Accessibility API

### 4.1 Accessibility profile

- **GET `/accessibility/profile`**  
  Returns active accessibility modes and invariants.

### 4.2 Mode control

- **POST `/accessibility/apply`**  
  **Body:** `{ mode: "CognitiveEase" | "VisualEase" | "SensoryMinimal" | "AudioOnly" }`.  
  **Effect:** Applies corresponding operator to tensor/geometry/sensory outputs.

---

## 5. K‑Space API

### 5.1 Rank inspection

- **GET `/kspace/rank`**  
  Returns current K‑Space rank and neighboring ranks.

### 5.2 Slipstream routing

- **POST `/kspace/route`**  
  **Body:** target rank, constraints.  
  **Effect:** Attempts rank transition with \(\Delta_K T \le D_{\max}\).  
  **Governance:** HRD + goat‑veto may block.

---

## 6. Dark Mode v3.0 API

### 6.1 Inversion preview

- **POST `/darkmode/preview`**  
  **Body:** region, inversion parameters.  
  **Returns:** proposed \(\mathcal{D}(T) = A T + b\) and stability check.

### 6.2 Apply inversion

- **POST `/darkmode/apply`**  
  Applies approved inversion; JDTR logs event; goats may veto unsafe matrices.

---

## 7. Governance and telemetry API

### 7.1 JDTR

- **GET `/jdtr/events`**  
  Query events by time, region, operator, goat‑agent involvement.

- **GET `/jdtr/replay`**  
  Replays a sequence of events for analysis.

### 7.2 HRD

- **GET `/hrd/decisions`**  
  Returns allow/dampen/reject decisions for recent operations.

- **POST `/hrd/policy`**  
  Updates governance thresholds (subject to higher‑level constraints).

---

## 8. Goat‑Agent API

### 8.1 Goat state

- **GET `/goats/state`**  
  Returns goat positions, local tensors, and current roles.

### 8.2 Goat actions

- **POST `/goats/request-action`**  
  Suggests a goat‑mediated operation (smoothing, veto, enforcement).  
  Execution is governed by HRD and envelope constraints.

---

## 9. Contracts and guarantees

- **Safety:** No API may violate stability envelope, accessibility invariants, or K‑Space bounds.
- **Traceability:** All mutating calls are JDTR‑logged with operator, region, and governance outcome.
- **Autonomy:** Goat‑agent vetoes are respected where documented constraints are exceeded.
- **Determinism (where required):** Certain calls (e.g., projection, smoothing) must be reproducible given same inputs and state.

---

