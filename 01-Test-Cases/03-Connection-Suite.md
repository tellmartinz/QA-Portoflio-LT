# 🧪 Connection Test Suite — ForkMesh Desktop (Windows)

Offline mode toggle and connection restore.

[← Back to Test Cases index](./README.md)

---

## TC-WIN-006 — Turn Offline mode on from the footer toggle

| Field | Value |
|---|---|
| **Module** | Connection |
| **Priority** | High |
| **Type** | Functional |
| **Created** | 2026-10-15 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately) |
| **Status** | Not Executed |

**Preconditions**
- User is logged in
- Footer shows "Offline mode: Off"
- Network > Nodes shows "1 of 1 relay(s) online" and `app.forkmesh.com` as Online

**Test data**
- N/A

**Steps**
1. Open ForkMesh Desktop
2. Click the "Offline mode" toggle in the footer to turn it on
3. Click "Network" in the left bar menu
4. Click the "Nodes" tab
5. Click the "Hosts" tab

**Expected result**
- The toggle is active and the footer label changes to indicate Offline mode is on
- Nodes shows "0 of 1 relay(s) online" and `app.forkmesh.com` as Offline
- Requests that are not sent show a message naming offline mode as the reason, not a generic network error
- No error dialog appears and the app does not freeze

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Screenshot of the footer before and after
- Screenshot of Network > Nodes before and after
- Screenshot of the message in Hosts

---

## TC-WIN-007 — Turn Offline mode off and restore the connection without restarting

| Field | Value |
|---|---|
| **Module** | Connection |
| **Priority** | High |
| **Type** | Functional |
| **Created** | 2026-10-19 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately), ForkMesh v1.2.x (exact version from the footer) |
| **Status** | Not Executed |

**Preconditions**
- User is logged in
- Footer indicates Offline mode is on
- Network > Nodes shows "0 of 1 relay(s) online" and `app.forkmesh.com` as Offline

**Test data**
- N/A

**Steps**
1. Open ForkMesh Desktop
2. Click the "Offline mode" toggle in the footer to turn it off
3. Click "Network" in the left bar menu
4. Click the "Nodes" tab
5. Click the "Hosts" tab
6. Click "Repos" in the left bar menu
7. Click the "Remote repositories" tab

**Expected result**
- The toggle is inactive and the footer label indicates Offline mode is off
- Within 60 seconds, Nodes shows "1 of 1 relay(s) online" and `app.forkmesh.com` as Online
- The offline-mode message in Hosts > Runners no longer appears
- The Remote repositories tab lists repositories
- Sent and Received values in Network > Endpoints increase again
- No app restart and no new login are needed, and no error dialog appears

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Assumption: the 60-second limit is a proposed threshold; adjust it if the developer states another value
- Record the time between turning the toggle off and the relay showing Online
- Screenshots of the footer, Network > Nodes and Repos > Remote repositories

---
