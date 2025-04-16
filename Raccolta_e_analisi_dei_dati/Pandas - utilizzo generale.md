

## Accesso alle **colonne** mediante notazione chiave
##### Accesso ad una colonna
`df["colonna1"]`

##### Accesso a più colonne
`df[[colonna1, colonna2]]`


## Accesso alle righe / colonne mediante `.loc`

##### Accesso ad una riga
`df.loc['colonna1']`, dove `colonna1` indica il nome della riga


## Accesso alle righe / colonne mediante `.iloc` (posizione numerica)

##### Accesso ad una riga
`df.iloc[0]`, dove l'elemento all'interno della parentesi quadra rappresenta **l'indice numerico**


##### Accesso ad una cella
`df.iloc[0, 2]`, dove:
* `0` rappresenta la **riga**
* `2` rappresenta la **colonna**


## Selezione di intervalli (mediante `.iloc`)
##### Accesso ad un intervallo di dati
`df.iloc[0 : 2]`, dove si seleziona la prima e la seconda riga



## Filtraggio dei dati
* Mediante `.loc` --> `df.loc[df["colonna1"] == "colonna 1"]`
	* Restituisce le righe che contengono `colonna 1` rispettivamente nella `colonna1`
* Mediante `.query` --> `df.query("colonna1" == colonna1")`
	* Utilizzando **variabili --> `df.query("colonna1" == @variable")`
