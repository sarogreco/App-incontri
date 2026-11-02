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
| 4 | Chi riceve | Vede selfie, messaggio e distanza approssimativa |
| 5 | Chi riceve | Se vuole, risponde con selfie dal vivo + messaggio |
| 6 | Chi invia | Scorre le risposte con swipe destra/sinistra |
| 7 | App | Alla scelta, comunica il punto d'incontro alla persona scelta |
| 8 | Entrambi | Si incontrano entro ~15 minuti |

## Regole di base

- Solo maggiorenni (18+).
- Solo foto scattate al momento, mai dalla galleria.
- Ogni utente può **segnalare** e **bloccare** un altro utente.
- Le richieste **scadono** dopo un tempo prestabilito.

## Decisioni aperte

1. **Punto d'incontro**: posizione esatta di chi invia, oppure luogo pubblico
   suggerito dall'app (bar, piazza) vicino a chi invia? *(consigliato: luogo pubblico)*
2. **Durata di una richiesta** prima della scadenza (es. 30 minuti).
3. **Cosa vede chi riceve**: solo la distanza ("a 600 m") o anche il quartiere.
4. **Nome dell'app.**

## Sicurezza (da definire nel dettaglio)

- Posizione mai mostrata in modo preciso prima del match.
- Verifica dell'identità prima del primo incontro.
- Condivisione dell'incontro con un amico e pulsante di emergenza.
- Feedback dopo l'incontro.
