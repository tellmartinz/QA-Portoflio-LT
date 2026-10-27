# 🧪 Repositories Test Suite — ForkMesh Desktop (Windows)

Creating, importing and cloning repositories.

[← Back to Test Cases index](./README.md)

---

## TC-WIN-008 — Create a new public repository with the "New repository..." button

| Field | Value |
|---|---|
| **Module** | Repositories |
| **Priority** | High |
| **Type** | Functional |
| **Created** | 2026-10-23 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately), ForkMesh v1.2.x (exact version from the footer) |
| **Status** | Not Executed |

**Preconditions**
- TC-WIN-005 passed and the user is logged in
- Footer shows "Offline mode: Off"
- No repository named `qa-new-001` exists in the account
- The folder `C:/Users/<user>/Documents/ForkMesh-tests` exists and does not contain a folder named `qa-new-001`

**Test data**
- Name: `qa-new-001`
- Description: Happy path testing
- Organization: the personal account (default)
- Visibility: Public
- Add a README on the main branch: unchecked
- Local only: unchecked
- Location: `C:/Users/<user>/Documents/ForkMesh-tests`

**Steps**
1. Open ForkMesh Desktop
2. Click "Repos" in the left bar menu
3. Click "New repository..."
4. Enter the name in the "Name" field
5. Enter the description in the "Description" field
6. Select the "Public" radio button
7. Make sure "Add a README on the main branch" and "Local only — don't publish it to the network" are unchecked
8. Click "Browse..." and select the folder in Location
9. Click "Create"
10. Click the "Remote repositories" tab
11. Open `https://app.forkmesh.com/<username>/qa-new-001` in a private browser window without logging in

**Expected result**
- No error dialog or error toast appears
- A folder `qa-new-001` exists inside the chosen Location
- The repository is listed under "Remote repositories" with its name, and not under "Private / local"
- The Mirrors column shows at least 1
- The private-window page shows the repository without asking to log in

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Source of expected result: the dialog texts "Public repos appear in the catalog" and "Local only - don't publish it to the network"
- The URL pattern comes from `app.forkmesh.com/forkmesh/forkmesh`; verify it with the "Web" button
- Record which files the new repo contains (in v1.2.x a repo created this way held only `.forkmesh/info.json`)
- Screenshots of the filled form, the Remote repositories list and the private window
- Cleanup: delete the repository, check "Keep the repository files on disk" and confirm. This frees the name for the next case

---

## TC-WIN-009 — Create a private repository with "Public" checked using the "New repository..." button

| Field | Value |
|---|---|
| **Module** | Repositories |
| **Priority** | Low |
| **Type** | Functional |
| **Created** | 2026-10-23 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately), ForkMesh v1.2.x (exact version from the footer) |
| **Status** | Not Executed |

**Preconditions**
- TC-WIN-005 passed and the user is logged in
- Footer shows "Offline mode: Off"
- No repository named `qa-new-002` exists in the account
- The folder `C:/Users/<user>/Documents/ForkMesh-tests` exists and has no folder named `qa-new-002`

**Test data**
- Name: `qa-new-002`
- Description: Private with local only test
- Visibility: Private
- Add a README on the main branch: unchecked
- Local only: checked
- Location: `C:/Users/<user>/Documents/ForkMesh-tests`

**Steps**
1. Open ForkMesh Desktop
2. Click "Repos" in the left bar menu
3. Click "New repository..."
4. Enter the name in the "Name" field
5. Enter the description in the "Description" field
6. Select the "Private" radio button
7. Check "Public"
8. Make sure "Add a README on the main branch" is unchecked
9. Click "Browse...", select the Location folder and click "Select Folder"
10. Click "Create"
11. Click the "Remote repositories" tab
12. Click the "Private / local" tab
13. Open `https://app.forkmesh.com/<username>/qa-new-002` in a private browser window without logging in

