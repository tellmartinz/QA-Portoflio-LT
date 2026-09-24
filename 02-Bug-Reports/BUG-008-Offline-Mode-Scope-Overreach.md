# [BUG-008] "Offline" Mode Blocks Far More Functionality Than Intended

**Project:** ForkMesh (Desktop Client / Networking)
**Severity:** Medium (Functional / Scope Overreach)

**Environment:** ForkMesh Desktop v0.8.10, Windows

**Preconditions:**
- Desktop app installed and running.

**Steps to Reproduce:**
1. Open ForkMesh Desktop.
2. Click the "Offline" toggle (bottom-right corner) to activate it.
3. Open the Network panel → "Endpoints" tab.

**Expected Result:** Per the codebase's own design comment (`qt_client/src/MainWindowSetup.cpp`, inside the `if (m_nodeOffline)` block), offline mode should only affect two things: staying connected for chat, but not serving repos or sending the reward heartbeat. All other API traffic (status, dashboard, network stats, accounts, chat activity, agent/model listings) should continue working normally.

**Actual Result:** 8 of 9 tracked endpoints (`/api/status`, `/api/dashboard`, `/api/network/stats`, `/api/accounts/users`, `/api/chat/activity`, `/api/forkbot/models`, etc.) are never sent and show "Offline mode." Only `/api/version` succeeds (HTTP 200). The Web Requests tab shows an explicit error that `app.forkmesh.com` could not be reached because ForkMesh is in offline mode.

**Root Cause (code reference):** `qt_client/src/MainWindow.cpp:156` loads `m_nodeOffline` from persisted `QSettings` at startup instead of resetting it per session — combined with the endpoint-gating logic checking that flag far more broadly than the documented intent in `MainWindowSetup.cpp`.
