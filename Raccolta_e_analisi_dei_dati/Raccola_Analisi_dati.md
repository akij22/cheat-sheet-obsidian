
#### Utilizzo di Pandas - link file
[[Pandas - utilizzo generale]]

# Appunti sulla raccolta e analisi dei dati
Questi appunti si concentrano sugli steps - TO DO list utilizzate per realizzare la raccolta, l'analisi e parte dell'elaborazione di dati utilizzati per la realizzazione di un software di analisi dei giocatori per il fantacalcio.
Lo scopo di tali appunti è quello di creare una guida utile da seguire per l'apprendimento della logica e delle tecnologie che si andranno ad utilizzare.


### Estrazione dati - Fonti

#### Statsbomb
* [Statistiche generali da StatsBomb](https://github.com/statsbomb/open-data)


#### Understat
* [Understat - documentation](https://readthedocs.org/projects/understat/downloads/pdf/latest/)
* [Github repo](https://github.com/amosbastian/understat)


#### Scraper FC (include Sofascore e Understats)
* ```https://api.sofascore.com/api/v1/player/{playerID}/unique-tournament/{tournamentID}/season/{seasonID}/statistics/overall```
* [Scraper FC / Sofascore - API documentation](https://scraperfc.readthedocs.io/en/stable/sofascore.html?utm_source=chatgpt.com)

**Sofascore** --> utile per elaborare dati in tempo reale
**Understat** --> utile per elaborare statistiche precise (XG, passaggi, ...)
#### Scraping - FBref
* Possibile scraping per estrarre dati di singoli giocatori (xG, xAG, goal, assist, ...)




#### Elaborazione dati con Pandas - [documentazione](https://pandas.pydata.org/docs/user_guide/index.html#user-guide)
	* Pandas - elaborazione dei dati
	* Filtraggio per key (xG, ...)

### Step successivi - estrazione dati
* Generazione grafici
* Generazione tabelle
* Pianificazione dell'aggiornamento dati


### Pulizia dati
* Video riferimento: [Scikit-learn - conversione e pulizia dati](https://www.youtube.com/watch?v=GsfXAzfvJVM)

1. Necessario convertire molti dati (anche di tipo str) in bool, ad esempio, shotType deve essere rimosso, al suo posto
	1. Si inseriscono tante colonne di tipo bool, che indicano il tipo di tiro (RighFoot, LeftFoot, Head, ...)
2. Feature per "aiutare" il modello: ho aggiunto la shot_distance

## TODO
1. Visualizzazione dati
	1. [X] Come posso migliorare la visualizzazione dei dati?
		1. Possibile necessità di utilizzare grafici per poterli visualizzare meglio
		2. [X] Utilizzo di Pandas per convertire i dati in data frame e visualizzarli meglio
		3. [x] Utilizzo di **Jupyter Notebook** (i DataFrame vengono visualizzati in modo chiaro)
		4. Utilizzo di dati salvati in CSV (**non utilizzata al momento**)
			1. Memorizzare i dati in file CSV mediante il relativo metodo di Pandas
	2. Come posso manipolare / filtrare i dati?
	3. Devo per forza eseguire web scraping (almeno in questa parte iniziale dello sviluppo)? 
2. Chiamate API
	1. Le API forniscono tutti i metodi / dati necessari?
3. Integrazione con web app
	1. Come integro API e database?
	2. Che scopo dovrà avere il mio db?
	3. Che struttura avrà il mio db? (Entità, relazioni tra entità)
4. Visualizzazione mediante grafici (**Matplotlib / Seaborn**) / **Scikit-learn** (machine-learning) - step complesso


### Todo 06/02/2025 - other days...
1. Dato un giocatore in input, restituire:
	1. [X] Squadra attuale in cui gioca
	2. Storico delle squadre in cui ha giocato (con rispettive annate)
	3. [X] Numero di partite giocate
	4. [X] Numero di minuti totali giocati
	5. [X] Percentuale di minutaggio (quanti minuti in campo rispetto al totale)
	6. Gol, assist, tiri totali, tiri totali in porta, xG, xA, Sh90, xG90, xA90
	7. Percentuale di realizzazione
		1. Utilizza numero di tiri totali e i gol fatti [da approfondire]
	8. Possibile valutazione finale (da capire come calcolare / dove estrapolarla)
	9. [X] Visualizzazione shots map mediante grafici di Seaborn
		1. [Possibile necessità di mostrare un football pitch](https://www.kaggle.com/code/josegabrielgonzalez/understat-series-heatmaps/notebook#Plotting-heatmaps)


