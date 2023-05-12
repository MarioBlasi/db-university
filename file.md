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

9. SELECT `departments`.`id`, `students`.`date_of_birth`, `courses`.`cfu`, `courses`.`period`, `exams`.`hour`, `teachers`.`phone`, `courses`.`degree_id`, `departments`.`head_of_department`
   FROM `departments`
   , `students`
   , `courses`
   LEFT JOIN `exams` ON `exams`.`course_id` = `courses`.`id`
   , `teachers`
   WHERE YEAR(students.date_of_birth) = 1990;

10.
