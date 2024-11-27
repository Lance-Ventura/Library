# 📘 Library Management API

The **Library Management API** is a backend service designed to manage library systems efficiently. It provides endpoints for handling **users**, **books**, **authors**, and their associations, while ensuring security with **JWT authentication** and one-time tokens for critical actions.

---

##  Features
- **User Management**: Secure registration, login, and account management.
- **Book Management**: Add, update, delete, and view books.
- **Author Management**: Add, update, delete, and view authors.
- **Book-Author Relationships**: Link books with authors and retrieve associations.
- **Secure API**: Features JWT-based authentication and one-time tokens for sensitive operations.

---

##  Security Features
- **JWT Authentication**: Protects endpoints with secure tokens.
- **One-Time Tokens**: Prevents replay attacks for critical operations.
- **Input Validation**: Ensures data integrity with validation rules.

---

##  Prerequisites
Make sure the following tools and technologies are installed:
- PHP 7.2+ with Slim Framework
- Composer
- XAMPP or similar local server
- SQLyog or phpMyAdmin
- Node.js
- JWT PHP Library
- API testing tools (e.g., Postman or ThunderClient)

---

##  Endpoints Overview

###  User Endpoints

| Method | Endpoint         | Description                      |
|--------|------------------|----------------------------------|
| POST   | `https://127.0.0.1/library/public/user/register` | Register a new user.             |
| POST   | `https://127.0.0.1/library/public/user/auth`    | Authenticate and retrieve JWT.   |

###  Book Endpoints

| Method | Endpoint        | Description              |
|--------|-----------------|--------------------------|
| POST   | `https://127.0.0.1/library/public/books`     | Add a new book.          |
| PUT    | `https://127.0.0.1/library/public/books/update/2`  | Edit book details.       |
| DELETE | `/https://127.0.0.1/library/public/books/delete/2`  | Delete a book.           |
| GET    | `/listhttps://127.0.0.1/library/public/books/get`    | View all books.          |

###  Author Endpoints

| Method | Endpoint         | Description               |
|--------|------------------|---------------------------|
| POST   | `https://127.0.0.1/library/public/authors`    | Add a new author.         |
| PUT    | `https://127.0.0.1/library/public/authors/update/121` | Update author information.|
| DELETE | `https://127.0.0.1/library/public/authors/delete/121` | Delete an author.         |
| GET    | `https://127.0.0.1/library/public/authors/get`   | View all authors.         |

---
### SAMPLE API

### User Endpoints
1. **Register User**
   - **Endpoint**: `POST /user/register`
   - **Request Body**:
     ```json
     {
       "username": "string",
       "password": "string"
     }
     ```
   - **Response**:
     - `success`: User registered successfully.
     - `fail`: Username already exists.

2. **Login**
   - **Endpoint**: `POST /user/login`
   - **Request Body**:
     ```json
     {
       "username": "string",
       "password": "string"
     }
     ```
   - **Response**:
     - `success`: Returns a JWT token.
     - `fail`: Invalid username or password.

3. **Delete User**
   - **Endpoint**: `DELETE /user/delete`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Response**:
     - `success`: User deleted successfully.
     - `fail`: Authorization failed.

---

### Book Endpoints
1. **Add Book**
   - **Endpoint**: `POST /book/add`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "title": "string"
     }
     ```
   - **Response**:
     - `success`: Book added.
     - `fail`: Book already exists.

2. **Update Book**
   - **Endpoint**: `PUT /book/update`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "book_id": "integer",
       "title": "string"
     }
     ```
   - **Response**:
     - `success`: Book updated successfully.
     - `fail`: Book not found.

3. **Delete Book**
   - **Endpoint**: `DELETE /book/remove`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "book_id": "integer"
     }
     ```
   - **Response**:
     - `success`: Book deleted.
     - `fail`: Book not found.

4. **List Books**
   - **Endpoint**: `GET /book/list`
   - **Response**:
     - `success`: Returns a list of books.

---

### Author Endpoints
1. **Add Author**
   - **Endpoint**: `POST /author/add`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "name": "string"
     }
     ```
   - **Response**:
     - `success`: Author added.
     - `fail`: Author already exists.

2. **Update Author**
   - **Endpoint**: `PUT /author/update`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "author_id": "integer",
       "name": "string"
     }
     ```
   - **Response**:
     - `success`: Author updated.
     - `fail`: Author not found.

3. **Delete Author**
   - **Endpoint**: `DELETE /author/remove`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "author_id": "integer"
     }
     ```
   - **Response**:
     - `success`: Author removed.
     - `fail`: Author not found.

4. **List Authors**
   - **Endpoint**: `GET /author/list`
   - **Response**:
     - `success`: Returns a list of authors.

---

### Book-Author Relationship Endpoints
1. **Add Relationship**
   - **Endpoint**: `POST /relation/add`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "book_id": "integer",
       "author_id": "integer"
     }
     ```
   - **Response**:
     - `success`: Relationship added.
     - `fail`: Book or author not found.

2. **List Relationships**
   - **Endpoint**: `GET /relation/list`
   - **Response**:
     - `success`: Returns all book-author relationships.

---

## 🏁 Getting Started

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/library-management-api.git
