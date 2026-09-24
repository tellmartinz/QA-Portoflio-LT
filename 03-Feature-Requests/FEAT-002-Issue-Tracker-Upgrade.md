# [FEAT-002] Upgrade Issue Tracker for Professional QA: Multi-Format Attachments and Issue Templates

**Project:** ForkMesh (Platform / Issue Tracker)

**Current Limitations:**
- **Attachment limits:** the current Issue reporting form only accepts image uploads.
- **Lack of structure:** the description box is entirely blank, leading to inconsistent and ambiguous bug reports from regular users.

**Proposed Solution:**
- Expand file support to essential QA formats: `.mp4` (screen recordings), `.txt`/`.log` (crash logs, console output), `.csv`/`.chls` (network proxy sessions, e.g. Charles Proxy).
- Add a default Markdown template that auto-populates the Description box on "New issue," enforcing standard QA fields: Environment (OS, browser version), Steps to Reproduce, Expected Result, Actual Result.
