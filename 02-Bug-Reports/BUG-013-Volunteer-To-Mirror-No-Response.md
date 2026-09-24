# [BUG-013] "Volunteer to Mirror" Button Does Nothing

**Project:** ForkMesh (Web App)
**Severity:** Medium (Functional / Dead UI Element)

**Environment:** Web App (app.forkmesh.com), viewing an "External repository" entry, no ForkMesh desktop node installed

**Preconditions:** A repository has been imported via the GitHub/GitLab/Codeberg flow and appears under "External repositories & stubs" with a "Volunteer to mirror" button.

**Steps to Reproduce:**
1. Go to the Repositories dashboard.
2. Scroll to "External repositories & stubs."
3. Click "Volunteer to mirror" on any listed external repository.

**Expected Result:** Clicking the button starts some process to volunteer the current node/account to mirror the repository — at minimum, visible feedback (a modal, loading state, instructional message, or redirect to the relevant setup step).

**Actual Result:** Nothing happens — no modal, no loading indicator, no error, no navigation. Combined with BUG-014, this confirms there is currently no working path, from the web app alone, to get a repository actually mirrored on ForkMesh's network without installing the desktop client — a significant first-impression / onboarding blocker for users evaluating the web version before installing anything.
