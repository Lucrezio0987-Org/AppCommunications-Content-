# CableCheck — Annuncio lancio | revisione creativa v2 HTML/CSS

> **REVISIONE CREATIVA v2 — 1 novembre 2026.** La proposta con grande indicatore «W», barre decorative e glow uniforme è stata scartata dall'owner: troppo generica e poco fedele a CableCheck. La nuova variante prende come riferimenti BatteryLevelGauge, ChargeArcGauge, MonitorHeroAccent, CareScoreRing e docs/design-system.md. Gli screenshot allegati sono render Chromium degli stessi template HTML/CSS v2.
>
> **Collaudo pre-lancio è consentito**, anche se la scheda Play non è pubblica. Non annunciare falsa disponibilità pubblica né aggiungere CTA Store non verificate. Questa PR resta Draft, niente Produzione/FCM.


**Stato:** BOZZA GRAFICA v2 DA APPROVARE — COLLAUDO PRE-LANCIO CONSENTITO, NON ANCORA PUBBLICATA  
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

## Creative direction v2: UI effettiva di CableCheck

**Headline:** «Capisci meglio ogni ricarica.» (in sei lingue). **Supporting line:** «Monitora. Confronta. Prenditi cura della batteria.».

- **Poster 4:5:** wordmark, eyebrow, headline e deck, una superficie dati con **arco 260°** ispirato a ChargeArcGauge e un andamento sottile ispirato a MonitorHeroAccent. In basso tre micro-indicatori richiamano Monitor/Test/Cura senza moltiplicare le card; footer localizzato.
- **Banner inbox 16:9:** composizione autonoma, testo a sinistra, gauge minimale a destra, nessun pulsante interno: l'intera card è tappabile nel client.
- **Landscape/inline:** testo e footer a sinistra, gauge e traccia dati in una sola superficie a destra.
- **Colori reali:** background #050706, surfaceRaised #111713, verde energia #4FE36B, azzurro informativo #69D2FF. Il design system richiede **meno box**, glow minimo, griglia discreta e colori semantici.
- **Niente valori fittizi:** archi e grafici sono stilizzazioni editoriali senza percentuali, watt, score o diagnosi inventati; W/°C/mA sono unità di misura, non dati di un dispositivo.
- **Fedeltà dichiarata:** il logomark batteria CSS è stilizzato, non la bitmap del launcher; i componenti raffigurati non sono screenshot reali.
- **Contratto:** tre template HTML/CSS statici con placeholder tradotti, nessuna risorsa remota, JS, SVG, img o CTA arbitraria. Le immagini PNG nel dossier sono **screenshot di revisione**, non immagini distribuite nel feed.

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

### Gate indipendenti: Collaudo / Lancio pubblico

**Collaudo pre-lancio:** dopo review grafica e test del contratto è possibile integrare la campagna senza alcuna disponibilità sul Play Store, mantenendo status draft fino all'approvazione. Pubblicare soltanto in Collaudo mediante workflow con SHA approvato. Verificare il vero APK e il rendering in Novità. Niente FCM.

**Produzione e CTA pubblica:** quando l'app sarà effettivamente disponibile e confermata, verificare la pagina Store, aggiungere azione dichiarativa open_store(cablecheck) nel solo poster/landscape, aggiornare copy e QA e chiedere autorizzazione separata per Produzione o FCM. Non inferire autorizzazioni da una PR approvata per Collaudo.

## QA già eseguito / residuo

- [x] Sorgenti CableCheck consultati (tema, componenti, README, note release e catalogo Store).
- [x] Tre template distinti 4:5/16:9, senza CTA duplicate o dati fittizi.
- [x] Copy e notifica IT/EN/ES/FR/DE/PT.
- [x] Preview Chromium per **18 combinazioni** (3 layout × 6 lingue): nessun elemento fuori dai viewport 320×400, 320×180, 640×360.
- [x] Limite di lunghezza template e policy HTML statico verificati localmente.
- [ ] Approvazione visiva owner (poster, banner, landscape).
- [ ] Verifica Play e CTA Store **solo per la futura comunicazione pubblica**, non necessaria al test Collaudo.
- [ ] Qualificazione publisher/CI della PR Draft.
- [ ] Smoke Android su CableCheck Collaudo e azione eventuale.
- [ ] Dopo review owner, collaudo su APK e verifica feed. Produzione/FCM separati.

**Questa è una creatività di pre-lancio per Collaudo, senza affermazioni di disponibilità su Play Store.**
