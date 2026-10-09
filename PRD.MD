# PRD di ScuolaChill · Matteo Padesi

<aside>
💡

**Come usare questo template**

Duplica questa pagina e compilala con il tuo team. Dove trovi del testo in _corsivo_, sostituiscilo con il vostro. I callout 💡 sono consigli per te: cancellali prima della consegna da questo markdown.

Il documento ha due parti. Nella prima scrivi **cosa** fa ScuolaChill, nella seconda **come** lo costruirai. Tienile separate. Chi legge la prima parte deve capire tutto senza sapere cos'è Spring Boot.

Un buon PRD sta fra le 15 e le 25 pagine. Se ne scrivi di più, probabilmente stai descrivendo invece di decidere.

</aside>

---

## Informazioni sul documento

|              |                                      |
| ------------ | ------------------------------------ |
| **Prodotto** | ScuolaChill                          |
| **Team**     | Matteo Padesi — sviluppo individuale |
| **Autori**   | Matteo Padesi                        |
| **Versione** | _1.0_                                |
| **Data**     | 23/09/2026                           |
| **Stato**    | Bozza                                |

### Storico delle versioni

| Versione | Data       | Autore        | Cosa è cambiato e perché |
| -------- | ---------- | ------------- | ------------------------ |
| 1.0      | 23/09/2026 | Matteo Padesi | Prima stesura            |

<aside>
💡

Il PRD cambierà durante l'anno. Ogni modifica va registrata qui, con la sua ragione. Un PRD che dice una cosa mentre il codice ne fa un'altra è peggio di nessun PRD.

</aside>

---

# Prima parte · Il cosa

## Scopo e perimetro

### Perché esiste ScuolaChill

**Dal lato business.** A scuola materiale didattico, verifiche e voti passano spesso da strumenti diversi: email, chat, cartelle condivise, moduli online. ScuolaChill li riunisce in un solo posto. Il Direttore vede l'andamento della scuola senza chiedere i dati a ogni docente. I docenti preparano materiale, verifiche e voti senza fare lo stesso lavoro due volte. Gli studenti trovano in un'unica app, anche da smartphone, tutto ciò che serve per studiare e i propri voti.

**Dal lato tecnico.** Il sistema copre principalmente quattro aree: account e classi, materiale didattico, verifiche, voti e medie. Ogni utente vede solo ciò che serve al suo ruolo: Direttore, Docente o Studente. Si usa dal browser, sia da PC sia da smartphone, ed è pubblicato su internet, così che possa essere collaudato da utenti reali.

### Cosa è incluso

- Accesso (login e logout) con account creati dal Direttore: nessuno si registra da solo
- Recupero della password dimenticata via email
- Creazione degli account di docenti e studenti da parte del Direttore, con invio via email delle credenziali di primo accesso
- Gestione delle classi: composizione, assegnazione dei docenti per materia, trasferimento degli studenti, materie facoltative come religione
- Panoramica della scuola per il Direttore: classi, docenti, studenti, andamento dei voti
- Caricamento del materiale didattico da parte dei docenti e consultazione da parte degli studenti, per classe e materia
- Verifiche: materiale che il docente segna come verifica, con un orario di apertura e uno di chiusura, l'eventuale consegna dell'elaborato da parte dello studente e la riapertura a scelta del docente
- Voti da 1 a 10 con "+", "½" e "−", giudizi per religione e attività alternativa, medie per studente, classe e materia
- Passaggio al nuovo anno scolastico, con archivio degli anni precedenti

### Cosa non è incluso

- **Scrutini, pagelle e registro ufficiale.** Le medie di ScuolaChill servono a orientarsi e non hanno valore ufficiale.
- **Genitori.** Non hanno un account, e ScuolaChill non invia comunicazioni alle famiglie.
- **Messaggi fra utenti.** ScuolaChill non è uno strumento per comunicare: niente chat né bacheche.
- **Assenze, presenze e giustificazioni.**
- **Orario delle lezioni e calendario.**
- **Rette e pagamenti.**

<aside>
💡

La lista di cosa **non** è incluso è la più preziosa del documento. Ogni riga qui ti evita una settimana di discussioni più avanti.

</aside>

---

## Stakeholder

| Stakeholder                 | Cosa fa                                                                   | Cosa gli interessa                                          | Come lo coinvolgete                   |
| --------------------------- | ------------------------------------------------------------------------- | ----------------------------------------------------------- | ------------------------------------- |
| Direttore                   | Dirige la scuola, crea account e classi, ha visione d'insieme             | Poco tempo, vuole vedere tutto senza entrare in ogni pagina | Intervista + collaudo finale          |
| Docenti                     | Insegna una o più materie, carica materiale, crea verifiche, assegna voti | Fare le operazioni quotidiane senza attrito                 | Collaudo con un docente reale         |
| Studenti                    | Consulta materiale, svolge verifiche, controlla i voti                    | Trovare tutto in un posto, non perdere voti                 | Collaudo con i ragazzi del primo anno |
| Docente del corso           | Valida il PRD                                                             | Che le scelte siano motivate e coerenti fra loro            | Presentazione e domande               |
| Collaudatori del primo anno | Usano ScuolaChill come utenti reali                                       | Che sia semplice da usare, anche da smartphone              | _Intervista, collaudo_                |
| _Altri?_                    |                                                                           |                                                             |                                       |

<aside>
💡

Gli stakeholder non sono solo gli utenti. Sono anche chi approva, chi paga, chi manterrà il sistema. Chiediti chi resterebbe deluso se ScuolaChill non funzionasse.

</aside>

---

## Destinatari e contesto d'uso

### La scuola che avete immaginato

Progetto ScuolaChill per un istituto reale, quello che frequento: il **CFP Don Bosco** di San Donà di Piave.

- **Molte ore si passano in laboratorio**, nei settori elettrico, termoidraulico, informatico, meccanico e automotive. Docenti e studenti non sono sempre seduti davanti a un computer, quindi lo smartphone conta quanto il PC.
- **I percorsi non durano tutti uguale**: alcuni finiscono dopo tre anni, altri dopo quattro.

