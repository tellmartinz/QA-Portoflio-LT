# [BUG-015] No Path to Create a Hosted Repository Without the Desktop App or an External Provider

**Project:** ForkMesh (Web App / Onboarding)
**Severity:** Medium (Functional / Onboarding Gap)

**Environment:** Web App (app.forkmesh.com), no ForkMesh desktop node installed

**Preconditions:** New user who only has code in a local folder, has no GitHub/GitLab/Codeberg account connected, and does not have the ForkMesh desktop node running.

**Steps to Reproduce:**
1. Click to create a new repository ("Create & mirror a repository" modal).
2. Review the 3 "Source" tabs: Remote clone URL, Local repository, GitHub/GitLab/Codeberg.
3. Try "Local repository" by entering a local folder path without the desktop node running.

**Expected Result:** A way to create a completely empty repository from the web and push code to it directly with `git push`, without depending on the desktop app or an external provider — as GitHub, GitLab, or Bitbucket allow.

**Actual Result:** All 3 source options require either a repository that already exists on another provider, or the desktop node running locally to read the folder. There is no path to a "new, empty repository" purely from the web, which currently contradicts the project's stated vision of not depending on a single centralized provider.

**Additional Notes:**
- Minor UX inconsistency: the "Local repository" field's placeholder text shows a Linux-style path (`/home/you/code/my-project`) even for Windows users, where paths look different (`C:\Users...`).
- Confirmed the same limitation applies to the GitHub-import path (BUG-014): a user importing from GitHub remains fully dependent on GitHub afterward.
- Suggested fix: offer temporary/lightweight hosting by ForkMesh itself for new repos, with an option to migrate to a self-hosted mirror later — preserves the decentralization goal while removing the day-one onboarding wall.
