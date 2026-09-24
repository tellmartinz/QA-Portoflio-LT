# [BUG-009] Desktop App Fails to Open — Persistent "configuration_lock_unavailable" Survives Full Uninstall/Reinstall

**Project:** ForkMesh (Desktop Client)
**Severity:** High (Regression / Blocker)

**Environment:** ForkMesh Desktop v1.2.3, Windows (regression from v0.8.10, which opened normally even when login/connectivity failed)

**Preconditions:**
- Previously working install of v0.8.10 upgraded to v1.2.3.

**Steps to Reproduce:**
1. Install ForkMesh Desktop v1.2.3.
2. Open ForkMesh.

**Expected Result:** The app opens to its normal interface (login screen or dashboard), consistent with previous versions.

**Actual Result:** The app immediately shows a fatal error dialog: "ForkMesh could not recover an interrupted mirror Actions configuration (`configuration_lock_unavailable`). No Actions services were started." No further access to the app is possible.

**Additional Verification:**
- Reproduced across 3 separate uninstall/reinstall cycles.
- One uninstall used GeekUninstaller to also clear leftover registry entries — same error persisted.
- Points to a server-side stuck state, not a local/client-side install issue, since a clean client install can't clear it.
