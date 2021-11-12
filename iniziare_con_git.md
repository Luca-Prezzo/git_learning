# Iniziare con Git





- # Prefazione

    **Git** è una VCS (Version Control System), ovvero un programma che ti permette di avere pieno controllo sulle versioni di un progetto nel tempo.

    La peculiarità di un VCS è che, in caso tu ne abbia bisogno, ti permette di ripristinare i file o anche l'intero progetto ad uno stato precedente, revisionare le modifiche fatte nel tempo, in caso di condivisione del progetto anche di vedere chi ha cambiato qualcosa, chi ha introdotto una funzionalità, un problema, chi ha eliminato un file importante e anche di recuperarlo in caso ti serva.<br><br>



- # Capitolo 1 - La creazione

    Nel nostro caso useremo **Git**, il più famoso VCS, che ci permetterà di creare un repository locale, che sarà la casa del nostro progetto, mentre per la parte server del progetto utilizzeremo <a href="https://github.com">**Github**</a> che metterà il nostro repository online e noi potremmo accedervi e sincronizzarci anche da altri client.

    Per creare un repository locale basta creare la cartella, spostarci al suo interno e dare da terminale il comando `git init`.

    A questo punto il nostro repository verrà inizializzato e da qui in poi potremo lavorarci



- # Capitolo 2 - Il nostro primo commit

    A questo punto avremo il nostro repository, ma manca ancora la parte fondamentale, i file!

    Creiamo, spostiamo, scriviamo, andiamo a popolare la nostra cartella con tutto ciò di cui abbiamo bisogno e quando avremo finito dovremo dire a git quali file prendere in considerazione dando il comando `git add "nome del file"`  oppure `git add .` per aggiungere tutti i file.

    Ora che abbiamo i nostri file dobbiamo creare uno stage, una "versione nel tempo", del nostro repository e lo facciamo tramite il comando `git commit` e ci si aprirà un editor dove andare a scrivere il nostro commit, ovvero il 

