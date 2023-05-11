//Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:

- sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi Insegnanti;
- ogni Corso prevede più appelli d'Esame;
- ogni Studente è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.
  Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni.
  Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

## data types:

- strings:

  - varchar(number) limite 255 caratteri,
  - char(number) \\
  - text 65.535 caratteri usato descrizione prodotto,
  - MediumTEXT 16MB
  - longtext 4.2GB usato per salvare porzioni HTML o lunghi testi

- numbers:

  - tinyint ( usa solo 1BYTE num da -128 a 127 boolean),
  - small/medium int ( occupano 2 E 3 BYTE),
  - int ( BYTE da MENO a PIU' 2 milioni),
  - bigint ( il DOPPIO di INT)

- decimals: float(i, d), double(i,d), decimal(i, d)

- dates: DATETIME (YYYY--MM-GG HH:II:SS), DATE, YEAR, TIME, TIMESTAMP ---> date nel database - tipi di dato per le date

## Attributes

- PK (PRIMARY KEY)
- AI (AUTO_INCREMENT)
- NULL (che il campo può essere lasciato vuoto e quindi non contiene alcun valore.)
- NOT NULL ( deve essere riempito non puó essere lasciato vuoto)
- DEFAULT ( setta il valore alla colonna qualora non ci fosse nessun valore)
- AUTO_INCREMENT (incrementa di +1 usato colonne tipo numero per gli ID )
- UNIQUE ( valore unico NO ripetizioni all'interno colonna)
- NULLABLE (non tutte i dati posso avere descrizione)

//-----------------------------------//

# Database tabella

1 Un Dipartimento offre molti Corsi di Laurea (relazione uno-a-molti).
2 Un Corso di Laurea può essere offerto da un solo Dipartimento (relazione molti-a-uno).
3 Un Corso di Laurea prevede molti Corsi (relazione uno-a-molti).
4 Un Corso può essere tenuto da molti Insegnanti, e un Insegnante può insegnare molti Corsi (relazione molti-a-molti).
5 Un Corso prevede molti appelli di Esame (relazione uno-a-molti).
6 Uno Studente è iscritto ad un solo Corso di Laurea, ma un Corso di Laurea può avere molti Studenti iscritti (relazione uno-a-molti).
7 Uno Studente può iscriversi a molti appelli di Esame, e un appello di Esame può avere molti Studenti iscritti (relazione molti-a-molti).

## Entity name:

## Table name:

## Table columns

- Dipartimenti
- Corsi di Laurea
- Corsi
- Insegnanti
- Appelli di Esame
- Studenti
- Iscrizioni
- Esami

| Dipartimenti: id_dipartimento (int, chiave primaria), nome_dipartimento (varchar)

| Corsi di Laurea: id_corso_laurea (int, chiave primaria), nome_corso_laurea  
 (varchar),id_dipartimento (int, chiave esterna verso Dipartimenti)

| Corsi: id_corso (int, chiave primaria), nome_corso (varchar), id_corso_laurea (int, chiave esterna verso Corsi di Laurea), id_insegnante (int, chiave esterna verso Insegnanti)

|Insegnanti: id_insegnante (int, chiave primaria), nome_insegnante (varchar), cognome_insegnante (varchar)

| Appelli di Esame: id_appello (int, chiave primaria), data_appello (date), id_corso (int, chiave esterna verso Corsi)

| Studenti: id_studente (int, chiave primaria), nome_studente (varchar), cognome_studente (varchar), id_corso_laurea (int, chiave esterna verso Corsi di Laurea)

| Iscrizioni: id_iscrizione (int, chiave primaria), id_studente (int, chiave esterna verso Studenti), id_appello (int, chiave esterna verso Appelli di Esame)

| Esami: id_esame (int, chiave primaria), voto (int), id_iscrizione (int, chiave esterna verso Iscrizioni)
