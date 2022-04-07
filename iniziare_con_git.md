# Iniziare con Git



<br>



[TOC]



<br>



# Capitolo 1 - La creazione

Nel nostro caso useremo **Git**, il più famoso VCS, che ci permetterà di creare un repository locale, che sarà la casa del nostro progetto, mentre per la parte server del progetto utilizzeremo <a href="https://github.com">**Github**</a> che metterà il nostro repository online e noi potremmo accedervi e sincronizzarci anche da altri client.

Per creare un repository locale basta creare la cartella, spostarci al suo interno e dare da terminale il comando `git init`.

A questo punto il nostro repository verrà inizializzato e da qui in poi potremo lavorarci



<br>



# Capitolo 2 - Nuovi nodi

A questo punto avremo il nostro repository, ma manca ancora la parte fondamentale, i file!

Creiamo, spostiamo, scriviamo, andiamo a popolare la nostra cartella con tutto ciò di cui abbiamo bisogno e quando avremo finito dovremo dire a git quali file prendere in considerazione dando il comando `git add "nome del file"`  oppure `git add .` per aggiungere tutti i file all'area di staging, e se vogliamo portare indietro qualcosa dall'area di staging possiamo digitare il comando `git restore --staged nome_del_file`

Ora che abbiamo i nostri file dobbiamo creare uno stage, una "versione nel tempo", del nostro repository e lo facciamo tramite il comando `git commit` e ci si aprirà un editor dove andare a scrivere il nostro commit, ovvero il testo che racchiude cosa abbiamo fatto, quali modifiche a quali file, e dovrà essere esplicativo in modo da rendere più facile lavorarci durante il tempo. 

In alternativa possiamo digitare `git commit -m "testo del commit"`.

Esiste un comando per velocizzare l'aggiunta e il commit dei file ed è `git commit -am "testo del commit"`.



<br>



# Capitolo 3 - Questione di tempo

Quando creiamo un commit è come se aggiungessimo un nodo alla nostra linea temporale.

Se ad esempio ho un file contenente una storia, per esempio:

> Cappuccetto rosso va nel bosco.

E volessi aggiornare il file in modo che contenga per esempio:

> Cappuccetto rosso va nel bosco.
>
> Cappuccetto rosso incontra il lupo.

Devo creare un nuovo nodo nella linea temporale, e per farlo mi basta aggiungere il file modificato all'area di staging e farne il commit.

Quando il commit sarà creato, il mio puntatore, l'HEAD, si sposterò verso il nuovo nodo



<br>



# Capitolo 4 - Muoversi nel tempo

## Capitolo 4.1 - Avanti e indietro nella linea temporale

Prima o poi qualcuno commetterà un errore e cappuccetto rosso verrà mangiato dal lupo, ma grazie a git potremo spostarci ad una versione precedente della nostra storia in cui ciò non è ancora successo.

Per farlo dovremo spostare la "testa", il puntatore a cui git fa riferimento , al suo codice univoco, digitando il comando `git checkout "numero_commit"`, il codice univoco a cui potremo attingere è uno sha1, un codice crittografato di 40 caratteri.

In alternativa possiamo utilizzare il comando `git checkout HEAD^` per spostarci indietro di un solo commit.

Per andare in avanti all'ultimo commit basta digitare `git checkout nome_del_branch` o `git checkout -`



## Capitolo 4.2 - Dove trovo lo sha1 del commit?

Per vedere lo storico dei commit che ho creato nel tempo mi basta digitare il comando `git log`, esso mi restituirà in ordine cronologico tutti i commit che ho eseguito a partire dal più recente.

Il log è strutturato su 4 righe, in cui abbiamo:

1. commit e il relativo sha1, se presente troveremo anche il puntatore e il branch;
2. l'autore del commit, con nome utente e email;
3. data e ora del commit;
4. testo del commit.

Il problema principale di questo comando è che potrebbe risultare un po' confusionario e dispersivo, possiamo ovviare a questo problema aggiungendo il parametro "oneline" al comando log e scrivendo `git log --oneline` che restituirà la lista strutturata in 2 colonne:

1. a sinistra l'id del commit
2. a destra il testo del commit

Avendo una linea temporale, magari anche piuttosto lunga e complessa, avremo bisogno di un modo per viaggiare velocemente al suo interno, come dei portali temporali, chiamati **branches**.

Creiamo un branch con il comando `git branch nome_del_branch` in un punto comodo e poi possiamo spostarci semplicemente digitando `git checkout nome_del_branch`

Ora, quando ci sposteremo tra i nodi dovremo fare attenzione a come lo faremo, digitando infatti il comando `git checkout nome_del_branch` ci sposteremo sul branch e in caso di nuovi commit il branch crescerà con noi e il branch punterà sempre all'ultimo commit, mentre se digiteremo `git branch --detach nome_del_branch` ci sposteremo all'ultimo commit del branch e in caso di nuovi commit la linea temporale crescerà, ma il branch punterà sempre allo stesso commit



<br>



# Capitolo 5 - Linee temporali parallele, i "branch"

Git ci mette a disposizione anche altri strumenti potentissimi, uno fra tutti è quello dei branch, diramazioni, delle linee temporali parallele che ci permettono di sviluppare il progetto in modo indipendente da branch a branch.

Quando digitiamo il comando `git branch nome_del_branch` viene creata una nuova diramazione del nostro repository.

Se noi andiamo a fare il checkout digitando `git checkout nome_del_branch` ci sposteremo sull'etichetta e d'ora in poi ogni nuovo commit sarà aggiunto a questo branch.

La particolarità di questo strumento è che io posso lavorare a due versioni distinte e separate dello stesso progetto, ad esempio se sto scrivendo un software e voglio implementare delle funzioni posso creare un branch per lo sviluppo e rimanere le versioni stabili sul branch master finché non avrò finito con lo sviluppo.

Quando saremo soddisfatti del nostro branch e queste funzioni vogliamo implementare sul branch master possiamo fare il merge e fondere le due diramazioni con il comando `git merge branch_1 branch_2` e git cercherà di unire i file presenti nei due branch in uno solo 
