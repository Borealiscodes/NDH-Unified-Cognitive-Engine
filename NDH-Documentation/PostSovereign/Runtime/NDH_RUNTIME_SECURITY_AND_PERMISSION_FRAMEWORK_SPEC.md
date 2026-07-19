### NDH Runtime Security & Permission Framework  
*Security brain and access‑control lattice for the NDH runtime*

---

## 1. Purpose

The NDH Runtime Security & Permission Framework governs **who can do what** within NDH, and under which conditions.  
It ensures that:

- external and internal actions respect safety constraints  
- dangerous operations are restricted or denied  
- modes and profiles interact coherently with permissions  
- NDH cannot be destabilized by misuse or malicious input  

It is the **security brain** of the NDH runtime.

---

## 2. Responsibilities

The framework:

- defines permission models for users, tools, and subsystems  
- enforces access control on all external interface operations  
- integrates with safety profiles and runtime modes  
- validates high‑risk commands (transport, flux, governance, axiom changes)  
- provides audit trails for security‑relevant actions  
- cooperates with the Interrupt & Exception Handler for violations  

---

## 3. Permission Model

Key elements:

- **Subjects:** users, external systems, tools, roles (e.g., admin, observer, analyst)  
- **Objects:** runtime subsystems, APIs, configuration domains, state segments  
- **Actions:** read, write, control (start/stop/step), configure, subscribe, replay  
- **Policies:** allow/deny/conditional based on mode, safety profile, and context  

Supports:

- role‑based access control (RBAC)  
- context‑aware rules (e.g., stress‑test mode vs. demo mode)  
- operation‑specific constraints (e.g., no direct axiom mutation in safe mode)

---

## 4. Security Domains

- **Control Security:** start/stop/step, mode changes, replay control  
- **State Security:** access to geometry, domains, flux, axioms, governance state  
- **Configuration Security:** changing safety profiles, tick rates, logging levels  
- **Transport Security:** corridor/channel/front operations, cross‑domain transitions  
- **Axiom & Governance Security:** axiom graph changes, policy decisions  
- **Serialization Security:** save/load, rollback, replay sequences  

Each domain has its own permission set and policies.

---

## 5. Interfaces

### Inputs

- authentication/identity context (user, tool, role)  
- requested operation (API call, command, subscription)  
- current mode and safety profile  
- configuration and policy rules  

### Outputs

- allow/deny/conditional decision  
- security audit logs  
- violation reports  
- optional triggers to Interrupt Handler for severe violations  

---

## 6. Configuration

Key parameters:

- **roles** and **role hierarchies**  
- **permission_profiles** (e.g., `admin_lab`, `safe_demo`, `observer_only`)  
- **operation_risk_levels**  
- **violation_severity_thresholds**  
- **logging_level** for security events  

---

## 7. Integration

The framework integrates with:

- **Runtime External Interface Layer** (to gate external commands)  
- **Configuration & Mode Manager** (to couple permissions with modes/profiles)  
- **Event Bus** (to emit security events and violations)  
- **Interrupt & Exception Handler** (for critical security breaches)  
- **Metrics & Logging Layer** (for audit trails)

---

