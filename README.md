# airbnb-clone-# AirBnB Clone Project

## Project Goals
User Management: Implement a secure system for user registration, authentication, and profile management.
Property Management: Develop features for property listing creation, updates, and retrieval.
Booking System: Create a booking mechanism for users to reserve properties and manage booking details.
Payment Processing: Integrate a payment system to handle transactions and record payment details.
Review System: Allow users to leave reviews and ratings for properties.
Data Optimization: Ensure efficient data retrieval and storage through database optimizations.

## Tech Stack
Django
Django REST Framework
PostgreSQL
GraphQL
Celery
Redis
Docker
CI/CD Pipelines

## Team Roles
Backend Developer: Responsible for implementing API endpoints, database schemas, and business logic.
Database Administrator: Manages database design, indexing, and optimizations.
DevOps Engineer: Handles deployment, monitoring, and scaling of the backend services.
QA Engineer: Ensures the backend functionalities are thoroughly tested and meet quality standards.

## Technology Stack
Django: A high-level Python web framework used for building the RESTful API.
Django REST Framework: Provides tools for creating and managing RESTful APIs.
PostgreSQL: A powerful relational database used for data storage.
GraphQL: Allows for flexible and efficient querying of data.
Celery: For handling asynchronous tasks such as sending notifications or processing payments.
Redis: Used for caching and session management.
Docker: Containerization tool for consistent development and deployment environments.
CI/CD Pipelines: Automated pipelines for testing and deploying code changes.

##Database Design
1.Users
Field	   Description
user_id	Unique identifier for each user.
name	Full name of the user.
email	User’s email address (must be unique).
password_hash	Encrypted password for login authentication.
role	Specifies user type (e.g., admin, host, guest).
phone_number	Contact number.
date_joined	Timestamp for when the user created their account.

Relationships:

A User can own multiple Properties (if host).

A User can make multiple Bookings.

A User can leave multiple Reviews.

2.Properties
Field      	Description
property_id	Unique identifier for each property.
owner_id	References the user_id of the property owner.
title	Name or short description of the property.
description	Detailed description of the property.
location	Address or city where the property is located.
price_per_night	Cost of renting the property per night.
availability_status	Indicates if the property is available for booking.
created_at	Timestamp when the property was added.

Relationships:

A Property belongs to one User (owner).

A Property can have multiple Bookings and Reviews.

3.Bookings
Field	      Description
booking_id	Unique identifier for each booking.
user_id	References the user who made the booking.
property_id	References the booked property.
check_in_date	Date the booking starts.
check_out_date	Date the booking ends.
total_amount	Total cost of the booking.
booking_status	e.g., pending, confirmed, cancelled.
created_at	Timestamp for when the booking was made.

Relationships:

A Booking belongs to one User and one Property.

A Booking can have one Payment.

 4.Reviews
Field	      Description
review_id	Unique identifier for each review.
user_id	References the user who wrote the review.
property_id	References the property being reviewed.
rating	Numeric rating (e.g., 1–5 stars).
comment	Text feedback about the property.
created_at	Timestamp when the review was posted.

Relationships:

A Review belongs to one User and one Property.

5.Payments
Field	Description
payment_id	Unique identifier for each payment.
booking_id	References the booking being paid for.
user_id	References the user making the payment.
amount	Amount paid.
payment_method	e.g., credit card, PayPal, M-Pesa.
payment_status	e.g., pending, completed, failed.
payment_date	Timestamp when payment was made.

Relationships:

A Payment belongs to one Booking and one User.

## Feature Breakdown
1.API Documentation
OpenAPI Standard: The backend APIs are documented using the OpenAPI standard to ensure clarity and ease of integration.
Django REST Framework: Provides a comprehensive RESTful API for handling CRUD operations on user and property data.
GraphQL: Offers a flexible and efficient query mechanism for interacting with the backend.
2. User Authentication
Endpoints: /users/, /users/{user_id}/
Features: Register new users, authenticate, and manage user profiles.
3. Property Management
Endpoints: /properties/, /properties/{property_id}/
Features: Create, update, retrieve, and delete property listings.
4. Booking System
Endpoints: /bookings/, /bookings/{booking_id}/
Features: Make, update, and manage bookings, including check-in and check-out details.
5. Payment Processing
Endpoints: /payments/
Features: Handle payment transactions related to bookings.
6. Review System
Endpoints: /reviews/, /reviews/{review_id}/
Features: Post and manage reviews for properties.
7. Database Optimizations
Indexing: Implement indexes for fast retrieval of frequently accessed data.
Caching: Use caching strategies to reduce database load and improve performance.
