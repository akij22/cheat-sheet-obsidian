
# Appunti sulla raccolta e analisi dei dati
Questi appunti si concentrano sugli steps - TO DO list utilizzate per realizzare la raccolta, l'analisi e parte dell'elaborazione di dati utilizzati per la realizzazione di un software di analisi dei giocatori per il fantacalcio.
Lo scopo di tali appunti è quello di creare una guida utile da seguire per l'apprendimento della logica e delle tecnologie che si andranno ad utilizzare.


### Estrazione dati - Fonti

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


## TODO
1. __Visualizzazione dati__
	1. Come posso migliorare la visualizzazione dei dati?
		1. Possibile necessità di utilizzare grafici per poterli visualizzare meglio
		2. Utilizzo di Pandas per convertire i dati in data frame e visualizzarli meglio
		3. Utilizzo di **Jupyter Notebook** (i DataFrame vengono visualizzati in modo chiaro)
		4. Utilizzo di dati salvati in CSV
			1. Memorizzare i dati in file CSV mediante il relativo metodo di Pandas
	2. Come posso manipolare / filtrare i dati?
	3. Devo per forza eseguire web scraping (almeno in questa parte iniziale dello sviluppo)? 
2. Chiamate API
	1. Le API forniscono tutti i metodi / dati necessari?
3. Integrazione con web app
	1. Come integro API e database?
	2. Che scopo dovrà avere il mio db?
	3. Che struttura avrà il mio db? (Entità, relazioni tra entità)