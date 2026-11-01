# CableCheck — Annuncio lancio | r1 brand-first HTML/CSS

**Stato:** BOZZA DA APPROVARE — NON PUBBLICATA, NON ABILITATA ALLO STORE  
**Data:** 2026-11-01  
**Campaign ID:** `2026-11-01-cablecheck-launch`  
**Owner:** Developer Profile / AppCommunications  
**Materiale:** `content/campaigns/2026-11-01-cablecheck-launch.json`  
**Fonte delle regole:** [Playbook multiprodotto](https://github.com/Lucrezio0987-Org/AppCommunications/blob/main/docs/EDITORIAL-CAMPAIGN-PLAYBOOK.md).

## Premessa / stop sul claim di disponibilità

- Il catalogo [`content/catalog/apps.json`](../../../content/catalog/apps.json) riporta **`storePublished: false`** per `cablecheck`; perciò **non possiamo annunciare che è scaricabile ora** senza conferma ufficiale.
- `CableCheck/package.json` su `main` riporta **0.16.0**, ma quella è versione del sorgente, **non** una prova che Google Play l'abbia distribuita.
- La build [CableCheck Collaudo #41327878501](https://github.com/Lucrezio0987-Org/CableCheck/actions/runs/41327878501) è APK di prova distinto dal pacchetto `com.lucrezio0987.cablecheck`; non implica pubblicazione su Play.
- **Niente FCM, Produzione, campagna live o CTA Play prima del gate.** Non inventare data, review, prezzo, download e stato Play.

## Audit del vero prodotto

| Elemento | Fonte canonica | Scelta |
| --- | --- | --- |
| Palette dark | [`src/view/theme/tokens.ts`](https://github.com/Lucrezio0987-Org/CableCheck/blob/main/src/view/theme/tokens.ts) | `#050706` background, `#0A0D0B` surface, `#111713` raised, `#4FE36B` green positive, `#69D2FF` info, `#1E2720` border, `#F6F8F6` text, `#A4ACA6` muted |
| Regole UI | [`docs/design-system.md`](https://github.com/Lucrezio0987-Org/CableCheck/blob/main/docs/design-system.md) | Tool tecnico, dati leggibili, pochi box, una CTA, verde energia / azzurro informazione, niente grafica stock |
| Cerchio batteria | [`BatteryLevelGauge.tsx`](https://github.com/Lucrezio0987-Org/CableCheck/blob/main/src/view/components/monitor/BatteryLevelGauge.tsx) e [`ChargeArcGauge.tsx`](https://github.com/Lucrezio0987-Org/CableCheck/blob/main/src/view/components/charging/ChargeArcGauge.tsx) | Ring CSS illustrativo, non fotografia né misurazione reale |
| Stato e traccia | [`MonitorHeroAccent.tsx`](https://github.com/Lucrezio0987-Org/CableCheck/blob/main/src/view/components/monitor/MonitorHeroAccent.tsx) | Accento energetico organico, linea sottile e visualizzazione stilizzata |
| Cura | [`CareScoreRing.tsx`](https://github.com/Lucrezio0987-Org/CableCheck/blob/main/src/view/components/care/CareScoreRing.tsx) e [`CareSectionBackdrop.tsx`](https://github.com/Lucrezio0987-Org/CableCheck/blob/main/src/view/components/care/CareSectionBackdrop.tsx) | Indicatore circolare, glow discreto e colori legati al significato |
| Confronti | [`ChargingComparisonPanel.tsx`](https://github.com/Lucrezio0987-Org/CableCheck/blob/main/src/view/components/charging/ChargingComparisonPanel.tsx) | Confronti disponibili ma condizionati ai dati e alla comparabilità |
| Identità app | [`assets/icon.png`](https://github.com/Lucrezio0987-Org/CableCheck/blob/main/assets/icon.png) | Il **marchio in CSS è una stilizzazione editoriale**, non pixel-identico all'icona installata; non dichiararlo screenshot originale |

## Creative direction

**Hero:** *«La ricarica, più chiara.»*  
**Punti chiave:** Monitor, Test, Cura.  
**Messaggio:** monitoraggio della potenza e della temperatura, confronti accessori e indicatori sulla batteria, limitati dai dati esposti dal dispositivo Android. Evitare diagnosi certe del cavo o garanzie assolute di stato batteria.

- HTML/CSS statico, WebView isolata: **nessun JavaScript, immagine, fetch, SVG inline, link arbitrario o risorsa remota**.
- Il diagramma mostra un ring generico con unità **W** e una traccia **illustrativa**, senza percentuali, wattaggi, temperature o score fittizi.
- Le informazioni sono in `{{eyebrow}}`, `{{headline}}`, `{{deck}}`, `{{footer}}`; le sei traduzioni provengono dal JSON.
- L'icona CSS raffigura concettualmente una batteria, non replica la vera icona app: limitazione documentata.
- L'host gestisce il frame, la X, la navigazione e l'attribuzione `source`.

## Anteprime del sorgente della campagna

| Poster 4:5, 320×400 | Banner inbox 16:9, 320×180 |
| --- | --- |
| ![CableCheck poster 4:5](./previews/cablecheck-launch-poster-4x5.png) | ![CableCheck banner inbox 16:9](./previews/cablecheck-launch-inbox-16x9.png) |

![CableCheck landscape 16:9](./previews/cablecheck-launch-landscape-16x9.png)

Le immagini sono **screenshot Chromium dello stesso HTML/CSS** incorporato nella campagna, non asset scaricati dallo Store né figure AI. Il client finale renderizza HTML/CSS compilato dal publisher.

## Contratto e distribuzione — stato attuale

| Campo | Valore |
| --- | --- |
| `status` | `draft` |
| `revision` | `1` |
| `audiences` | `["product.cablecheck"]` per primo preview client |
| `environments` | `["collaudo"]` |
| `placements` | `launch_modal`, `inbox`, `inline_promo` |
| `prioritySchedule` | `low`, quindi nessun popup automatico |
| `notification` | copy in sei lingue già preparato, **nessun invio** |
| `actions` | `[]`, nessuna CTA inattiva o link Play che porta a pagina non disponibile |
| `action` | `none` |

La PR in bozza **non cambia il feed pubblicato**, né il catalogo approvato WakeCupPC.

### Passaggio al lancio effettivo

1. **Confermare lo stato reale su Play Console/Store**: `com.lucrezio0987.cablecheck` disponibile, data, track e versione. Per promozioni pubbliche il catalogo `storePublished` deve essere vero solo **dopo conferma**.
2. Preparare la CTA dichiarativa `primary` con intent `open_store(cablecheck)` e label tradotte; inserire il placeholder `{{cta:primary}}` soltanto nel poster e nel landscape, in una zona di layout verificata, e aggiungere `action: open_store(cablecheck)`. Nel banner inbox non inserire CTA.
3. Definire **recipients**: al primo test `product.cablecheck` (lettore installato); promozione incrociata verso WakeCupPC solo **quando WakeCupPC supporterà il client AppCommunications** e con target/consenso appropriati.
4. Scegliere il canale e la frequenza della campagna: non imporre autoapertura o push senza decisione.
5. Rivedere anteprime IT/EN/ES/FR/DE/PT, 320px e Android; verificare CTA/store deep link/attribuzione, senza nuovi claim di release.
6. Fare merge della PR solo dopo approvazione; pubblicare **soltanto Collaudo** mediante trigger [AppCommunications scoped publisher](https://github.com/Lucrezio0987-Org/AppCommunications/blob/main/docs/AC-05-PUBLISHING.md) con SHA e revisione espliciti. Confermare nel ramo `published` ID, hash e isolamento Produzione.
7. Richiedere **autorizzazione separata** per eventuale ambiente Produzione e invio FCM.

## QA già eseguito / residuo

- [x] Sorgenti CableCheck consultati (tema, componenti, README, note release e catalogo Store).
- [x] Tre template distinti 4:5/16:9, senza CTA duplicate o dati fittizi.
- [x] Copy e notifica IT/EN/ES/FR/DE/PT.
- [x] Preview Chromium per **18 combinazioni** (3 layout × 6 lingue): nessun elemento fuori dai viewport 320×400, 320×180, 640×360.
- [x] Limite di lunghezza template e policy HTML statico verificati localmente.
- [ ] Approvazione visiva owner (poster, banner, landscape).
- [ ] Conferma pubblicazione reale Play e aggiunta CTA Store.
- [ ] Qualificazione publisher/CI della PR Draft.
- [ ] Smoke Android su CableCheck Collaudo e azione eventuale.
- [ ] Solo in seguito, autorizzazione alla distribuzione Collaudo; Produzione/FCM separati.

**Questa è una creatività di pre-lancio, non un'affermazione pubblica che CableCheck sia già sul Play Store.**
