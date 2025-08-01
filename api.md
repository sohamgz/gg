# GEMS Backend API Documentation

## Base URLs

### Development (Local)
```
http://localhost:5000/api
```

### Production (Render)
```
https://gems-backend-whsr.onrender.com
```

## Authentication
All protected endpoints require a Bearer token in the Authorization header:
```
Authorization: Bearer node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
```

## Error Responses
All endpoints may return the following error responses:

- **400 Bad Request**: Invalid request data
- **401 Unauthorized**: Missing or invalid authentication token
- **404 Not Found**: Resource not found
- **500 Internal Server Error**: Server error

---

## Authentication Endpoints

### 1. Register User
**POST** `/auth/register`

Register a new user account.

**Request Body:**
```json
{
  "name": "string (required)",
  "email": "string (required, must be valid email format)",
  "password": "string (required)"
}
```

**Success Response (201):**
```json
{
  "_id": "string",
  "name": "string",
  "email": "string",
  "token": "string (JWT token)"
}
```

**Error Responses:**
- **400**: `{"message": "User already exists"}`
- **500**: `{"message": "error message"}`

---

### 2. Login User
**POST** `/auth/login`

Authenticate an existing user.

**Request Body:**
```json
{
  "email": "string (required)",
  "password": "string (required)"
}
```

**Success Response (200):**
```json
{
  "_id": "string",
  "name": "string",
  "email": "string",
  "token": "string (JWT token)"
}
```

**Error Responses:**
- **401**: `{"message": "Invalid credentials"}`
- **500**: `{"message": "error message"}`

---

## User Management Endpoints

*All user endpoints require authentication*

### 3. Get All Users
**GET** `/auth/users`

Get a list of all users (password field excluded).

**Headers:**
```
Authorization: Bearer <token>
```

**Success Response (200):**
```json
[
  {
    "_id": "string",
    "name": "string",
    "email": "string",
    "createdAt": "date",
    "updatedAt": "date"
  }
]
```

**Error Responses:**
- **401**: `{"message": "Not authorized, no token"}` or `{"message": "Not authorized, token failed"}`
- **500**: `{"message": "error message"}`

---

### 4. Get User by ID
**GET** `/auth/users/:id`

Get a specific user by ID (password field excluded).

**Headers:**
```
Authorization: Bearer <token>
```

**Success Response (200):**
```json
{
  "_id": "string",
  "name": "string",
  "email": "string",
  "createdAt": "date",
  "updatedAt": "date"
}
```

**Error Responses:**
- **401**: `{"message": "Not authorized, no token"}` or `{"message": "Not authorized, token failed"}`
- **404**: `{"message": "User not found"}`
- **500**: `{"message": "error message"}`

---

### 5. Update User
**PUT** `/auth/users/:id`

Update user information.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "name": "string (optional)",
  "email": "string (optional, must be valid email format)"
}
```

**Success Response (200):**
```json
{
  "_id": "string",
  "name": "string",
  "email": "string"
}
```

**Error Responses:**
- **400**: `{"message": "Email is already in use"}`
- **401**: `{"message": "Not authorized, no token"}` or `{"message": "Not authorized, token failed"}`
- **404**: `{"message": "User not found"}`
- **500**: `{"message": "error message"}`

---

## Task Management Endpoints

*All task endpoints require authentication*

### 6. Create Task
**POST** `/tasks`

Create a new task.

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "title": "string (required)",
  "description": "string (required)",
  "dueDate": "date (optional, ISO format: YYYY-MM-DD)",
  "assignedUser": "string (optional, user ID)"
}
```

**Success Response (201):**
```json
{
  "_id": "string",
  "title": "string",
  "description": "string",
  "dueDate": "date",
  "assignedUser": "string",
  "user": "string (creator's user ID)",
  "createdAt": "date",
  "updatedAt": "date"
}
```

**Error Responses:**
- **400**: `{"message": "Title is required"}`
- **401**: `{"message": "Not authorized, no token"}` or `{"message": "Not authorized, token failed"}`
- **500**: `{"message": "Server error: error message"}`

---

### 7. Get All Tasks
**GET** `/tasks`

Get all tasks for the authenticated user.

**Headers:**
```
Authorization: Bearer <token>
```

