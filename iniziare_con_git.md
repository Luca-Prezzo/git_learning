# Iniziare con Git

# Prefazione

**Git** è una VCS (Version Control System), ovvero un programma che ti permette di avere pieno controllo sulle versioni di un progetto nel tempo.

La peculiarità di un VCS è che, in caso tu ne abbia bisogno, ti permette di ripristinare i file o anche l'intero progetto ad uno stato precedente, revisionare le modifiche fatte nel tempo, in caso di condivisione del progetto anche di vedere chi ha cambiato qualcosa, chi ha introdotto una funzionalità, un problema, chi ha eliminato un file importante e anche di recuperarlo in caso ti serva.

<br>

# Capitolo 1 - La creazione

Nel nostro caso useremo **Git**, il più famoso VCS, che ci permetterà di creare un repository locale, che sarà la casa del nostro progetto, mentre per la parte server del progetto utilizzeremo <a href="https://github.com">**Github**</a> che metterà il nostro repository online e noi potremmo accedervi e sincronizzarci anche da altri client.

Per creare un repository locale basta creare la cartella, spostarci al suo interno e dare da terminale il comando `git init`.

A questo punto il nostro repository verrà inizializzato e da qui in poi potremo lavorarci

<br>

# Capitolo 2 - Nuovi nodi

A questo punto avremo il nostro repository, ma manca ancora la parte fondamentale, i file!

Creiamo, spostiamo, scriviamo, andiamo a popolare la nostra cartella con tutto ciò di cui abbiamo bisogno e quando avremo finito dovremo dire a git quali file prendere in considerazione dando il comando `git add "nome del file"`  oppure `git add .` per aggiungere tutti i file all'area di staging.

Ora che abbiamo i nostri file dobbiamo creare uno stage, una "versione nel tempo", del nostro repository e lo facciamo tramite il comando `git commit` e ci si aprirà un editor dove andare a scrivere il nostro commit, ovvero il testo che racchiude cosa abbiamo fatto, quali modifiche a quali file, e dovrà essere esplicativo in modo da rendere più facile lavorarci durante il tempo. 

In alternativa possiamo digitare `git commit -m "testo del commit"`.

<br>

# Capitolo 3 - Questione di tempo

Quando creiamo un commit è come se aggiungessimo un nodo alla nostra linea temporale.

Se ad esempio ho un file contenente una storia, per esempio:

> Cappuccetto rosso va nel bosco.

E volessi aggiornare il file in modo che contenga per esempio:

> Cappuccetto rosso va nel bosco.
>
> Cappuccetto rosso incontra il lupo.

Devo creare un nodo nella linea temporale, e per farlo mi basta aggiungere il file modificato all'area di staging e farne il commit.

<br>

# Capitolo 4 - Spostarsi nella linea temporale

Prima o poi qualcuno commetterà un errore e cappuccetto rosso verrà mangiato dal lupo, ma grazie a git potremo spostarci ad una versione precedente della nostra storia in cui ciò non è ancora successo.

Per farlo dovremo spostare la "testa", il puntatore a cui git fa riferimento , digitando il comando `git checkout "numero_commit"`, infatti ogni commit ha un codice univoco a cui potremo attingere per spostarci nel tempo.

In alternativa possiamo utilizzare il comando `git checkout HEAD^` per spostarci indietro di un solo commit.

Per andare in avanti all'ultimo commit basta digitare `git checkout nome_del_branch o `git checkout -`

Avendo una linea temporale, magari anche piuttosto lunga e complessa, avremo bisogno di un modo per viaggiare velocemente al suo interno, come dei portali temporali, chiamati **branches**.

Creiamo un branch con il comando `git branch nome_del_branch` in un punto comodo e poi possiamo spostarci semplicemente digitando `git checkout nome_del_branch`

Ora, quando ci sposteremo tra i nodi dovremo fare attenzione a come lo faremo, digitando infatti il comando `git checkout nome_del_branch` ci sposteremo sul branch e in caso di nuovi commit il branch crescerà con noi e il branch punterà sempre all'ultimo commit, mentre se digiteremo `git branch --detach nome_del_branch` ci sposteremo all'ultimo commit del branch e in caso di nuovi commit la linea temporale crescerà, ma il branch punterà sempre allo stesso commit
