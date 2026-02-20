# Calendar

## Metadata
- **name**: calendar
- **version**: 1.0.0
- **author**: kombalarasoftware
- **category**: productivity
- **description**: Manage calendar events, reminders, and scheduling

## Prompt Extension
You have access to a personal calendar system. You can create, list, update, and delete events.

When the user mentions a meeting, appointment, or deadline, offer to create a calendar event.
When asked about schedule or availability, check existing events.
Always confirm event details (date, time, title) before creating.
Use ISO 8601 format for dates internally but present human-readable dates to the user.

## Tools

### create_event
Create a new calendar event.

**Parameters:**
- `title` (string, required): Event title
- `start_time` (string, required): Start time in ISO 8601 format
- `end_time` (string, optional): End time. Defaults to 1 hour after start
- `description` (string, optional): Event description
- `location` (string, optional): Event location
- `reminder_minutes` (integer, optional): Reminder before event in minutes (default: 15)

**Returns:** Event object with id, title, start_time, end_time, description, location

### list_events
List upcoming calendar events.

**Parameters:**
- `start_date` (string, optional): Start of date range (ISO 8601). Defaults to today
- `end_date` (string, optional): End of date range. Defaults to 7 days from start
- `limit` (integer, optional): Max results (default: 20)

**Returns:** Array of events sorted by start_time

### update_event
Update an existing calendar event.

**Parameters:**
- `event_id` (integer, required): ID of the event to update
- `title` (string, optional): New title
- `start_time` (string, optional): New start time
- `end_time` (string, optional): New end time
- `description` (string, optional): New description
- `location` (string, optional): New location

**Returns:** Updated event object

### delete_event
Delete a calendar event.

**Parameters:**
- `event_id` (integer, required): ID of the event to delete

**Returns:** Confirmation message

### check_availability
Check if a time slot is available.

**Parameters:**
- `start_time` (string, required): Start of the time slot (ISO 8601)
- `end_time` (string, required): End of the time slot

**Returns:** Object with is_available boolean and conflicting events if any
