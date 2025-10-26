# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/360-observability.md

## 1. Logs

| Level | Fields | Description |
|---|---|---|
| **Info** | `timestamp`, `message` | Informational messages about the application's state. |
| **Debug** | `timestamp`, `message`, `data` | Detailed debugging information. |
| **Error** | `timestamp`, `message`, `error`, `stacktrace` | Errors that occur during the application's execution. |

## 2. Metrics

| Name | Type | Units | Description |
|---|---|---|---|
| `sync_duration` | Histogram | Milliseconds | The duration of the synchronization process. |
| `sync_count` | Counter | | The number of successful synchronizations. |
| `sync_error_count` | Counter | | The number of failed synchronizations. |

## 3. Events

| Name | Fields | Description |
|---|---|---|
| `app_launched` | `timestamp` | The application was launched. |
| `note_created` | `timestamp`, `note_id` | A new note was created. |
| `note_deleted` | `timestamp`, `note_id` | a note was deleted. |
| `sync_started` | `timestamp` | The synchronization process was started. |
| `sync_completed` | `timestamp`, `status` | The synchronization process was completed. |

## Coverage & Confidence

- **% of externally observable behavior captured:** 80%
- **Known gaps:** The full list of events and metrics is not yet defined.
- **Ambiguities flagged for product/UX decision:** The specific logging format needs to be finalized.