**Expected result**
- No error dialog or error toast appears
- A folder `qa-new-002` exists inside the chosen Location
- The repository is not listed under "Remote repositories"
- The repository is listed under "Private / local" with Access "Private"
- The private window does not show the repository's files or README

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Source of expected result: the dialog texts "Private repos stay hidden until you share them" and "Local only — don't publish it to the network"
- Record any difference between this result and TC-WIN-008 (Access label, Mirrors, Settings)
- Screenshots of the filled form, both tabs and the private window
- Cleanup: delete the repository in ForkMesh, check "Keep the repository files on disk", then delete the `qa-new-002` folder in File Explorer

---

## TC-WIN-010 — Import a local folder as a public repository with the "Import folder..." button

| Field | Value |
|---|---|
| **Module** | Repositories |
| **Priority** | High |
| **Type** | Functional |
| **Created** | 2026-10-23 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately), ForkMesh v1.2.x (exact version from the footer) |
| **Status** | Not Executed |

**Preconditions**
- TC-WIN-005 passed and the user is logged in
- Footer shows "Offline mode: Off"
- No repository named `task-cli` exists in the account
- The folder `C:/Users/<user>/Downloads/task-cli` is a Git repository with at least 1 commit (it contains a `.git` folder)

**Test data**
- Folder: the frozen `task-cli` fixture (`main.py`, `README.md`, `storage.py`, `tasks.py`, `test_tasks.py`)
- Visibility: Public

**Steps**
1. Open ForkMesh Desktop
2. Click "Repos" in the left bar menu
3. Click "Import folder..."
4. Select the `task-cli` folder
5. Click "Public" in the "Repository visibility" dialog
6. Click the "Remote repositories" tab
7. Click "Switch" on `task-cli`
8. Open `https://app.forkmesh.com/<username>/task-cli` in a private browser window without logging in

**Expected result**
- No error dialog or error toast appears
- The repository is listed under "Remote repositories", not under "Private / local"
- The Mirrors column shows at least 1
- The code view shows the 5 files and the rendered README, with the original commit in the history
- The private-window page shows the repository without asking to log in

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Source of expected result: the dialog text "Public repositories appear in the catalog"
- Assumption: the "Mirrors at least 1" check is inferred; to be confirmed with the developer
- Observed on v1.2.7: this flow imported the files but left the repo under "Private / local" with 0 mirrors and an error toast (reported)
- Screenshots of the visibility dialog, the Repos tabs, the code view and the private window
- Cleanup: delete the repository, check "Keep the repository files on disk" and confirm. Never delete the fixture folder

---

## TC-WIN-011 — Import a local folder as a private repository with the "Import folder..." button

| Field | Value |
|---|---|
| **Module** | Repositories |
| **Priority** | High |
| **Type** | Functional |
| **Created** | 2026-10-23 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately), ForkMesh v1.2.x (exact version from the footer) |
| **Status** | Not Executed |

**Preconditions**
- TC-WIN-005 passed and the user is logged in
- Footer shows "Offline mode: Off"
- No repository named `task-cli` exists in the account
- The folder `C:/Users/<user>/Downloads/task-cli` is a Git repository with at least 1 commit (it contains a `.git` folder)

**Test data**
- Folder: the frozen `task-cli` fixture (`main.py`, `README.md`, `storage.py`, `tasks.py`, `test_tasks.py`)
- Visibility: Private

**Steps**
1. Open ForkMesh Desktop
2. Click "Repos" in the left bar menu
3. Click "Import folder..."
4. Select the `task-cli` folder
5. Click "Private" in the "Repository visibility" dialog
6. Click the "Remote repositories" tab
7. Click the "Private / local" tab
8. Click "Switch" on `task-cli`
9. Open `https://app.forkmesh.com/<username>/task-cli` in a private browser window without logging in

**Expected result**
- No error dialog or error toast appears
- The repository is not listed under "Remote repositories"
- The repository is listed under "Private / local" with Access "Private"
- The code view shows the 5 files and the rendered README, with the original commit in the history
- The private window does not show the repository's files or README

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Source of expected result: the dialog text "Private repositories are hidden from public browse and clone routes unless shared"
- Record what the private window shows (login page, "not found", other)
- Record the Mirrors value of the row
- Screenshots of the visibility dialog, both tabs, the code view and the private window
- Cleanup: delete the repository, check "Keep the repository files on disk" and confirm. Never delete the fixture folder

