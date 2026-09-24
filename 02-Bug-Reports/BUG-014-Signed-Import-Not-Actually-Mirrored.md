# [BUG-014] "Signed Import Complete" From GitHub Does Not Result in an Actually Mirrored Repository

**Project:** ForkMesh (Web App / Import Flow)
**Severity:** Medium (Functional / Misleading State)

**Environment:** Web App (app.forkmesh.com), repository imported from GitHub, no ForkMesh desktop node installed

**Preconditions:** A public, empty GitHub repository was created and pushed to locally, then imported into ForkMesh via the "Create & mirror a repository" modal, using the "GitHub / GitLab / Codeberg" source tab.

**Steps to Reproduce:**
1. Open "Create & mirror a repository" and select the "GitHub / GitLab / Codeberg" tab.
2. Paste the URL of a public GitHub repository.
3. Leave "Provider access token" empty (public repo, token not required).
4. Click "Start resumable import."
5. Wait for the modal to display "Started 1 resumable import; 1 reached signed completion" with a signed state hash and object count.
6. Navigate to the Repositories dashboard and locate the repository.

**Expected Result:** After "signed completion" is reported, the repository appears as an active mirror hosted on ForkMesh's network, matching the confidence implied by the word "complete."

**Actual Result:** The repository does not appear as a mirror at all — it's listed under "External repositories & stubs," marked "External repository," with text stating it is external metadata not currently mirrored by ForkMesh, and that ForkMesh does not own or control it. Clicking into it redirects back to GitHub. The "signed import complete" messaging strongly implies mirroring finished successfully, when in fact only metadata/verification completed — no actual mirroring occurred. The same limitation applies to repos created from scratch (see BUG-015).
