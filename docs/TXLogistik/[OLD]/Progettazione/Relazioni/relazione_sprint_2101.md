# Relazione sprint 21/01

## Lavoro svolto 
Durante lo sprint sono state effettuate le seguenti operazioni:

- Analisi dei vincoli, con particolare attenzione ad eventuali univocità e nullità oltreché alle relazioni.  
- Aggiornamento delle tabelle Access secondo le modifiche apportate alla progettazione. 
- Creazione delle prime versioni delle maschere. 
- Iniziata la documentazione del programma. 

## Avanzamento della progettazione

_N.B. Tutti gli attributi non menzionati sono semplicemente NOT NULL! PK ed FK sono già evidenziate. Infine per ogni PK non specificata ON DELETE | UPDATE CASCADE e per ogni FK non specificata ON DELETE | UPDATE NO ACTION._

#### Magazzino

> Magazzino (__id_magazzino__, descrizione)

Identifica i magazzini descrivendoli.

#### Fornitore

> Fornitore (__id_fornitore__, descrizione, link)

Identifica i fornitori dei vari prodotti presenti nel magazzino.

	link NULL -- non indispensabile

#### Prodotto

> Prodotto (__id_prodotto__, specifiche_tecniche, _fornitore_, costo_approssimativo, riferimento_sgs, note, stato, adc, adv, adf, adat|aet, addetto_so|op_so, sos_rso, rso, banco_so|so, pds_vr_qe, pds_lonato, pds_brennero, armadio_fer, idc, idv, idf, idat, st, rru|ru, ref, rfer, rsgs, rspp, op_manutenzione, rsmt, re, ss, link)

Indica il prodotto specifico.

	link NULL -- non indispensabile
	note NULL -- non indispensabile

#### Articolo

> Articolo (__id_articolo_, _tipologia_, _categoria_, validita, descrizione, _prodotto_abituale_, _prodotto_alternativo_)

Identifica le varie dotazioni ed articoli che troveremo nel magazzino descrivendole ed indicandone le caratteristiche e il prodotto specifico che solitamente si acquista. Ex Dotazioni, Materiale è stata deprecata.

	UNIQUE tipologia -- può esistere solo un articolo per tipologia!
	prodotto_alternativo NULL -- come visto nelle tabelle forniteci il prodotto alternativo potrebbe non essere previsto
	prodotto_alternativo ON UPDATE NO ACTION ON DELETE SET NULL
	UNIQUE prodotto_alternativo -- non può venire utilizzato lo stesso prodotto per più articoli
	UNIQUE prodotto_abituale -- non può venire utilizzato lo stesso prodotto per più articoli

#### ArticoloMagazzino

> ArticoloMagazzino (__id_articolo__, _articolo_, _magazzino_, giacenza, soglia_riordino)

Associa un articolo ad un magazzino indicando la giacenza e la soglia di riordino.

	UNIQUE articolo, magazzino -- non possono esistere più articoli uguali nello stesso magazzino!
	CHECK giacenza, soglia_riordino > 0 -- la giacenza non può andare in negativo

#### Tipologia

> Tipologia (__id_tipologia__, descrizione)

Identifica la tipologia di un articolo

#### Categoria

> Categoria (__id_categoria__, descrizione)

Identifica la tipologia di una categoria.

#### Dipendente

> Dipendente (__id_dipendente__, nome, cognome)

Identifica i dipendenti con un'anagrafica molto basilare.

#### Transazioni

> Transazioni (__id_transazione__, _articolo_, tipologia_transazione, qta_transazione, _ricevitore_, data, note)

Identifica le transazioni descrivendone le caratteristiche ed associando il tutto tra un articolo ed un dipendente.

	CHECK qta_transazione > 0
	note, NULL

#### Indumento

> Indumento (__id_indumento__, descrizione)

Identifica un indumento.

#### Taglia

> Taglia (__id_taglia__, descrizione)

Identifica una taglia di un indumento.

#### TagliaIndumentoDipendente

> TagliaIndumentoDipendente (__id_tip__, _dipendente_, _indumento_, _taglia_)

Associa la taglia ad un indumento ad un dipendente.

	UNIQUE (dipendente, indumento, taglia) -- un dipendente non può portare n con n > 1 taglie diverse per lo stesso indumento!
	
## Conclusioni

Con lo sprint presente è stato compreso meglio il problema, ma rimangono ancora dei dubbi. In particolare:

- La tabella indumento potrebbe essere la stessa di prodotto, tutto dipende dal fatto che l'azienda tratti gli indumenti come un qualunque altro prodotto.

Inoltre persistono le incertezze riscontrate nello scorso sprint, ovvero:

- Possono essere previsti più di due fornitori per un articolo? Porterebbe vantaggi l'eventuale gestione di più fornitori?
- Tipologia e Categoria sono entrambe essenziali?
- È il caso di ampliare l'anagrafica dei dipendenti? Tornerebbe utile?
- Ci sono molte incertezze sulla tabella Prodotto, in merito riporto un passo della precedente relazione:

> Esiste molta coerenza tra le tabelle DPI e Dotazioni. Gli attributi sono tutti i medesimi, meno che per gli attributi finali che possono assumere valori di tipo booleano. Questi differiscono nelle due tabelle per alcuni, in particolare:
> DPI --> aet, op_so, so, ru
> Q.D. --> adat, addetto_so, banco_so, rru
> Rimane il dubbio sul fatto che questi attributi possano rispettivamente significare la stessa cosa. In tal caso una volta decisa la migliore nomenclatura il problema è risolto. Se invece alcuni o tutti avessero significati diversi, allora si potrebbero tenere entrambi in un'eventuale tabella riferita al prodotto.

Si ribadisce qui l'importanza di un incontro con i portavoce dell'azienda.