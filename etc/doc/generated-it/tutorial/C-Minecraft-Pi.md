Minecraft Pi

# Minecraft Pi

Sonic Pi ora supporta un'API semplice che permette di interfacciarsi con Minecraft Pi, una versione speciale di Minecraft che è installata di default sul sistema operativo Raspbian Linux sul Rasberry Pi.

## Non è necessario importare librerie

L'integrazione con Minecraft Pi è stata pensata per essere estremamente semplice da usare. Tutto quello che devi fare è lanciare Minecraft Pi e creare un mondo. Sarai libero di usare le funzioni `mc_*` esattamente come usi `play`e `synth`. Non è necessario importare nient'altro né installare librerie. È tutto pensato per funzionare all'avvio.

## Correzione automatica

L'API di Minecraft si prenderà cura di tutte le connessioni all'applicazione Minecraft Pi. Questo significa che non è necessario preoccuparsi di queste cose. Se provi a usare l'API Minecraft Pi senza aver aperto Minecraft PI, Sonic Pi te lo dirà. Allo stesso modo, se chiudi Minecraft Pi mentre stai ancora riproducendo un `live_loop` che usa l'API, il loop si fermerà e ti dirà che non può più connettersi. Per riconnettersi, apri di nuovo Minecraft Pi e Sonic Pi ricreerà automaticamente la connessione per te.

## Pensato per essere programmato dal vivo

L'API Minecraft Pi è stata pensata per lavorare senza problemi con i `live_loop`. Questo significa che è possibile sincronizzare le modifiche nel tuo mondo Minecraft Pi con le modifiche fatte nei suoni di Sonic Pi. Video musicali basati su Minecraft realizzati istantaneamente! Attenzione, però, Minecraft Pi è ancora in alpha e potrebbe avere qualche bug. Se riscontri dei problemi, prova a riavviare Minecraft Pi. Sonic Pi ristabilirà automaticamente la connessione.

## Richiedere un Raspberry Pi 2.0

È fortemente consigliato usare un Raspberry Pi 2 se vuoi utilizzare contemporaneamente Sonic Pi e Minecraft allo stesso tempo, specialmente se vuoi usare le possibilità sonore di Sonic Pi.

## Supporto API

A questo punto Sonic Pi supporta modifiche ai blocchi e al player come descritto nella sezione 11.1. Il supporto per il callback degli evneti lanciati dal player è pianificato per una release futura.
