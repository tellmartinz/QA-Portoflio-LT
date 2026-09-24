# [BUG-016] Issues List Incorrectly Filters Based on Global Search Bar Instead of Local Issues Search Bar

**Project:** ForkMesh (Web App / Repository Issues Page)
**Severity:** Medium (Functional / Search Logic)

**Environment:** Web Browser

**Preconditions:** None.

**Steps to Reproduce:**
1. Navigate to a repository's Issues page.
2. Enter any text (or let browser autofill insert text) into the Global Search bar at the top right of the navigation menu.
3. Leave the local "Search issues by title..." bar completely empty.

**Expected Result:** The repository issues list only filters based on the local "Search issues..." input. The Global Search bar should not interfere with the local page state.

**Actual Result:** The issues list filters its results based on the text in the Global Search bar instead, displaying "No results for '[Global Search Text]'" even though the local issues search bar is empty — rendering the issues list broken/hidden until the global search is cleared.
