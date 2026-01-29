# TodoList App

A full-stack Todo List application with a React frontend and Express.js backend using MySQL for data persistence.

## Features

- Add new todos
- Edit existing todos
- Delete todos
- REST API with Express.js
- Responsive UI using React + Tailwind CSS

## Tech Stack

**Frontend:** React 19, Vite, Tailwind CSS
**Backend:** Node.js, Express.js 5
**Database:** MySQL

## Prerequisites

- Node.js 18+
- MySQL server running locally
- Create a database named `todolist` with a `tasks` table:

```sql
CREATE DATABASE todolist;
USE todolist;

CREATE TABLE tasks (
  id INT AUTO_INCREMENT PRIMARY KEY,
  description VARCHAR(255) NOT NULL,
  status VARCHAR(50) DEFAULT 'pending',
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Installation

1. **Clone the repository**
```bash
git clone https://github.com/ezzaansar/Todolist-react-.git
cd Todolist-react-
```

2. **Install backend dependencies**
```bash
cd backend
npm install
```

3. **Install frontend dependencies**
```bash
cd ../frontend
npm install
```

## Running the App

1. **Start the backend**
```bash
cd backend
npm run dev
```
Server runs at http://localhost:3000

2. **Start the frontend**
```bash
cd frontend
npm run dev
```
Frontend runs at http://localhost:5173

## Project Structure

```
Todolist-react-/
├── backend/           # Express.js API server
│   ├── src/
│   │   ├── main.js    # Server entry point
│   │   ├── tasks.js   # API routes
│   │   └── db.js      # MySQL connection
│   └── package.json
│
├── frontend/          # React + Tailwind frontend
│   ├── src/
│   │   ├── components/
│   │   ├── main.jsx
│   │   └── index.css
│   ├── vite.config.js
│   └── package.json
│
└── Readme.md
```

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /tasks | Fetch all tasks |
| GET | /tasks?status=done | Fetch tasks by status |
| GET | /tasks/:id | Fetch task by ID |
| POST | /tasks | Create new task |
| PUT | /tasks/:id | Update a task |
| DELETE | /tasks/:id | Delete a task |

**POST /tasks body:**
```json
{ "description": "Buy groceries" }
```

**PUT /tasks/:id body:**
```json
{ "description": "Updated task", "status": "done" }
```

## License

MIT License
