# Full-Stack To-Do Application

This is a simple to-do list application built with the following technologies:

- **Frontend:** React
- **Backend:** Node.js with Express
- **Database:** PostgreSQL
- **Containerization:** Docker and Docker Compose

## Prerequisites

Before running the project, make sure the following are installed and configured on your machine. Recommended minimum versions are listed where applicable.

- Git — to clone the repository
- Node.js (v16 or newer) and npm (or yarn) — required only if you plan to run the frontend or backend locally without Docker
- Docker Engine — required for Docker-based setup
- Docker Compose (v1.29+ or Docker Compose plugin) — required for docker-compose commands
- PostgreSQL (optional) — only if you want to run the database locally instead of via Docker
- A terminal / command line interface

Recommended quick checks:
```bash
git --version
node --version
npm --version
docker --version
docker-compose --version
psql --version   # if running PostgreSQL locally
```

Environment / configuration

- Create a `.env` file for the server (if you plan to run locally or to override values). Example variables used by this project (adjust as needed):

```env
# server/.env (example)
PORT=5000
DATABASE_URL=postgres://postgres:postgres@db:5432/todos_db
# Or when running PostgreSQL locally:
# DATABASE_URL=postgres://postgres:your_password@localhost:5432/todos_db
JWT_SECRET=your_jwt_secret
```

- Ports used by the Docker Compose setup (change if needed):
  - Frontend: 3000
  - Backend/API: 5000
  - PostgreSQL: 5432

## How to Run (Docker)

1. Clone this repository:

   ```bash
   git clone https://github.com/gouthamguntuku/fullstack-todo-app.git
   cd fullstack-todo-app
   ```

2. Start services with Docker Compose:

   ```bash
   docker-compose up --build
   ```

3. The application will be available at:
   - Frontend (React App): http://localhost:3000
   - Backend (API): http://localhost:5000

4. To stop and remove containers, networks, and volumes created by compose:

   ```bash
   docker-compose down --volumes
   ```

## How to Run Locally (without Docker)

If you prefer to run services locally (Node and PostgreSQL installed on your machine):

1. Backend
   - Open a terminal and go to the server folder (if `server/` exists):

     ```bash
     cd server
     npm install
     # create a .env file (see example above)
     npm run dev   # or npm start depending on package.json scripts
     ```

   - Ensure `DATABASE_URL` in `server/.env` points to a running PostgreSQL instance.

2. Frontend
   - In a separate terminal:

     ```bash
     cd client
     npm install
     npm start
     ```

3. The frontend will default to port 3000 and the backend to port 5000 unless overridden in config or .env.

## Troubleshooting & Notes

- If Docker Compose fails, ensure Docker Engine and Docker Compose are installed and that your user has permission to run Docker commands.
- If ports 3000, 5000, or 5432 are already in use, stop those services or change ports in docker-compose.yml and the application configuration.
- If you run the database locally, ensure the database, user, and password in `DATABASE_URL` exist and are accessible.
- For production deployment, set strong secrets (e.g., JWT_SECRET) and use a managed database or otherwise secure credentials.

## Services

- `client`: The React frontend.
- `server`: The Node.js/Express backend.
- `db`: The PostgreSQL database.

## Next steps (what I did and how I can help)
I prepared this expanded README with detailed prerequisites, environment examples, and both Docker and local run instructions. If you want, I can commit this update directly to main (as requested) — which I'm doing now — and open a PR or create a backup branch if you prefer not to push directly to main.
