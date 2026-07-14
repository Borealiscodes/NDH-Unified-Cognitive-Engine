# **Operational Stability Basin Atlas — v1.0**  
### *NDH Stability Attraction Regions + Runtime Basin Geometry (OSBA)*

---

## **0. Atlas Metadata Block**

```
ATLAS ID: OSBA-v1.0
Atlas Type: Stability Basin Atlas
Version: 1.0
Cluster: Operational / Stability Geometry
Repo: NDH Simulation Suite
Placement: Internal (Operational Spine)
Status: Active (Governing)
```

This atlas sits directly under:

- **Operational Stability Potential Function**  
- **Operational Stability Gradient Map**  
- **Operational Invariant Preservation Engine**  

and above:

- stabilizer routing  
- drift correction pathing  
- envelope alignment decisions  
- recovery protocol basin selection  

---

# **1. Purpose**

The **Operational Stability Basin Atlas (OSBA)** defines:

- the basins of attraction in NDH’s stability landscape  
- the regions where NDH naturally descends under stability gradients  
- the PEP‑anchored stability wells  
- the continuity‑anchored basins  
- the invariant‑protected basins  
- the chaos‑margin‑adjacent unstable basins  
- the envelope‑bounded basin geometry  

OSBA is the **runtime map of “where NDH will end up if left alone.”**

---

# **2. Basin Definition**

A stability basin is defined as:

\[
\mathcal{B}_k = \{x : \lim_{t \to \infty} \Phi(x,t) = m_k\}
\]

Where:

- \(\Phi(x,t)\) — stability gradient flow  
- \(m_k\) — stability minimum (PEP, continuity anchor, invariant well)

This is the NDH analogue of a **gradient‑flow attractor region**.

---

# **3. Basin Classes**

OSBA defines **four basin classes**:

---

### **3.1 PEP Basins**
\[
\mathcal{B}_{\Pi} = \{x : \Phi(x,t) \rightarrow \Pi_{\text{nearest}}\}
\]

These are the **primary stability wells**.

Linked construct:  
**PEP Envelope**

---

### **3.2 Continuity Basins**
\[
\mathcal{B}_{\text{cont}} = \{x : \Phi(x,t) \rightarrow \Pi_{\text{cont}}\}
\]

Activated when CP‑01 is engaged.

Linked construct:  
**Continuity Lock Protocol**

---

### **3.3 Invariant Basins**
\[
\mathcal{B}_{I_j} = \{x : \Phi(x,t) \rightarrow m_{I_j}\}
\]

These basins preserve invariant minima.

Linked construct:  
**Operational Invariant Preservation Engine**

---

### **3.4 Chaos‑Margin Basins (unstable)**
\[
\mathcal{B}_{\tau} = \{x : \Phi(x,t) \rightarrow \Sigma_{\tau}\}
\]

These are **unstable basins** that trigger recovery.

Linked construct:  
**Operational Chaos-Margin Geometry**

---

# **4. Basin Geometry**

Each basin is shaped by:

- stability potential  
- envelope curvature  
- chaos‑margin gradients  
- invariant constraints  
- triangulation geometry  
- PEP anchoring fields  

The geometry is **piecewise smooth**, **envelope‑bounded**, and **invariant‑safe**.

---

# **5. Basin Boundaries**

Basin boundaries are defined as:

\[
\partial \mathcal{B}_k = \{x : G(x) = 0 \text{ and } V(x) = V_{\text{sep}}\}
\]

Where \(V_{\text{sep}}\) is the **separatrix potential**.

These boundaries are:

- envelope‑aligned  
- curvature‑shaped  
- chaos‑margin‑adjacent  
- PEP‑partitioned  
- invariant‑protected  

---

# **6. Basin Operations**

### **6.1 Basin Detection**
\[
x(t) \rightarrow \mathcal{B}_k
\]

### **6.2 Basin Descent**
\[
x(t+1) = x(t) - \alpha G(x)
\]

### **6.3 Basin Correction**
\[
x(t) \rightarrow \Pi_{\text{nearest}}
\]

### **6.4 Basin Stabilization**
\[
S_{\text{aux}} \rightarrow \text{active}
\]

### **6.5 Basin Recovery**
\[
\text{RP}(x(t))
\]

---

# **7. Integration With Runtime Stability Logic**

Runtime Stability Logic uses OSBA to:

- determine descent direction  
- select stabilizer pathways  
- avoid unstable basins  
- anchor to PEP minima  
- preserve invariants  
- route recovery protocols  

Linked construct:  
**NDH Runtime Stability Logic**

---

# **8. Implementation Requirements**

To implement OSBA v1.0:

- compute basin minima  
- map basin boundaries  
- integrate stability potential  
- integrate stability gradients  
- integrate invariant constraints  
- integrate chaos‑margin geometry  
- integrate envelope curvature  
- expose basin detection and descent  
- link runtime to basin atlas  

---

