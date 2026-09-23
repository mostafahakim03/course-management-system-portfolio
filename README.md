# MTC Center — Course Management System

A full-stack course management platform designed to simplify course administration, student registration, enrollment workflows, learning resources, and educational operations.

This repository is a **portfolio and case study** showcasing the system's features, user workflows, interface design, technical architecture, security, and deployment.

> **Note:** The source code is kept private. This repository contains selected screenshots, documentation, architecture information, and project case studies.

---

## 🌐 Live Demo

* **Website:** https://mtccenters.com
* **Frontend:** React
* **Backend:** Spring Boot REST API
* **Database:** PostgreSQL on Neon

---

## 📌 Project Overview

MTC Center is a course management system that supports different user roles and educational workflows.

The platform allows students to:

* Explore available courses.
* View course details.
* Register for courses.
* Join batches through enrollment requests.
* Use batch codes to request enrollment.
* Access their enrolled courses.
* Access authorized lecture resources.
* Manage their profiles.

Administrators can manage students, instructors, courses, categories, batches, lectures, lecture resources, registrations, enrollment requests, and contact messages through the administrative interface.

The platform also supports multiple types of learning resources, including uploaded files, uploaded videos, Google Drive links, and YouTube videos.

---

## ✨ Key Features

### 👨‍🎓 Student Features

* User registration and login
* Email verification code
* Password setup and authentication flow
* Student dashboard
* Course browsing
* Course details
* Course registration
* My Courses
* Batch enrollment using a batch code
* Enrollment request workflow
* Access to authorized lecture resources
* Student profile management

### 🛠️ Admin Features

* Admin dashboard
* Student management
* Instructor management
* Course management
* Category management
* Batch management
* Lecture management
* Lecture resources management
* Course registration management
* Batch enrollment request management
* Accept or reject student enrollment requests
* Directly assign students to batches
* Assign instructors to courses/batches
* Contact message management

### 👨‍🏫 Instructor

Currently, instructors can have accounts and be assigned to courses/batches by administrators.

> Instructor-specific dashboard features and workflows are planned for future development.

### 📚 Lecture Resources

Lectures can contain different types of learning resources:

* Uploaded files
* Uploaded videos
* Google Drive links
* YouTube links
* Embedded YouTube video playback in the student view

This allows the platform to support both platform-hosted and externally hosted educational content.

---

## 📝 Student Enrollment Workflow

The platform supports two ways of adding students to batches.

### Direct Admin Assignment

An administrator can directly select a student and assign them to a batch.

```text
Admin
  │
  ▼
Select Batch
  │
  ▼
Select Student
  │
  ▼
Assign Student
  │
  ▼
Student Added to Batch
```

### Batch Code Enrollment Request

Students can also use a batch code to request enrollment.

```text
Student
   │
   ▼
Enter Batch Code
   │
   ▼
Enrollment Request
   │
   ▼
Admin Review
   │
   ├── Accept ──► Student Added to Batch
   │
   └── Reject ──► Request Rejected
```

This allows students to request access while keeping the final enrollment decision under administrator control.

---

## 🖥️ Screenshots

### 🏠 Home & Course Discovery

The platform provides a clean course-focused experience for discovering and exploring available courses.

<p align="center">
  <img src="screenshots/home-page.png" alt="MTC Center Home Page" width="800">
</p>

<p align="center">
  <img src="screenshots/home-page-dark.png" alt="MTC Center Home Page - Dark Mode" width="800">
</p>

<p align="center">
  <img src="screenshots/home-categories.png" alt="Course Categories" width="800">
</p>

<p align="center">
  <img src="screenshots/home-featured-courses.png" alt="Featured Courses" width="800">
</p>

### 📚 Courses

Students can browse available courses and view detailed course information before registration.

<p align="center">
  <img src="screenshots/courses-page.png" alt="Courses Page" width="800">
</p>

<p align="center">
  <img src="screenshots/course-details.png" alt="Course Details" width="800">
</p>

<p align="center">
  <img src="screenshots/course-registration.png" alt="Course Registration" width="800">
</p>

### 👨‍🎓 Student Experience

The student workflow includes registration, verification, authentication, dashboard access, enrolled courses, lecture resources, and profile management.

<p align="center">
  <img src="screenshots/student-login.png" alt="Student Login" width="700">
</p>

<p align="center">
  <img src="screenshots/student-register.png" alt="Student Registration" width="700">
</p>

