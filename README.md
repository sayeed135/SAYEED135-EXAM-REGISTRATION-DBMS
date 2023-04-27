CREATE TABLE students (
student_id INT PRIMARY KEY,
student_name VARCHAR(255) NOT NULL,
student_email VARCHAR(255) NOT NULL,
ssn VARCHAR(9) UNIQUE,
student_phone VARCHAR(20) NOT NULL,
student_address VARCHAR(255) NOT NULL
);
CREATE TABLE exams (
exam_id INT PRIMARY KEY,
exam_name VARCHAR(255) NOT NULL,
exam_date DATE NOT NULL, exam_time
TIME NOT NULL, exam_duration INT
NOT NULL
);
CREATE TABLE exam_registrations ( 
registration_id INT PRIMARY KEY,
exam_id INT NOT NULL,
student_id INT NOT NULL,
registration_date DATE NOT NULL,
 registration_time TIME NOT NULL,
FOREIGN KEY (exam_id) REFERENCES exams(exam_id),
 FOREIGN KEY (student_id) REFERENCES students(student_id)
);

CREATE TABLE courses 
( course_id INT PRIMARY KEY,
course_name VARCHAR(255) NOT NULL,
 instructor_id INT NOT NULL,
 instructor_name VARCHAR(255) NOT NULL,
 instructor_phone VARCHAR(20) NOT NULL,
 duration VARCHAR(20) NOT NULL
);
INSERT INTO students (student_id, student_name, student_email,ssn,student_phone, student_address)
VALUES (1, 'Sayeed', 'sayeed.m@example.com', 'CS032','9177133972', 'Vijayawada'), (2, 'obul', 'obul.d@example.com', 'CS062', '9676197135', 'Chilakaluripet'),
(3, 'Mahesh Reddy', 'mahesh.s@example.com','CS056', '9765435672', 'Guntur'),
(4, 'Akhil' , 'akhil.j@example.com','CS08', '9985450118', 'Guntur');
INSERT INTO exams (exam_id, exam_name, exam_date, exam_time, exam_duration)
VALUES (121, 'Mathematics', '2023-05-15', '09:00:00', 180),
(221, 'Physics', '2023-05-17' , '09:00:00' , 200),
(321, 'Chemistry', '2023-05-20' , '09:00:00' , 120),
(421, 'French' , '2023-05-21' , '10:00:00' ,180);
INSERT INTO exam_registrations (registration_id, exam_id, student_id, registration_date, registration_time)
VALUES (1, 121, 1, '2023-04-20', '12:30:00'),
(2, 221, 2, '2023-04-21', '01:00:00'),
(3, 321, 3, '2023-04-22', '12:00:00'),
(4, 421, 4, '2023-04-22', '12:15:00');
INSERT INTO courses (course_id, course_name, instructor_id, instructor_name, instructor_phone, duration)
VALUES (101, 'Introduction to calculus and linear algebra', 1234, 'John Smith', '555-1234',
‘60Days’),
(205, 'Introduction to Computer Science', 9112, 'Dr. Alice Brown','522-6162',
‘45Days’),
(303, 'A course in writing and critical thinking', 6534,'Professor Jane Doe', '644-8769',
‘50Days’),
(309, 'A course in Writing and Reading Paragraphs', 7657, 'Professor Ramalingam', '786- 9876', ‘45Days’);
