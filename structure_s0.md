# Structure S₀ — Minimal Formal Summary

This document provides a compact, implementation-agnostic summary of the S₀ architecture:  
the axioms A1–A8, the four fundamental threat classes T₁–T₄, the resilience levels S₁–S₇, and the transition function F.

The goal is to give a self-contained reference that does **not** require reading the full S₀ document.

---

## 1. Core Elements of S₀

### 1.1 Subject
A subject is the minimal system element capable of forming a reaction to an input:

s = (φ → r)

There are no assumptions about internal structure, technology, or implementation substrate.

### 1.2 Inputs and Reactions
- **φ** — input available to the subject at time *t*  
- **r** — reaction formed by the subject  
- Reactions are the sole way subjects influence the system.

### 1.3 System State
- **x ∈ X** — current state of the system  
- The system moves between states through a shared transition function.

### 1.4 Transition Function
The collective transition is defined as:

F : (x, φ, r) → x’

- Same F applies to all subjects.  
- F must be reproducible, deterministic, and independent of any one subject.

### 1.5 History
A system history is a sequence of transitions:

h = (x₀, φ₀, r₀, x₁, …, xₙ)

The history must remain consistent and unambiguous.

---

## 2. Axioms of S₀ (A1–A8)

These eight axioms define the minimal conditions required for correct collective transitions.

### A1 — Multiplicity  
The system consists of a set of subjects 𝒮.  
No subject may be removed from participation in the transition process.

### A2 — Homogeneity  
All subjects are equal with respect to participation in transitions.  
No privileged subjects or special roles inside F.

### A3 — Reaction Accessibility  
Each subject must be able to receive inputs φ and produce reactions r.

### A4 — Unified Transition  
The transition F must be unified for the whole system; no separate transitions for subsets.

### A5 — Reproducibility  
Same inputs and reactions must always produce the same transition result x'.

### A6 — Independence of F  
No single subject or subset may control, alter, or override F.

### A7 — Replicability and Verifiability  
Transitions and history must be reproducible and verifiable by all subjects.

### A8 — Consistent History  
The history h must be free of contradictions, cycles, and divergent branches.

---

## 3. Fundamental Threat Classes (T₁–T₄)

Every structural failure in any system can be classified into one or more of these four threats.

### T₁ — Loss of Subject Participation  
Violations: A1, A3  
- subjects cannot react  
- subjects lose access to inputs  
- subjects disappear from transitions

### T₂ — Corrupted Inputs or Reactions  
Violations: A3, A4  
- different subjects see different φ  
- reactions r are incomplete, altered, or missing

### T₃ — Broken Transition Function  
Violations: A4, A5  
- F produces inconsistent results  
- F becomes non-deterministic  
- F changes without structural cause

### T₄ — Architectural Monopoly  
Violations: A1, A2, A6, A7  
- one subject controls F  
- privileged pathways or hidden transitions  
- opaque or unverifiable history

---

## 4. Resilience Levels (S₁–S₇)

Each Sₙ resolves specific threat classes.  
The levels are independent, modular, and orthogonal.

| Level | Purpose | Resolves |
|-------|---------|----------|
| **S₁** | correctness of inputs & reactions | T₂, T₃ |
| **S₂** | duplication & independent verification | T₂, T₄ |
| **S₃** | participation diagnostics | T₁, T₄ |
| **S₄** | state consistency checking | T₂, T₃ |
| **S₅** | state restoration | T₃ |
| **S₆** | independence of F enforcement | T₄ |
| **S₇** | subsystem alignment & history merge | T₄ |

---

## 5. Architecture Dynamics (Meta-Architecture X)

Three internal functions govern activation and deactivation of resilience levels:

- **τ(history)** — detects threats from observed violations  
- **ρ(T)** — chooses minimal required resilience levels  
- **δ(history)** — deactivates levels when threats disappear

Architecture state evolves as:

m’ = (m ∪ ρ(T)) \ δ(history)

This ensures minimality, monotonicity, and self-organization.

---

## 6. Summary

S₀ defines an **invariant, minimal, implementation-independent** architecture for:

- identifying subjects,  
- maintaining correct collective transitions,  
- classifying failures,  
- and stabilizing systems through modular resilience levels.

This file serves as the compact reference for all other documents in the repository.