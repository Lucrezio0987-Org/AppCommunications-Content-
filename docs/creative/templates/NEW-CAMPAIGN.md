# Kit editoriale — Nuova campagna AppCommunications

**Da copiare in un dossier dedicato per ciascuna campagna.** Questo è il modello di *lavorazione*, non un JSON di pubblicazione.

**Playbook centrale:** [AppCommunications/docs/EDITORIAL-CAMPAIGN-PLAYBOOK.md](https://github.com/Lucrezio0987-Org/AppCommunications/blob/main/docs/EDITORIAL-CAMPAIGN-PLAYBOOK.md) (repository privato).  
**Scheda completa:** [CAMPAIGN-CREATIVE-SPEC.template.md](https://github.com/Lucrezio0987-Org/AppCommunications/blob/main/docs/templates/CAMPAIGN-CREATIVE-SPEC.template.md).  
**Stato e approvazioni:** [Notion — Centro editoriale](https://app.notion.com/p/40b3e5f27c0b8116bc04c0885ec55784).

## A — Identificare la comunicazione

- **Titolo:** [prodotto, rilascio o promozione]
- **Prodotto raccontato (subject):** [id app, repo ufficiale]
- **Applicazioni destinatarie (audiences):** [chi vedrà la comunicazione]
- **Ambiente:** [collaudo / production esplicitamente approvata]
- **Formato:** [HTML/CSS statico / image_ad / altro contratto approvato]
- **Placements:** [poster 4:5 / inbox 16:9 / inline / notifica OS]
- **CTA:** [id, azione dichiarata, fonte Store/HTTPS verificata]
- **ID campagna e revisione:** [stabile, nuova revision solo per nuova esposizione]
- **Referente e ticket:** [Developer Profile, issue]

## B — Recuperare il brand del prodotto soggetto

Non copiare un tema da CableCheck per una promo WakeCupPC o viceversa. Aprire il **vero repository del soggetto** e indicare:

| Elemento | Percorso/versione verificati | Decisione |
| --- | --- | --- |
| Icona/launcher | [ref] | [uso diretto/stilizzazione dichiarata] |
| Palette/tema | [file + 3-6 token] | [colori] |
| Componenti visuali | [file UI] | [cosa rappresentare] |
| Promo/Store/screenshot | [link] | [approvato / non usare] |
| Stato funzionalità | [doc/changelog] | [claim ammessi/vietati] |

## C — Disegnare senza inventare l'app

Per la maggior parte delle comunicazioni basate su UI **preferire HTML/CSS statico**:
- grafica e sfondi dal brand del soggetto, non dall'host;
- UI **stilizzata e dichiarata**, non spacciata per screenshot autentico;
- `{{headline}}`, `{{deck}}`, `{{eyebrow}}`, `{{footer}}` e `{{cta:primary}}` compilati dal motore;
- solo markup/style consentiti dal contratto, niente JS, `<img>`, SVG remoto o `url()` arbitrario;
- CTA soltanto nel poster/landscape, **non** nel banner inbox;
- `prefers-reduced-motion` per animazioni CSS.

Se la creatività richiede **immagini ufficiali effettive**, usare `image_ad` con SHA-256 e limiti del client. Nessun JPG generico solo perché ha la palette giusta.

## D — Allegare le anteprime e verificare

| Placement | Dimensioni minime | Anteprima |
| --- | --- | --- |
| Poster | 320×400 (4:5) | [screenshot del medesimo HTML o file media] |
| Banner Novità | 320×180 (16:9) | [screenshot del medesimo HTML o file media] |
| Inline/landscape | 640×360 | [screenshot] |

- [ ] IT / EN / ES / FR / DE / PT senza testo sovrapposto o tagliato.
- [ ] Contrasto e leggibilità mobile, movimento ridotto, TalkBack/CTA sulla app reale.
- [ ] Identità del **soggetto** immediatamente riconoscibile.
- [ ] CTA valide e non duplicate; la card inbox apre la modale.
- [ ] Nessun markup/URI non autorizzato, nessun dato/secret riservato.
- [ ] PR in Draft con fonti, screenshot e chiarimento che **non è pubblicata**.

## E — Promuovere con controllo

- [ ] Revisione editoriale e CI effettuate sul contenuto effettivo.
- [ ] Merge del materiale nel catalogo `main`, solo ambiente approvato.
- [ ] Avvio manuale di **un nuovo workflow** `Publish public feed` dal `main` aggiornato del motore.
- [ ] Verifica del `published` vero: ID/revision, Collaudo/Produzione, hash se media.
- [ ] Apertura su app Collaudo e prova di CTA, cache, fallback, layout reale.
- [ ] Aggiornamento del Centro editoriale Notion con run/PR/stato.
- [ ] Pubblicazione produzione o FCM **solo con decisione separata**.

**I confini non cambiano:** status sul branch Draft ≠ distribuzione; merge ≠ public feed; feed ≠ push; codice client merged ≠ APK installato.

## Primo caso validato

- [WakeCupPC r4 HTML/CSS — PR editoriale #12](https://github.com/Lucrezio0987-Org/AppCommunications-Content-/pull/12) — layout e tema tratti dai componenti WakeCupPC, sei lingue, senza immagini.
- [Piano rilascio CableCheck (non ancora attivato)](../CABLECHECK-RELEASE-CAMPAIGN-PLAN.md) — prossimo caso con identità CableCheck.
