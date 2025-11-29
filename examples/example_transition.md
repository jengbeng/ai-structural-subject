# Example: Transition F(x, φ, S′)

This example demonstrates a minimal, abstract transition in the sense of S₀, showing how inputs φ and reactions r from a set of subjects S′ contribute to a unified state transition:

F : (x, φ, r) → x'

---

## 1. Setup

Let the system consist of three subjects:

S = {s₁, s₂, s₃}

Let the current system state be:

x = "idle"

Let all subjects receive the same input φ:

φ = "event_detected"

Each subject forms a reaction:

- s₁ → r₁ = "ack"
- s₂ → r₂ = "ack"
- s₃ → r₃ = "ack"

The set of reactions is:

r = {r₁, r₂, r₃}

---

## 2. Transition

According to S₀:

- all subjects must receive a unified φ (A3–A4),  
- all reactions r must be included in the transition (A1–A4),  
- the transition must be deterministic (A5),  
- no subject may control F (A6).

Thus, a valid F is:

F(x = "idle", φ = "event_detected", r = {"ack", "ack", "ack"}) → x' = "processing"

---

## 3. Resulting state

The next system state is:

x' = "processing"

This transition is unified, reproducible, and consistent with S₀ axioms.

---

## 4. Notes

This example is minimal and shows the **shape** of a correct S₀ transition. More complex cases (disagreement, partial φ, failure) correspond to threats T₂ and T₃ in the full specification.