**Success Response (200):**
```json
[
  {
    "_id": "string",
    "title": "string",
    "description": "string",
    "dueDate": "date",
    "assignedUser": "string",
    "user": "string",
    "createdAt": "date",
    "updatedAt": "date"
  }
]
```

**Error Responses:**
- **401**: `{"message": "Not authorized, no token"}` or `{"message": "Not authorized, token failed"}`
- **500**: `{"message": "Server error: error message"}`

---

### 8. Get Task by ID
**GET** `/tasks/:id`

Get a specific task by ID (only if owned by authenticated user).

**Headers:**
```
Authorization: Bearer <token>
```

**Success Response (200):**
```json
{
  "_id": "string",
  "title": "string",
  "description": "string",
  "dueDate": "date",
  "assignedUser": "string",
  "user": "string",
  "createdAt": "date",
  "updatedAt": "date"
}
```

**Error Responses:**
- **401**: `{"message": "Not authorized, no token"}` or `{"message": "Not authorized, token failed"}`
- **404**: `{"message": "Task not found"}`
- **500**: `{"message": "Server error: error message"}`

---

### 9. Update Task
**PUT** `/tasks/:id`

Update a specific task (only if owned by authenticated user).

**Headers:**
```
Authorization: Bearer <token>
```

**Request Body:**
```json
{
  "title": "string (optional)",
  "description": "string (optional)",
  "dueDate": "date (optional, ISO format: YYYY-MM-DD)",
  "assignedUser": "string (optional, user ID)"
}
```

**Success Response (200):**
```json
{
  "_id": "string",
  "title": "string",
  "description": "string",
  "dueDate": "date",
  "assignedUser": "string",
  "user": "string",
  "createdAt": "date",
  "updatedAt": "date"
}
```

**Error Responses:**
- **401**: `{"message": "Not authorized, no token"}` or `{"message": "Not authorized, token failed"}`
- **404**: `{"message": "Task not found"}`
- **500**: `{"message": "Server error: error message"}`

---

### 10. Delete Task
**DELETE** `/tasks/:id`

Delete a specific task (only if owned by authenticated user).

**Headers:**
```
Authorization: Bearer <token>
```

**Success Response (200):**
```json
{
  "message": "Task deleted successfully"
}
```

**Error Responses:**
- **401**: `{"message": "Not authorized, no token"}` or `{"message": "Not authorized, token failed"}`
- **404**: `{"message": "Task not found"}`
- **500**: `{"message": "Server error: error message"}`

---

## Data Models

### User Model
```json
{
  "_id": "ObjectId",
  "name": "string (required)",
  "email": "string (required, unique, validated)",
  "password": "string (required, hashed)",
  "createdAt": "date",
  "updatedAt": "date"
}
```

### Task Model
```json
{
  "_id": "ObjectId",
  "title": "string (required)",
  "description": "string (required)",
  "dueDate": "date (optional)",
  "assignedUser": "ObjectId (optional, references User)",
  "user": "ObjectId (required, references User - creator)",
  "createdAt": "date",
  "updatedAt": "date"
}
```

---

## Authentication Flow

1. **Register** or **Login** to get a JWT token
2. Include the token in the `Authorization` header for all protected endpoints
3. Token format: `Bearer <your_jwt_token>`
4. Tokens expire after 30 days

## Environment Configuration

### Required Environment Variables
```env
# Database
MONGODB_URI=your_mongodb_connection_string

# JWT Secret (for token generation)
JWT_SECRET=your_jwt_secret_key

# Server Port (optional, defaults to 5000)
PORT=5000
```

### JWT Configuration
- **Secret**: Set via `JWT_SECRET` environment variable
- **Expiration**: 30 days
- **Algorithm**: HS256 (default)
- **Token Format**: `Bearer <token>`

## Notes for Frontend Engineers

- All dates are in ISO format (YYYY-MM-DD)
- User IDs and Task IDs are MongoDB ObjectIds (24-character hex strings)
- Password validation is handled server-side
- Email validation uses regex pattern: `/^\S+@\S+\.\S+$/`
- All timestamps are automatically managed by Mongoose
- Tasks are user-scoped - users can only access their own tasks
- The `assignedUser` field in tasks is optional and references a User ID 