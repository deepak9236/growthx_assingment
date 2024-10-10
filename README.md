# Assignment Submission Portal

A backend system for managing assignment submissions with user and admin functionality. This system allows users to submit assignments and administrators to review and manage these submissions.

## Features

- User and Admin authentication
- Assignment submission system
- Assignment review system (accept/reject)
- MongoDB database integration
- JWT-based authentication

## Tech Stack

- Node.js
- Express.js
- MongoDB
- JWT for authentication

## API Documentation

### User Routes

#### 1. Register User
- **Method:** POST
- **Endpoint:** `/api/users/register`
- **Body:**
```json
{
  "username": "testuser",
  "email": "testuser@example.com",
  "password": "password123"
}
```
- **Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

#### 2. Login User
- **Method:** POST
- **Endpoint:** `/api/users/login`
- **Body:**
```json
{
  "email": "testuser@example.com",
  "password": "password123"
}
```
- **Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

#### 3. Upload Assignment
- **Method:** POST
- **Endpoint:** `/api/users/upload`
- **Body:**
```json
{
  "userId": "67066215cbb7f68b99e4b378",
  "task": "Task description",
  "admin": "67066134cbb7f68b99e4b375"
}
```
- **Response:**
```json
{
  "userId": "67066215cbb7f68b99e4b378",
  "task": "Task description",
  "admin": "67066134cbb7f68b99e4b375",
  "status": "pending",
  "_id": "6706635ccbb7f68b99e4b37d",
  "createdAt": "2024-10-09T11:05:00.612Z",
  "__v": 0
}
```

### Admin Routes

#### 1. Register Admin
- **Method:** POST
- **Endpoint:** `/api/admins/register`
- **Body:**
```json
{
  "username": "adminuser",
  "email": "adminuser@example.com",
  "password": "adminpassword123"
}
```
- **Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

#### 2. Login Admin
- **Method:** POST
- **Endpoint:** `/api/admins/login`
- **Body:**
```json
{
  "email": "adminuser@example.com",
  "password": "adminpassword123"
}
```
- **Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

#### 3. Get Assignments for Admin
- **Method:** GET
- **Endpoint:** `/api/admins/assignments/:adminId`
- **Response:**
```json
[
  {
    "_id": "6706635ccbb7f68b99e4b37d",
    "userId": {
      "_id": "67066215cbb7f68b99e4b378",
      "username": "testuser"
    },
    "task": "Task description",
    "admin": "67066134cbb7f68b99e4b375",
    "status": "pending",
    "createdAt": "2024-10-09T11:05:00.612Z",
    "__v": 0
  }
]
```

#### 4. Accept Assignment
- **Method:** PATCH
- **Endpoint:** `/api/admins/accept/:assignmentId`
- **Response:**
```json
{
  "_id": "6706635ccbb7f68b99e4b37d",
  "userId": "67066215cbb7f68b99e4b378",
  "task": "Task description",
  "admin": "67066134cbb7f68b99e4b375",
  "status": "accepted",
  "createdAt": "2024-10-09T11:05:00.612Z",
  "__v": 0
}
```

#### 5. Reject Assignment
- **Method:** PATCH
- **Endpoint:** `/api/admins/reject/:assignmentId`
- **Response:**
```json
{
  "_id": "6706635ccbb7f68b99e4b37d",
  "userId": "67066215cbb7f68b99e4b378",
  "task": "Task description",
  "admin": "67066134cbb7f68b99e4b375",
  "status": "rejected",
  "createdAt": "2024-10-09T11:05:00.612Z",
  "__v": 0
}
```
# growthx_assingment
