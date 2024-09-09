# Task Management App

A simple task management application built with Node.js, Express, and SQLite. This project allows you to manage tasks with states such as "done," "pending," and "on-hold."

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Database Schema](#database-schema)
- [Contributing](#contributing)
- [License](#license)

## Installation

### Prerequisites

- Node.js
- npm (Node Package Manager)

### Clone the Repository

```bash
git clone https://github.com/yourusername/task-management-app.git
cd task-management-app
```

### Install Dependencies

```bash
npm install
```

### Set Up Environment Variables

Create a `.env` file in the root directory with the following content:

```
PORT=3000
DATABASE_URL=path/to/your/database/file
```

### Initialize the Database

Run the database initialization script:

```bash
npm run init-db
```

## Usage

### Start the Server

```bash
npm start
```

The server will start on `http://localhost:3000`.

### API Endpoints

- **GET /api/tasks**

  Retrieve all tasks.

- **POST /api/tasks**

  Add a new task. Requires a JSON body with `text` and `state`:

  ```json
  {
    "text": "Task description",
    "state": "pending"
  }
  ```

- **PUT /api/tasks/:id**

  Update an existing task. Requires a JSON body with `text` and `state`:

  ```json
  {
    "text": "Updated task description",
    "state": "done"
  }
  ```

- **DELETE /api/tasks/:id**

  Delete a task by its ID.

### Frontend

The frontend for this project is a React application that interacts with the API. Ensure you have the frontend dependencies installed and start the development server:

```bash
cd frontend
npm install
npm start
```

## Database Schema

The database schema includes a single table `tasks` with the following columns:

- `id`: INTEGER PRIMARY KEY AUTOINCREMENT
- `text`: TEXT NOT NULL
- `state`: TEXT NOT NULL (CHECK constraint to ensure values are 'done', 'pending', or 'on-hold')