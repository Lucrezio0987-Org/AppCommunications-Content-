# AppCommunications · Contenuti pubblici

Repository editoriale pubblico delle applicazioni Lucrezio0987-Org.

Questa repository ospita **solo** annunci, traduzioni, catalogo applicazioni e asset destinati alla pubblicazione. Non contiene codice eseguibile per la pubblicazione, workflow di GitHub Actions o credenziali Firebase.

## Organizzazione
- `content/announcements/*.json` — annunci editoriali; singoli file versionati, con ID stabile.
- `content/catalog/apps.json` — catalogo di app ufficiali e link Google Play.
- `published` (branch separato) — feed JSON generati e validati dal repository **privato** AppCommunications.
- Il ramo `main` è il sorgente editoriale e **non** deve essere usato come sorgente di GitHub Pages.

## Pubblicazione
1. Creare una PR con le modifiche editoriali su `main`.
2. Ottenere approvazione e fare il merge.
3. Il publisher del repository privato genera il feed e lo distribuisce sul ramo `published`.
4. Le notifiche push FCM sono un'operazione separata e non vengono inviate automaticamente quando un annuncio viene modificato.

### Stato
Configurazione iniziale del pilot **CableCheck Collaudo**. Le notizie di test sono riservate all'ambiente `collaudo`. Nessun invio push attivo.

## Regole redazionali
- Non inserire mai token, dati personali, credenziali, notizie riservate o URL privati: **tutto il contenuto di questo repository è pubblico**, inclusi i draft.
- Testi in italiano obbligatori; altre lingue facoltative con fallback italiano finché non si completa la localizzazione.
- Tutte le CTA devono rimandare ad applicazioni del catalogo oppure a link HTTPS esplicitamente consentiti.
- `draft` non è pubblicato; per ritirare una notizia usare `archived`.
- Lo stato `published` non autorizza l'invio di notifiche FCM.

L'infrastruttura e i contratti sono documentati in [AppCommunications](https://github.com/Lucrezio0987-Org/AppCommunications) (repository privato).
