/\*

1. Contare quanti iscritti ci sono stati ogni anno

   SELECT YEAR(`enrolment_date`) AS `year`, COUNT(\*) AS `enrollment_count`
   FROM `students`
   GROUP BY YEAR(`enrolment_date`);

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

   SELECT `office_address`, COUNT(_) AS `teacher_count`
   FROM `teachers`
   GROUP BY `office_address`
   HAVING COUNT(_) > 1;

3. Calcolare la media dei voti di ogni appello d'esame

SELECT AVG(`exam_student`.`vote`) AS `average_vote`, `courses`.`name`, `degrees`.`name`
FROM `exam_student`
JOIN `exams` ON `exam_student`.`exam_id` = `exams`.`id`
JOIN `courses` ON `exams`.`course_id` = `courses`.`id`
JOIN `degrees` ON `courses`.`degree_id` = `degrees`.`id`
GROUP BY `courses`.`id`
ORDER BY `average_vote` DESC;

4. Contare quanti corsi di laurea ci sono per ogni dipartimento
   \*/
