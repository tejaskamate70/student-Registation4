# JWT Authentication with Protected Notes CRUD API

A full-stack **JWT Authentication and Notes Management System** built with **React**, **Express.js**, **JSON Web Token (JWT)**, and **bcryptjs**. Users can register, log in, and securely manage their own notes through protected CRUD API endpoints.

> **Note:** This project uses in-memory storage for users and notes. All data is lost when the server restarts.

---

# Features

## Authentication

- User Registration
- User Login
- Password Hashing using bcryptjs
- JWT Token Authentication
- Protected API Routes
- Logout Functionality

## Notes Management

- Create Notes
- View Personal Notes
- Edit Notes
- Delete Notes
- User-specific Notes (each user sees only their own notes)

## Frontend

- React + Vite
- Responsive User Interface
- Login/Register Toggle
- Error & Success Messages
- Notes CRUD Interface

## Backend

- Express REST API
- JWT Authentication Middleware
- bcrypt Password Encryption
- CORS Enabled

---

# Technologies Used

## Frontend

- React
- Vite
- CSS
- Fetch API

## Backend

- Node.js
- Express.js
- JSON Web Token (jsonwebtoken)
- bcryptjs
- CORS

---

# Project Structure

```
jwt-notes-app/
│
├── backend/
│   ├── index.js
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── App.jsx
│   │   ├── App.css
│   │   └── main.jsx
│   └── package.json
│
└── README.md
```

---

# Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/jwt-notes-app.git
```

```bash
cd jwt-notes-app
```

---

# Backend Setup

Move into the backend directory.

```bash
cd backend
```

Install dependencies.

```bash
npm install
```

Run the server.

```bash
node index.js
```

Backend runs at

```
http://localhost:5000
```

---

# Frontend Setup

Open another terminal.

```bash
cd frontend
```

Install dependencies.

```bash
npm install
```

Start the React development server.

```bash
npm run dev
```

Frontend runs at

```
http://localhost:5173
```

---

# Required Backend Packages

```bash
npm install express cors jsonwebtoken bcryptjs
```

---

# API Endpoints

## Register

Create a new account.

```
POST /register
```

### Request

```json
{
  "username": "john",
  "password": "123456"
}
```

### Success Response

```json
{
  "message": "Account created! You can now log in."
}
```

---

## Login

Authenticate a user and receive a JWT.

```
POST /login
```

### Request

```json
{
  "username": "john",
  "password": "123456"
}
```

### Success Response

```json
{
  "token": "eyJhbGciOiJIUzI1NiIs..."
}
```

---

# Protected Notes API

All Notes endpoints require the following header:

```
Authorization: Bearer YOUR_JWT_TOKEN
```

---

## Create Note

```
POST /notes
```

### Request

```json
{
  "text": "Study JWT Authentication"
}
```

### Response

```json
{
  "id": 1,
  "username": "john",
  "text": "Study JWT Authentication"
}
```

---

## Get All Notes

```
GET /notes
```

### Response

```json
[
  {
    "id": 1,
    "username": "john",
    "text": "Study JWT Authentication"
  }
]
```

---

## Update Note

```
PUT /notes/:id
```

### Request

```json
{
  "text": "Study JWT and Express"
}
```

### Response

```json
{
  "id": 1,
  "username": "john",
  "text": "Study JWT and Express"
}
```

---

## Delete Note

```
DELETE /notes/:id
```

### Success Response

```
204 No Content
```

---

# Authentication Workflow

```
User Registers
      │
      ▼
Password Hashing
      │
      ▼
User Login
      │
      ▼
Password Verification
      │
      ▼
JWT Generated
      │
      ▼
React Stores JWT
      │
      ▼
Protected API Request
Authorization: Bearer Token
      │
      ▼
JWT Middleware
      │
      ▼
Token Verified
      │
      ▼
CRUD Operations Allowed
```

---

# CRUD Workflow

```
Login
   │
   ▼
Load Notes
   │
   ▼
Create Note
   │
   ▼
Edit Note
   │
   ▼
Delete Note
```

---

# React Features

- User Registration
- User Login
- Automatic Notes Loading
- Add New Note
- Edit Existing Notes
- Delete Notes
- Logout
- Error Handling
- Success Messages

---

# Backend Features

- JWT Middleware
- Password Encryption
- Protected CRUD APIs
- User-specific Data
- RESTful Endpoints
- JSON Request Validation

---

# HTTP Status Codes

| Status | Meaning |
|---------|---------|
|200|Success|
|201|Created|
|204|Deleted Successfully|
|400|Bad Request|
|401|Unauthorized|
|403|Forbidden|
|404|Not Found|
|409|Username Already Exists|

---

# Example Testing with Postman

## Register

```
POST http://localhost:5000/register
```

```json
{
  "username": "john",
  "password": "123456"
}
```

---

## Login

```
POST http://localhost:5000/login
```

```json
{
  "username": "john",
  "password": "123456"
}
```

Copy the JWT token.

---

## Create Note

```
POST http://localhost:5000/notes
```

Headers

```
Authorization: Bearer YOUR_TOKEN
```

Body

```json
{
  "text": "My First Note"
}
```

---

## Get Notes

```
GET http://localhost:5000/notes
```

---

## Update Note

```
PUT http://localhost:5000/notes/1
```

```json
{
  "text": "Updated Note"
}
```

---

## Delete Note

```
DELETE http://localhost:5000/notes/1
```

---

# Security Features

- Passwords are hashed using **bcryptjs**.
- JWT protects all Notes API endpoints.
- Users can only access their own notes.
- Authentication middleware verifies every protected request.
- Unauthorized access is blocked.

---

# Current Limitations

- No database (uses in-memory objects and arrays)
- Data is lost after server restart
- No refresh tokens
- No persistent login
- No user profile management

---

# Future Enhancements

- SQLite/MySQL/PostgreSQL/MongoDB integration
- Refresh Tokens
- Email Verification
- Password Reset
- User Profile Page
- Rich Text Notes
- Search Notes
- Note Categories
- Favorite Notes
- Pagination
- Docker Deployment
- Unit Testing
- Role-Based Authorization

---

# License

This project is intended for educational purposes and may be freely modified for learning full-stack authentication, JWT, and CRUD API development.

---

# Author

**Tejas kamate**

Built using **React**, **Express.js**, **JWT**, and **bcryptjs** to demonstrate secure authentication and protected CRUD operations with user-specific notes.
