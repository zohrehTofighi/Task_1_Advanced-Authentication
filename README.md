The provided code comprises a collection of Python files for a web application built with Flask, MongoDB, and JWT for authentication. It includes functionality for user and book management, with an emphasis on RESTful API design, image handling, and input validation.

app.py:
Main Application File: Sets up the Flask application, routes, and configuration. It includes endpoints for user registration, login, profile updates, and account disabling, as well as book creation, update, retrieval, and deletion.
Environment Variables: Uses “dotenv” to manage environment variables, including the secret key for JWT and the database URL.
Authentication: Implements JWT-based authentication for protected routes, using the “token_required” decorator from “auth_middleware.py”.

models.py:
Data Models: Defines “Books” and “User” models for interacting with MongoDB, using the “pymongo” library. It covers basic CRUD operations for both books and users, as well as additional methods for specific queries like fetching books by category or user.
Password Handling: Utilizes Werkzeug's security functions to hash and verify passwords.

auth_middleware.py:
Middleware for Authentication: Contains the “token_required” decorator, which is used to protect routes by validating JWT tokens. It ensures that the token is present and valid, and that the user is active, before allowing access to the protected route.

save_image.py:
Image Saving Utility: Handles the saving of book cover images. It generates a unique filename for each image, ensures the creation of necessary directories, resizes the image to a thumbnail using Pillow (PIL fork), and saves it to the filesystem.

validate.py:
Input Validation: Provides functions for validating user input, including email, password, and book details. Uses regular expressions to enforce constraints on email and password formats, and custom logic to validate book data.
