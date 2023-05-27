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
##### 5. Students are enrolled in one year level at a time, and can move up to the next year level in the future. A year level could be kinder, grade 1,2,3 and so on.
- create a table name called "year_level"
- create a join table called "student_year_level" - **many to many relationship** - link student and year_level tables(one student can have many year levels, and one level can have many students
---
##### 6. Students are part of classes, and can be in more than one class at a time.
- create a table name called "class"
- create a join table called "student_class" - **many to many relationship** - link student and class tables(one student can have many clases, and one class can have many students
---
##### 7. A class has a subject, such as Sport, or Physics. A class subject may be a more general name for the junior years.
- create a table name called "subject"
- the relation between "subject" and "class" is **one to many**, one subject can have many classes
---
##### 8. Subject belong to departments.For example, Physics and Chemistry belong to the Science department.
- create a table name called "department"
- the relation between "department" and "subject" is **one to many**, one department can have many subjects
---
##### 9. A class is taught by a teacher,and teachers have names, genders and contact information
- create a table name called "teacher"
- the relation between "teacher" and "class" is **one to many**, one teacher can have many classes
---
##### 11. A class exsits for a term. There can be multiple classes in a year, and multiple classes within the same term(e.g. if there is a large number of English students and they need to split the class into two).
- add a new column in a "class" table called "term_id" to link term table
- the relation between "term" and "class" is **one to many**, one term can have many classes
---
##### 12. Classes are held in a classroom. A classroom can be a certain type of room, such as a gym or computer room or regular room. A classroom has a name that could include the location, and the capacity or number of students it can hold
- create a table name called "classroom"
- create a table name called "classroom_type"
- the relation between "classroom_type" and "classroom" is **one to many**, one classroom_type can have many classrooms
- the relation between "classroom" and "class" is **one to many**, one classroom can have many classes in a different times
---
##### 13. The time that a class occurs is called a period. There are a certain number of periods per day, and the periods are set for the entire school each year.
-  create a table name called "period"
-  the relation between "school_year" and "period" is **one to many** one school year can have many periods
---
##### 14. A class can occur over multiple periods, which could be two periods or up to the entire day
-  add two columns in to "class" table called "start_period_id" and "end_period_id"
---
##### 15. Students are garded based on their work in each class and given a score between 0 and 100. This score is stored for each class and a calculation is done to determine their overall socore for the year.
 - add a new columns in to "student_class" table called "score" - to get each score for each student 
 - add a new columns in to "student_year_level" table called "score" - to student of each school level and each school year
---
##### 16. The score can be matched to a letter grade. For example, a score of 0-50 means an "F", from 51 to 60 means a "D" and so on , up to 100.
- create a table name called "score_range"
- not related to any tables, it can be by joins or granter than or less operators 

