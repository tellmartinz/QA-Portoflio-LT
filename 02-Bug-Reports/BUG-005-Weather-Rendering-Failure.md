# [BUG-005] Environment and Weather Effects Fail to Render Across Presets

**Project:** ForkMesh (3D Engine / Environment)  
**Severity:** Low (Visual / Rendering)  
**Frequency:** 100% Reproducible  

---

## 📌 Executive Summary
Selecting weather presets within the Preferences menu triggers a success toast notification ("Saved to your account..."), but fails to update the global Skybox, lighting, or particle engine systems across the map, updating only localized center coordinates.

---

## 🐾 Steps to Reproduce
1. Open the **Preferences** panel in the top-right menu.
2. Navigate to **View tab > Personal environment**.
3. Select any weather preset (e.g., *Daylight + rain*, *Daylight + snow*, or *Daylight + winter*).

---

## 🎯 Expected Result
The 3D rendering engine should update the global Skybox, directional lighting, and activate particle emitter systems across the entire map.

## ❌ Actual Result
A confirmation toast appears, but the global environmental rendering remains unchanged outside of a small center map origin point.
