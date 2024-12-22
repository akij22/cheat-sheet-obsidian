
# Analisi statica

* **Cos'è❓** --> Analisi dei programmi senza eseguirli
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
### La base - Interpretazione astratta 🔭

#### Cos'è?
* Framework matematico utilizzato per fare analisi statica dei programmi
* L'interpretazione astratta si basa su strutture algebriche

#### Idea
* Osservare una versione approssimata / *astratta* del programma (**over-approximation**)
* Se si riesce a provare che la versione astratta è safe, allora anche il programma (ossia tutte le sue possibili esecuzioni) lo sono

![over-approximation](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ-4vLFGOhFqk18X1llIAnT03h8AAqYhq7eKyMPtouZvs3wHlLv4U09cC7OOM2zitG7Dag&usqp=CAU)

#### Casistiche negative (*qualcosa è andato storto...*)
* Anche se un programma è safe, la sua over-approximation potrebbe dire che non è del tutto safe (**false positive, falso positivo**)
* La over-approximation non comprende tutte le casistiche per un determinato programma (**Unsound abstraction**)

#### E quindi, il vantaggio❓
Se l'interpretazione astratta determina che il programma è sicuro, allora al 100% (anche matematicamente) lo è

******
### Domini - tecniche diverse

#### Dominio dei segni
* Il dominio più elementare, la base dell'astrazione
* Scopo didattico, data la **poca precisione**

#### Dominio degli intervalli
Utilizzo di intervalli in cui "comprendere le casistiche"
* Perdita di precisione, ma l'astrazione rispetta il programma concreto = **i valori concreti sono contenuti nell'astrazione**

##### Galois connection
![Galois](https://i.sstatic.net/QtA6Q.png)

# Sitografia
[Link 1 - presentazione](https://plmw2014.inria.fr/talks/dillig-plmw14.pdf)
[Link2](https://www.ida.liu.se/~TDDC90/literature/slides/TDDC90_static_I_handout.pdf)