## UDA: Analisi dati e processo di ETL

### Destinatari :
Alunni classe quinta di informatica
 
Alunni classe quarta di Telecomunicazioni

### Tempi: 
15-20 ore

### Discipline coinvolte:
Informatica, Sistemi

### Prodotti: 
Creazione di una base di dati normalizzata popolata con i dati filtrati da un file .csv o XML (es: dati MIUR)

## Competenze

###1) Modellare una realtà

#### Evidenza:
Capacità di analisi 
#### Abilità:
- Analizzare tracciati record 
- Progettare una base di dati
- Creare una base di dati
- Popolare la base di dati


#### Conoscenze:
- File in formato open 
- Concetto di normalizzazione 
- Nozioni di base su Data Base e DBMS
- Concetti di tabella, chiave, indice, dominio, associazione, integrità referenziale
- Data Modeler per la progettazione concettuale
- Data Modeler per la progettazione logica e fisica (DDL)
- Linguaggio Java per la lettura e scrittura di file e istruzione SQL per l’inserimento dei dati

### 2) Documentare	

#### Evidenza:
Documentazione del processo e del codice: organizzazione del documento, linguaggio utilizzato

#### Abilità:
Documentare: 

- le fasi di lavoro
- le lezioni (appunti e foto alla lavagna)
- il codice
- 
#### Conoscenze:
Strumenti di scrittura (Word, markdownPad)

### 3) Relazionare

#### Evidenza:
Linguaggio utilizzato, rispetto dei tempi di esposizione, modalità di presentazione

#### Abilità:
Presentare le attività ed il prodotto finito

#### Conoscenze:
Strumenti di presentazione (Power Point o simili)

## Fasi di applicazione

Fase 1: Informazioni teoriche sul concetto di data base (attraverso dialogo guidato)

Fase 2: Analisi del tracciato record e individuazione delle entità (processo di normalizzazione)

Fase 3: La progettazione concettuale usando Data Modeler (esempi a complessità crescente per spiegare le fasi di progettazione e le relazioni fra entità)

Fase 4: La progettazione logica e fisica usando Data Modeler per (si introducono i concetti tabella, dominio, PK FK, DDL)

Fase 5: Creazione fisica del DB 

Fase 6: Processo di ETL per l’inserimento dei dati nel data base 

Fase 7: Documentare


### Esperienze attivate ossia cosa fa l’allievo

- Analisi del tracciato record con i compagni e confronto delle soluzioni proposte
- Realizzazione del modello con Data Modeler (in laboratorio attività singola) 
- Creazione del data base in My SQL
- Estrazione dei dati da file e inserimento nel DB e creazione dei file di log e di errori

### Metodologia
I docenti

- guidano la classe nella discussione, fornisce materiale (filmati prodotti dal docente, documenti ecc.)
- propongono esercizi propedeutici
- preparano l’ambiente di lavoro in laboratorio

## LA CONSEGNA AGLI STUDENTI

#### Titolo UdA
Analisi dati e processo di ETL scuole MIUR


#### Cosa si chiede di fare: 
Viene fornito il file .csv che contiene i dati scaricati da  http://dati.istruzione.it/opendata/opendata/catalogo

1)	Analizzate il tracciato record ed individuate le entità coinvolte e giustificate le scelte

2)	Modellizzare la soluzione del punto 1 con Data Modeler

3)	Create in MySql le tabelle utilizzando il DDL prodotto dal punto 2

4)	Scrivete il codice in linguaggio Java per l’inserimento dei dati nel DB realizzato nel punto 3 e scrivete nel file error.csv i record non processati. Ricordate di scrivere anche il file di log con data, numero di righe processate, inserite e non inserite.

5)	Documentare con una relazione tutte le attività


### Modalità di lavoro: 
Si utilizza una modalità di lavoro mista, per alcune fasi (1 e 5) sono previsti lavori di gruppo per le altre lavoro autonomo.

### Il prodotti: 
Al termine del lavoro dovete presentare una base di dati normalizzata relativa alle scuole presenti sul territorio italiano e il relativo programma di ETL per popolarla.
Dovete inoltre scrivere una relazione descrittiva dell’attività svolta e preparare una presentazione (non più di 7 slide) per una eventuale relazione ai docenti

### Obiettivi di apprendimento:
L’obiettivo è quello di avere una visione completa dell’intero processo di ETL, capirne la funzione e le difficoltà relative

### Tempi: 
Circa due mesi

##PIANO DI LAVORO UDA

Fasi| Attività| Metodologia| Esiti|	Tempi|	Evidenze|Strumenti per la valutazione
----| --------|------------| ------|-----| ---------|----------------------
Fase 1| Acquisire il concetto da base di dati relazionale| Dialogo guidato| Conoscenze concetti base DB e DBMS| 2 ore| Partecipazione, il linguaggio| Relazione di sintesi
Fase 2|	Analisi del tracciato record|Lavoro di gruppo con guida nell’analisi|File normalizzati| 2 ore|	Risultato dell’analisi| Relazione di sintesi
Fase 3| Modello concettuale con Data Modeler| Lezione frontale per i concetti base e videolezioni| Documento modello concettuale| 3 ore|	Diagramma Entità e relazioni|Modello concettuale prodotto
Fase 4|	Modello logico con Data Modeler e DDL|	Focus teorico sui i concetti di base coinvolti in questa fase| Documento modello logico e file con istruzioni DDL|2 ore|	Le relazioni fra le entità, la scelta dei domini|	Modello prodotto e il file con le istruzioni DDL
Fase 5| Creazione fisica del DB| In laboratorio creazione del DB| Struttura fisica DB| 1 ora| La base di dati	| Operatività e stato dei lavori in laboratorio
Fase 6|	Processo di ETL| attività di laboratorio| Data Base popolato con programma in Java| 6 ore| Codice Java, i file di log ed error| Prodotto finito
Fase 7|	Relazione finale| Lavoro di gruppo|	Documento| 2 ore| Capacità di relazionare|Documento finale

