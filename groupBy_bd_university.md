## 1
SELECT count(enrolment_date) AS qtà_iscritti, year(enrolment_date)
FROM students 
GROUP BY YEAR(enrolment_date);

## 2
SELECT teachers.office_address, count(*)
FROM teachers
GROUP BY teachers.office_address

## 3
SELECT count(*) AS id_appelli, ROUND(AVG(exam_student.vote), 2) AS media_voti
FROM exam_student
GROUP BY exam_student.exam_id