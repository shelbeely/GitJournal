# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/150-data-models-and-io-schemas.md

## 1. Note Data Model

A note is represented as a Markdown file with the following structure:

### YAML Frontmatter
- A block of YAML at the beginning of the file, enclosed in `---` delimiters.
- Contains metadata about the note, such as `title`, `created`, `modified`, and `tags`.

### Body
- The main content of the note, in Markdown format.

### Schema
| Field | Type | Required | Default | Description |
|---|---|---|---|---|
| `title` | String | No | | The title of the note. |
| `created` | DateTime | No | | The creation date and time of the note. |
| `modified` | DateTime | No | | The last modification date and time of the note. |
| `tags` | List of Strings | No | `[]` | A list of tags associated with the note. |

### Validation Rules
- `created` and `modified` must be in ISO 8601 format.
- `tags` must be a list of strings.

### Normalization Rules
- Line endings are normalized to LF.

### Examples

#### Minimal
```markdown
---
---
This is a minimal note.
```

#### Typical
```markdown
---
title: My Note
created: 2023-10-27T10:00:00Z
modified: 2023-10-27T10:30:00Z
tags:
  - work
  - important
---
This is a typical note with metadata.
```

#### Edge
```markdown
---
title: ""
created: "2023-10-27"
tags: []
---
This is an edge case note.
```

## Coverage & Confidence

- **% of externally observable behavior captured:** 90%
- **Known gaps:** The full list of supported YAML frontmatter fields is not yet documented.
- **Ambiguities flagged for product/UX decision:** The behavior of the application when encountering invalid YAML frontmatter is not specified.
