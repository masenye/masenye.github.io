# 🎓 Student Project Portfolio - Botho University

![Status](https://img.shields.io/badge/status-active-success)
![Year](https://img.shields.io/badge/Year-3rd-blue)
![University](https://img.shields.io/badge/Botho%20University-Software%20Engineering-red)
![Skills](https://img.shields.io/badge/Skills-.NET%20%7C%20Java%20%7C%20Web%20Dev-orange)

---

## 📋 Project Information

| **Category** | **Details** |
|--------------|-------------|
| **Student Name** | [Katleho masenye] |
| **University** | Botho University |
| **Program** | Bachelor of Science in computing(Software Engineering) |
| **Year of Study** | 3rd Year 
| **Course Name** | [Software Engineering] |
| **Semester** | [Semester, 7, 2026] |
| **Project Title** | [bothoclinicmanagement] |

---

## 📖 Project Overview

This project was developed as part of my 3rd-year Software Engineering curriculum at Botho University. It demonstrates the integration of multiple technical and management skills acquired throughout my academic journey.

### 🎯 Purpose
[Write 2-3 sentences explaining what this project does and why it was created]

**Example:** *"This Student Management System was developed to streamline academic record-keeping. It allows administrators to manage student profiles, course registrations, and generate transcripts, demonstrating practical application of database connectivity and OOP principles."*

---

## 🛠️ Skills Demonstrated

### Technical Skills

| **Skill Area** | **Technologies Used** | **Level** |
|----------------|----------------------|-----------|
| **.NET Framework** | C#, ASP.NET, ADO.NET | Advanced |
| **Object-Oriented Programming** | Classes, Inheritance, Polymorphism, Encapsulation | Advanced |
| **Java Development** | Core Java, Swing, JDBC | Advanced |
| **Advanced Java** | Multithreading, Collections, Lambda Expressions | Intermediate |
| **Web Development** | HTML5, CSS3, JavaScript, Bootstrap | Intermediate |
| **Database Connectivity** | JDBC, ADO.NET, MySQL, SQL Server | Advanced |
| **Project Management** | Gantt Charts, Risk Assessment, Stakeholder Analysis | Intermediate |
| **Software Engineering** | SDLC, UML, Design Patterns, Testing | Intermediate |

### Professional Skills

| **Skill** | **Evidence in Project** |
|-----------|-------------------------|
| 📢 **Communication** | Clear documentation, comments, and user manuals |
| 📊 **Presentation** | Professional project demos and reports |
| 📝 **Documentation** | Comprehensive SRS, technical specs, and user guides |
| 🔍 **Research** | Analysis of existing solutions and best practices |
| 🤝 **Collaboration** | Team coordination and version control |
| 📋 **Quality Standards** | Code reviews, testing, and error handling |
| ⏰ **Time Management** | Meeting deadlines with Gantt chart tracking |

---



### Technical Implementation
- ✅ Object-Oriented Design with proper class hierarchy
- ✅ Database integration with CRUD operations
- ✅ User authentication and authorization
- ✅ Input validation and error handling
- ✅ Professional UI/UX design
- ✅ Comprehensive documentation

### Project Management Artifacts
- 📅 Project timeline with milestones
- 📊 Risk assessment matrix
- 👥 Stakeholder analysis
- 📈 Work Breakdown Structure (WBS)
- 🔄 Change management process

---

## 🗄️ Database Design

### Entity Relationship Diagram

```sql
-- Sample Database Schema

-- Users Table
CREATE TABLE Users (
    UserID INT PRIMARY KEY AUTO_INCREMENT,
    Username VARCHAR(50) NOT NULL UNIQUE,
    PasswordHash VARCHAR(255) NOT NULL,
    Email VARCHAR(100) NOT NULL,
    FullName VARCHAR(100) NOT NULL,
    Role ENUM('Admin', 'User', 'Manager') DEFAULT 'User',
    CreatedDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Projects Table
CREATE TABLE Projects (
    ProjectID INT PRIMARY KEY AUTO_INCREMENT,
    ProjectName VARCHAR(200) NOT NULL,
    Description TEXT,
    StartDate DATE,
    EndDate DATE,
    Status ENUM('Planning', 'Active', 'Completed', 'OnHold') DEFAULT 'Planning',
    UserID INT,
    FOREIGN KEY (UserID) REFERENCES Users(UserID)
);

-- Tasks Table
CREATE TABLE Tasks (
    TaskID INT PRIMARY KEY AUTO_INCREMENT,
    TaskName VARCHAR(200) NOT NULL,
    Description TEXT,
    Priority ENUM('Low', 'Medium', 'High', 'Critical') DEFAULT 'Medium',
    DueDate DATE,
    Status ENUM('Pending', 'InProgress', 'Completed') DEFAULT 'Pending',
    ProjectID INT,
    AssignedTo INT,
    FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID),
    FOREIGN KEY (AssignedTo) REFERENCES Users(UserID)
);

-- Sample Data
INSERT INTO Users (Username, PasswordHash, Email, FullName, Role) VALUES
('admin', 'hashed_password', 'admin@bothouniversity.ac.bw', 'System Admin', 'Admin'),
('jdoe', 'hashed_password', 'john.doe@email.com', 'John Doe', 'User');
