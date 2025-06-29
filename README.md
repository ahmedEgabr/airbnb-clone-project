# AirBnB Clone Project

Welcome to the **AirBnB Clone** project – a foundational part of the ALX Software Engineering program.

## 🧠 Project Overview

This project is a **full-stack clone** of the AirBnB web application, built step-by-step to demonstrate understanding of core backend and frontend development concepts. The goal is to rebuild AirBnB’s core functionality and design using a modular and scalable architecture.

## 🎯 Project Goals

- Build a flexible and reusable backend system in Python
- Create a functional command interpreter (console)
- Implement object-relational mapping (ORM) from scratch
- Connect a backend to a dynamic front-end using Flask and HTML/CSS
- Deploy a fully working web application

## ⚙️ Tech Stack

- **Programming Language:** Python 3
- **Frameworks:** Flask, Jinja2
- **Storage Engine:** File Storage & MySQL DB (ORM abstraction)
- **Frontend:** HTML5, CSS3
- **Deployment:** Linux / Ubuntu, Nginx, Gunicorn
- **Version Control:** Git & GitHub

## 👥 Contributors

This project is part of the ALX SE curriculum and will be developed in multiple phases as a team.

---


👥 Team Roles

This project involves collaboration among various team members, each with specific responsibilities. Below are the roles and their key duties:
🔹 Backend Developer

    Responsible for building the core logic of the application.

    Implements models, APIs, business logic, and integrates the database with the app.

    Ensures clean, testable, and scalable backend code.

🔹 Frontend Developer

    Designs and develops the user interface using HTML, CSS, and JavaScript (or frontend frameworks).

    Connects frontend with backend via API endpoints.

    Focuses on responsive, user-friendly, and accessible UI design.

🔹 Database Administrator (DBA)

    Manages the data layer: setting up databases, optimizing queries, ensuring data integrity.

    Designs schemas and relationships for models (e.g., User, Place, Review).

    Handles data backup, migration, and performance tuning.

🔹 DevOps Engineer

    Sets up version control, CI/CD pipelines, deployment environments, and monitors system health.

    Ensures the app is smoothly deployed to production using tools like Docker, Nginx, and Gunicorn.

    Manages server environments and scaling strategies.

🔹 QA Engineer / Tester

    Writes and runs unit, integration, and end-to-end tests to ensure code correctness.

    Finds and documents bugs or performance issues.

    Ensures reliability and compliance with project requirements.

🔹 Project Manager / Scrum Lead (optional role in larger teams)

    Coordinates between different team members.

    Tracks task progress, manages deadlines, and removes blockers.

    Ensures project is aligned with goals and learning outcomes.


🧰 Technology Stack

This project uses a collection of technologies across backend, frontend, and deployment layers. Each tool plays a critical role in building and running the AirBnB clone.

| Technology              | Description                                                  |
| ----------------------- | ------------------------------------------------------------ |
| **Python**              | The core programming language used to build the backend logic and data models. |
| **Flask**               | A lightweight Python web framework used to create RESTful APIs and serve dynamic web pages. |
| **MySQL**               | Relational database used to store user, property, booking, and review data. |
| **SQLAlchemy**          | ORM (Object-Relational Mapper) used to interact with the database using Python objects instead of raw SQL. |
| **HTML/CSS**            | Used to build and style the user interface of the website.   |
| **Jinja2**              | Templating engine integrated with Flask to dynamically generate HTML pages from Python. |
| **JavaScript**          | Enables client-side interactivity, form validation, and dynamic page behavior. |
| **Git**                 | Version control system for tracking source code changes and enabling team collaboration. |
| **GitHub**              | Online Git repository hosting platform used for source control and project collaboration. |
| **Linux/Ubuntu**        | Operating system used for deployment and testing of the project in a production-like environment. |
| **Nginx**               | A web server used as a reverse proxy to serve the Flask app in production. |
| **Gunicorn**            | A WSGI HTTP server for running Python web applications in production with high performance. |
| **Docker** *(optional)* | Containerization platform that ensures consistency across development and production environments. |




### 🗃️ Database Design

The AirBnB clone project relies on a relational database structure. Below are the core entities (tables), key fields, and how they relate to each other.

------

#### 🔸 **User**

Represents registered users of the platform.

**Key Fields:**

- `id` (Primary Key)
- `full_name`
- `email`
- `password_hash`
- `created_at`

A user can:

- Own multiple properties
- Create multiple bookings
- Leave reviews

------

#### 🔸 **Property**

Represents listings that users can rent.

**Key Fields:**

- `id` (Primary Key)
- `owner_id` (Foreign Key → User)
- `title`
- `location`
- `price_per_night`

A property:

- Belongs to one user (owner)
- Can have many bookings and reviews

------

#### 🔸 **Booking**

Represents a reservation made by a user for a property.

**Key Fields:**

- `id` (Primary Key)
- `user_id` (Foreign Key → User)
- `property_id` (Foreign Key → Property)
- `check_in_date`
- `check_out_date`

A booking:

- Is linked to one user
- Is linked to one property

------

#### 🔸 **Review**

Captures feedback from users who have stayed at properties.

**Key Fields:**

- `id` (Primary Key)
- `user_id` (Foreign Key → User)
- `property_id` (Foreign Key → Property)
- `rating` (e.g., 1 to 5)
- `comment`

A review:

- Is written by a user
- Is linked to a specific property

------

#### 🔸 **Payment**

Records payments for bookings.

**Key Fields:**

- `id` (Primary Key)
- `booking_id` (Foreign Key → Booking)
- `amount`
- `payment_status`
- `timestamp`

A payment:

- Belongs to one booking
- Ensures traceability of financial transactions

------

### 🔗 Entity Relationships Summary

- A **User** can own many **Properties**
- A **Property** can have many **Bookings** and **Reviews**
- A **Booking** is linked to one **User** and one **Property**
- A **Review** is tied to one **User** and one **Property**
- A **Payment** is tied to one **Booking**
