SELECT * FROM students
WHERE date_of_birth >= '1990-01-01' 
  AND date_of_birth <= '1990-12-31';
  
SELECT * FROM courses
WHERE cfu > '10';

SELECT * FROM students
WHERE date_of_birth <= '1995-04-15';

SELECT * FROM courses
WHERE period = 'I semestre' AND year = 1;

SELECT * FROM exams
WHERE date = '2020-06-20' and hour >= '14:00';

SELECT * FROM exams
WHERE date = '2020-06-20' and hour >= '14:00';

SELECT * FROM degrees
WHERE level = 'Magistrale';

SELECT * FROM departments;

SELECT * FROM teachers
WHERE phone IS NULL;