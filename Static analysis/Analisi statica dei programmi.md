
# Analisi statica

* **Cosa è❓** --> Analisi dei programmi senza eseguirli
* **Motivi dello studio❓** --> CrowdStrike, Faulty Update, Intel Pentium...

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

******
### Teorema di Rice 👨‍🏫
>Non esiste un programma in grado di determinare se un programma *P* termina o meno

******
### La base - Interpretazione astratta

#### Cos'è?
* Framework matematico utilizzato per fare analisi statica dei programmi
* L'interpretazione astratta si basa su strutture algebriche

#### Idea
* Osservare una versione approssimata / *astratta* del programma (**over-approximation**)
* Se si riesce a provare che la versione astratta è safe, allora anche il programma (ossia tutte le sue possibili esecuzioni) lo sono

#### Casistiche negative (*qualcosa è andato storto...*)
* Anche se un programma è safe, la sua over-approximation potrebbe dire che non è del tutto safe (**false positive, falso positivo**)
* La over-approximation non comprende tutte le casistiche per un determinato programma (**Unsound abstraction**)