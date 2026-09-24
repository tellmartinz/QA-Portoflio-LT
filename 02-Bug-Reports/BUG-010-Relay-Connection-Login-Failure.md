# [BUG-010] Desktop Client Cannot Connect to Relay — Login Fails Despite Correct Credentials

**Project:** ForkMesh (Desktop Client / Networking)
**Severity:** High (Functional / Blocker)

**Environment:** ForkMesh Desktop v0.8.10, Windows, freshly installed. Same account logs in successfully on the web app (app.forkmesh.com via browser).

**Preconditions:**
- Windows Defender Firewall exception for `forkmesh.exe` confirmed granted on Private networks.
- App fully closed (no leftover process in Task Manager) and reopened fresh.
- Credentials verified correct via successful login on the web app with the same email/password.
- "Offline" toggle tested in both states, with no change in behavior.

**Steps to Reproduce:**
1. Install ForkMesh Desktop v0.8.10 on Windows and launch it.
2. Log in with a valid, verified ForkMesh account (email + password, no 2FA).
3. Open the "Network" panel → "Relays" tab.

**Expected Result:** The app connects to the `app.forkmesh.com` relay, shows it as online, and allows login with valid credentials — matching the web app's behavior on the same machine and network.

**Actual Result:** Login fails immediately with a generic "Login failed." dialog, no further detail. The Network → Relays panel shows "0 of 1 relay(s) online," with the relay listed as Offline, Response time —, Version —. The summary shows 0/0 websockets connected, 0 B sent/received — indicating no data is exchanged with the relay at all, not just an auth rejection.
