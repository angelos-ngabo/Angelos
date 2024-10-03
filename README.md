```sql
  
#SIMPLE Database for managing University system

Below is the management system of university

### Table


CREATE TABLE Departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(100) NOT NULL
);
CREATE TABLE Professors (
    professor_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    email VARCHAR(100),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES Departments(department_id)
);
CREATE TABLE Students (
    student_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    email VARCHAR(100),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES Departments(department_id)
);
CREATE TABLE Courses (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(100),
    department_id INT,
    professor_id INT,
    FOREIGN KEY (department_id) REFERENCES Departments(department_id),
    FOREIGN KEY (professor_id) REFERENCES Professors(professor_id)
);CREATE TABLE Enrollments (
    enrollment_id INT PRIMARY KEY,
    student_id INT,
    course_id INT,
    FOREIGN KEY (student_id) REFERENCES Students(student_id),
    FOREIGN KEY (course_id) REFERENCES Courses(course_id)
);
INSERT INTO Departments (department_id, department_name) VALUES (1, 'Computer Science');
INSERT INTO Departments (department_id, department_name) VALUES (2, 'Mathematics');
INSERT INTO Departments (department_id, department_name) VALUES (3, 'Physics');
INSERT INTO Professors (professor_id, first_name, last_name, email, department_id) VALUES (1, 'Alice', 'Johnson', 'alice.johnson@university.edu', 1);
INSERT INTO Professors (professor_id, first_name, last_name, email, department_id) VALUES (2, 'Bob', 'Smith', 'bob.smith@university.edu', 2);
INSERT INTO Professors (professor_id, first_name, last_name, email, department_id) VALUES (3, 'Carol', 'Davis', 'carol.davis@university.edu', 3);

INSERT INTO Students (student_id, first_name, last_name, email, department_id) VALUES (1, 'John', 'Doe', 'john.doe@student.edu', 1);
INSERT INTO Students (student_id, first_name, last_name, email, department_id) VALUES (2, 'Jane', 'Roe', 'jane.roe@student.edu', 1);
INSERT INTO Students (student_id, first_name, last_name, email, department_id) VALUES (3, 'Jim', 'Beam', 'jim.beam@student.edu', 2);
INSERT INTO Students (student_id, first_name, last_name, email, department_id) VALUES (4, 'Jill', 'Stone', 'jill.stone@student.edu', 2);
INSERT INTO Students (student_id, first_name, last_name, email, department_id) VALUES (5, 'Jack', 'White', 'jack.white@student.edu', 3);


INSERT INTO Enrollments (enrollment_id, student_id, course_id) VALUES (1, 1, 1);
INSERT INTO Enrollments (enrollment_id, student_id, course_id) VALUES (2, 2, 1);
INSERT INTO Enrollments (enrollment_id, student_id, course_id) VALUES (3, 3, 3);
INSERT INTO Enrollments (enrollment_id, student_id, course_id) VALUES (4, 4, 4);
INSERT INTO Enrollments (enrollment_id, student_id, course_id) VALUES (5, 5, 5);

SELECT Students.first_name, Students.last_name, Courses.course_name
FROM Students
JOIN Enrollments ON Students.student_id = Enrollments.student_id
JOIN Courses ON Enrollments.course_id = Courses.course_id;

UPDATE Students
SET email = 'john.d.newemail@student.edu'
WHERE student_id = 1;

DELETE FROM Courses WHERE course_id = 5;

commit;

Roll back
ignment.sql…]()
```
###COURSES
![1](https://github.com/user-attachments/assets/d737988c-59c9-4bf5-af28-85b45ce273d1)

###DEPARTMENTS
![2](https://github.com/user-attachments/assets/f8e806e9-dcc2-46a0-b894-8df87c3fea18)

###ENROLLMENTS
![3](https://github.com/user-attachments/assets/59550e09-0606-40ec-8e05-3993f93c738c)

###PROFFESORS
![4](https://github.com/user-attachments/assets/6113082e-eac9-4537-9b91-2eb8372ee81d)

###STUDENTS
![5](https://github.com/user-attachments/assets/4443127e-eebb-4e9a-8147-3cd18c4d42c4)






