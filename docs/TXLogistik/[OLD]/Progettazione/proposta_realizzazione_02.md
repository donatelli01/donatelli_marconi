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
