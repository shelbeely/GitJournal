# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/240-error-taxonomy-and-recovery.md

## 1. Canonical Error Groups

| Error Group | Description |
|---|---|
| **Authentication** | Errors related to authenticating with the remote Git repository. |
| **Network** | Errors related to network connectivity. |
| **Repository State** | Errors related to the state of the local or remote repository (e.g., conflicts, invalid repository). |
| **IO** | Errors related to reading from or writing to the filesystem. |
| **Conflicts** | Errors that occur when merging changes from the remote repository. |

## 2. User-Facing Message Shapes

| Error Group | User-Facing Message | Suggested Action |
|---|---|---|
| **Authentication** | "Authentication failed. Please check your credentials." | Re-enter credentials, check SSH key configuration. |
| **Network** | "Could not connect to the remote repository. Please check your internet connection." | Check internet connection, try again later. |
| **Repository State** | "An error occurred with the repository. Please try resetting the repository." | Reset the repository, contact support. |
| **IO** | "An error occurred while accessing the filesystem." | Check storage permissions, free up space. |
| **Conflicts** | "Conflicts were detected. Please resolve them manually." | Open the conflict resolution screen. |

## 3. Recovery Strategies, Backoff Rules, Safe Rollback

- **Authentication Errors:** The application will prompt the user to re-enter their credentials.
- **Network Errors:** The application will attempt to reconnect to the remote repository using an exponential backoff strategy (e.g., 1s, 2s, 4s, 8s).
- **Repository State Errors:** The application will provide an option to reset the local repository, which will delete the local repository and re-clone it from the remote.
- **IO Errors:** The application will display an error message and may not be able to continue.
- **Conflicts:** The application will guide the user through a conflict resolution process.

## Coverage & Confidence

- **% of externally observable behavior captured:** 85%
- **Known gaps:** The specific backoff parameters for network errors are not yet defined.
- **Ambiguities flagged for product/UX decision:** The user interface for the repository reset option needs to be designed.
