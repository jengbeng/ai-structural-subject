# Example: Subject Function eₛ

This example illustrates the minimal definition of a subject in S₀:

s = (φ → r)

The purpose is to show a clean, implementation-agnostic reaction function without assumptions about internal structure.

---

## 1. Subject definition

Let subject s operate with:

eₛ(φ) =
    if φ = "ping"   → r = "pong"
    if φ = "hello"  → r = "hi"
    if φ = "event"  → r = "ack"
    else            → r = "none"

This mapping alone satisfies the structural definition of a subject in S₀.

---

## 2. Example reactions

Case 1  
φ = "ping"  
r = "pong"

Case 2  
φ = "event"  
r = "ack"

Case 3  
φ = "unknown"  
r = "none"

---

## 3. Participation in transitions

The reaction r can be inserted directly into a collective transition:

F(x, φ, r) → x'

where r = eₛ(φ).

---

## 4. Notes

This is a purely structural example: any entity that consistently implements (φ → r) qualifies as a subject in the S₀ sense.