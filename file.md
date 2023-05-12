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

----1.---- Selezionare tutti gli studenti nati nel 1990 (160):

mysql> SELECT \* FROM students WHERE YEAR(date_of_birth) = 1990;

----2.---- Selezionare tutti i corsi che valgono più di 10 crediti (479):
SELECT \* FROM `courses` WHERE `credits` LIKE "> 10";

----3-----. Selezionare tutti gli studenti che hanno più di 30 anni
mysql> SELECT \*
-> FROM `students`
-> WHERE DATE_FORMAT(NOW(), '%Y') - DATE_FORMAT(birthdate, '%Y')
->

ERROR 1054 (42S22): Unknown column 'birthdate' in 'where clause'
mysql>

-----4----- Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
SELECT \* FROM courses WHERE semester = 1 AND year = 1;

---5---. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del
20/06/2020 (21)

----6----- Selezionare tutti i corsi di laurea magistrale (38)
SELECT \* FROM courses WHERE degree_id IN (SELECT id FROM degrees WHERE level = 'magistrale');

---7--- Da quanti dipartimenti è composta l'università? (12)
SELECT COUNT(DISTINCT department) FROM courses;

---8--- Quanti sono gli insegnanti che non hanno un numero di telefono? (50)
SELECT COUNT(\*) FROM teachers WHERE phone_number IS NULL;
