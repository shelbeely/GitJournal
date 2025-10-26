# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/300-performance-and-resource-budgets.md

| Operation | Complexity | Threshold |
|---|---|---|
| **Initial Clone** | O(N) where N is the number of files in the repository | Skip >10MB files by default |
| **Synchronization** | O(M) where M is the number of changed files | Skip >10MB files by default |
| **Note Loading** | O(1) per note | |
| **Note Saving** | O(1) per note | |

## Caching Rules
- The application caches the content of notes in memory to improve performance.
- The cache is invalidated when a note is modified or when the repository is synchronized.

## Disk/Network I/O Constraints
- The application is designed to minimize disk and network I/O.
- Synchronization is performed in the background to avoid blocking the user interface.

## Coverage & Confidence

- **% of externally observable behavior captured:** 75%
- **Known gaps:** The performance of the application with very large notes is not yet specified.
- **Ambiguities flagged for product/UX decision:** The exact caching strategy needs to be defined.
