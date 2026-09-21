# Authentication & Security

## Overview

MTC Center uses a structured authentication and authorization flow to protect user accounts and restrict access to role-specific features.

The system was designed to ensure that authenticated users can only access resources and operations allowed for their role and account.

---

## Authentication Flow

The student authentication flow includes:

1. Account registration
2. Verification code
3. Password setup
4. Login
5. JWT authentication
6. Access to protected features

This provides a clear separation between account creation, verification, and authenticated access.

---

## JWT Authentication

The backend uses **JSON Web Tokens (JWT)** for authentication.

After successful login, the authenticated session uses the JWT when communicating with protected backend endpoints.

The authentication state is intentionally **not persisted in Local Storage**.

When the browser tab/session is closed, the authentication token is removed, requiring the user to authenticate again.

This approach avoids keeping the authentication session persisted across browser sessions.

---

## Role-Based Authorization

The system supports role-based access control.

Different roles have access to different features according to their permissions.

### Student

Students can access student-specific features such as:

* Their dashboard
* Their enrolled courses
* Their profile
* Their authorized lecture resources

### Admin

Administrators have access to management features including:

* Students
* Instructors
* Courses
* Categories
* Batches
* Lectures
* Lecture resources
* Course registrations
* Contact messages

### Instructor

Currently, instructors can have accounts and be assigned to courses by administrators.

Instructor-specific dashboard functionality is planned for future development.

---

## Resource-Level Access Control

Authorization is not limited to checking whether a user is logged in.

Student-specific resources are also restricted to the appropriate student.

A student cannot simply access another student's lecture resources by changing an identifier or requesting a different resource.

The backend validates the relationship between the authenticated student and the requested resource before allowing access.

This provides an additional layer of **resource-level authorization** beyond basic role-based access control.

---

## Protected API Endpoints

Backend endpoints that require authentication are protected through the application's authorization layer.

Requests are validated before allowing access to protected resources or operations.

This helps prevent unauthorized users from accessing administrative or student-specific data.

---

## Security Considerations

The public portfolio repository does not contain:

* Passwords
* JWT secrets
* API keys
* Database credentials
* Private source code
* Production secrets

The implementation details and source code remain in the private project repository.

---

## Future Improvements

Future security improvements may include:

* Refresh token workflow
* Additional account security features
* Enhanced session management
* More granular permissions
* Additional security monitoring
