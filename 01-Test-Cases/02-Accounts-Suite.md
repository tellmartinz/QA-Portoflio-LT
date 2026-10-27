# 🧪 Accounts Test Suite — ForkMesh Desktop (Windows)

Account creation and login from the desktop app.

[← Back to Test Cases index](./README.md)

---

## TC-WIN-004 — Create an account from the desktop app and receive the confirmation email

| Field | Value |
|---|---|
| **Module** | Accounts |
| **Priority** | High |
| **Type** | Functional |
| **Created** | 2026-10-15 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately) |
| **Status** | Not Executed |

**Preconditions**
- TC-WIN-003 passed and the user is not logged in
- "Offline mode" is Off
- Access to an inbox whose email has never been registered in ForkMesh

**Test data**
- Email: an inbox you control
- Username: a new username (e.g. `qa-tester-001`)
- Password: one that meets the rules shown on the form (never recorded in this document)

**Steps**
1. Open ForkMesh Desktop
2. Click "Log in / Sign up"
3. In the dropdown, click "Create account..."
4. Fill in the email, username and password fields
5. Select the checkbox "I agree to the terms and privacy"
6. Click "Create account"
7. Open the email inbox

**Expected result**
- After step 3, the browser opens `https://app.forkmesh.com/signup`
- The form submits with no validation errors and the page indicates the account was created or an email was sent (record the exact text)
- An email from ForkMesh arrives within 5 minutes asking to confirm the address, with a working link or code

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Screenshot of the signup page with all fields filled (password and part of the email censored)
- Screenshot of the confirmation email
- Note if the browser autofilled any field

---

## TC-WIN-005 — Log in to the desktop app with valid credentials

| Field | Value |
|---|---|
| **Module** | Accounts |
| **Priority** | High |
| **Type** | Functional |
| **Created** | 2026-10-15 |
| **Environment** | Windows 10 and Windows 11 (run once per OS, record each result separately) |
| **Status** | Not Executed |

**Preconditions**
- TC-WIN-003 passed and the user is not logged in
- "Offline mode" is Off
- A ForkMesh account whose email is confirmed (e.g. created in TC-WIN-004), with 2FA disabled

**Test data**
- Username: the registered username
- Email: the registered email
- Password: the account password (never recorded in this document)

**Steps**
1. Open ForkMesh Desktop
2. Click "Log in / Sign up"
3. In the displayed menu, click "Log in to your account..."
4. Enter the username and click "Continue"
5. Enter the email
6. Enter the password
7. Leave the 2FA field empty
8. Click "Log in"

**Expected result**
- A dialog titled "Account switched" appears stating "Signed in as <username>"
- No "Login failed." dialog appears
- The green "Log in / Sign up" button is replaced by the account avatar
- Network > Relays lists `app.forkmesh.com` as online

**Actual result:** _to be filled at execution_

**Notes / Evidence**
- Screenshot of the "Account switched" dialog
- Screenshot of the top bar after login
- Screenshot of Network > Relays
- Note if any field arrived pre-filled by the browser or the app

---