|                    | Valore                                                                                                                                                                                   |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Tipo di istituto   | Centro di formazione professionale (IeFP)                                                                                                                                                |
| Percorsi           | 10: cinque qualifiche di tre anni e cinque diplomi di quattro anni                                                                                                                       |
| Numero di studenti | 900 _(stima, ASS-01)_                                                                                                                                                                    |
| Numero di docenti  | 40 _(stima, ASS-01)_                                                                                                                                                                     |
| Numero di classi   | 36, in media 25 studenti ciascuna _(stima, ASS-01)_                                                                                                                                      |
| Orario scolastico  | Lezioni la mattina, dalle 8:00 alle 13:00, sei giorni su sei (lunedì–sabato); in due o tre pomeriggi a settimana si torna per i laboratori                                               |
| Connettività       | Una sola rete Wi-Fi della scuola, in comune fra aule e laboratori, che rallenta quando molti dispositivi sono collegati. Per questo molti usano la connessione dati del proprio telefono |

### Gli archetipi

Arricchisci gli archetipi della traccia.

| ID      | Archetipo | Contesto d'uso                                                      | Competenze digitali                                                                | Dispositivo principale       | Frequenza d'uso                                                                                                               |
| ------- | --------- | ------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| ARC-001 | Direttore | Ufficio, tempo limitato                                             | Medie, abituato a usare il PC per lavoro, vuole comunque viste rapide e sintetiche | PC                           | Più volte a settimana, con picchi a inizio anno (creazione classi) e sessioni più brevi per avere una panoramica della scuola |
| ARC-002 | Docente   | In classe o a casa                                                  | Variabili, sopratutto in base all'età                                              | PC (principale) e smartphone | Più volte a settimana, con picchi dopo ogni verifica (assegnazione voti)                                                      |
| ARC-003 | Studente  | A scuola fra le lezioni, durante l'intervallo o a casa per studiare | Alte, sopratutto per quanto riguarda lo smartphone                                 | PC e smartphone (principale) | giornaliera, uso sia breve (vedere voti), che lungo (vedere materiale scolastico)                                             |

<aside>
💡

I collaudatori veri sono i ragazzi del primo anno. Usano lo smartphone in corridoio o il PC in laboratorio? La risposta cambia l'interfaccia, i requisiti di usabilità e perfino il dimensionamento.

</aside>

---

## Panoramica e casi d'uso

### ScuolaChill in poche righe

ScuolaChill è il posto unico in cui la scuola gestisce materiale, verifiche e voti. A inizio anno il Direttore crea gli account e le classi, e da una sola pagina vede come va la scuola: le classi, i docenti, l'andamento dei voti. I docenti caricano il materiale e le verifiche, decidono quando una verifica si apre e si chiude, e registrano i voti. Gli studenti trovano tutto in un posto, anche dal telefono: il materiale per studiare, le verifiche da svolgere e consegnare, i propri voti con le medie. A fine anno, con pochi passaggi, le classi passano all'anno successivo senza perdere nulla.

### User flow e scenari

#### Direttore (ARC-001)

**DIR-01 — Creare account docente:** Come Direttore voglio creare gli account dei docenti così da dare al personale l'accesso al sistema con il ruolo corretto.

**User flow**

1. Il direttore accede a Scuola Chill
2. Apre la sezione "crea account"
3. Sceglie "docente"
4. Inserisce nome, cognome, data di nascita, email, materie insegnate e le classi in cui insegna (opzionale, viene segnalato in seguito per ricordare di aggiungere il dato). È la stessa assegnazione che si fa componendo una classe (DIR-03): farla da una parte la rende visibile anche dall'altra
5. Se un campo è vuoto o non valido, il sistema lo evidenzia e non crea l'account; altrimenti crea l'account con ruolo Docente e lo aggiunge all'elenco dei docenti
6. Al docente arriva una mail con un link per accedere alla piattaforma e le credenziali di primo accesso, con una password temporanea (se la mail non parte vale FR-EST-01)

**Scenario principale.** A scuola arriva un nuovo docente di matematica. Il direttore crea un nuovo account docente inserendo i suoi dati, mette "matematica" come materia e salta la sezione riguardante le classi per farla in seguito non appena sarà deciso in che classe farlo insegnare. Una volta conclusa la creazione del nuovo account, al nuovo docente arriva una mail con link e credenziali del suo account. Il nuovo docente apre il link che lo porta direttamente nella schermata di accesso e inserisce le credenziali scritte nella mail. ScuolaChill gli chiede subito di sostituire la password temporanea con una sua; fatto questo, accede al suo account personale.

**Scenari alternativi.** _Cosa succede quando qualcosa va storto? Connessione che cade, scadenza superata, doppia scheda aperta…_

**DIR-02 — Creare account studente:** Come Direttore voglio creare gli account degli studenti così da permettere a ogni iscritto di usare l'applicazione.

**User flow**

1. Il Direttore accede a ScuolaChill
2. Apre la sezione "crea account"
3. Sceglie "studente"
4. Inserisce nome, cognome, data di nascita, email e classe (opzionale, viene segnalato in seguito per ricordare di aggiungere il dato). Scegliere qui la classe equivale ad aggiungere lo studente alla classe in DIR-03, con le stesse regole (FR-CLA-01)
5. Se un campo è vuoto o non valido, il sistema lo evidenzia e non crea l'account; altrimenti crea l'account con ruolo Studente e lo aggiunge all'elenco degli studenti
6. Allo studente arriva una mail con un link per accedere alla piattaforma e le credenziali di primo accesso, con una password temporanea (se la mail non parte vale FR-EST-01)

**Scenario principale.** A scuola si iscrive un nuovo studente. Il direttore crea un nuovo account studente inserendo i suoi dati, salta la sezione riguardante la classe e la aggiungerà in seguito non appena avrà deciso in che classe inserirlo. Una volta conclusa la creazione del nuovo account, al nuovo studente arriva una mail con link e credenziali del suo account. Il nuovo studente apre il link che lo porta direttamente nella schermata di accesso e inserisce le credenziali scritte nella mail. ScuolaChill gli chiede subito di sostituire la password temporanea con una sua; fatto questo, accede al suo account personale.

**Scenari alternativi.** _Cosa succede quando qualcosa va storto? Connessione che cade, scadenza superata, doppia scheda aperta…_

**DIR-03 — Creare classi e comporle:** Come Direttore voglio creare le classi e assegnarvi studenti e docenti con le rispettive materie così da riprodurre l'organizzazione reale della scuola.

**User flow**

1. Il Direttore accede a ScuolaChill
2. Apre la sezione "Classi" e sceglie "Nuova classe"
3. Inserisce il nome della classe (es. 1A) e l'anno scolastico; nello stesso anno scolastico non possono esistere due classi con lo stesso nome
4. Aggiunge gli studenti scegliendoli dall'elenco
5. Per ogni materia, sceglie il docente che la insegna in quella classe (opzionale, si può fare anche in seguito). È la stessa assegnazione che si può fare creando l'account del docente (DIR-01)
6. Conferma; la classe compare nell'elenco con il numero di studenti
7. Se uno studente è già in un'altra classe, il sistema lo segnala e propone il trasferimento (vedi FR-CLA-01)

