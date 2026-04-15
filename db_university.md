# 1
SELECT * FROM students
WHERE date_of_birth BETWEEN '1990-01-01' AND '1990-12-31';
  
# 2
SELECT * FROM courses
WHERE cfu > 10;

# 3
SELECT * FROM students
WHERE date_of_birth <= DATE_SUB(CURDATE(), INTERVAL 30 YEAR);

# 4
SELECT * FROM courses
WHERE period = 'I semestre' AND year = 1;

# 5
SELECT * FROM exams
WHERE date = '2020-06-20' and hour >= '14:00';






 # 7
SELECT * FROM degrees
WHERE level = 'Magistrale';

# 8
SELECT * FROM teachers
WHERE phone IS NULL;