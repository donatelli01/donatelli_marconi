# Relazione sprint 01/14/2017

Segue la relazione Durante lo sprint terminato il 14 gennaio 2017 durato una settimana e con velocity stimata di 6SP/W.
Il membro Rossetto in questo sprint ha realizzato una velocity di 0SP/W.

### Lavoro svolto
- Revisione della proposta di realizzazione: il team si è reso conto che la tabelle dotazioni e materiale probabilmente contenevano la stessa cosa, ed è proceduta l'eliminazione della ridondanza. Pertanto i campi che materiale aveva in più rispetto a dotazione sono stati spostati in quest'ultima che ha preso il nome di articolo. Infine è stato deciso di gestire più magazzini perché anche se ipoteticamente fosse uno solo, questa struttura garantirebbe la scalabilità se in un futuro se ne aggiungesse un altro. Se rimanesse uno solo, poco male, viene gestito comunque bene.
- Creazione di una prima versione delle tabelle in Access, comprensiva della tipologia di dati e della descrizione del campo. Relazioni e vincoli abbiamo calcolato di farli in un prossimo sprint dove avremo converma di alcune incertezze che verranno successivamente illustrate.

### Proposta di realizzazione v0.2

Segue la nuova proposta di realizzazione:

> Magazzino (__id_magazzino__, descrizione)

Identifica i magazzini descrivendoli.

> Fornitore (__id_fornitore__, descrizione, link)

Identifica i fornitori dei vari prodotti presenti nel magazzino.

> Prodotto (__id_prodotto__, specifiche_tecniche, _fornitore_, costo_approssimativo, riferimento_sgs, note, stato, adc, adv, adf, adat|aet, addetto_so|op_so, sos_rso, rso, banco_so|so, pds_vr_qe, pds_lonato, pds_brennero, armadio_fer, idc, idv, idf, idat, st, rru|ru, ref, rfer, rsgs, rspp, op_manutenzione, rsmt, re, ss, link)

Indica il prodotto specifico.

> Articolo (__id_articolo_, tipologia, categoria, validita, descrizione, _prodotto_abituale_, _prodotto_alternativo_)

Identifica le varie dotazioni ed articoli che troveremo nel magazzino descrivendole ed indicandone le caratteristiche e il prodotto specifico che solitamente si acquista. Ex Dotazioni, Materiale è stata deprecata.

> ArticoloMagazzino (__id_articolo__, _articolo_, _magazzino_, giacenza, soglia_riordino)

Associa un articolo ad un magazzino indicando la giacenza e la soglia di riordino.

> Tipologia (__id_tipologia__, descrizione)

Identifica la tipologia di un articolo.

> Categoria (__id_categoria__, descrizione)

Identifica la tipologia di una categoria.

> Dipendente (__id_dipendente__, nome, cognome)

Identifica i dipendenti con un'anagrafica molto basilare.

> Transazioni (__id_transazione__, _articolo_, tipologia_transazione, qta_transazione, _ricevitore_, data, note)

Identifica le transazioni descrivendone le caratteristiche ed associando il tutto tra un articolo ed un dipendente.

> Indumento (__id_indumento__, descrizione)

Identifica un indumento.

> Taglia (__id_taglia__, descrizione)

Identifica una taglia di un indumento.

> TagliaIndumentoDipendente (__id_tip__, _dipendente_, _indumento_, _taglia_)

Associa la taglia ad un indumento ad un dipendente.

### Resoconto

La progettazione è avanzata, ed intanto il team si è portato avanti con Access. Il problema diventa sempre più chiaro, e la soluzione è alle porte. Tuttavia mancano ancora delle informazioni che solamente l'azienda ci può fornire. A tal scopo sarebbe il caso di convocare il cliente in maniera da poter discutere a voce sulle incertezze sorte. In particolare i punti da mettere in chiaro fin'ora (14 gen 2018) sono i seguenti:

- Possono essere previsti più di due fornitori per un articolo? Porterebbe vantaggi l'eventuale gestione di più fornitori?
- Tipologia e Categoria sono entrambe essenziali?
- È il caso di ampliare l'anagrafica dei dipendenti? Tornerebbe utile?
- Ci sono molte incertezze sula tabella Prodotto, in merito riporto un passo della precedente relazione:

> Esiste molta coerenza tra le tabelle DPI e Dotazioni. Gli attributi sono tutti i medesimi, meno che per gli attributi finali che possono assumere valori di tipo booleano. Questi differiscono nelle due tabelle per alcuni, in particolare:
> DPI --> aet, op_so, so, ru
> Q.D. --> adat, addetto_so, banco_so, rru
> Rimane il dubbio sul fatto che questi attributi possano rispettivamente significare la stessa cosa. In tal caso una volta decisa la migliore nomenclatura il problema è risolto. Se invece alcuni o tutti avessero significati diversi, allora si potrebbero tenere entrambi in un'eventuale tabella riferita al prodotto.


