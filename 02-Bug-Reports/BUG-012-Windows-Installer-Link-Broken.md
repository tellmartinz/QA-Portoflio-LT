# [BUG-012] Windows Installer Download Link Returns "mirror_unavailable" Error

**Project:** ForkMesh (Website / Distribution)
**Severity:** High (Functional / Onboarding Blocker)

**Environment:** Web browser, forkmesh.com homepage, "Direct downloads" section (v0.8.10)

**Preconditions:** None — public download page, no login required.

**Steps to Reproduce:**
1. Go to forkmesh.com.
2. Scroll to the "Direct downloads / Get the latest verified build" section.
3. Click the "Windows desktop" card (`forkmesh-windows-x86_64-setup.exe`).

**Expected Result:** The signed `.exe` file downloads to the user's machine.

**Actual Result:** The link redirects to `app.forkmesh.com/api/repo/forkmesh/forkmesh/releases/blob/sha256/...?filename=forkmesh-windows-x86_64-setup.exe`, which returns a raw JSON error instead of a file: `{"error":"mirror_unavailable"}`. New Windows users have no way to obtain the client from the official page.
