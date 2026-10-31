# Canali di distribuzione — AppCommunications

`content/catalog/routing.json` è il registro **pubblico** delle famiglie, piattaforme, gruppi personalizzati e prodotti. Non contiene credenziali, token o dati utente.

Il catalogo Play esistente `content/catalog/apps.json` rimane indipendente per retrocompatibilità; soltanto i prodotti `connected` hanno un client comunicazioni già integrato. `planned` indica prodotti censiti ma senza ricezione attiva delle notizie; non equivale a stato di pubblicazione del prodotto.

## Selezione destinatari

Negli annunci v1 o campagne v2 si può scegliere:

```json
"audiences": ["family.mobile"]
```

Altre chiavi disponibili: `global`, `family.desktop`, `platform.android`, `product.cablecheck`, `product.wakecuppc`, `product.monissh`, `group.beta`. La lista completa è derivata dal registro e mostrata nello Studio.

Le selezioni sono in OR e i prodotti duplicati vengono contati una sola volta. La distribuzione si aggiorna automaticamente quando aggiungi nuovi prodotti al catalogo nella famiglia appropriata, senza ritoccare la campagna originale.

**Non** usare contemporaneamente `targets` e `audiences`. `targets` è supportato per le notizie già pubblicate, `audiences` è il nuovo indirizzamento.

Il vecchio campo `channels` nelle notizie v1 resta riservato a `inbox`, `banner`, `push`: indica il mezzo, non i destinatari.

## Modifiche al catalogo

Per aggiungere un prodotto, definisci ID univoco, famiglie, piattaforme, gruppi e stato di integrazione. I canali `product.<id>` vengono generati automaticamente. Per creare un canale personalizzato, aggiungi il gruppo e assegna la sua ID ai prodotti interessati.

Le nuove pubblicazioni richiedono la validazione privata e la promozione distinta del ramo `published`. Il registro da solo non invia notifiche FCM o messaggi ad applicazioni non ancora collegate.
