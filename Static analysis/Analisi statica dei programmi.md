
# Analisi statica

* **Cos'è❓** --> Analisi dei programmi senza eseguirli
* **Motivi dello studio❓** --> CrowdStrike, Faulty Update, Intel Pentium...

#### Caratteristiche
1. Non necessita di eseguire il programma
2. Performato sul codice sorgente (source-code)
	1. Non è necessario limitarsi all'analisi di un singolo input, come avviene per i test
3. Utile in:
	1. Compiler optimization
	2. Ricerca di vulnerabilità di sicurezza
	3. Program analysis

******
### Manual inspection
* Controllo manuale del codice
* Non realizzabile, perché:
	* presente l'errore umano;
	* costi troppo elevati;
	* **Tutti i software contengono bug**

******
### Testing
**In cosa consiste❓** --> Si prendono alcune esecuzioni, poi si lancia il codice.
❗️Alcune casistiche sono **unsafe executuions** --> 
1. I testing non coprono alcune casistiche 
2. Per avere un **software bug-free**, sarebbe necessario **testare tutte le possibili casistiche**

******

### Quindi qual è l'obiettivo⁉️
**Certificare** che un programma è safe, ossia certificare che ==tutte le le esecuzioni del programma sono sicure==
* Vogliamo poter rispondere alla domanda: *"Il programma è safe oppure no?"*

******
### Teorema di Rice 👨‍🏫
>Non esiste un programma in grado di determinare se un programma *P* termina o meno

******
### La base - Interpretazione astratta 🔭

#### Cos'è?
* Framework matematico utilizzato per fare analisi statica dei programmi
* L'interpretazione astratta si basa su strutture algebriche

#### Idea (over approximation)
* Osservare una versione approssimata / *astratta* del programma (**over-approximation**)
* Se si riesce a provare che la versione astratta è safe, allora anche il programma (ossia tutte le sue possibili esecuzioni) lo sono
* E' necessario trovare un'efficiente approssimazione / algoritmo per dare la risposta corretta in più casistiche possibili

![over-approximation](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ-4vLFGOhFqk18X1llIAnT03h8AAqYhq7eKyMPtouZvs3wHlLv4U09cC7OOM2zitG7Dag&usqp=CAU)


#### Quando un algoritmo è definito *sound* (valido)?
Un algoritmo è definito **sound** se, ogni volta che afferma che un programma è sicuro, il programma lo è effettivamente
* Non genera **falsi negativi** --> riconosce tutti gli eventuali errori
* Può generare **falsi positivi** (segnalare problemi che non ci sono)


#### Quando un algoritmo è definito *complete* (completo)?
Un algoritmo è definito **completo** se un programma è sicuro (rispetto a certi errori) e tale algoritmo lo riconosce lo segnala come *safe*.
* Non genera falsi positivi
* Può generare falsi negativi (non rilevare tutti gli errori presenti)


#### Unsound abstraction
* La over-approximation di un determinato programma può non comprendere tutte le casistiche per un determinato programma *P*

#### E quindi, il vantaggio❓
Se l'interpretazione astratta determina che il programma è sicuro, allora al 100% (anche matematicamente) lo è

******
### Abstract interpretation - tecniche sui domini

#### Dominio dei segni
* Il dominio più elementare, la base dell'astrazione
* Scopo didattico, data la **poca precisione**

#### Dominio degli intervalli
Utilizzo di intervalli in cui "comprendere le casistiche"
* Perdita di precisione, ma l'astrazione rispetta il programma concreto = **i valori concreti sono contenuti nell'astrazione**

##### Galois connection
![Galois|500x250](https://i.sstatic.net/QtA6Q.png)

# Sitografia
[Link 1 - presentazione](https://plmw2014.inria.fr/talks/dillig-plmw14.pdf)
[Link2](https://www.ida.liu.se/~TDDC90/literature/slides/TDDC90_static_I_handout.pdf)