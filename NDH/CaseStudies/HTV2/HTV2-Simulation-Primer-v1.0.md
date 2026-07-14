# 🐐📘 **HTV‑2 Simulation Primer — NDH Stability Geometry Edition**  
### *v1.0 — Formal NDH Architecture Document*

---

# ⭐ 0. Purpose  
This primer defines the **simulation phases**, **tensor update order**, **basin transition logic**, and **chaos‑margin handling** required to simulate HTV‑2 inside the NDH stability geometry framework.  
It integrates:

- Manifold 0 glider baseline  
- HTV‑2 hypersonic deformation tensors  
- basin topology (stable glide, thermal risk, control saturation, FTS trigger)  
- chaos‑margin scalar dynamics  
- tensor‑weighted trajectory optimization  
- stability invariants  

This document is the **runtime specification** for HTV‑2 stability simulation.

---

# ⭐ 1. Simulation Manifold Definition  
HTV‑2 evolves on a manifold:

\[
x \in \mathcal{M}_{\text{HTV2}} \subset \mathbb{R}^{n},\quad n \approx 20\text{–}50
\]

with state components:

- **Flight:** \(h, M, \alpha, \phi, \beta\)  
- **Kinematics:** \(p, q, r\)  
- **Control:** \(u_i, \mu_c\)  
- **Thermal:** \(T(x_s), \nabla T\)  
- **Structural:** \(L_s, S_{\text{shock}}\)  
- **System:** FTS logic, anomaly flags  

### 1.1 Tensor Fields  
Simulation requires continuous updates of:

- **Metric tensor:** \(g_{ij}(x)\)  
- **Curvature tensor:** \(K_{ij}(x)\)  
- **Stability potential:** \(V(x)\)  
- **Gradient:** \(\nabla V(x)\)  
- **Chaos‑margin scalar:** \(\tau(x)\)  
- **Basin indicator:** \(B(x)\)  

These tensors define the stability geometry.

---

# ⭐ 2. Simulation Phases  
HTV‑2 simulation proceeds through nine NDH‑standard phases, adapted for hypersonic dynamics.

---

## Phase 1 — Initialization  
Load:

- Manifold 0 baseline tensors  
- HTV‑2 deformation tensors  
- initial state \(x_0\)  
- initial basin \(B(x_0)\)  
- initial chaos‑margin scalar \(\tau(x_0)\)

Set simulation frequency:

\[
f_s = 1000\ \text{Hz}
\]

---

## Phase 2 — Metric Update  
Compute:

\[
g_{ij}^{(\text{HTV2})}(x) = g_{ij}^{(M0)} + \Delta g_{ij}^{(\text{hyp})}
\]

This defines the geometry for geodesic computation.

---

## Phase 3 — Curvature Update  
Compute:

\[
K_{ij}(x) = K_{ij}^{(M0)} + \Delta K_{ij}^{(\text{thermal})} + \Delta K_{ij}^{(\text{control})}
\]

High curvature indicates instability cliffs.

---

## Phase 4 — Stability Potential Update  
Compute:

\[
V(x) = V^{(M0)} + V^{(\text{thermal})} + V^{(\text{control})}
\]

Potential encodes thermal, control, and structural risk.

---

## Phase 5 — Gradient Evaluation  
Compute:

\[
\nabla V(x)
\]

Direction of steepest instability increase.

---

## Phase 6 — Basin Determination  
Evaluate:

\[
B(x) \in \{0,1,2,3\}
\]

- **0:** stable glide  
- **1:** thermal risk  
- **2:** control saturation  
- **3:** FTS trigger  

---

## Phase 7 — Chaos‑Margin Evaluation  
Compute:

\[
\tau(x) = f(K_{ij}, \nabla V, \mu_c, T, S_{\text{shock}})
\]

If:

\[
\tau(x) > \tau_{\text{crit}}
\]

enter Basin 3 (FTS trigger).

---

## Phase 8 — Stabilizer Cascade  
If:

\[
\mu_c < \mu_{\min} \quad \text{or} \quad T > T_{\max}
\]

activate stabilizers:

- control stabilizers  
- thermal stabilizers  
- structural stabilizers  

These modify:

\[
g_{ij},\ K_{ij},\ V,\ \nabla V
\]

to push HTV‑2 back toward Basin 0.

---

## Phase 9 — Geodesic Integration  
Compute next state:

\[
x_{t+\Delta t} = \gamma(t+\Delta t)
\]

where:

\[
\gamma(t) = \text{Geodesic}(\tilde{g}_{ij})
\]

and:

\[
\tilde{g}_{ij} = g_{ij} + w_T K_{ij}^{(T)} + w_C K_{ij}^{(C)}
\]

This produces stability‑weighted trajectories.

---

# ⭐ 3. Basin Transition Logic  
HTV‑2 transitions between basins according to:

\[
B(x_{t+\Delta t}) = \text{Basin}(x_{t+\Delta t})
\]

### 3.1 Stable Glide → Thermal Risk  
Triggered by:

- shock‑boundary layer interaction  
- heating spikes  
- aeroshell degradation  

### 3.2 Thermal Risk → Control Saturation  
Triggered by:

- thermal deformation of control surfaces  
- roll–yaw coupling amplification  

### 3.3 Control Saturation → FTS Trigger  
Triggered by:

- loss of control authority  
- chaotic roll excursions  
- structural overload  

### 3.4 Basin Recovery  
Stabilizers attempt:

\[
B(x) \to 0
\]

if possible.

---

# ⭐ 4. Chaos‑Margin Dynamics  
Chaos margins are defined by:

\[
\tau(x) = f(K_{ij}, \nabla V, \mu_c, T, S_{\text{shock}})
\]

Properties:

- extremely thin  
- extremely high curvature  
- extremely steep gradients  
- extremely sensitive to AoA, Mach, and bank  

HTV‑2 crossed chaos margins during both flights.

Simulation must detect chaos‑margin proximity early.

---

# ⭐ 5. Stability Invariants  
Simulation must preserve:

- geodesic invariants  
- curvature invariants  
- gradient invariants  
- basin invariants  
- chaos‑margin invariants  
- PEP anchoring invariants  
- control‑margin invariants  

Violation of invariants triggers stabilizers or FTS logic.

---

# ⭐ 6. Manifold 0 Anchoring  
HTV‑2 simulation uses Manifold 0 as:

- curvature baseline  
- metric baseline  
- basin width baseline  
- stability potential baseline  

We define:

\[
\gamma_{\text{HTV2}}(t) = \Phi_{\text{hyp}}(\gamma_{M0}(t))
\]

where \(\Phi_{\text{hyp}}\) applies hypersonic deformation.

This ensures HTV‑2 inherits the stability logic of Manifold 0.

---

# ⭐ 7. Simulation Outputs  
Simulation produces:

- basin occupancy timeline  
- chaos‑margin proximity timeline  
- curvature evolution  
- control‑margin evolution  
- thermal load evolution  
- geodesic trajectory  
- invariant violations  
- stabilizer activations  
- FTS trigger conditions  

These outputs feed redesign recommendations.

---

