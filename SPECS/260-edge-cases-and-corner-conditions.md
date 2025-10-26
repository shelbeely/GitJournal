# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/260-edge-cases-and-corner-conditions.md

| Edge Case | Behavior |
|---|---|
| **Filename Collisions** | If a note is created with a filename that already exists, the application will append a number to the filename to make it unique (e.g., `note.md`, `note-1.md`). |
| **Unicode Normalization** | Filenames and note content are handled as Unicode strings. The application does not perform any specific normalization. |
| **Reserved Names** | The application does not restrict the use of reserved filenames (e.g., `CON`, `PRN`). |
| **CRLF/LF Normalization** | Line endings in note files are normalized to LF before being committed to the Git repository. |
| **Symlinks** | Symlinks are not supported and will be treated as regular files. |
| **Hidden Files** | Files and folders starting with a `.` are ignored by the application. |
| **Long Paths** | The application supports paths up to the limit of the underlying operating system. |
| **Large Files** | The application is designed for text-based notes and may not perform well with large binary files. |
| **Git LFS Pointers** | Git LFS pointers are treated as opaque files and their content is not displayed in the application. |
| **Simultaneous Edits** | If a note is edited simultaneously on multiple devices, a conflict will be created during synchronization. |
| **Clock Skew** | The application relies on the device's clock for timestamps. Significant clock skew may cause issues with timestamps and sorting. |

## Coverage & Confidence

- **% of externally observable behavior captured:** 80%
- **Known gaps:** The behavior of the application with very large repositories is not yet specified.
- **Ambiguities flagged for product/UX decision:** The maximum file size for notes should be defined.
