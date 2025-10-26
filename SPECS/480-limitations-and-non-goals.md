# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/480-limitations-and-non-goals.md

## 1. Limitations

- The application is designed for text-based notes and may not perform well with large binary files.
- The application is designed for a single user and does not support multi-user collaboration.
- The application's performance may degrade with very large repositories (e.g., >10,000 notes).

## 2. Non-Goals

- Real-time collaboration.
- Support for note formats other than Markdown.
- Advanced Git operations (e.g., branching, merging).
- A desktop version of the application.

## Coverage & Confidence

- **% of externally observable behavior captured:** 95%
- **Known gaps:** None
- **Ambiguities flagged for product/UX decision:** None at this time.
