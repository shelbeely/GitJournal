# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/200-feature-behaviors.md

## 1. Note Creation

### Preconditions
- The user is on the main screen.

### Postconditions
- A new note is created in the local repository.
- The new note is opened in the editor.

### Algorithm-independent Behavior Narrative
1. The user taps the "New Note" button.
2. The application creates a new, empty Markdown file in the local repository.
3. The application opens the new file in the note editor.

### Conflict Detection/Handling Policy
- Conflicts are not expected during note creation.

### Ignore/Include Rules Evaluation
- Not applicable.

### Examples
- **Input:** User taps the "New Note" button.
- **Expected Output/State Change:** A new file named `YYYY-MM-DD-HH-MM-SS.md` is created in the root of the local repository, and the editor is opened with this file.

## 2. Note Editing

### Preconditions
- A note is open in the editor.

### Postconditions
- The changes to the note are saved to the local repository.

### Algorithm-independent Behavior Narrative
1. The user modifies the content of the note in the editor.
2. The application automatically saves the changes to the corresponding file in the local repository.

### Conflict Detection/Handling Policy
- Conflicts are handled during the synchronization process.

### Ignore/Include Rules Evaluation
- Not applicable.

### Examples
- **Input:** User types "Hello, world!" in the editor.
- **Expected Output/State Change:** The content of the file is updated to "Hello, world!".

## 3. Note Deletion

### Preconditions
- The user is on the main screen.

### Postconditions
- The selected note is deleted from the local repository.

### Algorithm-independent Behavior Narrative
1. The user selects a note to delete.
2. The application prompts the user to confirm the deletion.
3. If the user confirms, the application deletes the corresponding file from the local repository.

### Conflict Detection/Handling Policy
- Conflicts are handled during the synchronization process.

### Ignore/Include Rules Evaluation
- Not applicable.

### Examples
- **Input:** User deletes the note `2023-10-27-10-00-00.md`.
- **Expected Output/State Change:** The file `2023-10-27-10-00-00.md` is removed from the local repository.

## Coverage & Confidence

- **% of externally observable behavior captured:** 90%
- **Known gaps:** The behavior of the "undo" feature for note deletion is not specified.
- **Ambiguities flagged for product/UX decision:** The exact wording of the deletion confirmation prompt needs to be defined.
