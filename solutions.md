||DOMANDE||

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

9. Inserire nella tabella degli studenti un nuovo record con i propri dati (per il campo
degree_id, inserire un valore casuale)

10. Cambiare il numero dell’ufficio del professor Pietro Rizzo in 126

11. Eliminare dalla tabella studenti il record creato precedentemente al punto 9

||RISPOSTE||

1. SELECT * FROM `students` WHERE YEAR(`date_of_birth`) = 1990; 

2. SELECT * FROM `courses` WHERE `cfu` > 10; 

3. SELECT * FROM `students` WHERE TIMESTAMPDIFF(YEAR, `date_of_birth`, CURDATE()) > 30;

4. SELECT * FROM `courses` WHERE `period` LIKE 'I semestre' AND `year` = 1;

5. SELECT * FROM `exams` WHERE `date` LIKE '2020-06-20' AND `hour` > '14:00:00';

6. SELECT * FROM `degrees` WHERE `level` LIKE 'magistrale'; 

7. SELECT COUNT(*) as `n_dipartimenti` FROM `departments`; 

8. SELECT COUNT(*) as `null_number` FROM `teachers` WHERE `phone` IS NULL; 

||BONUS||

9. INSERT INTO `students`(`degree_id`, `name`, `surname`, `date_of_birth`, `fiscal_code`, `enrolment_date`, `registration_number`, `email`) VALUES ('6','Wendigo','Fungi','2002-08-14','wndgfng08080808','2024-09-12','666','wendigo.notdisturbthefungi@forest.it'); 

10. UPDATE `teachers` SET office_number='126' WHERE `name` LIKE 'Pietro' AND `surname` LIKE 'Rizzo'; 

11. DELETE FROM `students` WHERE `email` LIKE 'wendigo.notdisturbthefungi@forest.it'; 


||DOMANDE CON GROUP BY||

1. Contare quanti iscritti ci sono stati ogni anno

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

3. Calcolare la media dei voti di ogni appello d'esame

4. Contare quanti corsi di laurea ci sono per ogni dipartimento

||RISPOSTE CON GROUP BY||

1.  SELECT COUNT(*) AS number_students, YEAR(`enrolment_date`) AS `entolment_year`
    FROM `students`
    GROUP BY YEAR(`enrolment_date`);

2.

3.

4.

||DOMANDE CON JOIN||

1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
Neuroscienze

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
nome

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

6. Selezionare tutti i docenti che insegnano nel Dipartimento di
Matematica (54)

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
per ogni esame, stampando anche il voto massimo. Successivamente,
filtrare i tentativi con voto minimo 18.

||RISPOSTE CON JOIN||

1.

2.

3.

4.

5.

6.

7. BONUS: