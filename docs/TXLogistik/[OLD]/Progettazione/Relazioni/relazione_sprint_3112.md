# Relazione analisi del problema TxLogistik

## Magazzino Generale
Seguono gli schemi delle tabelle del magazzino generale.

##### Modulistica

	Modulistica (
		validita, 
		categoria, 
		materiale,  
		giacenza_iniziale, 
		qta_prelievo, 
		qta_inserimento, 
		data, 
		ricevitore, 
		giacenza_residua, 
		soglia_riordino, 
		note
	)

##### Dotazioni

	Dotazioni (
		validita, 
		categoria, 
		materiale,  
		giacenza_iniziale, 
		qta_prelievo, 
		qta_inserimento, 
		data, 
		ricevitore, 
		giacenza_residua, 
		soglia_riordino, 
		note
	)

##### Divisa

	Divisa (
		validita, 
		materiale,  
		giacenza_iniziale, 
		qta_prelievo, 
		qta_inserimento, 
		data, 
		ricevitore, 
		giacenza_residua, 
		soglia_riordino, 
		note
	)

##### DPI (Dispositivi Protezione Individuale)

	Dpi (
		validita, 
		materiale,  
		giacenza_iniziale, 
		qta_prelievo, 
		qta_inserimento, 
		data, 
		ricevitore, 
		giacenza_residua, 
		soglia_riordino, 
		note
	)

##### IT

	It ( 
		validita, 
		materiale, 
		giacenza_iniziale, 
		qta_prelievo, 
		qta_inserimento, 
		data, 
		ricevitore, 
		giacenza_residua, 
		soglia_riordino, 
		note
	)

##### Gadget

	Gadget (
		validita, 
		materiale, 
		giacenza_iniziale, 
		qta_prelievo, 
		qta_inserimento, 
		data, 
		ricevitore, 
		giacenza_residua, 
		soglia_riordino, 
		note
	)

### Analisi del campi

Ogni possibile tabella ha all'incirca gli stessi attributi:

