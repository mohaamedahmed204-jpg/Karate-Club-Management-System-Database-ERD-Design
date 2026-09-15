# 🥋 Karate Club Management System (Database & ERD Design)

![Database](https://img.shields.io/badge/Database-SQL%20Server-blue)
![Modelling](https://img.shields.io/badge/Design-Draw.io-orange)
![License](https://img.shields.io/badge/License-MIT-green)

A comprehensive relational database design and architectural model for managing a **Karate Club System**. It covers member registration, instructor assignments, subscription tracking, belt rank testing, and financial transaction management.

The database model was developed and structured using **Draw.io**, adhering strictly to **3NF Normalization** principles to ensure data integrity and eliminate data redundancy.

---

## 📌 1. Overview

The **Karate Club Management System** aims to digitize and streamline administrative operations within martial arts clubs. 

The system tracks member enrollments and membership renewals, manages instructor details and qualifications, monitors belt rank promotions and testing evaluations, and handles recurring and one-time financial payments.

---

## ⚙️ 2. Core Operations

The database design handles key operational modules:

### 👤 Member & Instructor Management
* **Person Entity (`Person`):** Stores common demographic data (Name, Phone, Email, Address) in a central table using the `Inheritance / Is-A` relational concept.
* **Members (`Members`):** Extends person records for club members, capturing emergency contact details (`Emergency Contact`).
* **Instructors (`Instructors`):** Extends person records for trainers, recording their coaching qualifications and specialties (`Qualifications`).
* **Member-Instructor Assignment (`MemberInstructor`):** A junction table mapping members to their designated instructors.

### 💳 Subscriptions & Payments
* **Subscriptions (`Memberships`):** Manages active membership durations (`StartDate`, `EndDate`) and connects them to pricing models (`SubscriptionPeriod`).
* **Payment Status (`IsPaid`):** Tracks subscription payment statuses.
* **Financial Transactions (`Payments`):** Records financial transactions, linking payments to either membership renewals or belt testing fees (`TestFees`).

### 🥋 Belt Rank & Testing System
* **Belt Ranks (`BeltRanks`):** Defines rank tiers (White, Yellow, Orange, Green, Black, etc.) along with associated testing fees.
* **Rank Tests (`BeltRankTests`):** Records belt promotion exams, test dates, candidate members, evaluating instructors (`TestedByInstructorID`), and final test results (`Result`).

---

## 🎯 3. Key Concepts Demonstrated

* **Inheritance / IS-A Relationship:** Implemented Supertype/Subtype mapping where `Person` acts as the primary base entity inherited by `Member` and `Instructor`.
* **Database Normalization:** Normalized up to **3rd Normal Form (3NF)** to ensure logical data organization and eliminate update anomalies.
* **Referential Integrity:** Enforced strict primary-foreign key constraints (`PK-FK`) to maintain data validity across relational tables.
* **Optimized Data Types:** Selected appropriate data types (e.g., `nvarchar` for Unicode text, `decimal(10,2)` for monetary values, `bit` for status flags).

---

## 📐 4. Architecture & Design

The system architecture was constructed across two key phases:

1. **Entity-Relationship Diagram (ERD):**
   * Identified primary entities, attributes, primary keys, and relationships (`1:1`, `1:N`, `M:N`).
2. **Relational Schema:**
   * Converted ERD concepts into concrete database tables.
   * Resolved Many-to-Many (`M:N`) relationships using associative/junction tables (e.g., `MemberInstructor`).

---

## 🛠️ 5. Technologies & Tools

* **Draw.io:** Used for designing the **ERD** and **Relational Schema** diagrams.
* **Microsoft SQL Server (T-SQL):** Used for database implementation, script generation, and testing (`.mdf` / `.bak`).
* **Git & GitHub:** Used for project version control and repository management.

---

## 📁 Project Files

* `KarateClub_ERD.drawio` – Entity-Relationship Diagram file.
* `KarateClub_RelationalSchema.drawio` – Relational Database Schema diagram.
* `KarateClub_Database.mdf / .bak` – Database data and backup files for testing and deployment.

---


## 👨‍🏫 Instructor

Dr. Mohammed Abu-Hadhoud.
Founder & Instructor — Programming Advices

Programming Advices
https://programmingadvices.com
