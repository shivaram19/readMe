# Full-Stack Todo Application

A full-stack todo application built with React, Node.js, Express, and Prisma ORM, featuring user authentication and CRUD operations.

## Features

- User authentication (signup/login)
- JWT-based authorization
- Create, read, update, and delete todos
- Protected routes
- Database persistence with PostgreSQL
- Type-safe with TypeScript (Frontend)

## Tech Stack

### Frontend
- React with TypeScript
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

## Project Structure
project/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Login.tsx
│   │   │   ├── Signup.tsx
│   │   │   └── TodoList.tsx
│   │   ├── App.tsx
│   │   └── main.tsx
│   ├── package.json
│   └── vite.config.ts
│
└── backend/
├── routes/
│   ├── auth.js
│   └── todos.js
├── middleware/
│   └── auth.js
├── prisma/
│   └── schema.prisma
├── server.js
└── package.json

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