<p align="center">
  <img src="screenshots/student-verification.png" alt="Student Verification" width="700">
</p>

<p align="center">
  <img src="screenshots/student-set-password.png" alt="Student Password Setup" width="700">
</p>

<p align="center">
  <img src="screenshots/student-my-courses.png" alt="Student My Courses" width="800">
</p>

<p align="center">
  <img src="screenshots/student-lecture-resources.png" alt="Student Lecture Resources" width="800">
</p>

<p align="center">
  <img src="screenshots/student-profile.png" alt="Student Profile" width="800">
</p>

### 🛠️ Admin Dashboard

The administration interface provides centralized management of the platform's users, courses, categories, batches, instructors, registrations, lectures, resources, enrollment requests, and contact messages.

<p align="center">
  <img src="screenshots/admin-dashboard.png" alt="Admin Dashboard" width="800">
</p>

### 👥 Student & Instructor Management

Administrators can manage students and instructors and control their relationship with courses and batches.

<p align="center">
  <img src="screenshots/admin-students.png" alt="Admin Student Management" width="800">
</p>

<p align="center">
  <img src="screenshots/admin-instructor management.png" alt="Admin Instructor Management" width="800">
</p>

### 📖 Course & Lecture Management

Administrators can create and manage courses, batches, lectures, and learning resources.

<p align="center">
  <img src="screenshots/admin-courses-management.png" alt="Admin Course Management" width="800">
</p>

<p align="center">
  <img src="screenshots/admin-batches-management.png" alt="Admin Batch Management" width="800">
</p>

<p align="center">
  <img src="screenshots/admin-batch-lectures.png" alt="Admin Batch Lectures" width="800">
</p>

### 📝 Registration & Requests

The administration interface provides visibility into course registrations and batch-related student enrollment requests.

<p align="center">
  <img src="screenshots/admin-course-registrations.png" alt="Admin Course Registrations" width="800">
</p>

<p align="center">
  <img src="screenshots/admin-batch-requests.png" alt="Admin Batch Enrollment Requests" width="800">
</p>

### 🗂️ Categories & Communication

Administrators can manage course categories and review contact messages submitted through the platform.

<p align="center">
  <img src="screenshots/admin-categories-management.png" alt="Admin Categories Management" width="800">
</p>

<p align="center">
  <img src="screenshots/admin-contact-messages.png" alt="Admin Contact Messages" width="800">
</p>

> Additional screenshots covering specific administrative actions such as creating, editing, deleting, assigning students, and managing batches are available in the [`screenshots`](screenshots) directory.

---

## 📧 Email & Notification Service

The system includes email-based communication for
authentication and important student workflow events.

Supported use cases include:

- Email verification codes during registration
- Student enrollment status notifications
- Batch acceptance notifications
- Lecture publication notifications (if implemented)
- Other system-related email notifications

Email delivery is handled through the backend's
email service integration.

---

## 🔐 Security, Authentication & Authorization

The system implements authentication and authorization using **JWT (JSON Web Tokens)**.

The authentication and security architecture includes:

* User registration
* Email verification code
* Password setup
* JWT-based authentication
* Role-based authorization
* Protected API endpoints
* Rate limiting
* OTP request and verification protection
* Brute-force login protection
* Temporary account/IP blocking after repeated failed attempts
* In-memory security caching
* Resource-level authorization

Students can only access lecture resources they are authorized to access through their course/batch relationship.

Detailed security implementation is documented in the [Authentication & Security Case Study](case-studies/01-authentication-and-security.md).

---

## ⚡ Performance & Image Optimization

The system includes a dedicated image-processing service that automatically converts uploaded images to **WebP format** during the upload process.

This helps:

* Reduce image file sizes
* Optimize storage usage
* Improve image loading performance
* Reduce bandwidth consumption
* Deliver optimized images to the frontend

More details are available in the [Image Optimization Case Study](case-studies/02-image-optimization.md).

---

## 🧰 Technology Stack

### Frontend

* React
* JavaScript
* HTML5
* CSS3
* Responsive UI design
* Light/Dark themes

### Backend

* Java
* Spring Boot
* REST API
* JWT Authentication
* Role-based Authorization
* Rate limiting
* Brute-force protection
* OTP protection
* Image processing and WebP conversion

### Database

* PostgreSQL
* Neon

### Deployment

* Cloudflare Pages
* VPS
* Docker
* Nginx
* HTTPS / SSL configuration
* Custom domains

---

