# [BUG-003] Elevator System Fails to Initialize via Secondary Entrances

**Project:** ForkMesh (3D Interactive Environment)  
**Severity:** Medium (Functional / Trigger Volume)  
**Frequency:** 100% Reproducible  

---

## 📌 Executive Summary
The elevator system trigger volume fails to register character entry when approaching through either of the two secondary/exterior entrances. The floor selection panel remains inactive, functioning only when the elevator is accessed exclusively through the main office lobby entrance.

---

## ⚙️ Preconditions
* Character has standard role permissions.

---

## 🐾 Steps to Reproduce
1. Approach the elevator structure using any of the two secondary/exterior entrances.
2. Enter the elevator cab and attempt to interact with the floor selection panel.
3. *(Control Test)* Exit the elevator, re-enter through the main office lobby entrance, and interact with the panel again.

---

## 🎯 Expected Result
The elevator trigger volume should detect character entry from all 3 entrance points, activating the floor selection UI panel according to player role permissions.

## ❌ Actual Result
The elevator system only initializes when accessed via the main office lobby door. Approaching through secondary entrances leaves the floor panel completely inactive and unresponsive.
