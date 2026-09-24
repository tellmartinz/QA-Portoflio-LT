# [BUG-004] Quadcopter Flight Interaction State Locks Permanently After Parking

**Project:** ForkMesh (Vehicles / Interactive Objects)  
**Severity:** Medium (State Management)  
**Frequency:** 100% Reproducible  

---

## 📌 Executive Summary
After mounting, flying, and parking the quadcopter near the office building, dismounting and walking away causes the vehicle to enter a locked state. Upon returning, interaction triggers become unresponsive, rendering the vehicle permanently unusable for subsequent flights.

---

## ⚙️ Preconditions
* Quadcopter entity is active and operational in the world map.

---

## 🐾 Steps to Reproduce
1. Mount and fly the quadcopter to the office building zone.
2. Dismount/exit the vehicle and park it on the ground.
3. Walk away from the quadcopter until interaction prompts clear.
4. Return to the parked quadcopter and attempt to interact or re-mount.

---

## 🎯 Expected Result
The vehicle state should reset its interaction listener upon dismount, allowing repeated flight sessions.

## ❌ Actual Result
The quadcopter enters a permanently locked interaction state, ignoring input prompts upon player return.
