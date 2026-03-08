
# Apartment Management System

A full-stack Apartment Management System designed to help administrators manage residents, apartments, billing, and payments efficiently. The system provides a modern dashboard with analytics, payment integration via QR codes, and automated financial tracking.

---

#  Key Features

###  User & Authentication Management
- Secure login and registration using JWT (JSON Web Tokens).
- Profile management.
- Password reset functionality.
- Secure API endpoints with authentication and authorization.

###  Resident & Apartment Management
- Manage apartment information.
- Assign residents to apartments.
- Maintain detailed resident profiles.

###  Billing & Fee Management
- Create and manage different types of fees:
  - Utility bills
  - Management fees
  - Other service charges
- Track payment status and billing history.

###  Payment Integration
- Generate QR codes for fast and convenient payments.
- Simplifies the payment process for residents.

###  Revenue Tracking
- Automated system to calculate and track revenue.
- Scheduled background tasks to update financial data.

###  Notification System
- Broadcast announcements to all residents.
- Send targeted notifications.
- Email integration for important alerts.

###  Interactive Dashboard
- Visual charts and analytics.
- Monitor:
  - Total revenue
  - Occupancy rate
  - Pending bills
  - Payment trends

---

#  Technology Stack

## Frontend
- **Framework:** React.js
- **UI Library:** Material-UI (MUI)
- **Design System:** Material Dashboard
- **Styling:** Custom CSS / JavaScript
- **Theme:** Dark / Light mode support
- **Routing:** React Router DOM

## Backend
- **Framework:** Java Spring Boot
- **Security:** Spring Security with JWT Authentication
- **ORM:** Spring Data JPA / Hibernate
- **Build Tool:** Maven
- **Additional Services:**
  - QR Code generation
  - Email service
  - Spring Scheduling

## Database
- **RDBMS:** MySQL  
- Database schema included in:

```

QLCC.sql

```

---

#  Project Structure

This repository is a monorepo containing both the frontend and backend applications.

```

├── backend/
│   ├── src/main/java/...
│   │   ├── controllers
│   │   ├── services
│   │   ├── repositories
│   │   ├── models
│   │   └── security
│   │
│   ├── src/main/resources/
│   │   ├── application.properties
│   │   ├── static
│   │   └── fonts
│   │
│   ├── pom.xml
│   └── mvnw

├── frontend/
│   ├── public/
│   │   ├── index.html
│   │   └── manifest.json
│   │
│   ├── src/
│   │   ├── components
│   │   ├── layouts
│   │   ├── context
│   │   ├── assets
│   │   └── pages
│   │
│   ├── package.json
│   └── genezio.yaml

├── QLCC.sql
└── README.md

````

---

#  Getting Started

Follow these instructions to run the project locally for development and testing.

---

#  Prerequisites

Make sure the following tools are installed:

| Tool | Version |
|-----|-----|
| Java | JDK 11+ (JDK 17 recommended) |
| Node.js | v14+ |
| npm | Latest |
| MySQL | Installed and running |
| Maven | Optional (project uses Maven Wrapper) |

---

#  Database Setup

Open your MySQL client (MySQL Workbench, phpMyAdmin, or CLI).

Create a new database:

```sql
CREATE DATABASE apartment_management;
````

Import the SQL schema:

```bash
mysql -u your_username -p apartment_management < QLCC.sql
```

This script will create all necessary tables and initial data.

---

#  Backend Setup

Navigate to the backend directory:

```bash
cd backend
```

Configure the database connection.

Open:

```
src/main/resources/application.properties
```

Update the following properties:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/apartment_management
spring.datasource.username=your_username
spring.datasource.password=your_password
```

Configure additional settings if needed:

* JWT secret keys
* Email SMTP configuration

Run the backend server:

```bash
./mvnw spring-boot:run
```

Backend will start at:

```
http://localhost:8080
```

---

#  Frontend Setup

Navigate to the frontend directory:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Run the development server:

```bash
npm start
```

Frontend will start at:

```
http://localhost:3000
```

---

#  Authentication & Security

The system uses **JWT (JSON Web Token)** for authentication.

Workflow:

1. User logs in through the React frontend.
2. Backend validates credentials.
3. Backend returns a **JWT token**.
4. Token is stored on the client side (localStorage or cookies).
5. All API requests include:

```
Authorization: Bearer <token>
```

Additional security features include:

* Protected endpoints
* Token validation filters
* Token blacklist mechanism for logout security

---

# UI / UX Theme

The frontend UI is built on a customized version of Material Dashboard.

Features include:

* Pre-built dashboard layout
* Data tables
* Billing management interface
* User profile pages
* Light / Dark theme toggle
* Configurator panel for UI customization

---

#  Future Improvements

Potential features for future development:

* Mobile application integration
* Online payment gateway (VNPay, MoMo)
* Role-based access control (Admin / Manager / Resident)
* Real-time notifications with WebSocket
* Advanced analytics and reporting

---

