# 🧪 Installation Test Suite — ForkMesh Desktop (Windows)

Windows installer download, installation and first launch.

[← Back to Test Cases index](./README.md)

---

## TC-WIN-001 — Download the Windows installer from the official page

| Field | Value |
|---|---|
| **Module** | Installation |
| **Priority** | High |
| **Type** | Smoke |
| **Created** | 2026-10-15 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately) |
| **Status** | Not Executed |

**Preconditions**
- Windows 10 or 11 machine with internet access
- A web browser installed

**Test data**
- N/A

**Steps**
1. Go to https://forkmesh.com/
2. Scroll down to the section "Get the latest verified build"
3. Click "Download" on the Windows card
4. Open the browser's Downloads panel
5. If the browser warns about the file, click "Download suspicious file"

**Expected result**
- The download completes with no error page (e.g. `{"error":"mirror_unavailable"}`)
- The file is named `forkmesh-windows-x86_64-setup.exe` and its size matches the one shown on the card

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Screenshot of the main page with the URL visible
- Screenshot of the download section
- Screenshot of the Downloads panel with the finished file
- Note the version shown on the card and whether the browser showed a warning

---

## TC-WIN-002 — Install ForkMesh Desktop with the Windows installer

| Field | Value |
|---|---|
| **Module** | Installation |
| **Priority** | High |
| **Type** | Smoke |
| **Created** | 2026-10-15 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately) |
| **Status** | Not Executed |

**Preconditions**
- TC-WIN-001 passed (installer is in the Downloads folder)
- ForkMesh is not installed and no ForkMesh folder exists in `C:\Users\<user>\AppData\Local\`

**Test data**
- N/A

**Steps**
1. Open File Explorer and go to the Downloads folder
2. Double-click `forkmesh-windows-x86_64-setup.exe`
3. If Windows SmartScreen appears, click "More info"
4. Click "Run anyway"
5. In the installer, click "Next"
6. Leave the default destination folder
7. Click "Install"
8. Click "Finish"

**Expected result**
- The installer completes with no error message
- The app is installed in the default per-user folder (`C:\Users\<user>\AppData\Local\ForkMesh`)
- A ForkMesh shortcut exists on the desktop and/or in the Start menu

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Screenshot of the installation folder

---

## TC-WIN-003 — Open ForkMesh Desktop for the first time

| Field | Value |
|---|---|
| **Module** | Installation |
| **Priority** | High |
| **Type** | Smoke |
| **Created** | 2026-10-15 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately) |
| **Status** | Not Executed |

**Preconditions**
- TC-WIN-002 passed
- ForkMesh has never been opened on this machine

**Test data**
- N/A

**Steps**
1. Double-click the ForkMesh shortcut on the desktop
2. If a Windows Security Alert appears, select "Private networks" and click "Allow access"

**Expected result**
- The main window opens with no error dialog (e.g. missing DLL, `configuration_lock_unavailable`)
- The "Welcome to ForkMesh" dialog appears with the buttons "Take the tour" and "Explore on my own"
- The footer shows "Offline mode: Off"

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Video of the first launch
- Screenshot of the welcome dialog

---
