## CONSEGNA 
Modellare la struttura di un database per memorizzare tutti i dati riguardanti una università:
sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
ogni Corso può essere tenuto da diversi Insegnanti;
ogni Corso prevede più appelli d'Esame;
ogni Studente è iscritto ad un solo Corso di Laurea;
ogni Studente può iscriversi a più appelli di Esame;
per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente. Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

## TABELLE 
 - dipartimenti
 - corsi_laurea
 - corsi
 - insegnanti
 - esami
 - studenti
 



 # DIPARTIMENTI
 - ID BIGINT - AI - PK
 - NOME | VARCHAR(240) - NOT NULL
 - INDIRIZZO | VARCHAR (20)

 # CORSI_LAUREA
 - ID BIGINT - AI - PK 
 - NOME | VARCHAR(240) - NOT NULL
 - ID_DIPARTIMENTO | BIGINT

 # CORSI
 - ID BIGINT  - AI - PK
 - NOME | VARCHAR(240) - NOT NULL
 - CREDITI | INT - NOT NULL
 - ID_CORSO_LAUREA | BIGINT

 # INSEGNANTI
 - ID BIGINT -  AI - PK
 - NOME | VARCHAR(15) - NOT NULL
 - COGNOME | VARCHAR(15) - NOT NULL
 - EMAIL | VARCHAR(25) - NOT NULL
 - NUMERO_TELEFONO  | VARCHAR(13) - NOT NULL

 # ESAMI
 - ID BIGINT - AI - PK
 - CORSO_ID | BIGINT 
 - DATA | DATE - NOT NULL 
 - TIPOLOGIA | VARCHAR(50)
 - ID_INSEGNANTE | BIGINT 
 - VOTO | TINYNT - NOT NULL

 # STUDENTI
 - ID BIGINT - AI - PK
 - NOME | VARCHAR(15) - NOT NULL
 - COGNOME | VARCHAR(15) - NOT NULL
 - NUMERO_TELEFONO | VARCHAR(13) - NOT NULL
 - EMAIL | TEXT - NOT NULL
 - ID_CORSO_LAUREA | BIGINT 

 