**Scenario principale.** _Racconta il caso in cui tutto va bene, con un personaggio e una situazione concreta._

**Scenari alternativi.** _Cosa succede quando qualcosa va storto? Connessione che cade, scadenza superata, doppia scheda aperta…_

**DIR-04 — Vedere tutto:** Come Direttore voglio una vista complessiva su classi, docenti, studenti e voti così da monitorare l'andamento della scuola senza entrare in ogni singola pagina.

**User flow**

1. Il Direttore accede a ScuolaChill
2. Apre la "Panoramica"
3. Vede in una sola pagina: le classi con il numero di studenti, i docenti con le loro materie, l'andamento dei voti (medie per classe e per materia, FR-VOT-03)
4. Se vuole i dettagli, apre un elenco completo, diviso in pagine

**Scenario principale.** _Racconta il caso in cui tutto va bene, con un personaggio e una situazione concreta._

**Scenari alternativi.** _Cosa succede quando qualcosa va storto? Connessione che cade, scadenza superata, doppia scheda aperta…_

#### Docente (ARC-002)

**DOC-01 — Caricare materiale didattico:** Come Docente voglio caricare il materiale didattico per le mie materie e classi così da metterlo a disposizione degli studenti in un posto solo.

**User flow**

1. Il Docente accede a ScuolaChill
2. Apre "classi" e sceglie la classe interessata
3. Sceglie la materia
4. Seleziona "Carica materiale", sceglie il file e gli dà un titolo
5. Conferma
6. Il materiale compare nell'elenco della materia, visibile agli studenti di quella classe

**Scenario principale.** _Racconta il caso in cui tutto va bene, con un personaggio e una situazione concreta._

**Scenari alternativi.** _Cosa succede quando qualcosa va storto?_

**DOC-02 — Creare le proprie verifiche:** Come Docente voglio creare verifiche per le mie classi così da valutare gli studenti sulle mie materie.

**User flow**

1. Il Docente accede a ScuolaChill
2. Apre "classi" e sceglie la classe interessata
3. Sceglie la materia
4. Seleziona "Carica materiale", sceglie il file, gli dà un titolo e lo segna come verifica (FR-VER-01)
5. Indica data e ora di apertura e di chiusura (FR-VER-02) e se gli studenti devono consegnare un elaborato
6. Salva
7. La verifica compare fra quelle della classe: gli studenti ne vedono titolo e orari, ma possono aprire il file solo dall'apertura alla chiusura

**Scenario principale.** _…_

**Scenari alternativi.** _Cosa succede quando il docente prova a modificare una verifica già aperta (regola in FR-VER-03)._

**DOC-03 — Assegnare i voti:** Come Docente voglio assegnare i voti delle mie verifiche così da registrare formalmente la valutazione di ogni studente.

**User flow**

1. Il Docente accede a ScuolaChill
2. Apre una sua verifica
3. Vede l'elenco degli studenti della classe che seguono la materia (FR-MAT-01); se la verifica prevede la consegna, per ciascuno vede se ha consegnato e può aprire il suo elaborato
4. Inserisce il voto di ogni studente (es. 6½ o 7−, scala in FR-VOT-01), oppure il giudizio nelle materie che lo prevedono (FR-VOT-02)
5. Salva: il voto diventa visibile allo studente

**Scenario principale.** _…_

**Scenari alternativi.** _…_

#### Studente (ARC-003)

**STU-01 — Consultare il materiale didattico:** Come Studente voglio consultare il materiale caricato da ogni docente delle mie materie così da avere tutto ciò che serve per studiare in un unico posto.

**User flow**

1. Lo Studente accede a ScuolaChill
2. Apre la sezione "Materie" e sceglie una materia
3. Vede l'elenco del materiale caricato dal docente
4. Apre o scarica il materiale che gli serve

**Scenario principale.** _…_

**Scenari alternativi.** _…_

**STU-02 — Svolgere una verifica:** Come Studente voglio svolgere le verifiche assegnate alla mia classe così da essere valutato sulle materie che seguo.

**User flow**

1. Lo Studente accede a ScuolaChill
2. Apre la sezione "Verifiche" e vede quelle della sua classe, con orari di apertura e chiusura
3. Quando la verifica è aperta, apre il file e la svolge
4. Se la verifica prevede la consegna, carica il suo elaborato (un documento o la foto del foglio) prima della chiusura
5. Il sistema conferma che la consegna è avvenuta; da quel momento non può più consegnare di nuovo

**Scenario principale.** _…_

**Scenari alternativi.** _Cosa succede quando la connessione cade mentre carica la consegna (regola in FR-VER-04)._

**STU-03 — Consultare i propri voti:** Come Studente voglio consultare i miei voti raggruppati per materia così da sapere come sto andando in ciascuna.

**User flow**

1. Lo Studente accede a ScuolaChill
2. Apre la sezione "I miei voti"
3. Vede i voti raggruppati per materia, ognuno con la verifica da cui proviene, e la media di ogni materia (FR-VOT-03)

**Scenario principale.** _…_

**Scenari alternativi.** _…_

---

## Requisiti funzionali

### Le user story della traccia

| ID     | Storia                            | AC aggiunti dal team | Note |
| ------ | --------------------------------- | -------------------- | ---- |
| DIR-01 | Creare account docente            | _…_                  | _…_  |
| DIR-02 | Creare account studente           | _…_                  | _…_  |
| DIR-03 | Creare classi e comporle          | _…_                  | _…_  |
| DIR-04 | Vedere tutto                      | _…_                  | _…_  |
| DOC-01 | Caricare materiale didattico      | _…_                  | _…_  |
| DOC-02 | Creare le proprie verifiche       | _…_                  | _…_  |
| DOC-03 | Assegnare i voti                  | _…_                  | _…_  |
| STU-01 | Consultare il materiale didattico | _…_                  | _…_  |
| STU-02 | Svolgere una verifica             | _…_                  | _…_  |
| STU-03 | Consultare i propri voti          | _…_                  | _…_  |

<aside>
💡

Gli acceptance criteria della traccia sono il minimo. Puoi aggiungerne, non toglierne. Scrivi quelli nuovi nello stesso formato _Dato che / Quando / Allora_.

</aside>

### Le decisioni lasciate aperte dalla traccia

