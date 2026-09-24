# [BUG-006] Interactive Table Anchor Point Displacement & Mesh Boundary Bleed

**Project:** ForkMesh (World Objects / Collision)  
**Severity:** Low (Visual / Anchor Alignment)  
**Frequency:** 100% Reproducible  

---

## 📌 Executive Summary
Interactive round tables located across the map (Lobby Portal / Rooftop Patio) suffer from misaligned origin/anchor points. Jumping onto or interacting with the table causes character model displacement directly inside physical table geometry.

---

## 🐾 Steps to Reproduce
1. Approach any interactive round table (e.g., Rooftop Patio).
2. Jump on top of the table mesh and trigger an interaction prompt.

---

## 🎯 Expected Result
The interaction anchor point should respect physical mesh collision boundaries.

## ❌ Actual Result
The character model and UI response bleed directly inside the table structure due to incorrect anchor point origins.
