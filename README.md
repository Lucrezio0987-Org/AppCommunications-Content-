# AppCommunications · Contenuti pubblici

Repository editoriale pubblico delle applicazioni Lucrezio0987-Org.

Questa repository ospita **solo** annunci, traduzioni, catalogo applicazioni e asset destinati alla pubblicazione. Non contiene codice eseguibile per la pubblicazione, workflow di GitHub Actions o credenziali Firebase.

## Organizzazione
- `content/announcements/*.json` — notizie v1; singoli file versionati, con ID stabile.
- `content/campaigns/*.json` — campagne v2 con template HTML/CSS e, quando previsto, creativeMedia.
- `content/media/` — asset editoriali verificati, se usati dalle campagne.
- `docs/creative/` — dossier prodotto, checklist, anteprime e futuri piani editoriali.
- `content/catalog/apps.json` — catalogo di app ufficiali e link Google Play.
- `published` (branch separato) — feed JSON generati e validati dal repository **privato** AppCommunications.
- Il ramo `main` è il sorgente editoriale e **non** deve essere usato come sorgente di GitHub Pages.

## Pubblicazione
1. Creare una PR con le modifiche editoriali su `main`.
2. Ottenere approvazione e fare il merge.
3. Il publisher del repository privato genera il feed e lo distribuisce sul ramo `published`.
4. Le notifiche push FCM sono un'operazione separata e non vengono inviate automaticamente quando un annuncio viene modificato.

### Stato
Il pilot è **CableCheck Collaudo**. Lo storico Novità usa campagne v2: la promozione WakeCupPC r2 è attualmente la revisione distribuita, con r4 HTML/CSS in revisione (PR #12). Nessuna pubblicazione in Produzione o push implicita.

## Creative system — standard multiprodotto

**Regola obbligatoria:** ogni comunicazione usa il **tema del prodotto promosso**, anche quando compare in un'applicazione con una palette diversa. Il sistema editoriale, le dimensioni, i controlli e il publisher sono comuni; il **design NON è riutilizzato identico** tra progetti.

- [Playbook editoriale e pubblicazione](https://github.com/Lucrezio0987-Org/AppCommunications/blob/main/docs/EDITORIAL-CAMPAIGN-PLAYBOOK.md) (motore privato; fonte canonica)
- [Kit campagna riutilizzabile](./docs/creative/templates/NEW-CAMPAIGN.md) — dossier sorgenti, brand, formati, localizzazioni, preview, QA e PR
- [WakeCupPC r4 HTML/CSS](https://github.com/Lucrezio0987-Org/AppCommunications-Content-/pull/12) — esempio pilota con tema WakeCupPC, responsive e copy localizzato
- [Piano futuro comunicazione rilascio CableCheck](./docs/creative/CABLECHECK-RELEASE-CAMPAIGN-PLAN.md) — da attivare dopo verifica della release
- [Centro editoriale Notion](https://app.notion.com/p/40b3e5f27c0b8116bc04c0885ec55784) — registro di stato e decisioni

**Default consigliato:** HTML/CSS statico basato sulle componenti UI autentiche del soggetto, senza JavaScript remoto o asset generici. Usare `image_ad` quando materiale ufficiale approvato migliora davvero il messaggio; nessuna immagine generata senza richiesta. Le preview 4:5 e 16:9 si controllano sul dispositivo e nelle lingue supportate.

Le PR Draft **non** sono distribuite; il campo `status: published` da solo non pubblica il feed. Il ramo `published` è aggiornato solo dal workflow privato dedicato. Eventuali push FCM sono una procedura separata.

## Regole redazionali
- Non inserire mai token, dati personali, credenziali, notizie riservate o URL privati: **tutto il contenuto di questo repository è pubblico**, inclusi i draft.
- Testi in italiano obbligatori; altre lingue facoltative con fallback italiano finché non si completa la localizzazione.
- Tutte le CTA devono rimandare ad applicazioni del catalogo oppure a link HTTPS esplicitamente consentiti.
- `draft` non è pubblicato; per ritirare una notizia usare `archived`.
- Lo stato `published` non autorizza l'invio di notifiche FCM.

L'infrastruttura e i contratti sono documentati in [AppCommunications](https://github.com/Lucrezio0987-Org/AppCommunications) (repository privato).
