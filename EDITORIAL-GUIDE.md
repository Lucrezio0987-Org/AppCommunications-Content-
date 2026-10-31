# Guida editoriale — AppCommunications-Content-

Il repository è **pubblico**: anche le bozze saranno visibili su GitHub. Non inserire informazioni riservate o personali.

## Nuova notizia
1. Aggiungi un file JSON sotto `content/announcements`. Il nome suggerito è `YYYY-MM-DD-slug.json`.
2. Usa un ID univoco che **non deve essere riutilizzato** per una nuova comunicazione.
3. Scrivi almeno `localizations.it.title` e `localizations.it.body`; fornisci le altre lingue quando disponibili.
4. Definisci `targets` (app), `environments` (`collaudo`, `production`), `channels` (`inbox`, `banner`, `push`) e date UTC.
5. Inizia da `status: "draft"`; apri una pull request verso `main` per revisione.
6. Dopo il merge, il publisher *privato* valida e produce il feed. Un invio push richiede un'azione separata di chi gestisce le infrastrutture.

### Esempio di azione
Per un annuncio senza tasti: `"action": { "kind": "none" }`.
Per una nuova app nello Store: `"action": { "kind": "open_store", "appId": "wakecuppc" }` (solo se `storePublished=true` nel catalogo).

**Le comunicazioni tecniche della batteria non vanno inserite qui**: questo repository serve alle notizie dello sviluppatore.

## Correzioni e ritiro
Modifica il file esistente per correggere un refuso; il publisher sostituirà il contenuto alla prossima generazione. Imposta `status: "archived"` per rimuovere il contenuto dal feed. Non cancellare gli ID già distribuiti senza una ragione e senza revisione.

## Controlli di sicurezza
Solo link HTTPS, niente URL a servizi privati, script, HTML o allegati eseguibili. Mai aggiungere token FCM, chiavi GitHub, file `google-services.json` o dati personali.
