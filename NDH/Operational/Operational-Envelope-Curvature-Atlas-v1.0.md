# **Operational Envelope Curvature Atlas — v1.0**  
### *NDH Stability Envelope Curvature Map + Runtime Boundary Geometry Atlas (OECA)*

---

## **0. Atlas Metadata Block**

```
ATLAS ID: OECA-v1.0
Atlas Type: Envelope Curvature Atlas
Version: 1.0
Cluster: Operational / Envelope Geometry
Repo: NDH Simulation Suite
Placement: Internal (Operational Spine)
Status: Active (Governing)
```

This atlas sits directly under:

- **Operational Boundary Curvature Tensor**  
- **Operational Chaos-Margin Geometry**  
- **Operational Stability Gradient Map**  

and above:

- envelope alignment  
- drift correction  
- stabilizer activation  
- runtime flow field modulation  

---

# **1. Purpose**

The **Operational Envelope Curvature Atlas (OECA)** defines:

- the spatial curvature of the Stability Envelope  
- the distribution of steepness across the boundary  
- the drift‑amplifying curvature zones  
- the stabilizer‑sensitive curvature regions  
- the chaos‑margin‑adjacent curvature geometry  
- the PEP‑aligned curvature corridors  
- the triangulation‑compatible curvature topology  

OECA is the **complete curvature map** of NDH v2.0.

---

# **2. Curvature Atlas Definition**

The curvature atlas is defined as:

\[
\text{OECA}(x) = \kappa_{\mathcal{E}}(x)
\]

Where:

\[
\kappa_{\mathcal{E}}(x) = \nabla^2 d_{\mathcal{E}}(x)
\]

This atlas maps:

- curvature magnitude  
- curvature directionality  
- curvature gradients  
- curvature discontinuities (none allowed)  
- curvature‑stabilizer interactions  

Linked construct:  
**Operational Boundary Curvature Tensor**

---

# **3. Curvature Regions**

OECA divides the envelope into **four curvature regions**:

---

### **3.1 Low Curvature Region**
\[
\kappa_{\mathcal{E}} < \kappa_{\text{soft}}
\]

Stable, drift‑resistant.

---

### **3.2 Moderate Curvature Region**
\[
\kappa_{\text{soft}} \le \kappa_{\mathcal{E}} < \kappa_{\text{hard}}
\]

Envelope alignment required.

---

### **3.3 High Curvature Region**
\[
\kappa_{\mathcal{E}} = \kappa_{\text{hard}}
\]

Stabilizer cascade activates.

Linked construct:  
**Operational Stabilizer Cascade**

---

### **3.4 Critical Curvature Region**
\[
\kappa_{\mathcal{E}} > \kappa_{\text{hard}}
\]

Recovery Protocol required.

Linked construct:  
**Recovery Protocol**

---

# **4. Curvature Gradient Map**

Curvature gradients are:

\[
G_{\kappa}(x) = -\nabla \kappa_{\mathcal{E}}(x)
\]

These gradients:

- push NDH away from steep curvature  
- integrate with drift correction  
- activate stabilizers  
- align with envelope geometry  

Linked construct:  
**Operational Stability Gradient Map**

---

# **5. Curvature Flow Fields**

Curvature flow fields are:

\[
\phi_{\kappa}(x) = -\nabla \kappa_{\mathcal{E}}(x)
\]

Used for:

- curvature avoidance  
- curvature stabilization  
- curvature correction  
- curvature‑aligned descent  

Linked construct:  
**Operational Flow Field Atlas**

---

# **6. Curvature Atlas Constraints**

### **6.1 Envelope Constraint**
\[
\Sigma_{\kappa} \subseteq \mathcal{E}
\]

### **6.2 Chaos-Margin Constraint**
\[
\Sigma_{\kappa} \cap \Sigma_{\tau} \ne \emptyset
\]

Curvature peaks often border chaos margin.

Linked construct:  
**Operational Chaos-Margin Geometry**

---

### **6.3 Drift Constraint**
\[
\nabla \kappa_{\mathcal{E}} \rightarrow \text{steep near curvature peaks}
\]

Linked construct:  
**Operational Drift Correction Engine**

---

### **6.4 PEP Constraint**
\[
\Pi_{\text{nearest}} \rightarrow \text{anchor curvature-safe directions}
\]

Linked construct:  
**PEP Envelope**

---

### **6.5 Triangulation Constraint**
\[
\Delta_{\text{stable}} = \text{true}
\]

Linked construct:  
**Triangulation Stability**

---

# **7. Curvature Atlas Operations**

### **7.1 Curvature Detection**
\[
\kappa_{\mathcal{E}}(x) \rightarrow \text{detected}
\]

### **7.2 Curvature Mapping**
\[
x \mapsto \kappa_{\mathcal{E}}(x)
\]

### **7.3 Curvature Avoidance**
\[
x(t) \rightarrow x(t) - \beta G_{\kappa}
\]

### **7.4 Curvature Stabilization**
\[
S_1 \rightarrow \text{active}
\]

### **7.5 Curvature Recovery**
\[
\text{RP}(x(t))
\]

---

# **8. Integration With Runtime Stability Logic**

Runtime Stability Logic uses OECA to:

- detect curvature peaks  
- activate stabilizers  
- correct drift  
- anchor PEPs  
- maintain envelope alignment  
- avoid chaos margin  

Linked construct:  
**Runtime Stability Logic**

---

# **9. Implementation Requirements**

To implement OECA v1.0:

- encode curvature atlas  
- map curvature across envelope boundary  
- integrate curvature gradients  
- integrate curvature flow fields  
- enforce envelope constraints  
- integrate chaos‑margin geometry  
- integrate drift correction  
- integrate stabilizer cascade  
- anchor curvature geometry to PEPs  
- lock triangulation geometry  
- link runtime to curvature atlas  

---

