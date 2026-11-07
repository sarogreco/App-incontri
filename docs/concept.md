# Concept

## Il problema

Chi arriva in una città nuova non ha un modo rapido e spontaneo per conoscere gente
del posto *adesso*. Le app di incontri esistenti puntano su chat lunghe e appuntamenti
fissati giorni dopo.

## La soluzione

Una "richiesta d'incontro" istantanea, basata sulla vicinanza, che si chiude con un
incontro reale entro 15 minuti.

## Flusso principale

| Passo | Chi | Cosa succede |
|---|---|---|
| 1 | Chi invia | Scatta un selfie dal vivo e scrive un messaggio |
| 2 | Chi invia | Preme Invia: nasce una **richiesta** |
| 3 | App | Notifica tutti gli utenti nel raggio (default 1 km) |
| 4 | Chi riceve | Vede selfie, messaggio e che la persona è "nei dintorni" |
| 5 | Chi riceve | Se vuole, risponde con selfie dal vivo + messaggio |
| 6 | Chi invia | Scorre le risposte con swipe destra/sinistra |
| 7 | App | Alla scelta, mostra alla persona scelta la posizione da cui è partita la richiesta |
| 8 | Entrambi | Si incontrano entro ~15 minuti |

## Regole di base

- Solo maggiorenni (18+).
- Solo foto scattate al momento, mai dalla galleria.
- Ogni utente può **segnalare** e **bloccare** un altro utente.
- Le richieste **scadono** dopo un tempo prestabilito.

## Filosofia

> *"Uno sconosciuto è un amico non ancora incontrato."*

## Decisioni prese

1. **Punto d'incontro**: la posizione esatta da cui è stata inviata la richiesta, mostrata solo
   alla persona scelta. Le note d'uso invitano a regole di buon senso.
2. **Durata di una richiesta**: 30 minuti.
3. **Cosa vede chi riceve**: solo che qualcuno è "nei dintorni".

Le regole complete sono nella costituzione: `.specify/memory/constitution.md`.

## Decisioni aperte

1. **Nome dell'app.**

## Sicurezza (da definire nel dettaglio)

- Posizione mai mostrata in modo preciso prima del match.
- Verifica dell'identità prima del primo incontro.
- Condivisione dell'incontro con un amico e pulsante di emergenza.
- Feedback dopo l'incontro.
