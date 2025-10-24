# Settings Module Specification

## Purpose

The Settings Module is responsible for managing the application's settings. It provides a high-level API for loading, saving, and modifying settings.

## Settings Management

### Loading Settings

- **Purpose**: Loads the settings from persistent storage.
- **Inputs**: None.
- **Outputs**: None.
- **Preconditions**: None.
- **Postconditions**: The settings are loaded into memory and are available for use.
- **Behavioral Examples**:
  - When the application starts, the settings are loaded from a configuration file.

### Saving Settings

- **Purpose**: Saves the settings to persistent storage.
- **Inputs**: None.
- **Outputs**: None.
- **Preconditions**: None.
- **Postconditions**: The settings are saved to persistent storage.
- **Behavioral Examples**:
  - When the user changes a setting, the new value is saved to the configuration file.

## Configuration Options

### Default New Note Folder

- **Type**: String
- **Description**: The default folder where new notes are created.

### Remote Sync Frequency

- **Type**: Enum (Automatic, Manual)
- **Description**: How often the application should sync with the remote repository.

### Theme

- **Type**: Enum (Light, Dark, SystemDefault)
- **Description**: The theme of the application.

### Zen Mode

- **Type**: Boolean
- **Description**: Whether to enable Zen mode, which hides all UI elements except for the note editor.

### Swipe To Delete

- **Type**: Boolean
- **Description**: Whether to allow deleting notes by swiping them.

### Bottom Menu Bar

- **Type**: Boolean
- **Description**: Whether to display the bottom menu bar.

### Confirm Delete

- **Type**: Boolean
- **Description**: Whether to confirm before deleting a note.

## Git Configuration

### Author Name

- **Type**: String
- **Description**: The author name to use for commits.

### Author Email

- **Type**: String
- **Description**: The author email to use for commits.

### Public SSH Key

- **Type**: String
- **Description**: The public SSH key to use for authentication with the remote repository.

### Private SSH Key

- **Type**: String
- **Description**: The private SSH key to use for authentication with the remote repository.

## Non-goals

- **User Interface**: This module does not provide a user interface for managing settings.
- **Cloud Sync**: This module does not handle the synchronization of settings across multiple devices.
