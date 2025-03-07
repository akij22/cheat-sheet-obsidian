

###### [Video di riferimento](https://www.youtube.com/watch?v=0B5eIE_1vpU)
## Introduzione
Abbiamo dei dati, i quali vengono forniti ad un modello per realizzare delle **predictions**

Dati divisi in:
* X --> tutto ciò che viene utilizzato per realizzare la prediction
* y --> la prediction che si vuole ottenere

## Scopo del model
Analizzare X, imparare il pattern e capire **come prevedere Y partendo da X.**

Vi sono due fasi riguardanti il model:
1. Fase in cui il model viene creato --> model è un python object
2. Fase in cui il model apprende (impara) dai dati --> **.fit(X, Y)**


Ci sono **diversi model** che è possibile utilizzare in Scikit-learn
* Essi funzionano in modo diverso ( = restituiscono delle predictions differenti), ma le API su cui vengono chiamati rimangono invariate (.fit(...), .predict(...))

### Creazione del model
`mod = KNeighborsRegressor()` --> fase di creazione del modello, utilizzando un model specifico (`KNeighborsRegressor`)



## .fit()
Serve per addestrare il model sui dati di training

* Il modello viene addestrato (.fit()) utilizzando sia X che y
	* X contiene le caratteristiche, le informazioni in input che il modello utilizza per fare previsioni
	* y contiene i valori target che il modello cerca di prevedere
* Calcolo dell'errore --> il modello calcola "quanto ha sbagliato", confrontando le sue predictions con i valori reali di y, e cerca di ridurre l'errore sempre di più

## .predict()
Serve per ottenere le predictions sui dati di test

## Funzionamento del KNeighborsRegressor model
1. Quando si cerca di ottenere una prediction su un valore specifico, tale modello guarda **i punti più vicini** ed osserva la distanza da essi (per individuare per l'appunto i punti più vicini a lui).
2. Dopodichè, calcola la media dei 5 punti più vicini che ha trovato


## Pre-processing
Prima di inserire X all'interno del model per eseguire la predictions, è necessario eseguire un pre-processing --> adattare i dati tra loro, in caso abbiano unità di misure troppo diverse (**scaling**) e causino **noise (rumore) --> errore casuale**
### Implementazione
`from sklearn.preprocessing import StandardScaler`

### Obiettivo di StandardScaler?
Ridurre il rumore, rendendo i dati più omogenei tra loro, migliorando stabilità e precisione
* Quindi, **riduce l'impatto degli outliers**, ossia di quei valori che hanno "comportamenti" / valori anomali rispetto a tutto il set (ad esempio, valori troppo grandi / piccoli rispetto all'insieme)



## Concetto di **pipeline**
Pipeline = sequenza di passaggi che vengono applicati ai dati
* transforming data --> standardizzazione dei dati
* applying model
* predictions

Mediante la pipeline, è possibile eseguire una sequenza di operazioni che definiamo, garantendo di applicare le stesse trasformazioni ai dati di training.

Ad esempio, all'interno di una pipeline, è possibile definire **una prima fase di standardizzazione dei dati** (mediante **StandardScaler object**) ed una **successiva fase di di predictions** (mediante un model)


#### pipe.get_params()
Restituisce tutti i parametri / setting per quella specifica istanza di pipeline


### Sintassi di una pipeline nel codice
`pipe = Pipeline([` <br />
	`("scale", StandardScaler()),` <br />
	`("model", KneighborsRegressor())` <br />

`])`

`pipe.fit(X, Y)`


## GridSearchCV (cross-validation)
E' il "vero e proprio" model che si andrà ad utilizzare

#### Cross-validation: in cosa consiste?
Metodo che divide i dati di addestramento in più parti.

Ad esempio, facciamo caso che i dati vengano divisi in **k** "pieghe":
* il modello viene addestrato su **k - 1** pieghe
* il modello viene testato sulla **k-esima** piega
* tale processo è ripetuto per ogni possibile combinazione, cambiando ogni volta la "piega" utilizzata per il test

Per ogni combinazione, viene calcolata la performance media e, al termine, verrà selezionata la combinazione con la media più alta

#### Perche' effettuare tante combinazioni?
I dati presenti in ogni piega ad ogni combinazione sono diversi (scelti in modo randomico): alcuni dati in una piega potrebbero avere qualità minore rispetto ad altri, oppure essere addestrati in modo migliore solo su una parte di dati


Prende come parametri:
1. estimator --> 
2. parameter grid (param_grid) --> si specificano il numero di neighbors da utilizzare
	1. E' possibile indicare più numeri per il numero di neighbors
3. cv --> cross validation steps

