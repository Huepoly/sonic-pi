C.1 Basic API

# API di base di Minecraft Pi

Sonic Pi attualmente supporta le seguenti interazioni con Minecraft Pi:

Mostrare i messaggi della chat
Impostare la posizione dell'utante
Ricevere la posizione dell'utente
Impostare il tipo di blocco a una coordinata specifica
Ricevere il tipo di blocco a una coordinata specifica


Diamo un'occhiata a ognuna di esse, una alla volta.

## Mostrare i messaggi della chat

Per prima cosa, guardiamo come sia semplice controllare Minecraft Pi da Sonic Pi. Assicurati di avere Minecraft Pi e Sonic Pi aperti e di essere entrato in un mondo di Minecraft.

In un buffer di Sonic Pi, inserisci il seguente codice:

```
mc_message "Hello from Sonic Pi"
```

Quando premi *Run* vedrai comparire un messaggio nella finestra di Minecraft. Congratulazioni! Hai scritto il tuo primo codice Minecraft. Semplice, no?

## Impostare la posizione dell'utante

Ora, proviamo con un po' di magia. Usiamo il teletrasporto! Prova con il seguente codice:

```
mc_teleport 50, 50, 50
```

Quando premi *Run*, boom! Sei stato teletrasportato in un luogo nuovo. Probabilmente era da qualche parte nel cielo e sei caduto in terra o nell'acqua. Ragioniamo: cosa sono quei numeri `50, 50, 50`? Sono le coordinate del luogo verso cui stiamo cercando di teletrasportarci. Prendiamoci un momento per capire come funzionano le coordinate perché sono molto importanti in Minecraft.

## Coordinate

Immagina una mappa dei pirati con una grande `X` a segnalare il luogo del tesoro. L'esatta posizione di `X` può essere descritta con due numeri: la posizione da destra a sinistra e quella dal basso verso l'alto. Per esempio `10cm` orizzontalmente e `8cm` in verticale. Questi due numeri: `10` e `8` sono coordinate. Puoi immaginare di descrivere il luogo dove si trovano altri pezzi del tesoro con altre paia di numeri. Ad esempio può esserci un secchio di oro a `2` orizzontale e `9` verticale...

Ora, in Minecraft due numeri non bastano. Dobbiamo anche sapere la profondità per cui ci servono tre numeri:

Quanto da destra a sinistra: `x`
Quanto in profondità: `z`
E quanto in alto: `y`

Un'ultima cosa, di solito scriviamo queste coordinate in quest'ordine: `x`, `y`, `z`.

## Trovare le tue coordinate

Proviamo a giocare con le coordinate. Naviga in un punto della mappa di Minecraft e apri Sonic Pi. Ora, inserisci questo codice:

```
puts mc_location
```

Quando premi il pulsante *Run* vedrai le coordinate della tua posizione corrente mostrate nella finestra di log. Prendi nota. Muoviti nel mondo e prova di nuova. Guarda come sono cambiate. Ti consiglio di fare qualche prova in più, ripetendo gli stessi passaggi: muoviti in giro, guarda le coordinate e ripeti. Fallo finché non ti senti a tuo agio su come cambiano i valori quando ti muovi. Una volta capito come funzionano, sarà semplicissimo usare l'API Minecraft.

## Costruiamo!

Ora che sai come trovare le tue coordinate e come teletrasportarti, hai tutti gli strumenti a disposizione per costruire qualcosa in Minecraft. Facciamo finta che tu voglia costruire un blocco di vetro alle seguenti coordinate: `40`, `50`, `60`. È molto semplice:

```
mc_set_block :glass, 40, 50, 60
```

Semplice, no? Per vedere il risultato, teletrasportati nelle vicinanze:

```
mc_teleport 35, 50, 60
```

Ora guardati intorno, dovresti vedere un blocco di vetro! Proviamo a cambiarlo in diamante:

```
mc_set_block :diamond, 40, 50, 60
```

Se stavi guardando nella giusta direzione, forse l'hai visto cambiare direttamente con i tuoi occhi. Questo è l'inizio di qualcosa di eccitante...

## Guardare i blocchi

Prendiamo in esame un'ultima cosa prima di andare avanti con qualcosa di più complesso. Dato un set di coordinate, possiamo chiedere a Minecraft la tipologia del blocco. Proviamolo con il blocco di diamante che abbiamo appena creato:

```
puts mc_get_block 40, 50, 60
```

Evviva! Dice `:diamond`. Prova a cambiarlo di nuovo in vetro e a rifare la richiesta. Ora dice `:glass`, giusto? Sono sicuro che lo fa :-)

## Tipi di blocco disponibili

Prima di andare avanti con Minecraft Pi, eccoti una lista delle tipologie di blocchi disponibili:

```
    :air
    :stone
    :grass
    :dirt
    :cobblestone
    :wood_plank
    :sapling
    :bedrock
    :water_flowing
    :water
    :water_stationary
    :lava_flowing
    :lava
    :lava_stationary
    :sand
    :gravel
    :gold_ore
    :iron_ore
    :coal_ore
    :wood
    :leaves
    :glass
    :lapis
    :lapis_lazuli_block
    :sandstone
    :bed
    :cobweb
    :grass_tall
    :flower_yellow
    :flower_cyan
    :mushroom_brown
    :mushroom_red
    :gold_block
    :gold
    :iron_block
    :iron
    :stone_slab_double
    :stone_slab
    :brick
    :brick_block
    :tnt
    :bookshelf
    :moss_stone
    :obsidian
    :torch
    :fire
    :stairs_wood
    :chest
    :diamond_ore
    :diamond_block
    :diamond
    :crafting_table
    :farmland
    :furnace_inactive
    :furnace_active
    :door_wood
    :ladder
    :stairs_cobblestone
    :door_iron
    :redstone_ore
    :snow
    :ice
    :snow_block
    :cactus
    :clay
    :sugar_cane
    :fence
    :glowstone_block
    :bedrock_invisible
    :stone_brick
    :glass_pane
    :melon
    :fence_gate
    :glowing_obsidian
    :nether_reactor_core
```
