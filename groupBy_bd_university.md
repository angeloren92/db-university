## 1
SELECT count(enrolment_date) AS qtà_iscritti, year(enrolment_date)
FROM students 
GROUP BY YEAR(enrolment_date);

## 2
SELECT teachers.office_address, count(*)
FROM teachers
GROUP BY teachers.office_address