# 🧪 Test Cases — ForkMesh Desktop (Windows)

13 manual test cases designed for the **ForkMesh** Windows desktop client, from first download to repository creation, import and cloning. Cases follow a structured format: preconditions, test data, numbered steps, verifiable expected results, and the evidence to collect at execution.

> **Status:** designed and ready for execution. Each case lists the source of its expected result (UI text, project documentation or developer statement) and flags assumptions still pending confirmation.

| ID | Title | Module | Priority | Type | Status |
|---|---|---|---|---|---|
| [TC-WIN-001](./01-Installation-Suite.md#tc-win-001--download-the-windows-installer-from-the-official-page) | Download the Windows installer from the official page | Installation | High | Smoke | Not Executed |
| [TC-WIN-002](./01-Installation-Suite.md#tc-win-002--install-forkmesh-desktop-with-the-windows-installer) | Install ForkMesh Desktop with the Windows installer | Installation | High | Smoke | Not Executed |
| [TC-WIN-003](./01-Installation-Suite.md#tc-win-003--open-forkmesh-desktop-for-the-first-time) | Open ForkMesh Desktop for the first time | Installation | High | Smoke | Not Executed |
| [TC-WIN-004](./02-Accounts-Suite.md#tc-win-004--create-an-account-from-the-desktop-app-and-receive-the-confirmation-email) | Create an account from the desktop app and receive the confirmation email | Accounts | High | Functional | Not Executed |
| [TC-WIN-005](./02-Accounts-Suite.md#tc-win-005--log-in-to-the-desktop-app-with-valid-credentials) | Log in to the desktop app with valid credentials | Accounts | High | Functional | Not Executed |
| [TC-WIN-006](./03-Connection-Suite.md#tc-win-006--turn-offline-mode-on-from-the-footer-toggle) | Turn Offline mode on from the footer toggle | Connection | High | Functional | Not Executed |
| [TC-WIN-007](./03-Connection-Suite.md#tc-win-007--turn-offline-mode-off-and-restore-the-connection-without-restarting) | Turn Offline mode off and restore the connection without restarting | Connection | High | Functional | Not Executed |
| [TC-WIN-008](./04-Repositories-Suite.md#tc-win-008--create-a-new-public-repository-with-the-new-repository-button) | Create a new public repository with the "New repository..." button | Repositories | High | Functional | Not Executed |
| [TC-WIN-009](./04-Repositories-Suite.md#tc-win-009--create-a-private-repository-with-public-checked-using-the-new-repository-button) | Create a private repository with "Public" checked using the "New repository..." button | Repositories | Low | Functional | Not Executed |
| [TC-WIN-010](./04-Repositories-Suite.md#tc-win-010--import-a-local-folder-as-a-public-repository-with-the-import-folder-button) | Import a local folder as a public repository with the "Import folder..." button | Repositories | High | Functional | Not Executed |
| [TC-WIN-011](./04-Repositories-Suite.md#tc-win-011--import-a-local-folder-as-a-private-repository-with-the-import-folder-button) | Import a local folder as a private repository with the "Import folder..." button | Repositories | High | Functional | Not Executed |
| [TC-WIN-012](./04-Repositories-Suite.md#tc-win-012--import-a-folder-as-local-only-and-commit-while-offline-mode-is-on) | Import a folder as "Local only" and commit while Offline mode is on | Repositories | High | Functional | Not Executed |
| [TC-WIN-013](./04-Repositories-Suite.md#tc-win-013--clone-the-imported-public-repository-with-git-from-its-forkmesh-url) | Clone the imported public repository with Git from its ForkMesh URL | Repositories | High | Smoke | Not Executed |

### Suites
- [Installation](./01-Installation-Suite.md) — Windows installer download, installation and first launch.
- [Accounts](./02-Accounts-Suite.md) — Account creation and login from the desktop app.
- [Connection](./03-Connection-Suite.md) — Offline mode toggle and connection restore.
- [Repositories](./04-Repositories-Suite.md) — Creating, importing and cloning repositories.

### Techniques applied
Smoke testing, functional happy-path and negative scenarios, state-transition checks (Offline ↔ Online), and public/private access-control verification.
