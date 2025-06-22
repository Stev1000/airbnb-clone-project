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
