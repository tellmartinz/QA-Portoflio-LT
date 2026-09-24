# [BUG-007] Abrupt Settings Redirection on 'Reconnect Node' Button for Web Users

**Project:** ForkMesh (Web App / Navigation UX)  
**Severity:** Low (UX / User Guidance)  
**Frequency:** 100% Reproducible  

---

## 📌 Executive Summary
Clicking the yellow "Reconnect node" indicator while browsing repositories in a web-only environment redirects users directly to `/dashboard/settings/nodes` without contextual guidance, input placeholders, or explanation on local node requirements.

---

## 🐾 Steps to Reproduce
1. Log into the web application without a local node running.
2. Access a repository displaying an offline mirror state.
3. Click the yellow **Reconnect node** button in the top navigation bar.
4. Observe redirection to `/dashboard/settings/nodes` and attempt input.

---

## 🎯 Expected Result
Clicking "Reconnect node" should display an explanatory modal detailing local node setup requirements, or provide clear placeholder text inside the Node ID input field.

## ❌ Actual Result
The user is abruptly redirected to Settings. Manual text entry throws a generic `"Enter a valid node ID"` error, creating a UX dead end for web-only users.
