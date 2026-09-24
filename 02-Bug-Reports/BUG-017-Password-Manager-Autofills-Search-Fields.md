# [BUG-017] Browser Password Manager Mistakenly Treats Search Fields as Login Inputs

**Project:** ForkMesh (Web App / UI)
**Severity:** Low (UI / Privacy)

**Environment:** Web Browser (Chrome). Area: Global Search Bar, Top Repositories Search, Issues Search.

**Preconditions:** User is logged in with credentials saved in the browser.

**Steps to Reproduce:**
1. Log in to the ForkMesh web application with saved browser credentials.
2. Navigate to the Home dashboard or a Repository Issues page.
3. Click inside the Global Search bar, "Find a repository..." bar, or "Search issues..." bar.

**Expected Result:** Search fields remain blank and do not trigger the browser's credential manager (e.g., via `autocomplete="off"` or avoiding generic field names that trigger autofill).

**Actual Result:** The browser's password manager misidentifies the search inputs as login fields, automatically injecting the user's email address and displaying a credential-fill prompt — a privacy concern and an annoying UX loop while searching.