- _validità_, che può assumere solamente due valori (ACTUAL, OLD).Si pensa faccia riferimento alla validità di un oggetto in quanto potrebbe diventare deprecato (Sicuramente l'utilizzo di tale campo va approfondito).

- _categoria_, che non è presente in tutte le tabelle ma solo in Modulistica e Dotazioni. Serve a distinguere gli elementi in base al tipo (potrebbe diventare utile al fine di applicare dei filtri). Dato che le tabelle in questione non sono differenti se non per questo campo si potrebbe aggiungere anche alle tabelle dove non è presente permettendogli di accettare la categoria - per esempio - UNICO, la quale indica la presenza di una sola tipologia di quell'oggetto e magari valutare di aggiungerne ulteriori dove possibile. Si potrebbe separare dalle altre tabelle in una specifica contenente i valori che la categoria può assumere.

- _materiale_, il quale identifica in maniera specifica la sottospecie di oggetto al quale ci si riferisce. Dato che le attrezzature aziendali non sono illimitate, per portare a termine il lavoro in maniera ottimale e risolvere i problemi di normalizzazione si potrebbe procedere in maniera simile a categoria, valutando di creare un'ulteriore tabella contenente i materiali alla quale riferirsi in questo campo mediante una chiave esterna.

- _giacenza_iniziale_, indica la quantità di una risorsa aziendale in un momento iniziale. Ciò è sicuramente utile all'azienda per tenere traccia dei movimenti ma per portare a termine un prodotto in maniera ottimale bisognerebbe creare una tabella a parte che tenga traccia di queste transazioni.

- _qta_prelievo_, indica la quantità di elementi che vengono eventualmente prelevati. Stesso discorso di giacenza_inziale.

- _qta_inserimento_, indica la quantità di elementi che vengono eventualmente inseriti. Stesso discorso di giacenza_inziale.

- _data_, indica la data dell'operazione effettuata. Stesso discorso di giacenza_inziale.

- _ricevitore_, indica chi ha ricevuto una data risorsa aziendale. Stesso discorso di giacenza_inziale. Inoltre si sottolinea che sarebbe buona cosa fare riferimento al dipendente mediante una chiave esterna (la tabella dipendenti esiste già).

- _giacenza_residua_, indica la quantità di una risorsa aziendale al termine della transazione. Stesso discorso di giacenza_iniziale.

- _soglia_riordino_, indica a che quantità la risorsa aziendale va riordinata. Sembrerebbe un valore costante per ogni tipo di risorsa aziendale presente nel magazzino, pertanto questa va inserita nella tabella con gli elementi del magazzino.

- _note_, indica degli appunti probabilmente sulle transazioni in caso di eventi particolari.  Stesso discorso di giacenza_inziale.

- ---

## Dipendenti
Segue lo schema della tabella Dipendenti.

	Dipendente (
		dipendente, 
		giacca_hv, 
		felpa, 
		pantalone_felpato, 
		pantalone_estivo, 
		polo_manica_lunga, 
		polo_manica_corta, 
		tuta_alta_visibilita, 
		scarpe_invernali, 
		scarpe_estive, 
		bermuda, 
		maglietta_fotl)

### Analisi dei campi

- _dipendente_, nome e cognome del dipendente.

I restanti campi fanno semplicemente riferimento alla taglia indossata dai dipendenti per i vari capi di abbigliamento lavorativo (M, L, 43, ..).

---

## Quadro Dotazioni

Segue lo schema della tabella quadro dotazioni.

> QuadroDotazioni (tipologia, descrizione, specifiche_tecniche, produttore_prodotto, fornitore_abituale, costo_approssimativo, fornitore_alternativo, costo_approssimativo_alternativo, riferimento_sgs, note, stato, adc, adv, adf, adat, addetto_so, sos_rso, rso, banco_so, pds_vr_qe, pds_lonato, pds_brennero, armadio_fer, idc, idv, idf, idat, st, rru, ref, rfer, rsgs, rspp, op_manutenzione, rsmt, re, ss, link)

### Analisi dei campi

- _tipologia_, identifica la categoria della dotazione.

- _descrizione_, descrive la dotazione.

- _specifiche_tecniche_, fa probabilmente riferimento agli standard di idoneità ai quali risponde la dotazione.

- _fornitore_abituale_, esplicita il fornitre dal quale si tende ad acquistare la dotazione. In questo campo sarebbe una buona idea collocare una chiave esterna che punta ad una tabella fornitori.

- _produttore_prodotto_, indica precisamente il marchio ed il modello della dotazione. Sarebbe una buona idea separare il prodotto in maniera da potercisi riferire mediante una chiave esterna.

- _costo_approssimativo_, costo della dotazione abituale. Stesso discorso di produttore_prodotto.

- _fornitore_alternativo_, indica il fornitore da cui acquistarela dotazione che potrebbe non essere disponibile in un dato momento da quello abituale. Anche qui sarebbe una buona idea puntare ad una tabella coi fornitori tramite una chiave esterna.

- _costo_approssimativo_alternativo_, costo della dotazione alternativa. Stesso discorso di produttore_prodotto.

- _riferimento_sgs_, fin'ora ha assunto due valori (PS 14.1 e DVR) l'ultimo dei due valori sta probabilmente per "documento di valutazione dei rischi" e con SGS probabilmente si intende "SGS is the world's leading inspection, verification, testing and certification company.". Non è molto chiara la natura di questo campo, ma probabilmente è un parametro riguardante la sicurezza dei dipendenti. Una volta compreso meglio il problema si potrebbe valutare una chiave esterna.

- _note_, appunti probabilmente sulla quantità di un articoli di dotazione acquistati alla volta.

- _stato_, può assumere tre valori (IN VIGORE, NON IN VIGORE, ABROGATA), probabilmente fa riferimento all'idoneità della dotazione.

- _link_, collegamento web al prodotto.

I restanti campi (adc, adv, adf, ..) sono tutti valori booleani (si/ no) la cui natura non è nota. Fanno forse riferimento a degli standard?

---

## DPI

Segue lo schema della tabella DPI (Dispositivi di protezione individuale)<

> DPI (tipologia, descrizione, specifiche_tecniche, fornitore_abituale, produttore_prodotto, costo_approssimativo, fornitore_alternativo, produttore_prodotto_alternativo, costo_approssimativo_alternativo, riferimento_sgs, note, stato, adc, adv, adf, aet, op_so, sos_rso, rso, so, pds_vr_qe, pds_lonato, pds_brennero, armadio_fer, idc, idv, idf, idat, st, ru, ref, rfer, rsgs, rspp, op_manutenzione, rsmt, re, ss, link)

### Analisi dei campi

- _tipologia_, in questa tabella assume solo un valore (DPI). Identifica la categoria della dotazione.

- _descrizione_, descrive il DPI oggetto dell'istanza.

- _specifiche_tecniche_, fa probabilmente riferimento agli standard di idoneità ai quali risponde il DPI oggetto dell'istanza.

- _fornitore_abituale_, esplicita il fornitre dal quale si tende ad acquistare il DPI oggetto dell'istanza. In questo campo sarebbe una buona idea collocare una chiave esterna che punta ad una tabella coi fornitori.

- _produttore_prodotto_, indica precisamente il marchio ed il modello del DPI abituale oggetto dell'istanza. Sarebbe una buona idea separare il prodotto in maniera da potercisi riferire mediante una chiave esterna.

- _costo_approssimativo_, costo del DPI oggetto_dell'istanza abituale. Stesso discorso di produttore_prodotto.

- _fornitore_alternativo_, indica il fornitore da cui acquistare il DPI oggetto dell'istanza che potrebbe non essere disponibile in un dato momento da quello abituale. Anche qui sarebbe una buona idea puntare ad una tabella coi fornitori tramite una chiave esterna.

- _produttore_prodotto_alternativo_, indica precisamente marchio e prodotto del DPI alternativo oggetto dell'istanza. Stesso discorso di produttore_prodotto.

- _costo_approssimativo_alternativo_, costo del DPI alternativo.Stesso discorso di produttore_prodotto.

- _riferimento_sgs_, fin'ora ha assunto due valori (PS 14.1 e DVR) l'ultimo dei due valori sta probabilmente per "documento di valutazione dei rischi" e con SGS probabilmente si intende "SGS is the world's leading inspection, verification, testing and certification company. ". Non è molto chiara la natura di questo campo, ma probabilmente è un parametro riguardante la sicurezza dei dipendenti. Una volta compreso meglio il problema si potrebbe valutare una chiave esterna.

- _note_, appunti probabilmente sul numero di un articolo DPI acquistati alla volta.

- _stato_, può assumere tre valori (IN VIGORE, NON IN VIGORE, ABROGATA), probabilmente fa riferimento all'idoneità del DPI.

- _link_, collegamento web al prodotto.

I restanti campi (adc, adv, adf, ..) sono tutti valori booleani (si/ no) la cui natura non è nota. Fanno forse riferimento a degli standard?

---

## Considerazioni e proposta di realizzazione

Le tabelle presentateci non sono normalizzate, questo è sicuramente un problema in quanto non permettono la realizzazione di un prodotto finale prestante. In particolare bisognerebbe passare ad una 3NF. 

Inoltre anche tralasciando la normalizzazione le tabelle non risultano organizzate nella maniera migliore: le tabelle del magazzino generale si sarebbero potute con qualche accorgimento riassumere in una sola, e lo stesso discorso vale per le tabelle delle dotazioni e dei dpi. 

### Proposta di realizzazione

    Magazzino (__id_magazzino__, descrizione)

    ArticoloMagazzino (__id_articolo__, _materiale_, _magazzino_, giacenza, soglia_riordino)
    
    Materiale (__id_materiale__, tipologia_materiale*, categoria, validita, descrizione)
    
    Categoria (__id_categoria__, descrizione)
    
    Dipendente (__id_dipendente__, nome, cognome)
    
    Transazioni (__id_transazione__, _materiale_, tipologia_transazione**, qta_transazione, _ricevitore_, data, note)
    
    Indumento (__id_indumento__, descrizione)
    
    Taglia (__id_taglia__, _dipendente_, _indumento_, descrizione)
    
    Dotazioni (__id_dotazione__, descrizione, _prodotto_abituale_, _prodotto_alternativo_)
    
    Prodotto (__id_prodotto__, tipologia, specifiche_tecniche, _fornitore_, costo_approssimativo, riferimento_sgs, note, stato, adc, adv, adf, adat|aet, addetto_so|op_so, sos_rso, rso, banco_so|so, pds_vr_qe, pds_lonato, pds_brennero, armadio_fer, idc, idv, idf, idat, st, rru|ru, ref, rfer, rsgs, rspp, op_manutenzione, rsmt, re, ss, link)***
    
    Fornitore (__id_fornitore__, descrizione, link)
	
\* può assumere solo i valori Modulistica, Dotazioni, Divisa, DPI, IT e Gadget che possono venir controllati con un constraint o con una tabella a parte (magari sfruttando categoria)

** può assumere solo i valori prelievo/inserimento che potrebbe essere rappresentato da un booleano, una stringa con un constraint o una tabella a parte (magari sfruttando categoria)

*** Esiste molta coerenza tra le tabelle DPI e Dotazioni. Gli attributi sono tutti i medesimi, meno che per gli attributi finali che possono assumere valori di tipo booleano. Questi differiscono nelle due tabelle per alcuni, in particolare:

DPI --> aet, op_so, so, ru

Q.D. --> adat, addetto_so, banco_so, rru

Rimane il dubbio sul fatto che questi attributi possano rispettivamente significare la stessa cosa. In tal caso una volta decisa la migliore nomenclatura il problema è risolto. Se invece alcuni o tutti avessero significati diversi, allora si potrebbero tenere entrambi in un'eventuale tabella riferita al prodotto.

Inoltre il campo produttore_prodotto_alternativo (vedi sotto) è assente in Dotazioni ma presente in DPI . Andrebbe inserito comunque, nel peggiore dei casi se il prodotto abituale e quello alternativo fossere uguali basterebbe mettere due chiavi esterne che riferiscono allo stesso articolo, il che non risulta affatto un problema dal punto di vista applicativo.

> - produttore_prodotto_alternativo, indica precisamente marchio e prodotto del DPI alternativo oggetto dell'istanza. Stesso discorso di produttore_prodotto.
