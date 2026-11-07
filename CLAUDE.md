# CLAUDE.md

Istruzioni per Claude (in chat, in Xcode o in qualunque altro strumento) che lavora su questo repository.

## Il progetto

App iOS di incontri per conoscere persone nelle vicinanze **di persona, entro 15 minuti**.
Nome definitivo ancora da scegliere: per ora si chiama **AppIncontri**.

Flusso principale:

1. Chi invia scatta un **selfie dal vivo** e scrive un breve messaggio, poi preme Invia.
2. La richiesta arriva a tutti gli utenti nel raggio di **1 km**.
3. Chi vuole risponde con **un selfie dal vivo e un messaggio**.
4. Chi ha inviato scorre le risposte con **swipe** (destra = sì, sinistra = no).
5. La persona scelta riceve il **punto d'incontro** e arriva entro ~15 minuti.

Dettagli in [`docs/concept.md`](docs/concept.md).

## Chi è l'utente

- Il proprietario del progetto ha **solo le basi di Swift e Xcode**: lo guidiamo passo per passo.
- **Scrivi in italiano** messaggi, documentazione e testi dell'app.
- Una cosa per volta: spiega cosa fare, dove cliccare e cosa deve aspettarsi di vedere.
- Prima di azioni difficili da annullare (cancellare file, riscrivere la cronologia Git,
  aggiungere servizi a pagamento) chiedi conferma.

## Regole fisse dell'app

Valgono per ogni funzione. Non vanno aggirate nemmeno "per test".

- **Solo maggiorenni (18+).**
- **Solo foto scattate al momento** con la fotocamera dentro l'app.
  Non usare mai `PhotosPicker`, `UIImagePickerController` con `.photoLibrary` o altri accessi alla galleria.
- **Posizione mai precisa prima del match**: chi riceve una richiesta vede solo una distanza approssimativa.
- Ogni utente può **segnalare** e **bloccare** un altro utente.
- Le richieste **scadono** dopo un tempo prestabilito.
- Nessun segreto nel codice: chiavi e file come `GoogleService-Info.plist` non vanno nel repository
  (sono già in `.gitignore`).

### Decisioni ancora aperte

Non dare per scontata una scelta finché non è scritta qui o in `docs/concept.md`:

- Punto d'incontro: posizione esatta di chi invia o luogo pubblico suggerito dall'app (consigliato: luogo pubblico).
- Durata di una richiesta prima della scadenza.
- Cosa vede chi riceve: solo la distanza o anche il quartiere.
- Nome dell'app.

## Struttura tecnica

| Cosa | Scelta |
|---|---|
| Interfaccia | SwiftUI |
| Linguaggio | Swift |
| Xcode | 27.2 |
| iOS minimo | 18.6 |
| Orientamento | solo verticale (Portrait) |
| Bundle Identifier | `com.sarogreco.AppIncontri` |
| Nome del target | `MyApp` (nome interno; il nome visibile è `AppIncontri`) |
| Backend (previsto) | Firebase: Auth, Firestore, Storage, Cloud Functions, notifiche push |

Struttura delle cartelle:

```
AppIncontri/
├── AppIncontri.xcodeproj/   progetto Xcode (nuovo formato JSON `project.xcproj`)
└── MyApp/                   codice dell'app (target MyApp)
    ├── MyApp.swift          punto di ingresso (@main)
    ├── ContentView.swift
    └── Assets.xcassets
```

La cartella `MyApp/` è collegata al target come **cartella sincronizzata**: ogni file `.swift`
aggiunto lì dentro (anche in sottocartelle) entra automaticamente nell'app, senza modificare il
file di progetto. Non modificare `project.xcproj` a mano se non serve.

## Come lavoriamo

Ci sono due Claude che non si vedono a vicenda:

- **Claude in chat (cloud)**: decisioni, specifiche, scrittura di schermate e logica.
  Non ha Xcode: non può compilare né avviare l'app.
- **Claude dentro Xcode (sul Mac)**: correzioni veloci, errori di compilazione, prove nel simulatore.

Per evitare conflitti:

1. **Prima di iniziare**: Integrate → **Pull**.
2. **Alla fine**: Integrate → **Commit** con "Push to remote" spuntato.
3. Modifiche piccole e frequenti, con messaggi di commit in italiano che dicono cosa cambia.

Il ramo principale è `main`.

## Spec Kit

Il repository usa [Spec Kit](https://github.com/github/spec-kit) per le funzioni principali
(richiesta, risposte, swipe, incontro):

`/speckit-constitution` → `/speckit-specify` → `/speckit-plan` → `/speckit-tasks` → `/speckit-implement`

- La costituzione del progetto è in `.specify/memory/constitution.md`.
- Ogni documento di specifica va fatto rileggere al proprietario prima di passare al codice.
- Per correzioni piccole Spec Kit non serve.

## Documentazione aggiornata

Il repository configura il server MCP **Context7** (`.mcp.json`) per avere la documentazione
aggiornata di SwiftUI, Firebase e delle altre librerie. Usalo quando scrivi codice che dipende
da API che cambiano spesso.
