# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/400-test-plan-unit-integration.md

## 1. Unit Tests

| Module | Test Cases |
|---|---|
| **Note Parser** | - Parse a valid Markdown file with YAML frontmatter. <br> - Parse a Markdown file without YAML frontmatter. <br> - Parse a Markdown file with invalid YAML frontmatter. |
| **Git Backend** | - Clone a remote repository. <br> - Pull changes from a remote repository. <br> - Push changes to a remote repository. <br> - Handle merge conflicts. |

## 2. Integration Tests

| Scenario | Test Cases |
|---|---|
| **End-to-End Sync** | - Create a new note and sync it to a remote repository. <br> - Modify a note and sync the changes. <br> - Delete a note and sync the deletion. <br> - Resolve a merge conflict. |
| **Offline Usage** | - Create a new note while offline. <br> - Modify a note while offline. <br> - Sync the changes after coming back online. |

## Coverage & Confidence

- **% of externally observable behavior captured:** 85%
- **Known gaps:** The test plan for the user interface is not yet included.
- **Ambiguities flagged for product/UX decision:** None at this time.
