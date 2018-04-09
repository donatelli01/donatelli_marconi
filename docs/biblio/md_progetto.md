# BIBLIO
***
## DESCRIZIONE PROGETTO
Il progetto biblio prevede l'implementazione del sistema bibliotecario scolastico andando ad aggiungere nuove funzionalità che faciliteranno la gestione del processo.
Attualmente il sistema bibliotecario è accessibile da:

- apps.marconivr.it
- http://www.anobii.com/marconivr/profile
***
## IMPLEMENTAZIONI DA EFFETTUARE
#### 1 - APPLICAZIONE WEB
Una parte fondamentale del progetto prevede la creazione di un'applicazione web che eseguirà le funzionalità di **CRUD**(Create Read Update Delete) su un database MySQL il quale ricaverà i dati già esistenti effettuando un import dei dati esportati da SQL Server. 
La parte relativa alla visualizzazione dei dati resterà un'esclusiva di apps e di aNobii.
#### 2 - GESTIONE DEI DATI
Un'altra parte importante del progetto è quella relativa alla creazione di un processo **ETL** che terrà aggiornati i dati su cui opera il sistema bibliotecario, quindi sia l'applicazione che aNobii che la parte presente su apps dovranno poter utilizzare dati aggiornati.
### 3 - GESTIONE PRESTITI
Un'altra parte da tenere in considerazione è l'eventuale necessità di gestire i prestiti dei libri della biblioteca, quindi bisognerà attuare una serie di modifiche che favoriranno tale feature.
***
## CARATTERISTICHE MACCHINA VIRTUALE UTILIZZATA
Per lo sviluppo del progetto viene utilizzata una macchina virtuale Windows 7 a 64bit che presenta le seguenti caratteristiche:

- 2GB di RAM
- numero di processori: 2
- 32MB di memoria video

Per quanto riguarda i software installati sulla macchina quelli necessari sono:
- XAMPP
- Notepad++
- Python
