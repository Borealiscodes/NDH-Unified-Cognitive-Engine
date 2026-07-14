### NDH API Schemas v2.0 — Formal Specification  
*Canonical developer surface for NDH v2.0.*

---

### 1. Scope

NDH v2.0 exposes APIs in five main domains:

- **Runtime & State**
- **Sensory & Accessibility**
- **Stability & Geometry**
- **Multi‑Manifold & K‑Space**
- **Governance & Trace (HRD, JDTR)**

Each domain has:

- resources (what you talk to)  
- operations (what you can do)  
- payload shapes (what you send/receive)  
- safety & accessibility constraints  

---

### 2. Runtime & State APIs

**2.1 Resource: `/runtime/state`**

- **GET `/runtime/state`**  
  **Purpose:** Fetch current NDH state snapshot.  
  **Response (conceptual):**  
  - `manifoldId`  
  - `timestamp`  
  - `tensor`: `{ kappa, sigma, rho, phi }`  
  - `geometry`: `{ basinDepth, corridorWidth, marginDistance }`  
  - `kRank`  
  - `ladderMode`  
  - `accessibilityProfile`

- **POST `/runtime/state/transition`**  
  **Purpose:** Request a state transition.  
  **Body:**  
  - `targetLadderMode`  
  - `targetKRank` (optional)  
  - `constraints`: `{ accessibilityRequired: true, stabilityRequired: true }`  
  **Response:**  
  - `accepted: boolean`  
  - `hrdDecision`: `allow | dampen | reject`  
  - `jdtrEventId`

---

### 3. Sensory & Accessibility APIs

**3.1 Resource: `/sensory/output`**

- **GET `/sensory/output`**  
  **Purpose:** Inspect current sensory mapping.  
  **Response:**  
  - `audio`: `{ intensity, spectrumProfile }`  
  - `haptics`: `{ intensity, patternId }`  
  - `visual`: `{ toneProfile, contrastLevel }`  
  - `accessibilityProfile`

**3.2 Resource: `/accessibility/profile`**

- **GET `/accessibility/profile`**  
  **Purpose:** Get active accessibility profile.  
  **Response:**  
  - `profile`: `audioOnly | hapticPrimary | visualEase | cognitiveEase | sensoryMode_minimal`

- **POST `/accessibility/profile`**  
  **Purpose:** Set accessibility profile.  
  **Body:**  
  - `profile`: one of the above  
  **Response:**  
  - `accepted: boolean`  
  - `hrdDecision`  
  - `jdtrEventId`

---

### 4. Stability & Geometry APIs

**4.1 Resource: `/stability/envelope`**

- **GET `/stability/envelope`**  
  **Purpose:** Fetch current stability bounds.  
  **Response:**  
  - `kappaMax`  
  - `sigmaMax`  
  - `rhoMax`  
  - `phiMax`  
  - `marginMinDistance`

**4.2 Resource: `/geometry/envelope`**

- **GET `/geometry/envelope`**  
  **Purpose:** Inspect geometry envelope.  
  **Response:**  
  - `basins`: `[ { id, depth, curvature } ]`  
  - `corridors`: `[ { id, width, continuityScore } ]`  
  - `margins`: `[ { id, distance, instabilityScore } ]`

---

### 5. Multi‑Manifold & K‑Space APIs

**5.1 Resource: `/manifolds`**

- **GET `/manifolds`**  
  **Purpose:** List active manifolds.  
  **Response:**  
  - `manifolds`: `[ { id, name, status } ]`

- **POST `/manifolds/bridge`**  
  **Purpose:** Request a bridge between manifolds.  
  **Body:**  
  - `sourceManifoldId`  
  - `targetManifoldId`  
  - `constraints`: `{ stabilityRequired: true, accessibilityRequired: true }`  
  **Response:**  
  - `bridgeId`  
  - `hrdDecision`  
  - `jdtrEventId`

**5.2 Resource: `/kspace/rank`**

- **GET `/kspace/rank`**  
  **Purpose:** Get current K‑Space rank.  
  **Response:**  
  - `currentRank`  

- **POST `/kspace/rank/transition`**  
  **Purpose:** Request rank change.  
  **Body:**  
  - `targetRank`  
  - `constraints`: `{ maxDeltaNorm, accessibilityRequired }`  
  **Response:**  
  - `accepted`  
  - `hrdDecision`  
  - `jdtrEventId`

---

### 6. Governance & Trace APIs

**6.1 Resource: `/hrd/check`**

- **POST `/hrd/check`**  
  **Purpose:** Ask HRD to validate a proposed operation.  
  **Body:**  
  - `operationType`  
  - `payloadSummary`  
  **Response:**  
  - `decision`: `allow | dampen | reject`  
  - `reasonCodes`: `[ ... ]`

**6.2 Resource: `/jdtr/events`**

- **GET `/jdtr/events`**  
  **Purpose:** Query JDTR events.  
  **Query params:**  
  - `manifoldId`  
  - `fromTimestamp`  
  - `toTimestamp`  
  - `eventType`  
  **Response:**  
  - `events`: `[ { id, timestamp, type, summary } ]`

- **GET `/jdtr/events/{id}`**  
  **Purpose:** Fetch full event detail.  
  **Response:**  
  - `tensorSnapshot`  
  - `geometrySnapshot`  
  - `kRank`  
  - `accessibilityProfile`  
  - `hrdDecision`  
  - `sensorySnapshot`

---

### 7. Versioning & Safety Rules

- **Version header:**  
  - `X-NDH-API-Version: "2.0"`  
- **Safety constraints (conceptual):**  
  - Any operation that would push tensors outside \(\mathcal{S}\) → HRD `reject`  
  - Any operation that bypasses accessibility → HRD `reject`  
  - All state‑changing operations must emit a JDTR event ID in the response  

---

