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
#### City Fitness Club Management
<img width="1015" height="830" alt="image" src="https://github.com/user-attachments/assets/9f1d15ab-2dd3-4387-abca-3361bf0c11ee" />

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
| LOGIN|	login_id (PK), login_username, login_password| Stores user login details.|
| USER |	user_id (PK), user_mobile | user_mail	General user information.|
| ROLES |	role_id (PK), role_name, role_desc	|Defines user roles.|
| PERMISSION |	per_id (PK), per_name, per_module	| Permissions linked to roles.|
| MEMBER |	mem_id (PK), mem_name, mem_add, user_id (FK)	| A user can be a member.|
| GYM	| gym_id (PK), gym_type, gym_desc	| Gym details.|
| PAYMENT |	pay_id (PK), pay_cus_id, pay_amt, mem_id (FK), gym_id (FK)	|Payment transactions.|
| TRAINER |	trn_id (PK), trn_name, trn_add	| Trainer details.|

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
| USER – LOGIN	|1:1|	Total|	Each user must have one login.|
|USER – ROLES (HAS)|	M:N|	Partial|	A user can have multiple roles; roles can belong to multiple users.|
|ROLES – PERMISSION|	1:N|	Partial	|A role can have multiple permissions, but each permission belongs to one role.|
|USER – MEMBER|	1:1|	Partial|	A user may also be a member.|
|MEMBER – GYM (HAS)|	M:N|	Partial|	A member can be associated with many gyms, and a gym can have many members.|
|MEMBER – PAYMENT	|1:N|	Total|	A member can make multiple payments.|
|PAYMENT – GYM|	N:1	|Total|	Payment is made for a particular gym.|
|USER – TRAINER (MANAGE)|	1:N|	Partial|	A user (admin) manages many trainers.|
|TRAINER – PAYMENT (via MANAGE)|	1:N|	Partial|	Trainers are linked to payments indirectly.|

### Assumptions
- Each user has exactly one login credential (no shared accounts).
- A user may or may not be a member (staff vs. customer).
- Payments are linked to members and gyms, not directly to trainers.
- A gym can have multiple members and trainers.
- Roles and permissions are flexible (supporting M:N mappings).

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
![ER Diagram](er_diagram_library.png)

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
- 
- 
- 

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
![ER Diagram](er_diagram_restaurant.png)

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
- 
- 
- 

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
