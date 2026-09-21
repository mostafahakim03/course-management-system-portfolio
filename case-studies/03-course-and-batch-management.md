# Course & Batch Management

## Overview

The platform provides a complete administrative workflow for managing courses, batches, students, instructors, lectures, and learning resources.

The system supports both **direct student assignment by administrators** and a **student enrollment request workflow using batch codes**.

---

## Course Management

Administrators can manage the complete course lifecycle:

* Create courses.
* Edit course information.
* Delete courses.
* Assign categories.
* Manage course details.
* Manage course registrations.

Courses act as the main structure for organizing batches and educational content.

---

## Batch Management

Each course can contain one or more batches.

Administrators can:

* Create batches.
* Edit batch information.
* Delete batches.
* Manage batch students.
* Assign instructors.
* Manage batch lectures.
* Manage batch resources.
* Review student enrollment requests.

A batch can also have a dedicated **Batch Code** that students can use to request enrollment.

---

## Student Enrollment

The platform supports two different enrollment workflows.

### 1. Direct Admin Assignment

An administrator can directly assign a student to a batch.

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

This is useful when administrators need to manually manage registrations or enroll students on behalf of the center.

### 2. Student Enrollment Request

Students can also request enrollment themselves using a batch code.

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
Admin Reviews Request
   │
   ├── Accept ──► Student Added to Batch
   │
   └── Reject ──► Request Rejected
```

This provides a controlled self-enrollment workflow without allowing students to automatically join a batch.

---

## Enrollment Request Management

Administrators have a dedicated area for reviewing batch enrollment requests.

For each request, the administrator can:

* View the requesting student.
* View the requested batch.
* Review the request.
* Accept the request.
* Reject the request.

When a request is accepted, the student becomes associated with the corresponding batch and can access the content they are authorized to view.

---

## Batch Code

The batch code provides a simple way for students to identify the batch they want to join.

Instead of requiring an administrator to manually find the student first, the student can submit the batch code through the enrollment workflow.

The backend then creates an enrollment request rather than immediately granting access.

This keeps the final enrollment decision under administrator control.

---

## Instructor Assignment

Administrators can assign instructors to batches/courses.

The current system supports instructor accounts and administrative assignment.

Instructor-specific dashboard functionality can be expanded in future development.

---

## Lecture Management

Administrators can manage lectures associated with batches.

This includes:

* Creating lectures.
* Editing lectures.
* Managing lecture information.
* Organizing educational content within the batch.

Lectures provide the structure through which students access course materials.

---

## Lecture Resources

Each lecture can contain multiple types of educational resources.

Supported resource types include:

* Uploaded files.
* Uploaded videos.
* Google Drive links.
* YouTube links.

YouTube resources can be embedded and played directly in the student view, while Google Drive resources can be accessed through their configured links.

This allows a lecture to combine platform-hosted and externally hosted educational content.

---

## Student Resource Access

Students can access resources belonging to the courses and batches they are authorized to access.

The backend verifies the relationship between the authenticated student and the requested resource before returning protected content.

Therefore, a student cannot simply change a resource ID in a request and access another student's protected course content.

This provides **resource-level authorization** in addition to the platform's role-based authorization.

---

## Administrative Workflow

```text
                    Course
                       │
                       ▼
                     Batch
                       │
          ┌────────────┴────────────┐
          │                         │
          ▼                         ▼
   Admin Assignment          Batch Code
          │                         │
          │                         ▼
          │                Student Enrollment
          │                    Request
          │                         │
          │                         ▼
          │                  Admin Review
          │                    /       \
          │                   /         \
          │               Accept       Reject
          │                 │
          └────────┬────────┘
                   ▼
             Student in Batch
                   │
                   ▼
                Lectures
                   │
                   ▼
              Resources
                   │
        ┌──────────┼──────────┐
        ▼          ▼          ▼
      Files      Videos    External Links
                            │
                       ┌────┴────┐
                       ▼         ▼
                    YouTube   Google Drive
```

---

## Benefits

This architecture provides:

* Flexible student enrollment.
* Administrative control over enrollment requests.
* Direct assignment when needed.
* Batch-based organization.
* Multiple content delivery methods.
* P
