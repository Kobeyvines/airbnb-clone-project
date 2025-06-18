# airbnb-clone-project
alx pro-backend course work
# 🏡 Airbnb Clone Backend

Welcome to the **Airbnb Clone Backend** project! This repository contains the backend codebase for a scalable and feature-rich Airbnb-style application, built with Django, Django REST Framework, GraphQL, PostgreSQL, and more.

---

## 🚀 Objective

The backend is designed to provide a robust foundation for managing:

- ✅ User interactions  
- 🏠 Property listings  
- 📅 Bookings  
- 💳 Payments  

The goal is to replicate the core functionality of Airbnb and offer a smooth experience for users and hosts alike.

---

## 🏆 Feature Breakdown

- **User Management**  
  Secure registration, login, authentication, and profile management.

- **Property Management**  
  Listing creation, updates, and property retrieval.

- **Booking System**  
  Book and manage stays, with check-in/check-out details.

- **Payment Processing**  
  Handle transactions and record payment data.

- **Review System**  
  Users can leave reviews and ratings for properties.

- **Data Optimization**  
  Efficient data storage and retrieval using indexing and caching.

---

## 🛠️ Features Overview

### 1. API Documentation
- **OpenAPI**: Fully documented using the OpenAPI standard.  
- **Django REST Framework**: For building clean and functional RESTful APIs.  
- **GraphQL**: For efficient and customizable data queries.

### 2. User Authentication
- **Endpoints**: `/users/`, `/users/{user_id}/`  
- **Features**: Register, login, manage profiles.

### 3. Property Management
- **Endpoints**: `/properties/`, `/properties/{property_id}/`  
- **Features**: CRUD operations on property listings.

### 4. Booking System
- **Endpoints**: `/bookings/`, `/bookings/{booking_id}/`  
- **Features**: Create, update, and manage reservations.

### 5. Payment Processing
- **Endpoints**: `/payments/`  
- **Features**: Process and record booking payments.

### 6. Review System
- **Endpoints**: `/reviews/`, `/reviews/{review_id}/`  
- **Features**: Post and manage property reviews.

### 7. Database Optimizations
- **Indexing**: For fast lookups on critical queries.  
- **Caching**: Powered by Redis to enhance performance.

---

## ⚙️ Tech Stack

| Tech | Role |
|------|------|
| Django | Web framework |
| Django REST Framework | API layer |
| GraphQL | Flexible querying |
| PostgreSQL | Database |
| Celery | Asynchronous tasks |
| Redis | Caching & session store |
| Docker | Containerization |
| CI/CD Pipelines | Deployment automation |

---

## 👥 Team Roles

- **Backend Developer**: APIs, logic, and DB models  
- **Database Administrator**: Schema design and performance tuning  
- **DevOps Engineer**: Deployment, monitoring, and scalability  
- **QA Engineer**: Testing and quality assurance

---

## 🗄️ Database Design

This project uses a relational database to manage core entities and their relationships.

### Entities & Key Fields

#### 1. Users
- `id`, `name`, `email`, `password`, `is_host`
- A user can list multiple properties, make bookings, and leave reviews.

#### 2. Properties
- `id`, `title`, `description`, `location`, `price_per_night`, `host_id`
- A property belongs to one host, has many bookings and reviews.

#### 3. Bookings
- `id`, `user_id`, `property_id`, `start_date`, `end_date`, `status`
- A booking is made by a user for a property; each booking can have one payment.

#### 4. Payments
- `id`, `booking_id`, `amount`, `payment_method`, `payment_date`
- Each payment is linked to a single booking.

#### 5. Reviews
- `id`, `user_id`, `property_id`, `rating`, `comment`
- A user can review multiple properties; a property can have many reviews.

### Relationships Summary
- One **User** → Many **Properties**, **Bookings**, **Reviews**  
- One **Property** → Many **Bookings**, **Reviews**  
- One **Booking** → One **Payment**

----

## 📈 API Documentation Overview

### REST API
Comprehensive API docs powered by OpenAPI and DRF, covering all CRUD operations.

### GraphQL API
Flexible alternative to REST for frontend queries and mutations.

---

## 📌 Endpoints Overview

### Users
- `GET /users/` – List users  
- `POST /users/` – Create user  
- `GET /users/{user_id}/` – Retrieve user  
- `PUT /users/{user_id}/` – Update user  
- `DELETE /users/{user_id}/` – Delete user  

### Properties
- `GET /properties/` – List properties  
- `POST /properties/` – Add property  
- `GET /properties/{property_id}/` – Retrieve property  
- `PUT /properties/{property_id}/` – Update property  
- `DELETE /properties/{property_id}/` – Delete property  

### Bookings
- `GET /bookings/` – List bookings  
- `POST /bookings/` – Create booking  
- `GET /bookings/{booking_id}/` – Retrieve booking  
- `PUT /bookings/{booking_id}/` – Update booking  
- `DELETE /bookings/{booking_id}/` – Delete booking  

### Payments
- `POST /payments/` – Process payment  

### Reviews
- `GET /reviews/` – List reviews  
- `POST /reviews/` – Create review  
- `GET /reviews/{review_id}/` – Retrieve review  
- `PUT /reviews/{review_id}/` – Update review  
- `DELETE /reviews/{review_id}/` – Delete review  

---

## 🐳 Running the Project (Dockerized)

```bash
# Clone the repo
git clone https://github.com/your-username/airbnb-clone-backend.git
cd airbnb-clone-backend

# Start the containers
docker-compose up --build
