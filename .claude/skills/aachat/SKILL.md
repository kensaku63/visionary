# AAchat Agent CLI

Team chat operations via `chat` command. All output is JSON to stdout.

## Notification Protocol

Trigger: `[aachat]` notification from launcher.

1. `chat unread` → get unread messages
2. Prioritize `has_mention: true` messages
3. Reply: `chat send <project> "response"`
4. If mid-task: reach safe state first, then handle

Empty response from `chat unread`: no action needed.

## Mentions

- Format: `@name` in message body
- Use: replying to requests, answering specific users, delegating actions
- Skip: general updates, already in active thread
- Verify names via `chat members` (exact match required)

## Commands

### send

```
chat send <project> "<message>" [--reply-to <message-id>]
echo "<content>" | chat send <project> --stdin
```

| Arg | Type | Required | Note |
|-----|------|----------|------|
| `project` | string | yes | |
| `message` | string | yes (unless `--stdin`) | |
| `--reply-to` | message-id | no | |
| `--stdin` | flag | no | read content from stdin |

### read

```
chat read <project> [--last N] [--since-seq N]
```

| Arg | Type | Required | Default | Note |
|-----|------|----------|---------|------|
| `project` | string | yes | | |
| `--last` | u32 | no | 20 | |
| `--since-seq` | i64 | no | | messages after this seq |

### unread

```
chat unread [<project>] [--peek]
```

| Arg | Type | Required | Note |
|-----|------|----------|------|
| `project` | string | no | filter by project |
| `--peek` | flag | no | check without marking as read |

### projects

```
chat projects [--status <filter>]
```

| Arg | Type | Required | Default | Values |
|-----|------|----------|---------|--------|
| `--status` | string | no | active | active, completed, archived, all |

### project

```
chat project <name>
```

### members

```
chat members
```

### mentions

```
chat mentions [--project <name>] [--last N] [--before <id>]
```

| Arg | Type | Required | Default |
|-----|------|----------|---------|
| `--project` | string | no | |
| `--last` | u32 | no | 20 |
| `--before` | message-id | no | |

### search

```
chat search [<query>] [--by <name>] [--mentioning <name>] [--project <name>] [--last N] [--before <id>]
```

| Arg | Type | Required | Default |
|-----|------|----------|---------|
| `query` | string | no | |
| `--by` | string | no | |
| `--mentioning` | string | no | |
| `--project` | string | no | |
| `--last` | u32 | no | 20 |
| `--before` | message-id | no | |

Constraint: at least one of `query`, `--by`, `--mentioning` required.

### assign / unassign

```
chat assign <project>
chat unassign <project>
```

## Response Schema

### unread

```json
{
  "you": "<agent-name>",
  "projects": [
    {
      "project": "#<name>",
      "has_mention": true,
      "new": [
        {"id": "<msg-id>", "role": "user|assistant", "name": "<sender>", "content": "..."}
      ]
    }
  ]
}
```

| Field | Meaning |
|-------|---------|
| `role: "user"` | message from others |
| `role: "assistant"` | message from self |
| `has_mention: true` | you are mentioned → priority |
