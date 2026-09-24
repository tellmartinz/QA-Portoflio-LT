# [BUG-001] Quadcopter Collision Clip Allows Bypass of Elevator Role Permissions

**Project:** ForkMesh (3D / Web Environment)  
**Severity:** High (Security / Boundary Collision)  
**Frequency:** 100% Reproducible  

---

## 📌 Executive Summary
A boundary collision flaw in the quadcopter vehicle logic allows unauthorized players to bypass interior elevator access controls. By piloting the quadcopter along the exterior glass façade of the main office building, the vehicle clips through exterior boundaries, enabling players to dismount on restricted floor levels (e.g., Floors 2 & 3) without holding required role permissions.

---

## ⚙️ Preconditions
* Player character has restricted permissions (unauthorized for Floor 2 & Floor 3).
* A functional quadcopter is spawned and accessible in the outdoor environment.

---

## 🐾 Steps to Reproduce
1. Mount and pilot the quadcopter outside the main office building.
2. Fly vertically along the exterior glass façade of the building.
3. Directionally navigate into any restricted floor level (e.g., Floor 2 Marketing or Floor 3 Engineering).
4. Dismount the vehicle inside the restricted floor zone.

---

## 🎯 Expected Result
Exterior building glass panels and flight boundary colliders should block the quadcopter from passing through, enforcing role-based elevator access rules.

## ❌ Actual Result
The quadcopter clips through exterior glass boundaries and floor colliders, allowing the player to freely fly into restricted zones and dismount, completely bypassing elevator access controls.

---

## 🛠️ Root Cause & Impact
* **Impact:** Renders role-based access controls obsolete for 3D environments.
* **Suggested Fix:** Apply rigid body colliders to exterior building glass panels with active raycast layer masking for vehicle entities.
