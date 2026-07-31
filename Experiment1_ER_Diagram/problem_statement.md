# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
*Paste or attach your diagram here*  
<img width="893" height="495" alt="Screenshot 2026-07-31 103754" src="https://github.com/user-attachments/assets/23e7e351-283f-4389-a289-d7f3bbc8f60c" />


### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|  Trainer      |     trainer_id (PK), name, specialization, phone_no               |  Represents trainers who conduct fitness programs.     |
|   Program     | program_id (PK), name, category                   |   Defines the fitness programs offered.    |
|   Member     |     member_id (PK), name, email, member_type               |  Represents registered gym members.     |
|     Session   |  session_id (PK), session_time, session_type                  |    Represents personal training sessions.   |
|     Attendance   |       attendance_id (PK), date, status             |   Stores attendance details for each session.    |
|Payment          |payment_id (PK), member_id (FK), payment_type         |Stores payment details of members.|


### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|   Trainer – Program           |  M:N          |     Mandatory	          |    A trainer teaches multiple programs, and a program may be taught by multiple trainers.   |
|  Member – Program            |     M:N       |     Optional          |    A member may join multiple programs.   |
|  Trainer – Session            |   1:M         |        Mandatory       |    One trainer handles many sessions.   |
|  Member – Session            |   1:M         |    Optional           |   A member can book multiple sessions.    |
|   Session – Attendance           |   1:M         |    Mandatory           |  Every session has attendance records.     |
|  Member – Payment            |    1:M        |     Mandatory	          |   A member can make multiple payments.    |

### Assumptions
- Every trainer can teach one or more programs.
- Members may join multiple fitness programs.
- Attendance is recorded for every session
Payments are made only by registered members.

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
<img width="870" height="502" alt="Screenshot 2026-07-31 103809" src="https://github.com/user-attachments/assets/1fb1f5b1-583a-4c47-859c-5c0f96ca0626" />

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|  Trainer      |  trainer_id (PK), name, specialization, phone_no                  |     Represents trainers who conduct fitness programs.  |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- Only registered members can borrow books.
- Members may register for multiple events.
- Members may register for multiple events.
A book can be borrowed many times at different periods.
---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
<img width="900" height="456" alt="Screenshot 2026-07-31 103830" src="https://github.com/user-attachments/assets/e78ed3fe-1cd5-42f8-a5a5-5ec0904686a9" />


### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- Only customers can make reservations.
- Every reservation is served by one waiter
- Multiple dishes can be included in a single order.

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
