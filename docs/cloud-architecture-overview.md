# Cloud Architecture Overview

This document provides a simple system context view of the TODO monorepo architecture.

## System Context Diagram

```mermaid
flowchart LR
    U[User]
    B[Browser]
    FE[React Frontend\npackages/frontend]
    API[Express API\npackages/backend]
    DB[(In-Memory Store\nSQLite in process)]

    U --> B
    B --> FE
    FE -->|HTTP /api/tasks| API
    API --> DB
```

## Sequence Diagram: Create TODO

```mermaid
sequenceDiagram
    participant U as User
    participant FE as React Frontend
    participant API as Express API
    participant DB as In-Memory SQLite

    U->>FE: Enter title/description/due date and submit form
    FE->>FE: Validate title is present
    FE->>API: POST /api/tasks { title, description, due_date }
    API->>API: Validate request payload
    API->>DB: INSERT task row
    DB-->>API: Created row id
    API->>DB: SELECT created task by id
    DB-->>API: Created task record
    API-->>FE: 201 Created + task JSON
    FE->>API: GET /api/tasks
    API->>DB: SELECT * FROM tasks ORDER BY due_date, created_at
    DB-->>API: Task list including new TODO
    API-->>FE: 200 OK + tasks JSON
    FE-->>U: Updated task list displays new TODO
```

## Notes

- The frontend runs as a React application and calls the backend over HTTP.
- The backend runs as an Express API.
- Data is stored in an in-memory SQLite database, so data resets when the backend process restarts.
