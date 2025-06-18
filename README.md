# 🏡 Airbnb Clone Backend

Welcome to the **Airbnb Clone Backend** — a simplified booking platform inspired by Airbnb. This project is part of the **ALX Pro Backend Engineering** program and showcases backend development using modern tools and best practices.

---

## 🚀 Project Objective

Build a robust backend system to manage:
- ✅ User registration, authentication, and profiles  
- 🏠 Property listings  
- 📅 Bookings  
- 💳 Payments  
- ⭐ Reviews

---

## 🧩 Feature Breakdown

- **User Management**: Secure signup/login and profile handling for guests and hosts.  
- **Property Management**: Hosts can create and manage listings with pricing and location.  
- **Booking System**: Guests can book available properties and manage check-in/check-out.  
- **Payment Processing**: Secure handling of booking payments via external gateways.  
- **Review System**: Guests can leave ratings and reviews for properties.  
- **API Access**: Exposed via REST and GraphQL APIs.  
- **Performance Optimization**: Uses caching (Redis) and indexing for faster data access.

---

## 🛠️ Technology Stack

| Technology      | Purpose                                    |
|-----------------|---------------------------------------------|
| Django          | Web framework for API and backend logic     |
| DRF             | RESTful API support                         |
| GraphQL         | Flexible data querying                      |
| PostgreSQL      | Relational database                         |
| Redis           | Caching and task queue support              |
| Celery          | Background tasks (e.g., notifications)      |
| Docker          | Containerization for dev and prod parity    |
| GitHub Actions  | CI/CD automation for testing and deployment |

---

## 👥 Team Roles

- **Backend Developer**: API logic and model creation  
- **DB Administrator**: Schema design, indexing, and optimization  
- **DevOps Engineer**: Containerization, CI/CD setup, and monitoring  
- **QA Engineer**: Automated and manual testing, bug tracking  

---

## 🗄️ Database Design

### Main Entities and Relationships:
- **Users**: `id`, `name`, `email`, `password`, `is_host`  
- **Properties**: `id`, `title`, `location`, `price_per_night`, `host_id`  
- **Bookings**: `id`, `user_id`, `property_id`, `start_date`, `end_date`  
- **Payments**: `id`, `booking_id`, `amount`, `method`, `date`  
- **Reviews**: `id`, `user_id`, `property_id`, `rating`, `comment`

**Relationships**:
- A user can have multiple properties, bookings, and reviews.  
- A property can have many bookings and reviews.  
- A booking has one payment.

---

## 🔐 API Security

- **Authentication**: Token-based (e.g., JWT) to verify users  
- **Authorization**: Role-based access control for hosts and guests  
- **Rate Limiting**: Prevents abuse and DoS attacks  
- **Data Encryption**: Secure storage and HTTPS in transit  
- **Payment Security**: Isolated, validated, and handled via external gateways

---

## 🔁 CI/CD Pipeline

- **What**: Automates code testing, integration, and deployment  
- **Why**: Ensures rapid, stable, and error-free deployments  
- **Tools**:  
  - **GitHub Actions**: Workflow automation  
  - **Docker**: Environment consistency  
  - Optional: Jenkins, AWS CodePipeline, or Heroku for hosting

---

## 📌 API Endpoints Overview

### Users
- `GET/POST /users/`  
- `GET/PUT/DELETE /users/{id}`

### Properties
- `GET/POST /properties/`  
- `GET/PUT/DELETE /properties/{id}`

### Bookings
- `GET/POST /bookings/`  
- `GET/PUT/DELETE /bookings/{id}`

### Payments
- `POST /payments/`

### Reviews
- `GET/POST /reviews/`  
- `GET/PUT/DELETE /reviews/{id}`

---

## 🚀 Running the Project

```bash
# Clone the repository
git clone https://github.com/your-username/airbnb-clone-project.git
cd airbnb-clone-project

# Start services with Docker
docker-compose up --build
