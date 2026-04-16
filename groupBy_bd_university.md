## 1
SELECT count(enrolment_date) AS qtà_iscritti, year(enrolment_date)
FROM students 
GROUP BY YEAR(enrolment_date);

