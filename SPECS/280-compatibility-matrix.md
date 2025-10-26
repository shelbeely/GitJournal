# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/280-compatibility-matrix.md

| Feature | Linux | macOS | Windows | iOS | Android |
|---|---|---|---|---|---|
| **Note Creation** | Supported | Supported | Supported | Supported | Supported |
| **Note Editing** | Supported | Supported | Supported | Supported | Supported |
| **Note Deletion** | Supported | Supported | Supported | Supported | Supported |
| **Synchronization**| Supported | Supported | Supported | Supported | Supported |
| **Case-Sensitivity**| Filesystem Dependent | Filesystem Dependent | Filesystem Dependent | Case-Sensitive | Case-Sensitive |
| **Git Versions**| 2.x | 2.x | 2.x | N/A | N/A |
| **Network Transport**| SSH, HTTPS | SSH, HTTPS | SSH, HTTPS | SSH, HTTPS | SSH, HTTPS |
| **Locale/Encoding**| UTF-8 | UTF-8 | UTF-8 | UTF-8 | UTF-8 |

## Coverage & Confidence

- **% of externally observable behavior captured:** 90%
- **Known gaps:** The specific versions of iOS and Android that are supported are not yet defined.
- **Ambiguities flagged for product/UX decision:** None at this time.
