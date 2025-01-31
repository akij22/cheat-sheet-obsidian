
# Appunti sulla raccolta e analisi dei dati
Questi appunti si concentrano sugli steps - TO DO list utilizzate per realizzare la raccolta, l'analisi e parte dell'elaborazione di dati utilizzati per la realizzazione di un software di analisi dei giocatori per il fantacalcio.
Lo scopo di tali appunti è quello di creare una guida utile da seguire per l'apprendimento della logica e delle tecnologie che si andranno ad utilizzare.


### Estrazione dati

#### Statsbomb
* [Statistiche generali da StatsBomb](https://github.com/statsbomb/open-data)


#### Understat
* [Understat - documentation](https://readthedocs.org/projects/understat/downloads/pdf/latest/)


#### Scraper FC (include Sofascore e Understats)
* ```https://api.sofascore.com/api/v1/player/{playerID}/unique-tournament/{tournamentID}/season/{seasonID}/statistics/overall```
* [Scraper FC / Sofascore - API documentation](https://scraperfc.readthedocs.io/en/stable/sofascore.html?utm_source=chatgpt.com)

**Sofascore** --> utile per elaborare dati in tempo reale
**Understat** --> utile per elaborare statistiche precise (XG, passaggi, ...)



#### Elaborazione dati con Pandas
* Pandas - elaborazione dei dati
	* Filtraggio per key (xG, ...)
	* Problema: da risolvere la visualizzazione dei dati e trovare le key per filtrare con Pandas

### Step successivi - estrazione dati
* Generazione grafici
* Generazione tabelle
* Pianificazione dell'aggiornamento dati