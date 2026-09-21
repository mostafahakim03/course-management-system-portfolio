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

## Rate Limiting

The backend includes multiple layers of rate limiting to protect the API and reduce abuse.

### Global API Rate Limiting

A Bucket4j-based rate limiter limits requests by IP address.

* Up to **100 requests per minute per IP**
* CORS `OPTIONS` preflight requests are excluded
* Excessive requests receive HTTP `429 Too Many Requests`

The rate limiter uses Caffeine to manage IP-based buckets efficiently and limits the cache size to prevent uncontrolled memory usage.

---

## OTP Protection

OTP operations have dedicated rate limits separate from the general API rate limiter.

### OTP Sending

The system limits OTP sending by:

* **3 requests per email within 10 minutes**
* **10 requests per IP within 10 minutes**

This helps reduce OTP spam and abuse against individual email addresses and the API.

### OTP Verification

OTP verification attempts are protected using two independent limits:

* **5 attempts per email + IP within 10 minutes**
* **20 attempts per IP within 10 minutes**

This provides protection against repeated attempts against a specific account as well as broader abuse originating from a single IP address.

---

## Brute-Force Protection

The login process includes dedicated brute-force protection.

Failed login attempts are tracked using both:

* Email + IP combination
* IP address

### Account-Level Protection

If an email + IP combination reaches **5 failed login attempts**, it is temporarily blocked for **15 minutes**.

### IP-Level Protection

If an IP reaches **20 failed login attempts**, the IP is temporarily blocked for **15 minutes**.

This provides two layers of protection against repeated credential-guessing attempts.

After a successful login, the failed-attempt counter for the specific email + IP combination is cleared.

The IP-level counter is intentionally preserved so that successfully authenticating with another account cannot be used to reset the IP's failed-attempt history.

---

## In-Memory Security Caching

The rate-limiting and brute-force protection mechanisms use **Caffeine Cache** for short-lived security counters.

The caches use expiration policies and maximum entry limits to help control memory usage.

For example:

* Rate-limit caches can hold up to 100,000 entries.
* Inactive entries expire automatically.
* OTP counters expire according to their configured security windows.
* Brute-force tracking entries expire after inactivity.

This keeps temporary security state lightweight while providing fast access to counters.

---

## Security Layers

The authentication system therefore combines multiple security mechanisms:

```text
                    Incoming Request
                           │
                           ▼
                  Global Rate Limiting
                           │
                           ▼
                  Authentication / JWT
                           │
             ┌─────────────┴─────────────┐
             │                           │
             ▼                           ▼
       OTP Protection              Brute-Force
       Email + IP limits           Email + IP limits
             │                           │
             └─────────────┬─────────────┘
                           ▼
                 Role-Based Authorization
                           │
                           ▼
                 Resource-Level Authorization
```

These layers work together rather than relying on authentication alone.

---

## Resource-Level Access Control

Authorization is not limited to checking whether a user is logged in.

Student-specific resources are also restricted to the appropriate student.

A student cannot simply access another student's lecture resources by changing an identifier or requesting a different resource.

The backend validates the relationship between the authenticated student and the requested resource before allowing access.

This provides an additional layer of **resource-level authorization** beyond basic role-based access control.

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

## Future Improvements

Future security improvements may include:

* Refresh token workflow
* Additional account security features
* Enhanced session management
* More granular permissions
* Additional security monitoring
