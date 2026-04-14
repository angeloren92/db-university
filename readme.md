Esercizio di oggi:
nome repo: db-university

Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una `università`:
sono presenti diversi `Dipartimenti` (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);,
ogni Dipartimento offre più `Corsi di Laurea` (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..),
ogni Corso di Laurea prevede diversi `Corsi` (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);,
ogni Corso può essere tenuto da diversi `Insegnanti`;,
ogni Corso prevede più `appelli d'Esame`;,
ogni Studente è iscritto ad un solo `Corso di Laurea`;,
ogni Studente può iscriversi a più `appelli di Esame`;,
per ogni appello d'Esame a cui lo `Studente` ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.,
Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

Utilizzare https://www.drawio.com/ per la creazione dello schema.
Esportare quindi il diagramma in png, caricarlo in un file html e pushare tutto nella repo.


# Tabelle
Dipartimenti
Corso di Laurea
Corsi
Insegnanti
Appelli Esame
Studenti

# Tabella: Dipartimenti
ID - INT, Primary Key, Auto Increment, unique, not null
nome - VarChar(50), not null
Indirizzo - VarChar(200) null
email - VarChar(100) null
telefono - Char(12) not null
descrizione - Text null

# Tabella: Corsi di Laurea
ID - INT, Auto Increment, unique, not null
dipartimento_ID - INT, unique, not null
nome - VarChar(100), not Null
descrizione - Text null

# Tabella: Studenti
ID - INT, Primary Key, Auto Incremenet, unique, not null
nome - VarChar(50), not null
cognome - VarChar(50), not null
matricola - VarChar(20), unique, not null
data di nascita - date, not null
email - VarChar(100) null
telefono - Char(12) null

# Tabella: Insegnanti
ID - INT, Primary Key, Auto Incremenet, unique, not null
nome - VarChar(50), not null
cognome - VarChar(50), not null
email - VarChar(100) not null

# Tabella: Corsi
ID - INT, Primary Key, Auto Incremenet, unique, not null
corso_di_laurea_ID - INT, unique, not null
nome - VarChar(100), not null
periodo - VarChar(50), not null 
cfu - TinyInt, not null

# Tabella: Appelli Esame
ID - INT, Primary Key, Auto Incremenet, unique, not null
corso_ID - INT, unique, not null
data - date, not null
aula - VarChar(20) not null

## Ponti

# Tabella: corso_insegnate
corso_ID
insegnante_ID

# Tabella: voti_esami
appello_ID
studente_ID
voto - tinyInt
stato - VarChar(20)