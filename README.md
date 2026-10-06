# SQL-Final-Project
# 🎓 UniversityDB — SQL Database Project

> **A practical University Course Management Database built with MySQL**
>
> A clean, beginner-friendly SQL project covering database design, relationships, CRUD operations, joins, subqueries, aggregate functions, date/string functions, window functions, and CASE expressions.

---

## 📌 Project Overview

**UniversityDB** is a relational database project designed to manage basic university information such as:

- 👨‍🎓 Students
- 📚 Courses
- 👨‍🏫 Instructors
- 📝 Enrollments
- 🏫 Departments

The project demonstrates how multiple related tables can work together to answer real-world university data questions using SQL.

---

## 🗂️ Database Structure

```text
                    ┌─────────────────┐
                    │   Departments   │
                    │─────────────────│
                    │ DepartmentID PK │
                    │ DepartmentName  │
                    └────────┬────────┘
                             │
                    ┌────────┴────────┐
                    │                 │
                    ▼                 ▼
             ┌──────────────┐  ┌───────────────┐
             │   Courses    │  │  Instructors  │
             │──────────────│  │───────────────│
             │ CourseID PK  │  │InstructorID PK│
             │ CourseName   │  │ FirstName     │
             │ DepartmentID │  │ LastName      │
             │ Credits      │  │ Email         │
             └──────┬───────┘  │ DepartmentID  │
                    │           │ Salary*       │
                    │           └───────────────┘
                    ▼
             ┌──────────────┐
             │ Enrollments  │
             │──────────────│
             │EnrollmentID  │
             │ StudentID    │
             │ CourseID     │
             │EnrollmentDate│
             └──────┬───────┘
                    │
                    ▼
             ┌──────────────┐
             │   Students   │
             │──────────────│
             │ StudentID PK │
             │ FirstName    │
             │ LastName     │
             │ Email        │
             │ BirthDate    │
             │EnrollmentDate│
             └──────────────┘
```

> `Salary*` is added for the salary-based query because the original instructor table does not include a salary field.

---

## 🧩 Tables

| # | Table | Purpose |
|---|---|---|
| 1 | `Students` | Stores student information |
| 2 | `Courses` | Stores available university courses |
| 3 | `Instructors` | Stores instructor information |
| 4 | `Enrollments` | Connects students with courses |
| 5 | `Departments` | Stores university departments |

---

## 🔗 Relationships

```text
Departments 1 ────────< Courses
Departments 1 ────────< Instructors
Students    1 ────────< Enrollments >──────── 1 Courses
```

### Primary Keys

- `Students.StudentID`
- `Courses.CourseID`
- `Instructors.InstructorID`
- `Enrollments.EnrollmentID`
- `Departments.DepartmentID`

### Foreign Keys

- `Courses.DepartmentID → Departments.DepartmentID`
- `Instructors.DepartmentID → Departments.DepartmentID`
- `Enrollments.StudentID → Students.StudentID`
- `Enrollments.CourseID → Courses.CourseID`

---

## 🛠️ Technologies Used

- **MySQL**
- **phpMyAdmin / MySQL Workbench**
- **SQL**

---

## 🚀 How to Run

### 1. Create the database

```sql
CREATE DATABASE IF NOT EXISTS universitydb;
USE universitydb;
```

### 2. Create the tables

Create them in this project order:

```text
1. Students
2. Courses
3. Instructors
4. Enrollments
5. Departments
```

### 3. Insert the sample data

Run the `INSERT` statements from the project SQL file.

### 4. Add relationships

After all five tables exist, add the foreign keys with `ALTER TABLE`.

### 5. Run the SQL queries

The project contains examples of:

- CRUD
- Filtering with `WHERE`
- `INNER JOIN`
- `LEFT JOIN`
- `GROUP BY`
- `HAVING`
- Aggregate functions
- Subqueries
- `CONCAT()`
- `YEAR()`
- Window functions
- `CASE`
- Date calculations

---

## 🔎 SQL Concepts Demonstrated

### CRUD

```text
CREATE → INSERT
READ   → SELECT
UPDATE → UPDATE
DELETE → DELETE
```

### Aggregate Functions

```sql
COUNT()
AVG()
MAX()
```

### Useful SQL Functions

```sql
CONCAT()
YEAR()
DATE_SUB()
```

### Advanced SQL

```sql
JOIN
SUBQUERY
WINDOW FUNCTION
CASE
```

---

## 📋 Query Collection

The project demonstrates 16 practical tasks:

1. CRUD operations
2. Students enrolled after 2022
3. Courses from the Mathematics department
4. Courses with more than 5 students
5. Students enrolled in both SQL and Data Structures
6. Students enrolled in SQL or Data Structures
7. Average course credits
8. Maximum instructor salary in Computer Science
9. Student count by department
10. Student-course `INNER JOIN`
11. Student-course `LEFT JOIN`
12. Students in courses having more than 10 students
13. Extract enrollment year
14. Instructor full name
15. Running enrollment total
16. Senior/Junior classification using `CASE`

---

## 💡 Why This Project?

This project is designed to move beyond basic `SELECT` queries and demonstrate how SQL is used to solve practical database problems.

It is especially useful for practicing:

> **Database Design → Relationships → Data Manipulation → Data Analysis**

---

## 📁 Suggested Repository Structure

```text
UniversityDB/
│
├── README.md
│
├── universitydb.sql
│
└── screenshots/
    ├── database.png
    ├── tables.png
    └── queries.png
```

---

## 🎯 Learning Outcomes

After completing this project, you should be comfortable with:

- Creating relational databases
- Creating tables and defining primary keys
- Creating foreign-key relationships
- Inserting and modifying data
- Retrieving data with SQL
- Joining multiple tables
- Grouping and filtering aggregated data
- Writing subqueries
- Using date and string functions
- Using window functions
- Using conditional logic with `CASE`

---

## ✨ Project Highlight

> **One database. Five connected tables. Sixteen real-world SQL challenges.**

This project turns a simple university database into a complete SQL practice environment.

---

## 👤 Author

**UniversityDB SQL Project**

Built as a learning project to practice MySQL and relational database concepts.

---

## 📜 License

This project is intended for **educational and learning purposes**.