## 🏗️ System Architecture

The MTC Center platform follows a layered architecture
consisting of a React frontend, Spring Boot REST API,
Nginx reverse proxy, Docker deployment, and Neon PostgreSQL.

The architecture diagram illustrates:

- Frontend and backend communication
- VPS and Docker infrastructure
- Nginx reverse proxy and HTTPS
- JWT authentication and security layers
- Student enrollment workflows
- Lecture resource management
- Email notification service
- Image optimization and WebP conversion
- Managed PostgreSQL database

<p align="center">
  <img
    src="architecture/mtc-center-system-architecture.png"
    alt="MTC Center System Architecture"
    width="1200"
  >
</p>


---

## 📱 User Experience

The interface is designed to support:

* Responsive layouts
* Light and dark themes
* Clear navigation
* Role-specific workflows
* Course-focused user experience
* Multiple learning resource formats
* Student-friendly enrollment workflows
* Accessible learning resources

---

## 📚 Case Studies

Detailed technical documentation is available in the following case studies:

### 🔐 Authentication & Security

Covers JWT authentication, role-based authorization, protected endpoints, rate limiting, OTP protection, brute-force protection, security caching, and resource-level authorization.

[View Authentication & Security Case Study](case-studies/01-authentication-and-security.md)

### 🖼️ Image Optimization

Documents the image upload pipeline and automatic WebP conversion used to reduce image size, storage usage, and bandwidth consumption.

[View Image Optimization Case Study](case-studies/02-image-optimization.md)

### 📚 Course & Batch Management

Covers course management, batch management, direct student assignment, batch-code enrollment requests, admin approval/rejection, instructor assignment, lectures, and learning resources.

[View Course & Batch Management Case Study](case-studies/03-course-and-batch-management.md)

### 🚀 Deployment & Production Infrastructure

Documents the production architecture using Cloudflare Pages, VPS, Docker, Nginx reverse proxy, HTTPS, Spring Boot, and Neon PostgreSQL.

[View Deployment & Infrastructure Case Study](case-studies/04-deployment-and-infrastructure.md)

---

## 📁 Repository Structure

```text
course-management-system-portfolio/

│
├── screenshots/
│
├── case-studies/
│   ├── 01-authentication-and-security.md
│   ├── 02-image-optimization.md
│   ├── 03-course-and-batch-management.md
│   └── 04-deployment-and-infrastructure.md
│
├── architecture/
│
└── README.md
```

---

## 🚀 Deployment

The production environment uses a separate frontend and backend architecture.

```text
React Frontend
      │
      │ HTTPS / REST API
      ▼
Spring Boot Backend
      │
      ▼
Docker + VPS
      │
      ▼
Nginx Reverse Proxy
      │
      ▼
Neon PostgreSQL
```

### Production Environment

* **Frontend:** Cloudflare Pages
* **Frontend Domain:** https://mtccenters.com
* **Backend:** Spring Boot
* **Backend Domain:** https://api.mtccenters.com
* **Backend Hosting:** VPS
* **Containerization:** Docker
* **Reverse Proxy:** Nginx
* **Database:** Neon PostgreSQL
* **Communication:** HTTPS / REST API

More details are available in the [Deployment & Production Infrastructure Case Study](case-studies/04-deployment-and-infrastructure.md).

---

## 🔒 Source Code

The source code for this project is maintained in a private repository.

This public repository is intended to demonstrate:

* Project functionality
* User interface design
* Technical architecture
* Security and authentication approach
* Image optimization
* Database integration
* Deployment experience
* Development and implementation case studies

---

## 👨‍💻 Project Role

**Full-Stack Development**

Responsibilities include:

* Frontend development
* Backend API development
* JWT authentication and authorization
* Authentication workflows
* Rate limiting and security protection
* PostgreSQL database integration
* Database-related functionality
* Admin functionality
* Course and batch management
* Student enrollment workflows
* Lecture management
* Lecture resource management
* Image processing and WebP optimization
* Deployment and production configuration
* Docker deployment
* Nginx and HTTPS configuration
* UI improvements and responsive design

---

## 📌 Future Improvements

* Payment integration for online course registration and payments
* Automatic enrollment after successful payment
* Instructor dashboard
* Instructor-specific course workflows
* Additional learning features
* Student progress tracking
* Attendance management
* Expanded reporting and analytics
* Further platform improvements

---

## 📄 License

This repository is a portfolio presentation of the project.

The source code is private and is not included in this repository.