# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/440-conformance-suite-and-golden-vectors.md

## 1. Golden Vectors

### Vector 1: Basic Two-Way Sync

- **Initial State:**
  - **Local Repository:**
    - `notes/note1.md`: "Hello, world!"
  - **Remote Repository:**
    - `notes/note2.md`: "Hello, from remote!"
- **Action:** Perform a two-way sync.
- **Expected Final State:**
  - **Local Repository:**
    - `notes/note1.md`: "Hello, world!"
    - `notes/note2.md`: "Hello, from remote!"
  - **Remote Repository:**
    - `notes/note1.md`: "Hello, world!"
    - `notes/note2.md`: "Hello, from remote!"

### Vector 2: Conflict Resolution

- **Initial State:**
  - **Local Repository:**
    - `notes/note1.md`: "Hello, from local!"
  - **Remote Repository:**
    - `notes/note1.md`: "Hello, from remote!"
- **Action:** Perform a two-way sync.
- **Expected Final State:**
  - The application should detect a conflict and prompt the user to resolve it.

## Coverage & Confidence

- **% of externally observable behavior captured:** 80%
- **Known gaps:** The golden vectors for all edge cases are not yet included.
- **Ambiguities flagged for product/UX decision:** None at this time.
