# API Overview

The TaskTracker API allows you to integrate task management capabilities into your own applications.

## Base URL

```
https://api.tasktracker.example.com/v1
```

## Authentication

All API requests require authentication using an API key.

```http
Authorization: Bearer YOUR_API_KEY
```

To obtain an API key:

1. Log in to your TaskTracker account
2. Navigate to Settings > API Keys
3. Click "Generate New Key"

## Rate Limits

| Plan | Requests per minute |
|------|---------------------|
| Free | 60 |
| Pro | 300 |
| Enterprise | 1000 |

## Response Format

All responses are returned in JSON format.

### Success Response

```json
{
  "success": true,
  "data": { ... },
  "message": "Operation completed successfully"
}
```

### Error Response

```json
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid input data"
  }
}
```

## Available Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/tasks` | GET | List all tasks |
| `/tasks` | POST | Create a new task |
| `/tasks/{id}` | GET | Get a specific task |
| `/tasks/{id}` | PUT | Update a task |
| `/tasks/{id}` | DELETE | Delete a task |

For detailed information about task endpoints, see [Task Endpoints](./endpoints/tasks.md).

---

*Disclaimer: This is a fictional API for demonstration purposes.*
