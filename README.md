# Courses Registration System 

## Table of Contents
- [About The Project](#about-the-project)
- [Key Features](#key-features)
- [Built With](#built-with)
- [Project Timeline & Team](#project-timeline--team)
- [Contribution & My Role](#contribution--my-role)

---

## About The Project

The **Courses Registration System** is a console application developed as the final project for the **Data Structures** course at the **Faculty of Computer and Information Sciences, Ain Shams University**.

The system serves as a functional prototype for course management, enabling **Students** to register and track grades, and **Administrators** to manage course data and prerequisites. The project was evaluated primarily on the **optimal selection and implementation of advanced Data Structures** (such as Hash Maps, Queues, Linked Lists, Sets and Vectors) to ensure efficiency and maintainability, particularly for validating complex course dependencies.

---

## Key Features

The application provides a dual-interface model (Admin/Student) with critical functionalities:

### Student Functionalities
* **Course Registration:** Secure enrollment after checking course availability and satisfying prerequisites.
* **Academic Tracking:** Ability to view detailed **historical grades** and check **Overall GPA**.
* **Prerequisites Check:** Clear verification of required antecedent courses.
* **Report Generation:** Creating a printable report of the student's academic progress.

### Administrator Functionalities
* **Course Catalog Management:** Uploading and updating detailed course descriptions (Title, Syllabus, Credit Hours, Instructor).
* **Prerequisite Definition:** Defining and managing the **prerequisite dependency chains** to strictly enforce registration rules.
* **Grades Management:** Centralized system for uploading and managing student grades.

---

## Built With

The entire system was built using efficient and memory-safe C++ features, demonstrating strong foundational programming skills and understanding of data management principles.

* **Primary Language:** C++ (Standard Library)
* **Development Tool:** GCC/G++ Compiler
* **Key Data Structures Used:**
    * **`std::unordered_map` / `std::set`:** Used for **O(1) average time complexity** lookups, essential for Admin sign-in and checking the existence of course titles (demonstrated in `isValidPrerequisites`).
    * **`std::vector`:** Utilized for dynamic storage and sequential iteration, such as storing the main list of courses (`dm.courses`).
    * **Graph/Adjacency List Concept:** (Implicitly or explicitly) used to model the **course prerequisite dependencies** for efficient traversal and cycle detection (Crucial for the `SetPrerequisites` logic).

---

## Project Timeline & Team

This was a focused, short-term academic project showcasing rapid development and collaborative problem-solving.

* **Development Period:** 24 March – 21 May 2024
* **Team Size:** **7 Developers**
* **Context:** Course Project for Data Structures (Computer Science, Ain Shams University)

---

## Contribution & My Role

My primary focus was on implementing the robust course management logic, specifically guaranteeing data integrity and relationship modeling within the Administrator's domain.

### Key Deliverables: Admin Course Management

I was responsible for the core functions handling course data upload and prerequisite setting, which are vital for the system's compliance.

| Function Implemented | Technical Description / Role Focus |
| :--- | :--- |
| **`UploadCourse()`** | Handles validation (non-empty fields, positive credit hours) and **uniqueness checking** (`dm.courseTitles.find(title)`). Ensures safe data insertion (`dm.courses.push_back`) and persistent storage (`dm.writeCourses`). |
| **`SetPrerequisites()`** | Implements the core logic for **defining course dependencies**. Uses `std::find_if` to locate the course and calls validation checks. Focus was on correctly updating the dependency field (`it->prerequisites`). |
| **`isValidPrerequisites()`** | A critical validation function. **Utilizes `std::stringstream` and fast lookup operations** (`dm.courseTitles.find(prereq)`) to ensure that all courses listed as prerequisites actually exist in the system, preventing broken dependencies. |
| **`ShowCourses()`** | Manages clean, formatted output using `std::stringstream` to display the entire course catalog to the administrator. |

---
