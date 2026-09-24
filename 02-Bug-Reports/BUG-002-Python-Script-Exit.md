# [BUG-002] Unhandled Script Exit on Cold Start in branch_pr_review.py

**Project:** ForkMesh (Backend / CLI Tooling)  
**Severity:** Medium (Code Defect / Process Interruption)  
**Frequency:** 100% Reproducible on fresh environment setup  

---

## 📌 Executive Summary
The CLI utility `tools/branch_pr_review.py` abruptly terminates execution with a bare `sys.exit` call when initiated on a clean environment without a pre-existing identity key path (`KEY_PATH`), instead of generating the missing identity key or providing structured fallback instructions.

---

## ⚙️ Environment & Preconditions
* Repository cloned on a clean local environment without configured user key pairs.
* File location: `tools/branch_pr_review.py` (Lines 375-377).

---

## 🐾 Steps to Reproduce
1. Initiate a cold start execution of `tools/branch_pr_review.py` without an existing key file at `KEY_PATH`.
2. Observe script termination behavior in terminal output.

---

## 🎯 Expected Result
The script should catch the missing key condition, automatically prompt to generate the missing identity key, or exit gracefully with a clear setup error message.

## ❌ Actual Result
The script triggers an unhandled `sys.exit` exception at lines 375-377 due to a bare exit handler on missing `KEY_PATH`, causing execution failure on cold starts.

---

## 🔍 Code Diagnosis & Recommendation
* **Root Cause:** Bare `sys.exit` invocation within `tools/branch_pr_review.py:375-377`.
* **Fix Recommendation:** Replace the immediate exit logic with an automated identity key generation routine or an informative CLI setup wizard.
