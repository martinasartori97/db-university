# GROUP BY:
1  Contare quanti iscritti ci sono stati ogni anno
2  Contare gli insegnanti che hanno l'ufficio nello stesso edificio
3  Calcolare la media dei voti di ogni appello d'esame
4  Contare quanti corsi di laurea ci sono per ogni dipartimento

# RESULTS:
1:
SELECT YEAR(`enrolment_date`) AS `year`, COUNT(`id`) AS `registration_number`
FROM `students`
GROUP BY YEAR(`enrolment_date`)
ORDER BY `year`;

2:
SELECT `office_address`, COUNT(*) AS `teacher_count`
FROM `teachers`
GROUP BY `office_address`;

3:
SELECT AVG(`vote`) AS `average_vote`, `exam_id`
FROM `exam_student`
GROUP BY `exam_id`;

4:
SELECT `department_id`, COUNT(*) AS `total_degree`
FROM `degrees`
GROUP BY `department_id`;





# JOIN:
1  Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
2  Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
3  Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
4  Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
5  Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
6  Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

# RESULTS
1:
SELECT `students`.*,
`degrees`.`name` AS `degree_name`
FROM `students`
JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';

2:
SELECT `degrees`.*
FROM `degrees`
JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
WHERE `degrees`.`level` = 'Magistrale'
AND `departments`.`name` = 'Dipartimento di Neuroscienze'

3:
SELECT `courses`.`name` AS `Nome Corso`
FROM `courses`
JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
WHERE `teachers`.`id` = '44'

4:
SELECT `students`.*, `departments`.`name` AS `nome_dipartimento`, `degrees`.`name` AS `corsi di larurea`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id` 
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
ORDER BY `students`.`surname` ASC

5:














