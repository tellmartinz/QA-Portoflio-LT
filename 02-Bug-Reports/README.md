# 🐞 Bug Reports Index

18 defects identified while testing **ForkMesh**, a decentralized alternative to GitHub — spanning its 3D interactive environment, desktop client (Windows), and web app.

### 🔴 High
| ID | Title | Category |
|---|---|---|
| [BUG-001](./BUG-001-Quadcopter-Permission-Bypass.md) | Quadcopter Collision Clip Allows Bypass of Elevator Role Permissions | Security / Boundary Collision |
| [BUG-009](./BUG-009-Desktop-Configuration-Lock-Regression.md) | Desktop App Fails to Open — Persistent `configuration_lock_unavailable` Survives Reinstall | Regression / Blocker |
| [BUG-010](./BUG-010-Relay-Connection-Login-Failure.md) | Desktop Client Cannot Connect to Relay — Login Fails Despite Correct Credentials | Functional / Blocker |
| [BUG-012](./BUG-012-Windows-Installer-Link-Broken.md) | Windows Installer Download Link Returns "mirror_unavailable" Error | Functional / Onboarding Blocker |
| [BUG-018](./BUG-018-No-Prebuilt-Binaries-Onboarding-Friction.md) | High Friction and Installation Failure Due to Lack of Pre-Built Binaries | UX / Onboarding |

### 🟠 Medium
| ID | Title | Category |
|---|---|---|
| [BUG-002](./BUG-002-Python-Script-Exit.md) | Unhandled Script Exit on Cold Start in `branch_pr_review.py` | Code Defect / Process Interruption |
| [BUG-003](./BUG-003-Elevator-Secondary-Entrances.md) | Elevator System Fails to Initialize via Secondary Entrances | Functional / Trigger Volume |
| [BUG-004](./BUG-004-Quadcopter-State-Lock.md) | Quadcopter Flight Interaction State Locks Permanently After Parking | State Management |
| [BUG-008](./BUG-008-Offline-Mode-Scope-Overreach.md) | "Offline" Mode Blocks Far More Functionality Than Intended | Functional / Scope Overreach |
| [BUG-013](./BUG-013-Volunteer-To-Mirror-No-Response.md) | "Volunteer to Mirror" Button Does Nothing | Functional / Dead UI Element |
| [BUG-014](./BUG-014-Signed-Import-Not-Actually-Mirrored.md) | "Signed Import Complete" Does Not Result in an Actually Mirrored Repository | Functional / Misleading State |
| [BUG-015](./BUG-015-No-Path-To-Hosted-Repo-Without-Desktop.md) | No Path to Create a Hosted Repository Without the Desktop App or an External Provider | Functional / Onboarding Gap |
| [BUG-016](./BUG-016-Global-Search-Overrides-Local-Issues-Search.md) | Issues List Incorrectly Filters Based on Global Search Bar | Functional / Search Logic |

### 🟡 Low
| ID | Title | Category |
|---|---|---|
| [BUG-005](./BUG-005-Weather-Rendering-Failure.md) | Environment and Weather Effects Fail to Render Across Presets | Visual / Rendering |
| [BUG-006](./BUG-006-Table-Anchor-Displacement.md) | Interactive Table Anchor Point Displacement & Mesh Boundary Bleed | Visual / Anchor Alignment |
| [BUG-007](./BUG-007-Reconnect-Node-Guidance.md) | Abrupt Settings Redirection on 'Reconnect Node' Button for Web Users | UX / User Guidance |
| [BUG-011](./BUG-011-Offline-Toggle-Label-Ambiguous.md) | "Offline" Toggle Label Never Changes Regardless of State | UX / Clarity |
| [BUG-017](./BUG-017-Password-Manager-Autofills-Search-Fields.md) | Browser Password Manager Mistakenly Treats Search Fields as Login Inputs | UI / Privacy |
