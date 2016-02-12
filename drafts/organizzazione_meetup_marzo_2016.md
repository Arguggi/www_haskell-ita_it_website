## Meetup Marzo 2016

Documento in stile work-in-progress per l'organizzazione del Meetup Haskell-ITA di Marzo 2016.

### Quando e Dove

Saremo ospitati da https://www.develer.com/

    Develer Srl
    via Mugellese 1/A
    50013 Campi Bisenzio - Firenze - Italia

TODO indicare data precisa. Guardando il Doodle sarà l'ultimo o penultimo Sabato di Marzo

TODO indicare orari treno che va da Firenze centrale a Develer.

TODO indicare orario di fine preciso, di modo che le persone possano prenotare il treno preciso e poter fare il viaggio di ritorno insieme

TODO preparare locandina evento, da dare Pasqualino Assini da distribuire nelle bacheche delle università e simili

### Programma

#### Talk

TODO inserire dettagli talk di Luca. Ci saranno esercizi o talk puro con domande?

#### Coding with Mentor 

La proposta è di fare dei gruppetti di lavoro ristretti (2-6 persone, ideale 3-4) per lavorare su qualcosa di concreto, approfondire la conoscienza del linguaggio attraverso il confronto e divertirsi un pó rispetto ad un talk passivo. 

Invece di avere un esercizio/progetto comune, si è pensato di creare diversi gruppi con un mentor che propone lui il tema e fa un pó da guida (mentor).

Portate quindi il portatile, con un ambiente Haskell.

TODO è una proposta, sembra passata, ma si accettano critiche e contro proposte.

##### Proposta Luca 

Penso che durante il prossimo incontro oltre a qualche talk potremmo organizzare un gruppo per contribuire a un progetto open source scritto in Haskell, in modo da dare effettivamente qualcosa indietro alla comunità e programmare su una code base matura.

Personalmente mi propongo per fare mentoring e seguire un gruppo che si occuperà di provare a contribuire qualche cosa su Stack, prendendo dalla lista di issue aperti per neofiti di GitHub.

https://github.com/commercialhaskell/stack/issues?q=is%3Aopen+is%3Aissue+label%3Anewcomer

Obiettivo: una pull request. Ce la faremo? Chissà.
Non siate timidi orsù e fatemi sapere che ci organizziamo.

##### Proposta Massimo

Guardare insieme Functional Reactive Programming, in particolare NetWire https://wiki.haskell.org/Netwire, che è una FRP arrow-based, e completare degli esempi di Robot specificati usando https://github.com/massimo-zaniboni/hrobots

##### Proposta Titto

Sto lavorando ad un semplice sistema di scambio dati. E' una sorta di twitter ma in cui i messaggi sono valori di tipi ben definiti.

Molto brevemente, il sistema consente a qualsiasi utente di:

* definire uno o piu' tipi dati e registrarli presso il sistema.
* inviare valori di uno qualunque dei tipi registrati.
* ricevere tutti i valori di un certo tipo (opzionalmente anche filtrandoli sulla base del valore di alcuni campi)

E' una struttura semplice ma molto flessibile.

Supponiamo ad esempio che uno voglia implementare una chat intelligente, tipo Haskel lRC, da usare magari proprio durante il nostro incontro.

Un semplice modello dati potrebbe essere qualcosa cosa come:

    -- Protocol for a simple chat system
    data Chat = ChatEntry {
                       fromUser::String
                      ,subject::Subject
                      ,message::Message}

    -- Hierarchical subject
    -- Example: Subject ["Haskell","Meeting","Firenze","Marzo 2016","Stack Development"]
    data Subject = Subject [String] 

    -- Different kind of messages
    data Message = TextMessage String
                 | HaskellSearch String
                 | HaskellExpression String


L'esercizio consiste nel:

* creare un modello e registrarlo 
* creare una semplice interfaccia utente per creare messaggi e per visualizzarli
* creare qualche (ro)bot che quando vede un valore di un tipo particolare reagisce in maniera intelligente. Ad esempio se si tratta di una  HaskellExpression, la valuta e ritorna il risultato o quando vede una HaskellSearch fa la ricerca su Hoogle e ritorna il risultato.

Credo che un esercizio cosi' dovrebbe fornire materiale sufficiente tanto per utenti nuovi che per quelli più smaliziati.

Dopo aver creato il modello tutti insieme, dato che le varie funzionalita' di input/output ed elaborazione sono indipendenti una dall'altra, ognuno può scegliere il pezzo che preferisce, più o meno difficile, e lavorare in parallelo.

##### Esercizi semplici per chi è all'inizio

Problema: ci saranno al meetup anche alcune persone che non conoscono Haskell o sono ai primissimi passi. In questo caso partire da progetti più o meno reali, rischia di essere troppo difficile. Ci vorrebbe qualcuno disposto a seguire chi è all'inizio e fare magari qualche esercizio canonico che si trova nel WEB.

##### Proposte varie in cerca di un Mentor

###### Lenses

Studiare una libreria gia' esistente, magari una libreria di uso generale teoricamente ricca ma un po' ostica come "lens", sarebbe un ottimo esercizio.

###### Haskell Extensions

Sulla base di un vecchio post di Luca, mi piacerebbe studiare (anche senza mentor iniziale, quindi anche semplicemente "insieme") e applicare questo articolo su Haskell avanzato, e il suo uso nel scrivere query SQL corrette. http://ren.zone/articles/opaleye-sot Parla di come usare il type system di Haskell (in una sua variante avanzata, con GADT etc...) per scrivere delle query SQL "corrette", cercando di dare una definizione anche di cosa vuol dire scrivere una query corretta.

##### Altre proposte

TODO Sentitevi liberi di proporre quello che preferite, qua o in Mailing-List
