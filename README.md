# Database-design-of-school-management-system
Database design of a school management system-- Students can move to different year levels


#### Design app: **lucid.app**
- [Database design link](https://lucid.app/lucidchart/4a6e4e9a-f762-4ad0-8e10-a650465b0713/edit?beaconFlowId=0BDBC2A396664A3C&page=0_0&invitationId=inv_b1a1a729-c7da-4eab-865f-ccd5780a418b#)
- [Youtube tutorial](https://www.youtube.com/watch?v=7Ck8wSoKJXI](https://www.youtube.com/watch?v=1YPT6VH256w)

### Database requirements

##### 1. The school stores information about students: their names(first,last), gender, data of birth, and when they enrolled at the school
- create a table name called "student"
---


##### 2. We want to store information about parents, grandparents and other carers of students. A student can have many of these. Each of them has name and contact information, such as email and phone number
- create a table name called "guardian"
- the relation between "student" and "guardian" is **one to many**, one student can have many guardians
- create a table name called "guardian_type"to store the relationship of the student like mother or grangmonther
- create a join table called "student_guardian" - **many to many relationship** - link student and guardian and guardian_type tables
---

##### 3. Schools operate based on school years. A year has a start date and end date, and can be in a single calendar year or multiple calendar years
- create a table name called "school_year"
---
##### 4. A year has multiple terms, which have start and end dates. There is no specific number of terms that are required for a year.
- create a table name called "term"
---
