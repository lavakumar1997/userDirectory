# User Directory (React + .NET 8 + SQLite)

A small User Directory app.

## Tech Stack
- Frontend: React + React Router (Vite)
- Backend: .NET 8 Web API
- DB: SQLite (EF Core)
- Docs: Swagger/OpenAPI

## Features Implemented (Core)
### Frontend
- Two pages:
  - **List**: loads users from API on mount, shows loading spinner, empty state, and error state.
  - **Add**: create user form with client-side validation + inline errors.
- On successful create: redirects to List and shows a success toast.
- Top navigation with **Add** and **List**.

API Integration used:
- `GET /api/users`
- `POST /api/users`

### Backend
CRUD endpoints:
- `GET /api/users` → list
- `GET /api/users/{id}` → single
- `POST /api/users` → create
- `PUT /api/users/{id}` → update
- `DELETE /api/users/{id}` → delete

Validation:
- DataAnnotations on DTOs/models; returns 400 validation problems on invalid input.
Status codes:
- 200, 201, 204, 400, 404.

Swagger:
- Enabled in Development environment.

## Database
SQLite file path is configurable:
- Default: `/data/app.db` (appsettings.json)
- Development uses: `data/app.db` (appsettings.Development.json)

On startup the API ensures the DB file exists using `Database.EnsureCreated()`.

## How to Run Locally (Optional)
> Note: Running locally is optional per assignment; code is ready if needed.

### Backend
- `cd backend/UserDirectory.Api`
- `dotnet restore`
- `dotnet run`

### Frontend
- `cd frontend/user-directory-web`
- `npm install`
- `npm run dev`

If needed, set API base URL in frontend:
- `VITE_API_BASE=http://localhost:5000`

## Bonus Items (Not included)
- OAuth2/OIDC
- Docker / docker-compose
- Unit tests

## AI / Tools Disclosure
This project structure and boilerplate were created with assistance from AI tools (ChatGPT) for generating initial scaffolding and code snippets. Final code was reviewed and adjusted manually.
