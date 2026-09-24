# [BUG-018] High Friction and Installation Failure Due to Lack of Pre-Built Binaries

**Project:** ForkMesh (Desktop Client / Distribution)
**Severity:** High (UX / Onboarding)

**Environment:** Desktop client (qt_client), all platforms — most severe on non-pristine Windows environments

**Preconditions:** None — affects any user without a pristine build environment.

**Steps to Reproduce:**
1. Attempt to install the graphical client (`qt_client`) as a new user.
2. Follow the current required flow: clone the repository, manually resolve system dependencies, and compile from source locally.

**Expected Result:** Users should be able to download and run the application in under two minutes via single-click pre-built installers (`.exe` for Windows, `.dmg` for macOS, `.AppImage`/`.deb` for Linux) or a lightweight pre-configured Docker image, without needing a pristine host OS or local compilation.

**Actual Result:** Users with non-pristine operating systems or standard hardware cannot run the application directly. They are forced to set up a Linux virtual machine from scratch and compile locally, leading to excessive CPU/RAM usage, compilation crashes, and a multi-day troubleshooting onboarding process. This is the root cause behind related blockers such as BUG-009 and BUG-010.
