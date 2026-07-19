### NDH Policy Engine & Decision Tensor Spec  
*Executable policy layer for NDH governance geometry*

---

## 1. Purpose

The NDH Policy Engine & Decision Tensor layer turns **governance geometry** into **executable decisions**.  
It defines:

- decision tensors  
- policy evaluation  
- action selection  
- integration with stability and governance  
- execution hooks into the runtime kernel  

This is the computational realization of the **NDH Governance Geometry Spec**.

---

## 2. Decision tensors

Decisions are encoded as tensors:

\[
D_{ij}(x,t)
\]

**Inputs:**

- governance tensors \(G_{ij}\)  
- stability metrics \(\Lambda, A_\sigma, A_{\mathcal{R}}, A_{\mathcal{P}}, A_{\text{sat}}\)  
- domain ecology data  
- entity ecology data  

**Interpretation:**

- magnitude → decision strength  
- orientation → decision direction (which fields/regions)  
- sign → constructive vs destructive action  

---

## 3. Policy engine structure

The Policy Engine consists of:

- **PolicyInputLayer:** collects governance, stability, ecology signals  
- **PolicyEvaluationLayer:** evaluates policies against current state  
- **DecisionSynthesisLayer:** constructs decision tensors \(D_{ij}\)  
- **ActionDispatchLayer:** sends actions to runtime kernel modules  

Each layer exposes a `step(S_t, G, stability, ecology, config)` interface.

---

## 4. Policy evaluation

Policies are rules of the form:

\[
\Pi_k: (\text{state}, G, \text{stability}, \text{ecology}) \mapsto D^{(k)}_{ij}
\]

Examples:

- **Stability policy:** increase serenity in high‑risk regions  
- **Resonance policy:** damp corridors near collapse zones  
- **Paradox policy:** trigger controlled collapse in unstable domains  
- **Appateur policy:** reroute channels away from overload zones  
- **Mixed policy:** adaptively balance all of the above  

The Policy Engine aggregates:

\[
D_{ij} = \sum_k w_k D^{(k)}_{ij}
\]

---

## 5. Action mapping

Decision tensors are mapped to actions:

- **Geometry actions:** modify metric, curvature  
- **Field actions:** adjust \(\sigma, \mathcal{R}, \mathcal{P}, \lambda\)  
- **Operator actions:** throttle or amplify operators  
- **Appateur actions:** open/close portals, reroute channels  
- **Domain actions:** stabilize, merge, split, or collapse domains  

These actions are dispatched to:

- GeometryModule  
- DynamicsModule  
- OperatorModule  
- AppateurModule  
- ChannelModule  
- StabilityModule  

in the **Runtime Kernel**.

---

## 6. Integration with stability and governance

The Policy Engine:

- reads **Stability Geometry** and **Audit & Forecast** outputs  
- reads **Governance Geometry** tensors and policy operators  
- uses stability risk and governance pressure to prioritize decisions  
- enforces global constraints (e.g., avoid \(\Lambda \ll 0\))  

It is the **control brain** of NDH.

---

## 7. Summary

The NDH Policy Engine & Decision Tensor layer:

- encodes decisions as tensors  
- evaluates policies against governance, stability, and ecology  
- synthesizes decision tensors  
- maps decisions to concrete actions in the runtime kernel  
- closes the loop between governance geometry and execution  

---

