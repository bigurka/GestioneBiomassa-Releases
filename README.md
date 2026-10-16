# Gestione Biomassa — release

Questo repository pubblico contiene **solo i pacchetti di aggiornamento** di Gestione Biomassa
(gestione prenotazioni, magazzino e ordini di pellet e legna). Non contiene codice sorgente.

## Cosa c'è in ogni release

| File | A cosa serve |
|---|---|
| `Aggiornamento-GestioneBiomassa.zip` | Il pacchetto di aggiornamento: `AggiornaGestioneBiomassa.exe`, i nuovi file dell'app e, se serve, lo script del database. |
| `Aggiornamento-GestioneBiomassa.zip.sha256` | L'hash SHA-256 dello zip: l'app lo controlla prima di installare. |

Il tag di ogni release ha la forma `vX.Y.Z` (ad esempio `v0.13.0`) e le note descrivono le novità.

## Come si usa

- **Dall'app (consigliato).** Con gli aggiornamenti dall'app abilitati sul server, quando esce una
  versione nuova tutti gli utenti vedono un avviso e possono scaricarla; l'amministratore la installa
  dalla pagina *Aggiornamenti*. L'app legge sempre l'ultima release di questo repository.
- **A mano.** Scarica lo zip, estrailo sul server ed esegui `AggiornaGestioneBiomassa.exe` come
  amministratore: fa il backup dei file e del database, copia la nuova versione e riavvia il sito.

Il programma di aggiornamento non modifica `appsettings.json` né `web.config` del server.

## Verificare il file scaricato

```powershell
(Get-FileHash .\Aggiornamento-GestioneBiomassa.zip -Algorithm SHA256).Hash.ToLower()
```

Il risultato deve coincidere con il contenuto del file `.sha256`.

## Supporto

Sviluppatore: bigurka@gmail.com
