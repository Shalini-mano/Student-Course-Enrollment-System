====================================================
Guvi SDE Spring - Student Course Enrollment System
====================================================

A Spring Boot + MongoDB backend application for managing:

- Students
- Courses
- Enrollments

This project demonstrates clean layered architecture and backend best practices.
Developed as part of an internship project under the Guvi SDE program.

----------------------------------------------------
KEY FEATURES
----------------------------------------------------

- RESTful API Design
- Clean Layered Architecture
- Domain Modeling
- Repository Pattern
- MongoDB Reference Relationships

----------------------------------------------------
TECH STACK
----------------------------------------------------

Language    : Java 25 (LTS)
Framework   : Spring Boot, Spring Framework
Web         : Spring Web (REST APIs)
Database    : MongoDB
Data Access : Spring Data MongoDB
Build Tool  : Maven

----------------------------------------------------
PROJECT ARCHITECTURE
----------------------------------------------------

Controller
   |
Service
   |
Repository
   |
MongoDB

Each layer follows separation of concerns.

----------------------------------------------------
MONGODB COLLECTIONS
----------------------------------------------------

students     - Stores student details
courses      - Stores course details
enrollments  - Maps students to courses

----------------------------------------------------
DATA MODELS
----------------------------------------------------

Student Model:

{
  "_id": "65b7f3b2a9c7e24e0f4e1a91",
  "name": "Soumyajit",
  "email": "soumyajit@example.com",
  "active": true
}

Course Model:

{
  "_id": "65b9a0c2a9c7e24e0f4e20a1",
  "title": "Spring Boot Foundations",
  "code": "SB101",
  "active": true
}

Enrollment Model:

{
  "_id": "65b9a13aa9c7e24e0f4e20b2",
  "studentId": "65b7f3b2a9c7e24e0f4e1a91",
  "courseId": "65b9a0c2a9c7e24e0f4e20a1",
  "enrolledAt": "2026-02-01T10:15:00Z",
  "status": "ACTIVE"
}

----------------------------------------------------
API INFORMATION
----------------------------------------------------

Base URL:
http://localhost:9000

----------------
Student APIs
----------------

POST    /students          - Create student
GET     /students          - List students
GET     /students/{id}     - Get student by ID
PUT     /students/{id}     - Update student
DELETE  /students/{id}     - Delete student

Supports search, pagination, and sorting:

GET /students?q=example&sortBy=email&sortDir=desc&page=0&size=5

----------------
Course APIs
----------------

POST    /courses          - Create course
GET     /courses          - List courses
GET     /courses/{id}     - Get course by ID
DELETE  /courses/{id}     - Delete course

----------------
Enrollment APIs
----------------

POST  /enrollments?studentId={id}&courseId={id}
      - Enroll student

GET   /enrollments/student/{studentId}
      - Get enrollments by student

GET   /enrollments/course/{courseId}
      - Get enrollments by course

----------------------------------------------------
HOW TO RUN THE PROJECT
----------------------------------------------------

1. Clone Repository

git clone <your-repo-url>
cd student-course-enrollment

2. Configure MongoDB

Make sure MongoDB is running.

Edit application.properties:

spring.data.mongodb.uri=mongodb://localhost:27017/guvi_sde
server.port=9000

3. Run Application

mvn spring-boot:run

Server will start at:
http://localhost:9000

----------------------------------------------------
DESIGN DECISIONS
----------------------------------------------------

- Enrollment stores only studentId and courseId
- Unique index on course code
- Layered architecture
- Uses Instant for timestamps
- MongoDB _id mapped with @Id

----------------------------------------------------
FUTURE IMPROVEMENTS
----------------------------------------------------

- Prevent duplicate enrollments
- Use Enum for status
- Add DTO layer
- Add global exception handling
- Add pagination
- Add JWT authentication
- Add Swagger documentation

----------------------------------------------------
LEARNING OUTCOMES
----------------------------------------------------

- NoSQL document modeling
- Clean Spring Boot architecture
- REST API design
- Service validation
- Backend best practices

----------------------------------------------------
AUTHOR
----------------------------------------------------

Name   : Your Name
Program: Guvi SDE Internship
GitHub : Your GitHub Profile
Email  : Your Email

====================================================
END OF FILE
====================================================
