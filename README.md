# Hospital Management System Database

1. [Overview](#overview)
2. [Project Goals](#project-goals)
3. [Tech Stack](#tech-stack)
4. [Database Design](#database-design)
5. [What I Learned](#what-i-learned)
6. [Future Improvements](#future-improvements)
7. [Author](#author)
8. [Project Status](#project-status)
9. [License](#license)






## Overview

The Hospital Management System Database is a relational database project built using MySQL. It simulates how healthcare institutions manage patients, doctors, and appointments while demonstrating industry-standard database design principles.

This project was developed as part of my self-study journey in Database Management Systems (DBMS), SQL, and Backend Development.

---

## Project Goals

* Design a relational database from scratch
* Implement primary and foreign key relationships
* Practice database normalization
* Learn how SQL JOIN operations work
* Simulate real-world healthcare data management
* Build a foundation for future FastAPI and SQLAlchemy integration

---

## Tech Stack

### Database

* MySQL 8.x

### Database Administration

* MySQL Workbench

### Development Environment

* Visual Studio Code

### Version Control

* Git
* GitHub

---

## Database Design

The system is composed of three core entities:

### Patient_data

Stores patient information.

| Column     | Type        |
| ---------- | ----------- |
| Patient_ID | Primary Key |
| Name       | VARCHAR     |
| Sex        | VARCHAR     |
| Age        | INT         |

### Doctor

Stores doctor information.

| Column         | Type        |
| -------------- | ----------- |
| Staff_ID       | Primary Key |
| Name_Roles     | VARCHAR     |
| Specialization | VARCHAR     |

### Appointment

Acts as the bridge between patients and doctors.

| Column     | Type        |
| ---------- | ----------- |
| Patient_ID | Foreign Key |
| Staff_ID   | Foreign Key |
| Date       | DATE        |
| Problem    | VARCHAR     |

---

## Entity Relationship Diagram (ERD)

Patient_data

```
 │
 
 │ Patient_ID
 
 ▼
```

Appointment

```
 ▲
 
 │ Staff_ID
 
 │
```

Doctor

---

## Database Architecture

The project follows relational database principles by separating data into independent entities.

Instead of storing doctor names and patient names repeatedly inside appointment records, the system uses foreign keys to establish relationships between tables.

Benefits:

* Reduced Data Redundancy
* Improved Data Integrity
* Better Scalability
* Easier Maintenance
* Faster Data Retrieval Through Relationships

---

## SQL Concepts Demonstrated

### Database Fundamentals

* Database Creation
* Table Creation
* Data Types
* Data Insertion
* Data Retrieval

### Relational Database Design

* Primary Keys
* Foreign Keys
* Table Relationships
* Data Normalization
* Referential Integrity

### Querying

* SELECT Statements
* WHERE Clauses
* INNER JOIN Operations
* Multi-Table Queries

---

## Example Query

This query retrieves information from multiple related tables:

```sql
SELECT
    A.name,
    B.name_roles,
    D.date,
    A.sex,
    D.problem
FROM Appointment D
JOIN patients A
    ON D.Patient_ID = A.Patient_ID
JOIN doctor B
    ON D.staff_Id = B.staff_ID;
```

### Example Output

| Patient  | Doctor           | Date       | Sex  | Problem  |
| -------- | ---------------- | ---------- | ---- | -------- |
| Chrysler | Dr Michael Stein | 2026-06-25 | Male | Headache |

---

## What I Learned

Through this project, I gained practical experience in:

* Designing relational databases
* Building table relationships
* Understanding foreign keys
* Writing SQL JOIN queries
* Database normalization concepts
* Data modeling techniques
* Query optimization fundamentals

One of the most important lessons learned was understanding how JOIN operations connect related tables and allow data from multiple sources to be displayed as a single result set.

---

## Future Improvements

### Database Enhancements

* Billing Management System
* Treatment Records
* Prescription Management
* Medical History Tracking
* Room Assignment System

### Backend Development

* Python Integration
* MySQL Connector
* SQLAlchemy ORM
* FastAPI REST API
* Authentication & Authorization

### Deployment

* Docker Containerization
* Cloud Database Hosting
* CI/CD Integration

---

## Author

Chrysler Clarence Abanto

Incoming Information Technology Student

Currently studying:

* Python
* MySQL
* Database Design
* Backend Development
* FastAPI
* Systems Design

---

## Project Status

Completed (Version 1)

This project serves as a foundational milestone in my journey toward becoming a Backend Developer and Software Engineer.

## License

MIT License

Copyright (c) 2021 Hospital-Managemet-System-Database

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
