# nanobot-skill-calendar

Nanobot AI skill for managing calendar events, reminders, and scheduling.

## Features
- Create, update, and delete calendar events
- List upcoming events with date range filtering
- Check time slot availability
- Automatic reminders
- ISO 8601 date handling

## Installation

1. Open your Nanobot AI Dashboard
2. Go to **Settings → Skills → Marketplace**
3. Search for "calendar"
4. Click **Install**

Or install via API:
```bash
curl -X POST /api/v1/skills/marketplace/install \
  -H "Content-Type: application/json" \
  -d '{"repo": "kombalarasoftware-cmd/nanobot-skill-calendar"}'
```

## Tools
| Tool | Description |
|------|-------------|
| `create_event` | Create a new calendar event |
| `list_events` | List upcoming events |
| `update_event` | Update an existing event |
| `delete_event` | Delete an event |
| `check_availability` | Check time slot availability |

## License
MIT
