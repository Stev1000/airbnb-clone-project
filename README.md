# Airbnb Clone Project

## Overview
The Airbnb Clone Project is a backend-focused simulation of a real-world booking platform like Airbnb. It demonstrates backend architecture, API development, security integration, and team-based software workflows.

## Project Goals
- Develop a robust backend system.
- Design secure, scalable RESTful APIs.
- Collaborate using Git and GitHub.
- Integrate CI/CD and deployment tools.
- Practice real-world database design.

## Tech Stack
- Django
- MySQL
- GraphQL
- Docker
- GitHub Actions

## Team Roles

- **Backend Developer**: Builds and maintains the server-side logic, API endpoints, and handles authentication and authorization logic.
- **Database Administrator (DBA)**: Designs and manages the database structure, handles data migrations, performance, and security of data.
- **DevOps Engineer**: Sets up CI/CD pipelines, manages deployment, containerization using Docker, and monitors infrastructure.
- **Security Engineer**: Implements and reviews backend security measures, API protection, and encryption of sensitive data.
- **Project Manager**: Coordinates tasks, ensures timelines are met, and facilitates team communication.

## Database Design

### Entities and Attributes:

- **User**
  - `id`
  - `name`
  - `email`
  - `password_hash`
  - `role` (guest or host)

- **Property**
  - `id`
  - `title`
  - `description`
  - `location`
  - `price_per_night`
  - `owner_id` (FK to User)

- **Booking**
  - `id`
  - `user_id` (FK to User)
  - `property_id` (FK to Property)
  - `start_date`
  - `end_date`
  - `status`

- **Review**
  - `id`
  - `user_id`
  - `property_id`
  - `rating`
  - `comment`

- **Payment**
  - `id`
  - `booking_id` (FK to Booking)
  - `amount`
  - `status`
  - `payment_date`

### Relationships:
- A **User** can own many **Properties**.
- A **Booking** belongs to one **User** and one **Property**.
- A **Review** is linked to one **User** and one **Property**.
- A **Payment** is associated with one **Booking**.

## Feature Breakdown

- **User Management**: Users can register, log in, and manage their profile. Authentication and role-based access are enforced.
- **Property Management**: Hosts can list, update, or delete properties. Each property includes pricing, location, and description.
- **Booking System**: Users can search for available properties and make bookings with date validation.
- **Review System**: After a stay, users can leave reviews with a rating and feedback on a property.
- **Payment Integration**: Booking payments are recorded and processed securely to track transactions.

## API Security

- **Authentication**: Uses JWT (JSON Web Tokens) to ensure only verified users can access protected endpoints.
- **Authorization**: Role-based permissions ensure users can only perform actions allowed for their role (e.g., only hosts can manage listings).
- **Rate Limiting**: Prevents abuse by limiting the number of API requests per user/IP in a given time frame.
- **Data Encryption**: Sensitive information like passwords is encrypted before storage using hashing (e.g., bcrypt).
- **Input Validation**: Protects against common attacks like SQL injection and XSS by validating and sanitizing inputs.

**Why Security Matters**:
- **User Data Protection**: Prevents unauthorized access to personal information.
- **Secure Transactions**: Ensures payments and bookings are not tampered with.
- **Platform Integrity**: Builds trust and prevents system abuse or attacks.

## CI/CD Pipeline

**CI/CD (Continuous Integration and Continuous Deployment)** automates the process of testing, building, and deploying code.

### Benefits:
- Automatically runs tests when code is pushed.
- Builds Docker containers and deploys the app reliably.
- Minimizes human errors during deployment.

### Tools:
- **GitHub Actions**: Automates testing and deployment workflows.
- **Docker**: Ensures consistency across development, testing, and production environments.
- **Heroku / AWS / Railway**: Can be used as deployment platforms.
