# Full-Stack Todo Application

A full-stack todo application built with React, Node.js, Express, and Prisma ORM, featuring user authentication and CRUD operations.

## Features

- User authentication (signup/login)
- JWT-based authorization
- Create, read, update, and delete todos
- Protected routes
- Database persistence with PostgreSQL
- React with javascript (Frontend)

## Tech Stack

### Frontend
- React with javascript
- React Router DOM for routing
- Axios for API requests
- Vite as build tool

### Backend
- Node.js
- Express.js
- Prisma ORM
- PostgreSQL
- JSON Web Tokens (JWT)
- bcryptjs for password hashing

## Getting Started

### Prerequisites

- Node.js (v14 or higher)
- PostgreSQL installed and running
- npm or yarn package manager

### Installation

1. Clone the repository:
```bash
git clone [repository-url]
cd [project-name]
```

2. Frontend Setup:
```bash
cd frontend
npm install
```
3. Backend Setup:
```bash
cd backend
npm install
```

4. Create .env file in backend directory::
```bash
DATABASE_URL="postgresql://user:password@localhost:5432/todoapp"
JWT_SECRET="your-secret-key"
PORT=3000
```

5. Initialize the database:
```bash
npx prisma migrate dev --name init
```


6.Running the Application

Start the backend server:

```bash
cd backend
npm run dev

```
Start the frontend development server:

```bash
cd frontend
npm run dev
```


The application should now be running at:

Frontend: http://localhost:5173
Backend: http://localhost:3000

API Endpoints
Authentication

POST /api/signup - Register a new user
POST /api/login - Login user

Todos (Protected Routes)

GET /api/todos - Get all todos
POST /api/todos - Create a new todo
PUT /api/todos/:id - Update a todo
DELETE /api/todos/:id - Delete a todo


### Database Schema
## User
```bash
model User {
  id       Int      @id @default(autoincrement())
  email    String   @unique
  password String
  todos    Todo[]
}
```
## Todo
```bash
prismaCopymodel Todo {
  id        Int      @id @default(autoincrement())
  content   String
  completed Boolean  @default(false)
  userId    Int
  user      User     @relation(fields: [userId], references: [id])
}
```