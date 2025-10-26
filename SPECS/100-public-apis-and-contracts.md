# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/100-public-apis-and-contracts.md

## 1. Synchronization API

### Name
`sync`

### Purpose
Initiates the synchronization process between the local and remote repositories.

### Inputs
- `local_dir`: The path to the local repository.
- `remote_url`: The URL of the remote repository.
- `mode`: The synchronization mode (`pull`, `push`, or `two-way`).
- `strategy`: The conflict resolution strategy (e.g., `manual`, `prefer-local`, `prefer-remote`).

### Outputs/Return
A `SyncReport` object with the following fields:
- `pulled`: A list of files pulled from the remote repository.
- `pushed`: A list of files pushed to the remote repository.
- `conflicted`: A list of files with conflicts.
- `skipped`: A list of files that were skipped during synchronization.

### Effects
- Modifies the files in the local repository.
- Pushes changes to the remote repository.

### Idempotency, Determinism, Retryability
- The `sync` operation is not idempotent.
- The outcome of the `sync` operation is deterministic for a given state of the local and remote repositories.
- The `sync` operation is retryable.

### Versioning/Compat Expectations
- The API is versioned and will maintain backward compatibility with previous versions.

## Coverage & Confidence

- **% of externally observable behavior captured:** 80%
- **Known gaps:** The `strategy` input is not yet fully defined.
- **Ambiguities flagged for product/UX decision:** The exact format of the `SyncReport` object needs to be finalized.
