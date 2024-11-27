# 📘 Library Management API

The **Library Management API** is a backend service designed to manage library systems efficiently. It provides endpoints for handling **users**, **books**, **authors**, and their associations, while ensuring security with **JWT authentication** and one-time tokens for critical actions.

---

## Features Overview

### 1. **Efficient User Management**
   - **Registration & Authentication**: Secure sign-ups and log-ins for users.
   - **Role-based Access**: Different levels of access based on user roles (admin, user, etc.).
   - **Account Management**: Users can update and manage their personal account information.

### 2. **Library Book Operations**
   - **Add & Update Books**: Seamless book management with easy options to add, modify, or remove books from the library.
   - **Detailed Book Information**: Store and retrieve comprehensive details such as title and book ID.

### 3. **Author Management**
   - **Author Profiles**: Create and manage author profiles including name, and linked books.
   - **Track Author Contributions**: Keep a record of each author’s books in the library system.

### 4. **Book-Author Connections**
   - **Relationship Mapping**: Automatically link authors to their respective books in a clear, easy-to-understand format.
   - **Manage Associations**: Easily add or remove book-author relationships as needed.

### 5. **Secure API Endpoints**
   - **Token Authentication**: Secure access to all API endpoints using JSON Web Tokens (JWT).
   - **One-Time Use Tokens**: Added security for sensitive operations, ensuring tokens cannot be reused for malicious purposes.

---

## Robust Security Measures

### **JWT Token Authentication**
   - Every API request is secured using **JWT tokens**. These tokens ensure that only authenticated users can perform operations within the API.
   - Protects user accounts, books, and author data from unauthorized access.

### **One-Time Use Tokens for Critical Actions**
   - For actions such as adding, updating, or deleting resources (users, books, authors), the system generates **one-time tokens** to prevent replay attacks.
   - Tokens are valid only for a short duration or for a single operation, minimizing security risks.

### **Data Integrity with Input Validation**
   - **Strong Validation Rules**: Ensures all user input is thoroughly validated to prevent the insertion of invalid or malicious data.
   - Checks for the presence of required fields, correct formats (e.g., email format, password strength), and unique values for critical fields (e.g., book title or author name).

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
   - **Endpoint**: `https://127.0.0.1/library/public/user/register`
   - **Request Body**:
     ```json
     {
       "username": "Lance Kenneth Ventura",
       "password": "1111"
     }
     ```
   - **Response**:
     - `success`: User registered successfully.
     - `fail`: Username already exists.

2. **Login**
   - **Endpoint**: `https://127.0.0.1/library/public/user/auth`
   - **Request Body**:
     ```json
     {
       "username": "Lance Kenneth Ventura",
       "password": "1111"
     }
     ```
   - **Response**:
     - `success`: Returns a JWT token.
     - `fail`: Invalid username or password.

---

### Book Endpoints
1. **Add Book**
   - **Endpoint**: `https://127.0.0.1/library/public/books`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "title": "System Integration II"
     }
     ```
   - **Response**:
     - `success`: Book added.
     - `fail`: Book already exists.

2. **Update Book**
   - **Endpoint**: `https://127.0.0.1/library/public/books/update`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "book_id": "123",
       "title": "SYSTEM INTEGRATION"
     }
     ```
   - **Response**:
     - `success`: Book updated successfully.
     - `fail`: Book not found.

3. **Delete Book**
   - **Endpoint**: `https://127.0.0.1/library/public/books/delete/173`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "book_id": "123"
     }
     ```
   - **Response**:
     - `success`: Book deleted.
     - `fail`: Book not found.

4. **List Books**
   - **Endpoint**: `https://127.0.0.1/library/public/books/get`
   - **Response**:
     - `success`: Returns a list of books.

---

### Author Endpoints
1. **Add Author**
   - **Endpoint**: `https://127.0.0.1/library/public/authors`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "name": "Lance"
     }
     ```
   - **Response**:
     - `success`: Author added.
     - `fail`: Author already exists.

2. **Update Author**
   - **Endpoint**: `https://127.0.0.1/library/public/authors/update/121`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "author_id": "12",
       "name": "Lance Kenneth"
     }
     ```
   - **Response**:
     - `success`: Author updated.
     - `fail`: Author not found.

3. **Delete Author**
   - **Endpoint**: `https://127.0.0.1/library/public/authors/delete/121`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "author_id": "12"
     }
     ```
   - **Response**:
     - `success`: Author removed.
     - `fail`: Author not found.

4. **List Authors**
   - **Endpoint**: `https://127.0.0.1/library/public/authors/get`
   - **Response**:
     - `success`: Returns a list of authors.

---

### Book-Author Relationship Endpoints
1. **Add Relationship**
   - **Endpoint**: `https://127.0.0.1/library/public/books`
   - **Headers**: `Authorization: Bearer <JWT>`
   - **Request Body**:
     ```json
     {
       "book_id": "123",
       "author_id": "12"
     }
     ```
   - **Response**:
     - `success`: Relationship added.
     - `fail`: Book or author not found.

---
