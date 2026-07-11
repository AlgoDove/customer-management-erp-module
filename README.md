# Customer Management ERP Module

> A full-stack MERN application for managing customer profiles, automating loyalty segmentation, and calculating discounts dynamically based on purchase history.

![React](https://img.shields.io/badge/React-19-61DAFB?logo=react)
![Node.js](https://img.shields.io/badge/Node.js-Express-339933?logo=node.js)
![MongoDB](https://img.shields.io/badge/MongoDB-Database-47A248?logo=mongodb)
![JWT](https://img.shields.io/badge/Auth-JWT-black)
![License](https://img.shields.io/badge/License-MIT-blue)

---

## Project Overview

The **Customer Management ERP Module** is a full-stack web application built using the **MERN Stack**. It is designed as a modular ERP component that manages customer information while automatically determining customer loyalty segments and discount rates based on purchase history.

Instead of storing customer tiers statically, the application calculates them dynamically whenever customer information is requested. This ensures that discounts always remain accurate and synchronized with purchase data.

This project demonstrates practical backend architecture, REST API development, authentication, role-based authorization, and separation of business logic using a dedicated service layer.

---

## Key Features

- Customer Management (CRUD)
- Role-Based Authentication (Admin & Sales Staff)
- JWT Authentication & Authorization
- Dynamic Customer Segmentation
- Automatic Discount Calculation
- Purchase History Management
- Configurable Loyalty Thresholds
- Responsive React Interface
- RESTful API Architecture
- MongoDB Data Persistence

---

## Dynamic Segmentation

Customer loyalty is **not stored** inside the database.

Instead, the application calculates the customer segment dynamically using configurable threshold rules.

Example:

| Total Purchase | Segment | Discount |
|---------------|----------|----------|
| Rs. 12,000 | Normal | 0% |
| Rs. 75,000 | Gold | Calculated |
| Rs. 180,000 | Platinum | Calculated |

This approach prevents stale customer data and ensures pricing consistency throughout the ERP system.

---

# Technology Stack

## Frontend

- React 19
- Vite
- Tailwind CSS
- React Router DOM
- Axios
- Lucide React
- Recharts

## Backend

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT Authentication
- bcryptjs
- CORS

---

# System Architecture

```
React Client
      │
      ▼
Express REST API
      │
JWT Authentication
      │
Controllers
      │
Business Service Layer
      │
Mongoose Models
      │
MongoDB
```

---

# Folder Structure

```
customer-management-erp-module
│
├── client
│   ├── src
│   ├── public
│   └── ...
│
├── server
│   ├── controllers
│   ├── middleware
│   ├── models
│   ├── routes
│   ├── services
│   ├── config
│   └── ...
│
└── README.md
```

---

# Core Business Logic

The application separates business rules from database models.

A dedicated **Segmentation Service**:

- Retrieves threshold configurations
- Evaluates purchase totals
- Determines customer tier
- Calculates discounts
- Returns enriched customer data

This makes the application easier to maintain and avoids duplicated business logic across controllers.

---

# Authentication

The application uses **JSON Web Tokens (JWT)** for authentication.

User Roles:

- **Admin**
  - Manage customers
  - Configure loyalty thresholds
  - Full system access

- **Sales Staff**
  - View customers
  - Record purchases
  - Limited permissions

---

# API Overview

### Authentication

```
POST /api/auth/login
```

### Customers

```
GET    /api/customers
POST   /api/customers
PUT    /api/customers/:id
DELETE /api/customers/:id
PATCH  /api/customers/:id/purchase
```

### Segments

```
GET /api/segments
PUT /api/segments/:id
```

---

# Installation

## Clone Repository

```bash
git clone https://github.com/AlgoDove/customer-management-erp-module.git
```

## Install Backend

```bash
cd server
npm install
```

## Install Frontend

```bash
cd ../client
npm install
```

---

# Environment Variables

Create a `.env` file inside the `server` directory.

```env
PORT=
MONGO_URI=
JWT_SECRET=
```

---

# Running the Application

Backend

```bash
cd server
npm run dev
```

Frontend

```bash
cd client
npm run dev
```

---

# Deployment

The application has been deployed using free-tier cloud services for demonstration purposes.

### Backend

- Render (Free Tier)

### Frontend

- Railway (Free Tier)

> **Note:** Public deployment links may become temporarily unavailable because free-tier hosting services can suspend applications after periods of inactivity or when free usage limits are reached.

---

# Engineering Highlights

This project demonstrates:

- Full-Stack MERN Development
- REST API Design
- JWT Authentication
- Role-Based Access Control
- Service Layer Architecture
- Business Rule Encapsulation
- MongoDB Schema Design
- Dynamic Data Computation
- Separation of Concerns
- Responsive UI Development

---

# Future Enhancements

Planned improvements include:

- Pagination and search for customer records
- Request validation using Zod or Joi
- Redis caching for segmentation rules
- Swagger/OpenAPI documentation
- Unit and integration testing
- Docker containerization
- CI/CD using GitHub Actions
- Audit logging
- Performance optimization for large datasets
- Monitoring and centralized logging

---

# What I Learned

Building this project strengthened my understanding of:

- Designing scalable REST APIs
- Structuring backend applications using the Service Layer pattern
- JWT-based authentication and authorization
- MongoDB data modeling
- Business logic separation
- React state management
- Full-stack application deployment
- End-to-end project architecture

---

# Author

**AlgoDove**

Aspiring Software Engineer passionate about building scalable full-stack applications using modern web technologies.

GitHub:
https://github.com/AlgoDove

---

# License

This project is intended for educational and portfolio purposes.

MIT License.
