# [BUG-011] "Offline" Toggle Label Never Changes Regardless of State

**Project:** ForkMesh (Desktop Client / UI)
**Severity:** Low (UX / Clarity)

**Environment:** ForkMesh Desktop v0.8.10, Windows — bottom-right status bar of the main window

**Preconditions:** None specific — reproducible on default install.

**Steps to Reproduce:**
1. Open ForkMesh Desktop.
2. Click the "Offline" toggle in the bottom-right corner to switch it to green/active.
3. Click it again to switch it back to grey.

**Expected Result:** If the toggle represents live connection status, the label should update to reflect it (e.g., "Online" / "Offline"). If it's a manual mode switch instead, the label should make that clear regardless of state (e.g., a fixed "Offline mode" label with a separate ON/OFF indicator).

**Actual Result:** The text reads "Offline" in both the grey and green states — it never changes. This makes it ambiguous whether green means "you are now offline" or "offline mode is enabled," especially since toggling it has no visible effect on actual connectivity (see BUG-010).
