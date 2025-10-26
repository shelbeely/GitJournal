# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/180-state-machines-and-sequence-diagrams.md

## 1. Synchronization State Machine

### States
- `Idle`: The application is not currently synchronizing.
- `Pulling`: The application is fetching changes from the remote repository.
- `Merging`: The application is merging remote changes with local changes.
- `Pushing`: The application is pushing local changes to the remote repository.
- `Done`: The synchronization process is complete.
- `Error`: An error occurred during synchronization.

### Events
- `startSync`: Initiates the synchronization process.
- `pullComplete`: The pull operation has completed successfully.
- `mergeComplete`: The merge operation has completed successfully.
- `pushComplete`: The push operation has completed successfully.
- `errorOccurred`: An error has occurred.

### Guards
- `isTwoWaySync`: The synchronization mode is `two-way`.
- `isPullSync`: The synchronization mode is `pull`.
- `isPushSync`: The synchronization mode is `push`.

### Actions
- `fetchRemote`: Fetches changes from the remote repository.
- `mergeChanges`: Merges remote and local changes.
- `pushChanges`: Pushes local changes to the remote repository.

### Transition Table

| Current State | Event | Guard | Next State | Actions |
|---|---|---|---|---|
| `Idle` | `startSync` | `isTwoWaySync` | `Pulling` | `fetchRemote` |
| `Idle` | `startSync` | `isPullSync` | `Pulling` | `fetchRemote` |
| `Idle` | `startSync` | `isPushSync` | `Pushing` | `pushChanges` |
| `Pulling` | `pullComplete` | `isTwoWaySync` | `Merging` | `mergeChanges` |
| `Pulling` | `pullComplete` | `isPullSync` | `Done` | |
| `Merging` | `mergeComplete` | | `Pushing` | `pushChanges` |
| `Pushing` | `pushComplete` | | `Done` | |
| `Pulling` | `errorOccurred` | | `Error` | |
| `Merging` | `errorOccurred` | | `Error` | |
| `Pushing` | `errorOccurred` | | `Error` | |

## 2. Sequence Diagram: First Run

```
User -> App: Launch
App -> Filesystem: Check for local repository
Filesystem -> App: Not found
App -> User: Show setup screen
User -> App: Enter remote repository URL and credentials
App -> Network Remotes: Clone remote repository
Network Remotes -> App: Repository cloned
App -> Filesystem: Store local repository
App -> User: Show main screen
```

## 3. Sequence Diagram: Conflict Resolution

```
App -> Network Remotes: Pull changes
Network Remotes -> App: Changes with conflicts
App -> User: Show conflict resolution screen
User -> App: Resolve conflicts
App -> Filesystem: Save resolved files
App -> Network Remotes: Push resolved changes
Network Remotes -> App: Changes pushed
```

## Coverage & Confidence

- **% of externally observable behavior captured:** 85%
- **Known gaps:** The conflict resolution flow is not yet fully detailed.
- **Ambiguities flagged for product/UX decision:** The user interface for conflict resolution needs to be defined.