---

## TC-WIN-012 — Import a folder as "Local only" and commit while Offline mode is on

| Field | Value |
|---|---|
| **Module** | Repositories |
| **Priority** | High |
| **Type** | Functional |
| **Created** | 2026-10-19 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately), ForkMesh v1.2.x (exact version from the footer) |
| **Status** | Not Executed |

**Preconditions**
- Footer indicates Offline mode is on
- The `task-cli` folder exists locally with its 5 project files
- No repository named `task-cli` is listed in Repos
- Local Git identity is set (the footer shows "Local Git identity not set" otherwise)

**Test data**
- Folder: `task-cli`
- Commit message: `offline commit`

**Steps**
1. Open ForkMesh Desktop
2. Click "Repos" in the left bar menu
3. Click "Import folder..."
4. Select the `task-cli` folder
5. In the "Repository visibility" dialog, click "Local only"
6. Click the "Private / local" tab
7. Open `task-cli`'s code view (click the repository, then "Switch")
8. Open `README.md` in Notepad, add the line "offline test" and save it
9. In ForkMesh, click "Commit changes"
10. Enter the commit message and confirm

**Expected result**
- The import completes with no error dialog or error toast
- `task-cli` is listed under "Private / local", not under "Remote repositories"
- The code view shows the 5 files and the rendered README
- The new commit appears in the history with the message "offline commit" and the local author
- No data is sent: Sent and Received values in Network > Endpoints do not increase during the whole case
- No message asks to sign in or to go online

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Source of expected result: the developer's description of Offline mode as intended for working on a local project that is not meant to be published
- Assumption: the exact screens for steps 4 and 9-10 are to be verified against the current version
- Screenshots of the visibility dialog, the Private / local tab, the code view and the history

---

## TC-WIN-013 — Clone the imported public repository with Git from its ForkMesh URL

| Field | Value |
|---|---|
| **Module** | Repositories |
| **Priority** | High |
| **Type** | Smoke |
| **Created** | 2026-10-26 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately), ForkMesh v1.2.x (exact version from the footer) |
| **Status** | Not Executed |

**Preconditions**
- TC-WIN-010 executed (`task-cli` imported as Public)
- Footer shows "Offline mode: Off"
- Git for Windows is installed (`git --version` prints a version)
- The folder `C:/Users/<user>/Documents/ForkMesh-tests` has no folder named `clone-check`

**Test data**
- Clone URL: the one ForkMesh shows for `task-cli` (pattern in the README: `https://forkmesh.com/<owner>/<repo>`)
- Target folder: `clone-check`

**Steps**
1. Open `https://app.forkmesh.com/<username>/task-cli` in a browser
2. Copy the clone URL shown on the repository page
3. Open PowerShell
4. Run: `cd C:\Users\<user>\Documents\ForkMesh-tests`
5. Run: `git clone <clone URL> clone-check`
6. Run: `cd clone-check`
7. Run: `git log --oneline`
8. Run: `git fsck`

**Expected result**
- The clone finishes with no error (no "repository not found", no timeout, no password prompt)
- The folder `clone-check` contains `main.py`, `README.md`, `storage.py`, `tasks.py` and `test_tasks.py`
- `git log --oneline` shows the same commit hash as the history in ForkMesh's code view
- `git fsck` reports no errors

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Source of expected result: the project README ("Browse and clone public repositories through a stable URL"); repository availability is the developer's first priority
- Assumption: where the clone URL appears on the repository page and its exact format are to be verified
- If TC-WIN-010 failed (for example 0 mirrors), run this case anyway: the key question is whether the code can still be retrieved
- Screenshot of PowerShell with the commands and their output, and of the commit hash in ForkMesh
- Cleanup: delete the `clone-check` folder

---
