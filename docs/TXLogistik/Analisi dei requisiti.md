# Analisi dei requisiti
> Per l’implementazione del gestionale dell’azienda TxLogistik è possibile operare in 3 diverse maniere:
```
1.	Utilizzo della piattaforma MS Access per quanto riguarda entrambe le parti client e server.
2.	Utilizzo della piattaforma MS Access per quanto riguarda la parte server e di un client di tipo web costruito ad-hoc.
3.	Utilizzo di un RDBMS per quanto riguarda la parte server e di un client di tipo web costruito ad-hoc.
```
### Analisi della priorità
```
L’utilizzo di un RDBMS non è necessario, poiché il carico di lavoro da gestire è limitato e poiché la persistenza dei dati non è richiesta oltre alle regolari ore lavorativi.
Un client ad-hoc non è indispensabile, poiché con Access è possibile creare un client altrettanto potente e costruito sulla stessa piattaforma del livello server.
```
```
Inoltre, i sistemi informatici dell’azienda sono blindati, e l’installazione di un nuovo servizio client/server sarebbe troppo impegnativo
```
### Analisi dei costi
```
A causa dell’irrilevanza di un eventuale servizio DB server e di una macchina dedicata che ne assicuri la persistenza, i costi stimati sono nulli.
```