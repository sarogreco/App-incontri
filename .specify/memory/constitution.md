# Costituzione di AppIncontri

> **Filosofia:** *"Uno sconosciuto è un amico non ancora incontrato."*
>
> Ogni scelta di prodotto deve rendere più facile, più spontaneo e più sicuro trasformare uno
> sconosciuto nei dintorni in una persona conosciuta di persona.

## Principi fondamentali

### I. Incontri reali e immediati

- Lo scopo dell'app è **incontrarsi di persona entro circa 15 minuti**.
- Il raggio predefinito di una richiesta è **1 km**.
- L'app MUST favorire l'incontro, non la conversazione a distanza: niente chat lunghe o
  funzioni che sostituiscono l'incontro (profili elaborati, messaggi illimitati).
- Ogni funzione nuova MUST dichiarare come aiuta un incontro reale e rapido.

*Motivazione:* è ciò che distingue l'app da tutte le altre app di incontri.

### II. Autenticità

- Richieste e risposte sono composte **sempre** da un **selfie scattato al momento** e da un
  **breve messaggio di testo**.
- Le foto MUST essere scattate con la fotocamera dentro l'app. L'app MUST NOT accedere alla
  galleria in nessun modo (niente `PhotosPicker`, niente `.photoLibrary`, niente importazione
  di file immagine).
- Il selfie MUST NOT poter essere sostituito o modificato dopo lo scatto, se non rifacendolo.

*Motivazione:* chi incontri deve essere la persona che hai visto, così com'è adesso.

### III. Privacy della posizione e consenso

- Chi riceve una richiesta sa soltanto che **qualcuno "nei dintorni"** vuole conoscere una
  persona nuova. L'app MUST NOT mostrare distanza, quartiere, via o mappa prima del match.
- La posizione usata è un'**istantanea** presa al momento dell'invio. L'app MUST NOT tracciare
  la posizione in modo continuo.
- La **posizione esatta** da cui è stata inviata la richiesta viene mostrata **solo** alla
  persona scelta con lo swipe a destra, e solo dopo la scelta.
- Inviando una richiesta, l'utente acconsente in modo esplicito e informato a questa
  condivisione: l'app MUST spiegarlo prima del primo invio.
- La posizione MUST essere cancellata o resa inaccessibile alla scadenza della richiesta.
- Le posizioni degli altri utenti MUST NOT essere mai esposte al client: i calcoli di
  vicinanza avvengono sul server.

*Motivazione:* la posizione esatta è il dato più delicato dell'app. Va condivisa solo con chi
l'utente ha scelto, e solo per il tempo necessario.

### IV. Richieste effimere

- Una richiesta dura **30 minuti** dall'invio.
- Alla scadenza la richiesta, le risposte ricevute, i selfie e la posizione MUST diventare
  inaccessibili e poi essere cancellati.
- Un utente può avere **una sola richiesta attiva** alla volta.

*Motivazione:* l'app vive nel presente. Niente archivio di foto e posizioni.

### V. Sicurezza e buon senso

- Solo utenti **maggiorenni (18+)**, verificato prima del primo utilizzo.
- **Segnala** e **blocca** MUST essere raggiungibili da ogni schermata dove compare un'altra
  persona. Un utente bloccato non riceve più richieste né risposte dell'utente che l'ha bloccato.
- Le **note d'uso** con le regole di buon senso MUST essere mostrate al primo avvio e restare
  consultabili. Includono almeno:
  - incontrarsi in luoghi frequentati;
  - avvisare un amico di dove si va;
  - andarsene se qualcosa non convince;
  - rispettare il no.
- I contenuti degli utenti (selfie e messaggi) MUST essere moderabili, e l'app MUST rispettare
  le linee guida dell'App Store per le app con contenuti generati dagli utenti.

*Motivazione:* la filosofia dell'app funziona solo se le persone si sentono al sicuro.

### VI. Semplicità

- Il proprietario del progetto ha le basi di Swift: il codice MUST essere chiaro, diviso in
  file piccoli e commentato in italiano dove non è ovvio.
- Ogni modifica MUST essere piccola e verificabile in Xcode (simulatore o iPhone) prima della
  successiva.
- Niente librerie o servizi aggiuntivi senza una necessità dichiarata nella specifica.
- Nessun segreto nel repository: chiavi API e `GoogleService-Info.plist` restano fuori da Git.

*Motivazione:* un progetto che il proprietario capisce è un progetto che può portare avanti.

## Vincoli tecnici

| Cosa | Scelta |
|---|---|
| Piattaforma | solo iPhone, solo orientamento verticale |
| iOS minimo | 18.6 |
| Interfaccia | SwiftUI |
| Linguaggio | Swift |
| Backend | Firebase (autenticazione, database, archivio foto, funzioni server, notifiche push) |
| Lingua | italiano per testi dell'app, documentazione e commenti |

Ogni scostamento da questi vincoli MUST essere motivato nel piano della funzione interessata.

## Flusso di lavoro

- Le funzioni principali (richiesta, risposte, swipe, incontro) seguono Spec Kit:
  specifica → piano → compiti → codice.
- Il proprietario MUST approvare ogni specifica prima che si passi al piano e al codice.
- Ogni piano MUST contenere un controllo di conformità a questa costituzione.
- Prima di lavorare: **Pull**. Alla fine: **Commit e Push**, con messaggi in italiano.
- Le correzioni piccole non richiedono Spec Kit, ma rispettano comunque questi principi.

## Governance

- Questa costituzione prevale su ogni altra indicazione del progetto. `CLAUDE.md` contiene le
  indicazioni operative e MUST restare coerente con essa.
- Solo il proprietario (**sarogreco**) può approvare modifiche alla costituzione.
- Versioni:
  - **MAJOR**: un principio viene rimosso o cambiato in modo incompatibile;
  - **MINOR**: un principio o una sezione viene aggiunta o ampliata;
  - **PATCH**: chiarimenti e correzioni di forma.
- Ogni specifica e ogni piano MUST verificare la conformità ai principi. Una violazione si
  accetta solo se motivata per iscritto e approvata dal proprietario.

**Versione**: 1.0.0 | **Ratificata**: 2026-11-07 | **Ultima modifica**: 2026-11-07
