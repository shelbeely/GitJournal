# Core Module Specification

## Purpose

The Core Module is responsible for managing the fundamental data structures of the application, including notes and folders. It provides a high-level abstraction for interacting with the underlying version control system, allowing for synchronization of notes.

## Note Management

### Creating a Note

- **Purpose**: Creates a new, unsaved note object.
- **Inputs**:
  - The folder that will contain the new note.
  - The file format of the new note (e.g., Markdown, Plain Text).
  - The title of the note.
  - The body of the note.
  - A map of additional metadata to include in the note (optional).
  - The name of the file to be created (optional).
- **Outputs**: A new note object.
- **Preconditions**: The parent folder must exist.
- **Postconditions**: A new note object is created in memory but is not yet saved to the repository.
- **Error Cases**:
  - If the parent folder does not exist, an error is returned.
- **Edge Cases**:
  - If a file name is not provided, a unique file name is generated.
  - If no additional metadata is provided, the note is created with no additional metadata.
- **Behavioral Examples**:
  - A user can create a new note by providing a title and body.

### Rebuilding a File Name

- **Purpose**: Generates a new file name for a note based on its title and creation date.
- **Inputs**:
  - The note object to be renamed.
- **Outputs**: A new file name for the note.
- **Preconditions**: The note must have a title and creation date.
- **Postconditions**: A new file name is generated but is not yet applied to the note.
- **Error Cases**:
  - If the note does not have a title or creation date, an error is returned.
- **Behavioral Examples**:
  - When a note's title is changed, the file name is updated to reflect the new title.

## Folder Management

### Adding a Note to a Folder

- **Purpose**: Adds a note to a folder.
- **Inputs**:
  - The note object to be added.
- **Outputs**: None.
- **Preconditions**: The note must not already be in the folder.
- **Postconditions**: The note is added to the folder's list of notes.
- **Error Cases**:
  - If the note is already in the folder, an error is returned.
- **Behavioral Examples**:
  - A user can move a note from one folder to another.

### Removing a Note from a Folder

- **Purpose**: Removes a note from a folder.
- **Inputs**:
  - The note object to be removed.
- **Outputs**: None.
- **Preconditions**: The note must be in the folder.
- **Postconditions**: The note is removed from the folder's list of notes.
- **Error Cases**:
  - If the note is not in the folder, an error is returned.
- **Behavioral Examples**:
  - A user can delete a note from a folder.

### Renaming a Folder

- **Purpose**: Renames a folder.
- **Inputs**:
  - The new name for the folder.
- **Outputs**: None.
- **Preconditions**: The new name must be a valid folder name.
- **Postconditions**: The folder is renamed.
- **Error Cases**:
  - If the new name is invalid, an error is returned.
- **Behavioral Examples**:
  - A user can rename a folder to better reflect its contents.

## Non-goals

- **Real-time Collaboration**: This module does not handle real-time collaboration between multiple users.
- **Advanced Version Control Operations**: This module does not expose advanced version control operations, such as branching and merging.
- **User Interface**: This module does not provide a user interface for managing notes and folders.
