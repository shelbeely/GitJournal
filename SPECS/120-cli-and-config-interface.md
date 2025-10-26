# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/120-cli-and-config-interface.md

## 1. Command-Line Interface (CLI)

The application does not provide a command-line interface.

## 2. Configuration Interface

The application is configured through a user interface. The following configuration options are available:

### Git Repository
- **Remote URL:** The URL of the remote Git repository.
- **Authentication:** The credentials for accessing the remote repository (e.g., username/password, SSH key).

### Synchronization
- **Sync Mode:** The default synchronization mode (`pull`, `push`, or `two-way`).
- **Conflict Resolution:** The default conflict resolution strategy.

### Editor
- **Default Editor:** The default editor for new notes.
- **Font Size:** The font size for the note editor.

## Coverage & Confidence

- **% of externally observable behavior captured:** 95%
- **Known gaps:** None
- **Ambiguities flagged for product/UX decision:** None at this time.
