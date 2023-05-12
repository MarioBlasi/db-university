1. Selezionare tutti gli studenti nati nel 1990 (160)
2. Selezionare tutti i corsi che valgono più di 10 crediti (479)
3. Selezionare tutti gli studenti che hanno più di 30 anni
4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di
   laurea (286)
5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
   20/06/2020 (21)
6. Selezionare tutti i corsi di laurea magistrale (38)
7. Da quanti dipartimenti è composta l'università? (12)
8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

SELECT `departments`.`id`, `courses`.`degree_id`, `teachers`.`id`, `course_teacher`.`teacher_id`, `students`.`id`, `exams`.`course_id`, `exam_student`.`exam_id`
FROM `departments`
, `courses`
, `teachers`
LEFT JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id`
, `students`
LEFT JOIN `exams` ON `exams`.`course_id` = `courses`.`id`
LEFT JOIN `exam_student` ON `exam_student`.`exam_id` = `exams`.`id`;
