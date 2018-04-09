# readthedocs.org

---
##### author : Leonardo Bellomi leonardobellomi@gmail.com
##### version : 1.0 2018-02-28
---

### Scopo :
  
  Visualizzazione e navigazione della documentazione generata dai gruppi attraverso pagine web dinamiche
  
### Setup & Utilizzo :
  
  + Creare un account sul sito [read the docs](http://google.it)
  
  [LOGIN IMAGE](https://github.com/kidoleo/PMO_readthedocs/blob/master/docs/PMO/login.PNG)
  
  + Se non ancora presente, creare un account su [GitHub](https://github.com)
  
  + Creare o entrare in una propria repository su GitHub, ad esempio [PMO_readthedocs](https://github.com/kidoleo/PMO_readthedocs)
  + Andare alla voce settings (nella stessa repository) --> WebHooks e aggiungere il webhook copiando il Payload URL
  
  [SETTINGS IMAGE](https://github.com/kidoleo/PMO_readthedocs/blob/master/docs/PMO/settings.PNG)
  
  + Copiare il Payload URL da readthedocs in Amministrazione-->Integretion-->Add Integretion
    
  [PAYLOAD IMAGE](https://github.com/kidoleo/PMO_readthedocs/blob/master/docs/PMO/payload.PNG)

### NB :

  + Nella repository github sarà necessario avere una cartella `docs` in root alla repository, ad esempio:[PMO_docs](https://github.com/kidoleo/PMO_readthedocs/new/master/docs/)
  + Creare un file `index.md` all' interno della cartella `docs` con all'interno le informazioni principali che verranno mostrate in homepage

#### Possibili problemi e soluzioni :

  + Il file creato all' interno della cartella `docs` per la pagina principale della documentazione deve essere espressamente chiamata `index.md`, con qualsiasi altro nome, ad esempio `README.md`, il servizio non funziona.
  + Tutti i file di documentazione devono essere necessariamente messi in una directory denominata `docs` in root alla repository.
