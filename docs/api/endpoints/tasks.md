# Task Endpoints

This document provides detailed information about the task-related API endpoints.

## List Tasks

Retrieve a list of all tasks.

```http
GET /v1/tasks
```

### Query Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `status` | string | Filter by status (todo, in_progress, review, done) |
| `assignee` | string | Filter by assignee ID |
| `priority` | string | Filter by priority (low, medium, high, urgent) |
| `limit` | integer | Maximum number of results (default: 20) |
| `offset` | integer | Pagination offset (default: 0) |

### Example Response

```json
{
  "success": true,
  "data": {
    "tasks": [
      {
        "id": "task_123",
        "title": "Review documentation",
        "description": "Review and update API documentation",
        "status": "in_progress",
        "priority": "high",
        "assignee": {
          "id": "user_456",
          "name": "John Doe"
        },
        "created_at": "2026-02-20T10:00:00Z",
        "updated_at": "2026-02-22T15:30:00Z"
      }
    ],
    "total": 1,
    "limit": 20,
    "offset": 0
  }
}
```

## Create Task

Create a new task.

```http
POST /v1/tasks
```

### Request Body

```json
{
  "title": "string (required)",
  "description": "string (optional)",
  "assignee_id": "string (required)",
  "priority": "string (optional)",
  "due_date": "string (optional, ISO 8601 format)"
}
```

### Example Request

```json
{
  "title": "Implement new feature",
  "description": "Add export functionality to the dashboard",
  "assignee_id": "user_456",
  "priority": "high",
  "due_date": "2026-03-01T00:00:00Z"
}
```

## Get Task

Retrieve a specific task by ID.

```http
GET /v1/tasks/{task_id}
```

### Path Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `task_id` | string | The unique identifier of the task |

## Update Task

Update an existing task.

```http
PUT /v1/tasks/{task_id}
```

### Example Request

```json
{
  "title": "Updated task title",
  "status": "done"
}
```

## Delete Task

Delete a task permanently.

```http
DELETE /v1/tasks/{task_id}
```

### Example Response

```json
{
  "success": true,
  "message": "Task deleted successfully"
}
```

---

*Disclaimer: This is a fictional API for demonstration purposes.*
