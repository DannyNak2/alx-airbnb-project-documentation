# Airbnb Clone – Backend Feature Requirements

## 📌 Objective

This document outlines the **functional**, **technical**, and **API-level requirements** for three major backend features in the Airbnb Clone system.

---

## 1️⃣ USER AUTHENTICATION

### 🔧 Description
Handles user registration, login, and authentication using JWT and OAuth.

### 🧩 Functional Requirements
- Users can sign up as `guest`, `host`, or `admin`.
- Email must be unique.
- Passwords must be securely hashed.
- OAuth integration (Google, Facebook) is optional but recommended.
- JWT is used for session handling.

### 📡 API Endpoints

| Method | Endpoint            | Description               |
|--------|---------------------|---------------------------|
| POST   | `/api/auth/register`| Register new user         |
| POST   | `/api/auth/login`   | User login (email+password) |
| GET    | `/api/auth/profile` | Get authenticated user info |
| PUT    | `/api/auth/profile` | Update user profile       |

### 📥 Input Validation Rules
- Email: required, valid format, unique
- Password: required, min 8 characters
- Role: must be `guest`, `host`, or `admin`

### 📤 Output Examples (Login)
```json
{
  "token": "jwt_token_here",
  "user": {
    "user_id": "uuid",
    "email": "user@example.com",
    "role": "host"
  }
}