La traccia lascia alcune scelte a te. Ognuna diventa un requisito con il suo ID. Usa questo formato.

> **FR-[AREA]-[NN] · [Titolo]** (collegato a _ID della storia_)
> _Cosa avete deciso, in modo verificabile.Motivazione:_ _perché avete scelto così._

I punti che devi decidere almeno sono questi.

- [x] La scala dei voti (DOC-03). Da quanto a quanto, con quale passo, se ammette segni come "+" e "−".
- [x] Il trasferimento di uno studente fra classi (DIR-03). Si può fare? Cosa succede ai voti?
- [x] La modifica di una verifica dopo lo svolgimento (DOC-02).
- [x] La connessione che cade durante una verifica (STU-02).
- [x] Il fallimento del servizio esterno (per esempio l'email delle credenziali).
- [x] Le materie che non tutti seguono, come religione.
- [x] Il passaggio al nuovo anno scolastico.
- [x] Il tipo di domande delle verifiche e la loro correzione.
- [x] Dove si vedono le medie e come si calcolano.
- [x] Cosa succede se un utente dimentica la password.

> **FR-VOT-01 · Scala dei voti** (collegato a DOC-03, STU-03)
> I voti vanno da 1 a 10 e usano la stessa notazione del registro: un numero intero, eventualmente seguito da "+", "½" o "−". Ogni simbolo ha un valore fisso usato per calcolare le medie: "+" vale +0,25, "½" vale +0,5, "−" vale −0,25. Quindi 6+ = 6,25, 6½ = 6,5, 7− = 6,75. Il voto più basso è 1 e il più alto è 10: "1−" e "10+" non esistono. Un voto fuori da questa scala viene rifiutato con un messaggio che indica i valori ammessi. Fanno eccezione le materie valutate con giudizio (FR-VOT-02).
> **Motivazione:** è la notazione che docenti e studenti usano già ogni giorno, quindi nessuno deve impararne una nuova. Fissare il valore di ogni simbolo rende le medie uguali per tutti e verificabili.

> **FR-CLA-01 · Trasferimento di uno studente fra classi** (collegato a DIR-03)
> Uno studente appartiene a una sola classe alla volta. Se il Direttore prova ad aggiungerlo a una seconda classe, il sistema lo impedisce e indica la classe attuale. Per spostarlo il Direttore usa un'azione apposita, "Trasferisci", che chiede conferma. Dopo il trasferimento lo studente vede solo materiale e verifiche della nuova classe. I voti già registrati restano suoi: continua a vederli, con materia e verifica di provenienza, e il Direttore li vede nella sua panoramica.
> **Motivazione:** i cambi di classe capitano davvero (cambio di sezione o di indirizzo). I voti appartengono allo studente, non alla classe: perderli o nasconderli sarebbe un errore grave. Un'azione separata con conferma evita trasferimenti fatti per sbaglio.

> **FR-VER-01 · Cos'è una verifica e come si corregge** (collegato a DOC-01, DOC-02, DOC-03, STU-02)
> Una verifica è un materiale didattico che il docente, quando lo carica, segna come verifica per distinguerlo dal materiale normale e dai compiti. Come ogni materiale ha un titolo e un file, e appartiene a una classe e a una materia. In più ha una data e ora di apertura e una di chiusura (FR-VER-02). ScuolaChill non crea domande e non corregge nulla. Per ogni verifica il docente sceglie la modalità:
>
> - **con consegna**: lo studente svolge la verifica e carica il suo elaborato (un documento o la foto del foglio) prima della chiusura. Può consegnare una sola volta;
> - **senza consegna**: la verifica si svolge fuori da ScuolaChill, su carta, in laboratorio o con uno strumento esterno come Google Moduli (il docente può scriverne il link nel file o nella descrizione). ScuolaChill serve a mettere a disposizione il testo e a registrare i voti.
>
> In entrambi i casi il voto lo assegna il docente, a ogni studente della classe che segue la materia (FR-MAT-01), con la scala di FR-VOT-01 o con un giudizio (FR-VOT-02). Lo studente vede il voto da quando il docente lo salva. Il materiale normale, invece, non ha voti.
> **Motivazione:** Oggi manca un posto unico dove trovare il testo delle verifiche, raccogliere le consegne e registrare i voti. La modalità senza consegna copre le prove pratiche di laboratorio, frequenti in un CFP, e le verifiche su carta: così anche i loro voti finiscono in ScuolaChill e nelle medie.

> **FR-VER-02 · Apertura, chiusura e riapertura di una verifica** (collegato a DOC-02, STU-01, STU-02)
> Prima dell'apertura gli studenti vedono la verifica nell'elenco, con titolo e orari, ma non possono aprire il file. Fra apertura e chiusura possono aprirlo e, se previsto, consegnare. Dopo la chiusura il file non si può più aprire e le consegne non sono più accettate. Il blocco vale anche se lo studente prova ad aprire il file con un link diretto, senza passare dall'elenco.
> Il docente può riaprire una verifica chiusa, per tutta la classe o solo per alcuni studenti, fino a una nuova data e ora di chiusura. Quando la riapre sceglie fra:
>
> - **solo consultazione**: gli studenti possono aprire il file, per esempio per ripassare dopo la correzione, ma non consegnare;
> - **consultazione e consegna**: chi non ha ancora consegnato può farlo, per esempio uno studente assente il giorno della verifica. Chi ha già consegnato non può consegnare di nuovo (STU-02 AC-02).
>
> Le consegne arrivate durante una riapertura sono segnate come tali, così il docente sa che sono arrivate dopo la chiusura originale.
> **Motivazione:** il testo di una verifica non deve girare prima che inizi, né restare aperto dopo, quando qualcuno potrebbe ancora svolgerla conoscendo già le soluzioni. Riaprire solo per alcuni studenti risolve il caso dello studente assente senza riaprire per tutti. Distinguere consultazione e consegna permette di usare la verifica per ripassare senza accettare per sbaglio consegne in ritardo.

> **FR-VER-03 · Modifica di una verifica dopo lo svolgimento** (collegato a DOC-02, DOC-03)
> Prima dell'apertura il docente può modificare tutto: titolo, file, orari e modalità. Dall'apertura in poi file e modalità non si possono più cambiare: il docente può solo spostare la chiusura, riaprire la verifica (FR-VER-02) e assegnare i voti. Se si accorge di aver caricato il file sbagliato, può eliminare la verifica, ma solo finché nessuno ha consegnato e non ci sono voti, e poi crearne una nuova. Quando il docente salva una verifica, il sistema gli ricorda da quando non sarà più modificabile.
> **Motivazione:** è la regola più equa. Tutti gli studenti devono svolgere la stessa verifica, altrimenti i voti non sono confrontabili. Eliminare una verifica con consegne o voti cancellerebbe il lavoro degli studenti.

> **FR-VER-04 · Connessione che cade durante la consegna** (collegato a STU-02)
> La consegna è valida solo quando il file è arrivato per intero e lo studente vede la conferma a schermo. Se la connessione cade mentre lo carica, la consegna non avviene: lo studente vede l'errore e può riprovare finché la verifica è aperta. Il lavoro non si perde, perché l'elaborato resta sul suo dispositivo o sul foglio. Se la verifica si chiude prima che riesca a consegnare, risulta "non consegnata": lo studente avvisa il docente, che può riaprirla solo per lui (FR-VER-02).
> **Motivazione:** il Wi-Fi scolastico è condiviso e i collaudatori usano spesso lo smartphone, quindi una connessione che cade è un caso frequente, non un'eccezione. Una conferma esplicita evita che uno studente creda di aver consegnato quando non è così. Dopo la chiusura decide il docente, perché conosce la situazione (un guasto della rete di tutta la classe o uno studente che ha lasciato scadere il tempo apposta) e può valutarla caso per caso.

> **FR-EST-01 · Fallimento del servizio che invia l'email delle credenziali** (collegato a DIR-01, DIR-02)
> L'account viene creato anche se l'email non parte: il servizio esterno non può bloccare il lavoro del Direttore. Il sistema ritenta l'invio da solo _3 volte nell'arco di un'ora_. Se tutti i tentativi falliscono, nell'elenco l'account compare come "email non consegnata" e il Direttore ha due possibilità:
>
> - **reinviare l'email**, quando il servizio torna a funzionare;
> - **mostrare le credenziali di primo accesso**: il sistema genera una nuova password temporanea e la mostra a schermo una sola volta, così il Direttore può copiarla, stamparla o consegnarla di persona. La password temporanea precedente smette di funzionare.
>
> In ogni caso, al primo accesso l'utente deve sostituire la password temporanea con una sua. Il sistema non conserva le password in forma leggibile: nessuno, nemmeno il Direttore, può rileggere una password già creata.
> **Motivazione:** un servizio esterno può non rispondere, e il Direttore non deve ricreare l'account né restare bloccato. I tentativi automatici risolvono da soli i guasti brevi. La consegna di persona copre quelli lunghi, ad esempio all'inizio dell'anno, quando vanno creati centinaia di account. Mostrare la password una sola volta e obbligare a cambiarla al primo accesso limita il rischio che qualcuno la veda o la riusi.

> **FR-ACC-01 · Password dimenticata** (collegato a DIR-01, DIR-02 e a tutte le storie che richiedono l'accesso)
> Dalla schermata di accesso l'utente può chiedere di reimpostare la password inserendo la propria email. Il sistema invia un link che vale _30 minuti_ e si può usare una sola volta; aprendolo, l'utente sceglie una nuova password. Il messaggio a schermo è sempre lo stesso, che l'email sia registrata o no. Finché l'utente non sceglie la nuova password, la vecchia resta valida. Se l'email non arriva, l'utente si rivolge al Direttore, che genera nuove credenziali di primo accesso come in FR-EST-01.
> **Motivazione:** con 900 studenti, password dimenticate saranno frequenti, e farle passare tutte dal Direttore lo sommergerebbe di richieste. Un link che scade presto e vale una volta sola limita i danni se qualcuno lo intercetta. Mostrare sempre lo stesso messaggio impedisce di scoprire quali email sono registrate. La strada attraverso il Direttore resta per chi non riceve l'email.

> **FR-MAT-01 · Materie facoltative** (collegato a DIR-03, DOC-01, DOC-02, DOC-03, STU-01, STU-02, STU-03)
> Quando assegna una materia a una classe, il Direttore può segnarla come facoltativa (es. religione o l'attività alternativa) e scegliere quali studenti la seguono. Uno studente che non segue una materia facoltativa non ne vede materiale e verifiche, e non può ricevere voti in quella materia. Il docente di una materia facoltativa vede e valuta solo gli studenti che la seguono. Le materie non facoltative sono seguite da tutta la classe.
> **Motivazione:** non tutti gli studenti fanno religione, e chi non la fa segue spesso un'attività alternativa con un altro docente. Senza questa regola uno studente vedrebbe materiale e verifiche di una materia che non segue, e il docente si troverebbe in elenco studenti che non ha. La regola è generale, quindi vale anche per altre materie facoltative senza casi speciali.

> **FR-VOT-02 · Materie valutate con giudizio** (collegato a DOC-03, STU-03, DIR-04)
> Per ogni materia il Direttore indica il tipo di valutazione: con voto (scala di FR-VOT-01) oppure con giudizio. Religione e attività alternativa sono valutate con giudizio. I giudizi possibili, dal più basso al più alto, sono: insufficiente, sufficiente, discreto, buono, distinto, ottimo. Un valore diverso da questi viene rifiutato. I giudizi non entrano nelle medie numeriche: lo studente li vede nella sua pagina dei voti, nella materia di provenienza, e il Direttore li vede separati dalle medie nella panoramica.
> **Motivazione:** nella scuola italiana religione e attività alternativa si valutano con un giudizio, non con un voto. Il docente reale del collaudo se ne accorgerebbe subito. Tenere i giudizi fuori dalle medie evita di trasformare in numero qualcosa che per regola non lo è.

> **FR-VOT-03 · Medie** (collegato a STU-03, DOC-03, DIR-04)
> La media di una materia è la media dei voti numerici di quella materia nell'anno scolastico in corso, calcolata con i valori di FR-VOT-01 (es. 6+ = 6,25) e arrotondata a due decimali. Tutti i voti hanno lo stesso peso. Le medie sono visibili a tre ruoli:
>
> - lo **studente** vede, nella pagina dei voti, la media di ogni sua materia;
> - il **docente** vede, per ogni sua classe e materia, la media di ciascuno studente e la media della classe;
> - il **Direttore** vede nella panoramica le medie per classe e per materia.
>
> Una materia senza voti non mostra la media (non "0"). I giudizi (FR-VOT-02) non entrano nelle medie. Le medie si aggiornano non appena un voto viene salvato o modificato. Le medie degli anni precedenti restano consultabili nell'archivio (FR-ANN-01).
> **Motivazione:** lo studente capisce subito in quale materia è in difficoltà, il docente ha il quadro della classe senza fare conti a mano e il Direttore vede l'andamento della scuola. Mostrare "0" per una materia ancora senza voti la farebbe sembrare insufficiente.

> **FR-ANN-01 · Passaggio al nuovo anno scolastico** (collegato a DIR-03, DIR-04, STU-03)
> A fine anno il Direttore avvia il "Nuovo anno scolastico". Il sistema propone le classi dell'anno nuovo: ogni classe passa all'anno successivo con la stessa sezione e gli stessi studenti (es. 2A → 3A). Anche le assegnazioni dei docenti e le iscrizioni alle materie facoltative vengono proposte uguali all'anno prima. Prima di confermare, il Direttore può:
>
> - togliere gli studenti non ammessi e spostarli in una classe dello stesso anno (es. dalla 2A dell'anno vecchio alla 2A dell'anno nuovo);
> - togliere gli studenti ritirati;
> - cambiare docenti e iscrizioni alle materie facoltative;
> - creare le nuove classi prime e aggiungervi gli studenti appena iscritti.
>
> Finché il Direttore non conferma, l'anno in corso resta attivo e nulla cambia. Dopo la conferma, le classi dell'anno vecchio vengono archiviate: materiale, verifiche e voti restano consultabili ma non più modificabili. Lo studente ritrova i voti degli anni precedenti in una sezione separata. Gli studenti che hanno finito l'ultimo anno del percorso non possono più accedere, ma i loro voti restano conservati in archivio.
> **Motivazione:** con 36 classi e 900 studenti, ricreare tutto da zero ogni anno sarebbe un lavoro enorme e pieno di errori. La proposta automatica riduce il lavoro del Direttore ai soli casi diversi dalla regola. Archiviare invece di rinominare le classi tiene separati i voti di anni diversi e non perde lo storico. La conferma esplicita evita di cambiare anno per sbaglio a metà anno.

---

## Requisiti non funzionali

Ogni requisito ha una soglia, una condizione e un modo per verificarlo. Ed è collegato ad almeno una user story.

| ID     | Famiglia      | Requisito                                   | Soglia e condizione                                                                                                                    | Come si verifica                                                                   | Storie collegate                                                                                     |
| ------ | ------------- | ------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| NFR-01 | Prestazioni   | _es. Apertura della verifica nel picco_     | _es. meno di 2 s per il 95% delle richieste, 75 utenti nello stesso minuto_                                                            | _Test di carico_                                                                   | _STU-02_                                                                                             |
| NFR-02 | Sicurezza     | Tutto il traffico viaggia su HTTPS          | 100% delle richieste; una richiesta in HTTP viene reindirizzata su HTTPS                                                               | Chiamata a `http://` con Postman: risposta di redirect verso `https://`            | Tutte                                                                                                |
| NFR-03 | Sicurezza     | Controllo dei ruoli nel backend             | Ogni operazione non permessa al ruolo viene negata anche chiamando l'API direttamente, senza passare dall'interfaccia                  | Collezione Postman con una chiamata per ogni ruolo non autorizzato                 | DIR-01..04 AC-03, DOC-01 AC-02, DOC-02 AC-03, DOC-03 AC-03, STU-01 AC-02, STU-02 AC-03, STU-03 AC-02 |
| NFR-04 | Sicurezza     | Nessun segreto nel codice sorgente          | 0 password, chiavi o connection string nel repository                                                                                  | Ricerca nel repository prima di ogni consegna                                      | Tutte                                                                                                |
| NFR-05 | Scalabilità   | Elenchi paginati                            | Ogni elenco restituisce al massimo _N_ elementi per pagina                                                                             | Test Postman sugli elenchi di studenti, materiali e voti                           | DIR-04 AC-02, STU-01, STU-03                                                                         |
| NFR-06 | Interazione   | Errori in formato uniforme                  | 100% delle risposte di errore hanno lo stesso formato e un codice HTTP coerente                                                        | Test Postman sulle risposte di errore                                              | Tutte                                                                                                |
| NFR-07 | Supporto      | API documentate e verificabili              | Ogni API principale è documentata in OpenAPI/Swagger e ha almeno una richiesta nella collezione Postman                                | Confronto fra la documentazione Swagger e la collezione                            | Tutte                                                                                                |
| NFR-08 | Supporto      | Configurazioni Development e Production     | L'applicazione gira in entrambe le configurazioni senza modificare il codice                                                           | Avvio in entrambe le configurazioni                                                | Tutte                                                                                                |
| NFR-09 | Disponibilità | Raggiungibile pubblicamente per il collaudo | _Soglia da decidere (es. disponibile durante l'orario scolastico nei giorni di collaudo)_                                              | _…_                                                                                | Tutte                                                                                                |
| NFR-10 | Usabilità     | _…_                                         | _…_                                                                                                                                    | _…_                                                                                | _…_                                                                                                  |
| NFR-11 | Ambientale    | _…_                                         | _…_                                                                                                                                    | _…_                                                                                | _…_                                                                                                  |
| NFR-12 | Conformità    | Dati personali ridotti al minimo            | Per ogni utente si raccolgono solo nome, cognome, data di nascita (per distinguere gli omonimi) ed email; nessun altro dato anagrafico | Revisione dei campi richiesti nella creazione degli account e nel modello dei dati | DIR-01, DIR-02                                                                                       |

<aside>
💡

Le famiglie da coprire sono queste. **Prestazioni, disponibilità, scalabilità, sicurezza** e **conformità** vengono dalla lezione sui requisiti funzionali e non funzionali. **Usabilità, ambientali, supporto** e **interazione** vengono dalla lezione sul PRD. Se una famiglia resta vuota, scrivi perché non vi riguarda.

I requisiti trasversali della traccia (HTTPS, paginazione, OpenAPI, errori uniformi, Dev e Prod) sono già obbligatori. Riportali qui con il loro ID.

</aside>

### Requisiti impliciti

Prima di chiudere questa sezione, intervista per dieci minuti un ragazzo del primo anno. La domanda è una sola. _"Cosa daresti per scontato che un'app di questo tipo faccia sempre, o non faccia mai?"_

| Chi avete intervistato | Cosa ha detto                     | Requisito che ne avete ricavato |
| ---------------------- | --------------------------------- | ------------------------------- |
| _nome o iniziali_      | _"Il voto non deve sparire, mai"_ | _NFR-…_                         |
|                        |                                   |                                 |

---

## Assunzioni, vincoli e dipendenze

### Assunzioni

Quello che date per vero senza poterlo garantire.

| ID     | Assunzione                                                                                                          | Cosa succede se è falsa                                                                                                                                                                    |
| ------ | ------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ASS-01 | La scuola ha circa 900 studenti, 40 docenti e 36 classi (circa 25 studenti per classe)                              | Stima del carico, dimensionamento e costi vanno rifatti                                                                                                                                    |
| ASS-02 | L'orario è 8:00–13:00 dal lunedì al sabato, con rientri pomeridiani per i laboratori                                | I momenti di picco cambiano: la stima del carico va ricontrollata                                                                                                                          |
| ASS-03 | Ogni studente e ogni docente ha un indirizzo email personale funzionante                                            | Le credenziali di primo accesso e il recupero della password via email non funzionano per tutti: per chi non ha email resta solo la consegna di persona da parte del Direttore (FR-EST-01) |
| ASS-04 | Ogni studente può usare uno smartphone con un browser aggiornato, oppure un PC del laboratorio durante le verifiche | Bisogna prevedere postazioni della scuola per chi non ha un dispositivo adatto                                                                                                             |

### Vincoli

I limiti che non potete cambiare.

| ID     | Vincolo                                             | Da dove viene          |
| ------ | --------------------------------------------------- | ---------------------- |
| VIN-01 | _es. Il budget cloud è quello dei crediti studente_ | _Traccia del progetto_ |
|        |                                                     |                        |

### Dipendenze

Le cose esterne senza cui non potete andare avanti.

| ID     | Dipendenza                              | Serve entro          | Chi se ne occupa |
| ------ | --------------------------------------- | -------------------- | ---------------- |
| DIP-01 | _es. Account attivo sul servizio email_ | _Prima del collaudo_ | _nome_           |
|        |                                         |                      |                  |

---

# Seconda parte · Il come

<aside>
💡

Da qui in poi parli al tuo docente e al tuo team, non al Direttore. Ogni scelta tecnica va motivata e confrontata con almeno un'alternativa. "Lo conosciamo" è una motivazione valida, ma non può essere l'unica.

</aside>

## Stima del carico

### Utenti concorrenti

| Situazione                      | Utenti concorrenti | Da dove viene il numero |
| ------------------------------- | ------------------ | ----------------------- |
| Uso normale durante la giornata | _…_                | _…_                     |
| Picco delle 9:00 (verifiche)    | _…_                | _…_                     |
| Fine quadrimestre (voti)        | _…_                | _…_                     |

### Profilo di carico

| Operazione              | Frequente? | Pesante? | Critica? | Note |
| ----------------------- | ---------- | -------- | -------- | ---- |
| Login                   | _…_        | _…_      | _…_      | _…_  |
| Apertura verifica       | _…_        | _…_      | _…_      | _…_  |
| Consegna verifica       | _…_        | _…_      | _…_      | _…_  |
| Dashboard del Direttore | _…_        | _…_      | _…_      | _…_  |
| Caricamento materiale   | _…_        | _…_      | _…_      | _…_  |

<aside>
💡

I numeri di qui devono essere coerenti con la scuola che avete immaginato e con i requisiti non funzionali. Se dichiarate 800 studenti, non potete dimensionare per 20 utenti senza spiegare perché.

</aside>

---

## Scelte tecnologiche

**I criteri.** Tutte le scelte seguono tre criteri, in quest'ordine:

1. **Un solo linguaggio.** Frontend e backend in JavaScript: imparo meno cose nuove e passo dall'uno all'altro senza cambiare linguaggio.
2. **Strumenti che conosco o sto imparando** Abbiamo imparato MySQL e stiamo imparando React.
3. **Diffusione e documentazione.** Lavoro da solo: mi servono strumenti con tanti esempi e una comunità ampia.
4. **Costi bassi.** Tutto deve stare nel piano gratuito o costare pochi euro al mese.

| Area                      | Scelta                | Alternative scartate      | Motivazione                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ------------------------- | --------------------- | ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Backend                   | **Node.js + Express** | ASP.NET Core; Spring Boot | Stesso linguaggio del frontend (criterio 1). Express è semplice e ha moltissimi esempi e librerie (criterio 3). È minimale: struttura a livelli, validazione e Swagger li aggiungo con librerie dedicate (vedi Architettura). **ASP.NET Core** e **Spring Boot** scartati: hanno più funzioni già pronte, ma userei un linguaggio diverso dal frontend, e C# dovrei impararlo da zero.                                      |
| Frontend                  | **React**             | Angular                   | Lo stiamo imparando (criterio 2) ed è il framework con più componenti pronti ed esempi (criterio 3). **Angular** scartato: è più complesso.                                                                                                                                                                                                                                                                                 |
| Database                  | **MySQL**             | PostgreSQL                | Lo conosco già (criterio 2). I dati di ScuolaChill seguono regole precise (uno studente sta in una sola classe, ha al massimo un voto per verifica): un database relazionale le fa rispettare con i suoi vincoli. **PostgreSQL** scartato: è simile, ma non lo conosco.                                                                                                                                                     |
| Provider cloud            | **AWS**               | Azure; Google Cloud       | È il provider più diffuso e più richiesto nel mondo del lavoro, con la documentazione più ampia (criterio 3). Ha un piano gratuito per i nuovi account (criterio 4, _da verificare durata e limiti_). **Azure** scartato: offre crediti agli studenti, ma il suo punto di forza è l'integrazione con .NET, che non uso. **Google Cloud** scartato: i crediti di prova scadono in pochi mesi, prima della fine del progetto. |
| Regione                   |                       |                           |                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Hosting dell'applicazione |                       |                           |                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Archiviazione dei file    |                       |                           |                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Autenticazione            |                       |                           |                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Servizio esterno          |                       |                           |                                                                                                                                                                                                                                                                                                                                                                                                                             |

---

## Architettura

### Diagramma dei componenti

_Inserisci qui il diagramma. Deve mostrare i componenti principali e come comunicano._

### I livelli

| Livello                | Cosa fa in ScuolaChill | Esempio concreto |
| ---------------------- | ---------------------- | ---------------- |
| Presentation / API     | _…_                    | _…_              |
| Application / Business | _…_                    | _…_              |
| Data access            | _…_                    | _…_              |

### Le dipendenze fra i livelli

_Chi può conoscere chi, e in quale direzione. Spiega come questa struttura riduce l'accoppiamento e rende il sistema testabile._

---

## Le API

### Le risorse

_Elenca le risorse REST principali. Es. `/classi`, `/verifiche`, `/voti`._

### Il contratto delle API principali

| Verbo    | Route            | Chi può chiamarla | Payload di esempio                | Risposte previste    |
| -------- | ---------------- | ----------------- | --------------------------------- | -------------------- |
| `POST`   | `*/api/docenti*` | _Direttore_       | `*{ "nome": "…", "email": "…" }*` | _201, 400, 403, 409_ |
| `GET`    | _…_              | _…_               | _…_                               | _…_                  |
| `PUT`    | _…_              | _…_               | _…_                               | _…_                  |
| `PATCH`  | _…_              | _…_               | _…_                               | _…_                  |
| `DELETE` | _…_              | _…_               | _…_                               | _…_                  |

### Errori, validazione e paginazione

**Formato uniforme degli errori.** _Mostra un esempio di risposta di errore._

**Validazione degli input.** _Dove avviene e con quali regole._

**Paginazione.** _Come funziona. Parametri, dimensione di default, formato della risposta._

**Documentazione e verifica.** _Come userete OpenAPI/Swagger e la collezione Postman._

---

## Persistenza e modello dei dati

### Diagramma ER

_Inserisci qui il diagramma entità-relazioni con le cardinalità._

### Identificatori

_Come vengono generati gli ID, e perché. Numeri incrementali, UUID, altro?_

### Tre modelli diversi

| Entità     | Nel database | Nel dominio | Esposta dall'API | Dove differiscono e perché |
| ---------- | ------------ | ----------- | ---------------- | -------------------------- |
| _es. Voto_ | _…_          | _…_         | _…_              | _…_                        |

### Normalizzazione e letture aggregate

_Come è normalizzato il modello. Dove serve una lettura denormalizzata, per esempio la pagina dei voti per materia o la dashboard del Direttore._

### Accesso ai dati

_Strategia di accesso ai dati e uso delle query parametrizzate contro la SQL injection._

---

## Sicurezza e integrazione

### Autenticazione e token

_Come si ottiene il token, cosa contiene, come viaggia il profilo utente._

### Chi può fare cosa

| Operazione                    | Direttore | Docente | Studente |
| ----------------------------- | --------- | ------- | -------- |
| Creare un docente             | ✅        | ❌      | ❌       |
| Caricare materiale            | ❌        | ✅      | ❌       |
| Vedere i voti di uno studente | ❌        | ✅      | ✅       |
| _…_                           |           |         |          |

_Spiega dove viene fatto rispettare questo controllo. Ricorda che il frontend non basta mai._

### L'API esterna

_Quale servizio usate, per cosa, e cosa succede quando non risponde._

### Configurazione e segreti

_Dove vivono connection string e segreti, e come cambiano fra Development e Production._

---

## Qualità architetturale

### Organizzazione del codice

_Struttura di progetti, moduli e cartelle, con le motivazioni._

### Dependency inversion e IoC

_Dove li applicate e a cosa servono in ScuolaChill._

### Design Pattern

_La traccia chiede esplicitamente dove vengono applicati i design pattern e a cosa servono._

| Pattern | Dove lo usate in ScuolaChill | Che problema risolve |
| ------- | ---------------------------- | -------------------- |
| _…_     | _…_                          | _…_                  |

### Testabilità

_Cosa testerete, e come separate database e API esterne per sostituirli nei test._

### Development e Production

|          | Development | Production |
| -------- | ----------- | ---------- |
| Database | _…_         | _…_        |
| Segreti  | _…_         | _…_        |
| Log      | _…_         | _…_        |
| _…_      |             |            |

---

## Dimensionamento e costi

| Componente       | Servizio | Taglia (CPU, RAM, storage) | Istanze | Costo mensile stimato |
| ---------------- | -------- | -------------------------- | ------- | --------------------- |
| Backend          | _…_      | _…_                        | _…_     | _…_                   |
| Database         | _…_      | _…_                        | _…_     | _…_                   |
| Storage dei file | _…_      | _…_                        | _…_     | _…_                   |
| _…_              |          |                            |         |                       |
| **Totale**       |          |                            |         | **_…_**               |

**Strategia di scalabilità.** _Verticale o orizzontale? Manuale o automatica?_

**Se la stima si rivela sbagliata.** _Cosa fate se gli utenti sono il doppio? E se sono la metà?_

---

## Piano di deployment

_Come ScuolaChill arriva sul cloud scelto. Come si passa da una versione alla successiva. Come vengono gestite nel tempo le modifiche allo schema del database._

---

# Terza parte · Tempi e valutazione

## Milestone

| Milestone                    | Cosa è pronto    | Data prevista | Responsabile    |
| ---------------------------- | ---------------- | ------------- | --------------- |
| PRD validato                 | Questo documento | _…_           | _tutto il team_ |
| _Prima versione in cloud_    | _…_              | _…_           | _…_             |
| _Collaudo con il primo anno_ | _…_              | _…_           | _…_             |
| _…_                          |                  |               |                 |

<aside>
💡

Stima il tempo di ogni fase come se tutto andasse bene. Poi aggiungi un margine. Non va mai tutto bene.

</aside>

## Piano di valutazione

Come capirete che ScuolaChill funziona e come validerete che la vostra soluzione sta avendo un impatto positivo?

| Metrica                                                    | Obiettivo | Come la misurate                             | Quando       |
| ---------------------------------------------------------- | --------- | -------------------------------------------- | ------------ |
| _es. Collaudatori che completano una verifica senza aiuto_ | _90%_     | _Osservazione durante il collaudo_           | _Collaudo_   |
| _es. Voti persi_                                           | _0_       | _Confronto fra voti inseriti e voti salvati_ | _Primo mese_ |
|                                                            |           |                                              |              |

---

## Acceptance Criteria di questa PRD

- [ ] Ogni parte rappresentata da questo template ha tutte le sezioni richieste senza saltare nessun punto
- [ ] Avete deciso tutti i punti che la traccia e gli esempi lasciano aperti.
- [ ] Ogni requisito non funzionale ha una soglia e una condizione.
- [ ] Ogni NFR è collegato ad almeno una user story.
- [ ] Avete inserito i requisiti impliciti emersi da interviste che avete fatto.
- [ ] Assunzioni, vincoli e dipendenze sono separati e scritti.
- [ ] I numeri della stima del carico sono coerenti con la scuola immaginata e con il dimensionamento.
- [ ] Ogni scelta tecnica ha almeno un'alternativa scartata e una motivazione.
- [ ] La prima parte non contiene scelte tecniche.
- [ ] Lo storico delle versioni è aggiornato .
