---
title: Sample API Documentation
parent: Writing
nav_order: 5
---

# 📘 Sample API Documentation

This mock API demonstrates how I structure and write REST API documentation for clarity, usability, and consistency.  
It includes authentication, request/response examples, error handling, and usage notes.

## 🔐 Authentication

All requests require an API key:

- Include in the `Authorization` header:

```http
Authorization: Bearer YOUR_API_KEY
```

- Or as a query parameter:

```
?api_key=YOUR_API_KEY
```

## 📚 Resources

### 🧑‍🤝‍🧑 Users

#### `GET /users`

Retrieve a list of users.

**Query Parameters:**

| Parameter | Type   | Description         |
|-----------|--------|---------------------|
| `limit`   | number | Max number of users |
| `offset`  | number | Pagination offset   |

**Request:**

```http
GET /users?limit=10&offset=0
Authorization: Bearer sk_test_1234
```

**Response:**

```json
{
  "users": [
    { "id": 1, "name": "Alice", "email": "alice@example.com" },
    { "id": 2, "name": "Bob", "email": "bob@example.com" }
  ]
}
```

#### `POST /users`

Create a new user.

**Body Parameters:**

| Field   | Type   | Required | Description |
|---------|--------|----------|-------------|
| `name`  | string | ✅       | Full name   |
| `email` | string | ✅       | Valid email |

**Request:**

```http
POST /users
Content-Type: application/json
Authorization: Bearer sk_test_1234

{
  "name": "Charlie",
  "email": "charlie@example.com"
}
```

**Response:**

```json
{
  "id": 3,
  "name": "Charlie",
  "email": "charlie@example.com"
}
```

## 📝 Notes

- All endpoints return JSON.
- Invalid or missing API keys will return a `401 Unauthorized`.
- Requests that fail validation will return a `400 Bad Request` with a message.

## ⚠️ Error Responses

| Code | Message               | When It Happens                    |
|------|-----------------------|------------------------------------|
| 400  | Invalid input         | Missing or malformed fields        |
| 401  | Unauthorized          | No or invalid API key              |
| 404  | Not Found             | Resource doesn't exist             |
| 500  | Internal Server Error | Something broke on our side        |

**Example error response:**

```json
{
  "error": "Missing email"
}
```
