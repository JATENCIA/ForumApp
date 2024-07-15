# **Forum App**

```bash
    This project is a Java Spring Boot application that empowers users to engage in discussions and manage content
    effectively. It provides functionalities for:
    
    * User management: Create, view, update, and delete user accounts.
    * Post management: Create, update, view, and like/unlike posts.
    * Comment management: Create, view, like/unlike comments, and moderate their visibility.
    * Robust authentication and authorization: Leverages JWT tokens for secure access control based on user roles (ADMIN,
      USER).
```

## Technologies

```bash
   - Java
   - Spring Boot
   - Spring Security
   - JWT (JSON Web Tokens)
   - Spring Data JPA
   - MySql Database (for development)
   - Swagger UI (for API documentation)
```

## Project Structure

```bash
    The project adheres to a well-organized structure for maintainability:
    
    Use code with caution.
    content_copy
    src/main/java/com.atencia.ForumApp
    ├── config  (Security and Swagger configurations)
    ├── controller  (REST controllers for various endpoints)
    ├── dto  (Data Transfer Objects for request/response mapping)
    ├── model  (Entity classes representing database tables)
    ├── repository  (Spring Data repositories for database access)
    ├── service  (Service classes for business logic implementation)
    └── util  (Utility classes)
    
    src/main/resources
    ├── application.properties  (Application configuration)
    └── swagger  (Swagger configuration)    
```

## Setup

1. **Clone the repository:**

   ```bash
   git clone [https://github.com/JATENCIA/ForumApp.git)

## Configuration:

```bash
   Update application.properties with your database credentials and other necessary properties.
   Build and Run:
   
   Bash
   mvn spring-boot:run
   Use code with caution.
   content_copy
   The application will start on http://localhost:5454.
   
   Main Features
   Authentication and Authorization:
   
   JWT-based authentication ensures secure access.
   Role-based access control (RBAC) restricts functionalities based on roles (ADMIN, USER).
   User Management:
   
   Comprehensive CRUD operations: Create, Read, Update, and Delete users.
   Registration for new users.
   Profile update functionality.
   Post Management:
   
   Create, update, and view posts.
   Control post visibility.
   Implement a like/unlike system.
   Comment Management:
   
   Create, view, and like/unlike comments.
   Moderate comment visibility.
   API Endpoints
   The API provides well-defined endpoints categorized by their access roles:
```

## **Public Endpoints:**

 ```bash
     POST /api/public/auth/signup: Register a new user.
     POST /api/public/auth/signing: Authenticate and receive a JWT token.
 ```

## **Admin Endpoints:**

```bash
     PUT /api/admin/toggleUserActivation/{userId}: Activate or deactivate a user (ADMIN only).
     PUT /api/admin/toggleCommentActivation/{commentId}: Activate or deactivate a comment (ADMIN only).
```

## **User Endpoints:**

```bash     
     POST /api/user/post: Create a new post.
     GET /api/user/post/{postId}: Get a post by ID.
     PUT /api/user/like/{postId}: Like or unlike a post.
     GET /api/user/search/{userId}: Get user details by ID.
     PUT /api/user/update: Update user profile.
     GET /api/user/all/users: Get all registered users (ADMIN only).
     GET /api/user/profile: Get authenticated user profile.
     POST /api/user/comment/{postId}: Create a comment on a post.
     GET /api/user/comment/{commentId}: Get a comment by ID.
     PUT /api/user/like/comment/{commentId}: Like or unlike a comment.
     Example Usage
     Here are some examples illustrating how to interact with the API using cURL commands:
```

## **Document Api Endpoints:**

```bash
     UrlBase /v3/api-docs/**
     UrlBase /swagger-ui/** 
     UrlBase /swagger-ui.html 
```

## **Register a New User:**

```bash
    Bash
    curl -X POST http://localhost:5454/api/public/auth/signup \
    -H "Content-Type: application/json" \
    -d ADMIN '{"firstName":"John","lastName":"Doe","email":"john.doe@example.com","password":"password", "roles": ["ADMIN"]}'
    -d USER '{"firstName":"John","lastName":"Doe","email":"john.doe@example.com","password":"password", "roles": ["ADMIN, USER"]}'
    Use code with caution.
    content_copy
    Create a New Post:
    
    (Replace <JWT_TOKEN> with your actual JWT token)
    
    Bash
    curl -X POST http://localhost:5454/api/user/post \
    -H "Authorization: Bearer <JWT_TOKEN>" \
    -H "Content
```
