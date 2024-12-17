
# 📚 Library Management API

This Library Management API, built using **PHP** with the **Slim framework**, allows for streamlined management of library resources, such as users, authors, and books. Utilizing **JSON Web Tokens (JWT)**, it ensures secure user authentication and access control to keep the library system safe.

---

## 🌟 Features
- **User Management**  
  Manage user accounts with registration, authentication, profile updates, and deletion.

- **Author Management**  
  Support author-related actions: add, update, view, and remove author details.

- **Book Management**  
  Provides endpoints to add, update, view, and delete book records.

- **Token Management**  
  Secure, single-use tokens for each session, ensuring reliable authentication.

---

## 🛠️ API Endpoints

### User Endpoints

#### 1. Register User
- **Endpoint:** `POST /user/register`
- **Description:** Register a new user.
- **Description:** Registers a new user in the system with a username and password.

##### Request:
```json
@@ -48,7 +48,7 @@

#### 2. Authenticate User
- **Endpoint:** `POST /user/auth`
- **Description:** Authenticate user and retrieve JWT.
- **Description:** Authenticates an existing user, returning a JWT token upon successful login.

##### Request:
```json
@@ -71,7 +71,7 @@

#### 3. Show User Profile
- **Endpoint:** `GET /user/show`
- **Description:** Fetch user profile with JWT authentication.
- **Description:** Retrieves the authenticated user’s profile information. Requires a valid JWT token.

##### Headers:
```json
@@ -97,7 +97,7 @@

#### 4. Update User Profile
- **Endpoint:** `PUT /user/update`
- **Description:** Update user details.
- **Description:** Updates the profile information of an existing user.

##### Request Headers:
```json
@@ -129,7 +129,7 @@

#### 1. Register Author
- **Endpoint:** `POST /author/register`
- **Description:** Register a new author.
- **Description:** Registers a new author in the library system.

##### Request:
```json
@@ -150,7 +150,7 @@

#### 2. Show Authors
- **Endpoint:** `GET /author/show`
- **Description:** Retrieve a list of authors.
- **Description:** Returns a list of authors available in the library. Requires a valid JWT token.

##### Headers:
```json
@@ -176,7 +176,7 @@

#### 3. Delete Author
- **Endpoint:** `DELETE /author/delete`
- **Description:** Delete an author.
- **Description:** Deletes an author from the library.

##### Request Headers:
```json
@@ -206,7 +206,7 @@

#### 1. Register Book
- **Endpoint:** `POST /book/register`
- **Description:** Register a new book.
- **Description:** Adds a new book to the library system, associating it with an author by ID.

##### Request:
```json
@@ -228,7 +228,7 @@

#### 2. Show Books
- **Endpoint:** `GET /book/show`
- **Description:** List all books.
- **Description:** Adds a new book to the library system, associating it with an author by ID.

##### Headers:
```json
@@ -255,7 +255,7 @@

#### 3. Update Book
- **Endpoint:** `PUT /book/update`
- **Description:** Update book details.
- **Description:**Updates details for an existing book in the library system.

##### Request Headers:
```json