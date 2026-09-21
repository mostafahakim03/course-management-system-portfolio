# MTC Center — Course Management System

A full-stack course management platform designed to simplify course administration, student registration, learning resources, and educational operations.

This repository is a **portfolio and case study** showcasing the system's features, user workflows, interface design, and deployment.

> **Note:** The source code is kept private. This repository contains selected screenshots, documentation, and project case studies.

---

## 🌐 Live Demo

* **Website:** https://mtccenters.com
* **Frontend:** React
* **Backend:** Spring Boot REST API
* **Database:** PostgreSQL

---

## 📌 Project Overview

MTC Center is a course management system that supports different user roles and educational workflows.

The platform allows students to explore courses, register for available courses, access lecture resources, and manage their profiles.

Administrators can manage students, instructors, courses, categories, batches, lectures, lecture resources, registrations, and contact messages through the administrative interface.

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
* Access to lecture resources
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
* Assigning instructors to courses
* Contact message management

### 👨‍🏫 Instructor

Currently, instructors can have accounts and be assigned to courses by administrators.

> Instructor-specific dashboard features and workflows are planned for future development.

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

The administration interface provides centralized management of the platform's users, courses, categories, batches, instructors, registrations, lectures, resources, and contact messages.

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

The administration interface provides visibility into course registrations and batch-related student requests.

<p align="center">
  <img src="screenshots/admin-course-registrations.png" alt="Admin Course Registrations" width="800">
</p>

<p align="center">
  <img src="screenshots/admin-batch-requests.png" alt="Admin Batch Requests" width="800">
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


### Home Page

The landing page introduces the platform and highlights available course content.

### Student Experience

The student experience includes authentication, dashboard access, course registration, and access to lecture resources.

### Admin Experience

The administrative interface provides tools for managing the platform's educational data and operations, including courses, batches, lectures, lecture resources, students, instructors, and registrations.

> Detailed screenshots and feature demonstrations are available in the `screenshots` directory.

---

## 🔐 Security, Authentication & Authorization

The system implements authentication and authorization using **JWT (JSON Web Tokens)**.

The authentication flow includes:

* User registration
* Login
* Email verification code
* Password setup
* JWT-based authentication
* Role-based authorization
* Protected API endpoints
* Role-specific access to platform features

Different user roles have access to different platform features based on their authorization level.

---

## ⚡ Performance & Image Optimization

The system includes a dedicated image-processing service that automatically converts uploaded images to **WebP format** during the upload process.

This helps:

* Reduce image file sizes
* Optimize storage usage
* Improve image loading performance
* Reduce bandwidth consumption
* Deliver optimized images to the frontend

---

## 🧰 Technology Stack

### Frontend

* React
* JavaScript
* HTML5
* CSS3
* Responsive UI design

### Backend

* Java
* Spring Boot
* REST API
* JWT Authentication
* Role-based Authorization
* Image processing and WebP conversion

### Database

* PostgreSQL

### Deployment

* Cloudflare Pages
* VPS deployment
* Docker
* Custom domain configuration

---

## 📱 User Experience

The interface is designed to support:

* Responsive layouts
* Light and dark themes
* Clear navigation
* Role-specific workflows
* Course-focused user experience
* Accessible learning resources

---

## 📁 Repository Structure

```text
course-management-system-portfolio/
│
├── screenshots/
│
├── case-studies/
│
├── architecture/
│
└── README.md
```

---

## 🚀 Deployment

The frontend is deployed through Cloudflare Pages, while the backend is deployed on a VPS.

The application uses a separate frontend and backend architecture connected through REST APIs.

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
* PostgreSQL database integration
* Database-related functionality
* Admin functionality
* Course and lecture management
* Lecture resource management
* Image processing and WebP optimization
* Deployment and production configuration
* UI improvements and responsive design

---

## 📌 Future Improvements

* Instructor dashboard
* Instructor-specific course workflows
* Additional learning features
* Expanded reporting and analytics
* Further platform improvements

---

## 📄 License

This repository is a portfolio presentation of the project.

The source code is private and is not included in this repository.
