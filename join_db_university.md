## JOIN 1
SELECT degrees.name, students.*
FROM students 
JOIN degrees ON students.degree_id = degrees.id
WHERE degrees.name = 'Corso di Laurea in Economia';

## JOIN 2
SELECT departments.name, degrees.*
FROM departments
JOIN degrees ON departments.id = degrees.department_id
WHERE degrees.level = 'magistrale' 
AND departments.name = 'Dipartimento di Neuroscienze';

## JOIN 3
SELECT teachers.id, teachers.name, teachers.surname, courses.*
FROM teachers
JOIN course_teacher ON teachers.id = course_teacher.teacher_id
JOIN courses ON courses.id = course_teacher.course_id
WHERE teachers.name = 'Fulvio' AND teachers.surname = 'Amato';

## JOIN 4
SELECT students.id, students.surname, students.name, departments.name AS department_name, students.degree_id, degrees.name AS degrees_name
FROM students
JOIN degrees ON students.degree_id = degrees.id
JOIN departments ON degrees.department_id = departments.id
ORDER BY students.surname ASC, students.name ASC;

## JOIN 5
SELECT degrees.*, teachers.name AS teacher_name, teachers.surname AS teacher_surname, courses.name AS course_name 
FROM degrees
JOIN courses ON degrees.id = courses.degree_id
JOIN course_teacher ON courses.id = course_teacher.course_id
JOIN teachers ON course_teacher.teacher_id = teachers.id;

## JOIN 6
SELECT DISTINCT teachers.name, teachers.surname, departments.name AS nome_dipartimento
FROM teachers
JOIN course_teacher ON teachers.id = course_teacher.teacher_id
JOIN courses ON course_teacher.course_id = courses.id
JOIN degrees ON courses.degree_id = degrees.id
JOIN departments ON degrees.department_id = departments.id
WHERE departments.name = 'Dipartimento di Matematica'
ORDER BY teachers.name ASC;

## JOIN 7 tentativi e voto massimo
SELECT students.name, students.surname,  count(*) AS tentativi_sostenuti, max(exam_student.vote) AS voto_massimo
FROM students
JOIN exam_student ON students.id = exam_student.student_id
GROUP BY students.id;

## JOIN 7 tentativi con voto minimo 18
SELECT students.name, students.surname,  count(*) AS tentativi_con_voto_minimo
FROM students
JOIN exam_student ON students.id = exam_student.student_id
WHERE exam_student.vote >= 18
GROUP BY students.id;
