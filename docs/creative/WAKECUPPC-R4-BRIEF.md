# WakeCupPC — Campagna AppCommunications r4

**Stato:** specifica editoriale verificata sulle fonti di prodotto — `ASSET PRODUCTION NOT STARTED` / `NOT APPROVED FOR PUBLISH`  
**Data di decisione:** 2026-11-01  
**Proprietario:** Developer Profile / AppCommunications  
**Canale:** `product.cablecheck`, esclusivamente `collaudo`, `prioritySchedule: low`  
**Campagna:** `2026-10-31-wakecuppc-cross-promo` — futura `revision: 4` solo quando gli asset sono approvati  
**Ultima revisione effettivamente pubblicata:** r2. R3 scartata per mancata fedeltà al prodotto; ripristino [PR #9](https://github.com/Lucrezio0987-Org/AppCommunications-Content-/pull/9).

## 1. La causa dell'errore r3

La r3 riprendeva una **scena promozionale illustrativa** con finto screenshot smartphone e fondale luminoso. Non era costruita sui componenti realmente presenti nel codice di WakeCupPC, né seguiva la regia già approvata del suo video. Trasformare la stessa illustrazione in 4:5 e 16:9 non costituisce una coppia di creatività ottimizzate. Il logo illustrativo era simile, ma il prodotto non veniva rappresentato con sufficiente precisione. I due JPG r3 sono stati rimossi dal ramo editoriale attivo.

**Non riproporre né variare i due JPG r3.** Non usare immagini AI, stock, schermate inventate o immagini di altri progetti. Non trattare una palette blu come prova di aderenza al brand.

## 2. Fonti canoniche verificate — in ordine di autorità

| Fonte | Cosa estrarre | Vincolo |
| --- | --- | --- |
| [WakeCupPC, progetto Android](https://github.com/lucrezio0987/HIDAutoInput2) | Posizionamento, funzioni e interfaccia effettiva | Non inventare comportamenti e controlli |
| [Store Listing](https://github.com/lucrezio0987/HIDAutoInput2/blob/main/docs/STORE_LISTING.md) | Promessa consumer e gerarchia funzionale | Keep Awake prima; touchpad secondario |
| [Icona launcher in produzione](https://github.com/lucrezio0987/HIDAutoInput2/blob/studio/wakecuppc-promo/assets/app-icon/icon.png) | Marchio esatto, monitor sorridente + tazza, cromie | Riutilizzare byte ufficiali, non ricostruire o ridisegnare il logo |
| [Remotion — WakeCupPCPromo](https://github.com/lucrezio0987/HIDAutoInput2/blob/studio/wakecuppc-promo/promo-video/src/WakeCupPCPromo.tsx) | Scelta di inquadrature, final card, ritmo e priorità comunicativa | Rispettare regia consolidata (v24), no montaggio generico |
| [Remotion — ReelPhone](https://github.com/lucrezio0987/HIDAutoInput2/blob/studio/wakecuppc-promo/promo-video/src/ReelPhone.tsx) | Device, PC, activity panel e mascotte esistente | Sono primitive già sviluppate, non mockup esterni |
| [Remotion — RealWakeCupPCUi](https://github.com/lucrezio0987/HIDAutoInput2/blob/studio/wakecuppc-promo/promo-video/src/RealWakeCupPCUi.tsx) | RealDeviceCard, RealKeepAwakeControl, RealTouchpadPreview e timer/schedule | Sono wrapper di componenti reali dell'app; riusarli o acquisirli tramite render ufficiale |
| [Remotion — styles.css](https://github.com/lucrezio0987/HIDAutoInput2/blob/studio/wakecuppc-promo/promo-video/src/styles.css) | Tipografia, effetti, composizione e colori corretti | Non importare un tema CableCheck |
| [Palette predefinita app](https://github.com/lucrezio0987/HIDAutoInput2/blob/main/src/config/personalization.config.ts) | Primary blu, secondary rosa, tertiary giallo | I temi utente sono personalizzabili; per campagna adottare visual v24 |

**Nota:** i file promozionali originali mostrati in chat possono essere usati come *reference di intenzione*, ma non costituiscono prova di come appare realmente la UI. La verticale con il testo incompleto è **bloccata**. Il materiale quadrato illustrativo è anch'esso **non utilizzabile come output finale**.

## 3. Design system derivato dal video ufficiale

| Token | Valore | Uso |
| --- | --- | --- |
| `canvas` | `#0B1016` | Sfondo principale, reale in Remotion |
| `surface` | `#121922` | Schede e interfaccia |
| `raised` | `#1B2530` | Pannelli attivi |
| `border` | `#2A3745` | Outline interfaccia |
| `actionBlue` | `#4C84FF` | Controlli e feedback Keep Awake |
| `cyan` | `#15DBF7` | Accento tipografico del finale |
| `successGreen` | `#4ADE9B` | **Solo stato ACTIVE**, non campitura generale |
| `accentPink` | `#FF567C` | Punchline completa `Or Unfocus.` quando culturalmente utilizzabile |
| `text` | `#F7F9FC` | Testo principale |
| `muted` | `#9CAABA` | Supporto |

Font: gerarchia sans moderna già presente nel video (stile Inter), con contrasto netto. Il lettering manuale Caveat è riservato alla **battuta completa** del finale inglese; mai mostrare `Or Unfocus.` isolato.

**Identificatore visivo decisivo:** il computer/mascotte reale che passa da AWAY a AWAKE, la barra di attività che si rinnova, il pallino verde ACTIVE e il pulsante Mantieni attivo. Non un generico telefono in una stanza piena di luci.

## 4. Composizione A — poster 4:5 (960 × 1200)

**Scopo:** far capire immediatamente *cosa fa WakeCupPC* e mostrare il controllo vero.

| Area di artwork | Priorità e contenuto | Fonte esatta |
| --- | --- | --- |
| Fascia superiore (circa 0–18%) | Icona launcher originale e wordmark `WakeCupPC`, ben visibili | `assets/app-icon/icon.png` e stile `FinalScene` |
| Corpo (18–80%) | In evidenza il **RealKeepAwakeControl ATTIVO**, una miniatura fedele di `RealDeviceCard` e l'indicatore di attività PC di `TutorialActivityPanel`. Un solo percorso visuale telefono → Keep Active → PC ACTIVE | `RealWakeCupPCUi.tsx`, `ReelPhone.tsx` |
| Ultima fascia artwork (80–100%) | Respiro visivo, non impaginare qui una CTA nel JPEG. Eventuali elementi decorativi solo se già derivano dalle primitive del video | Sfondo e aurora ufficiali |

**Copy nel JPEG:** solo il nome `WakeCupPC` e simboli strettamente necessari a rappresentare il prodotto; i messaggi di vendita devono rimanere **nel feed localizzato e nel renderer nativo**. Non stampare `Your PC stays active / You stay focused / Or Unfocus` sopra l'asset: il client mostra già `campaign.title`, `campaign.body` e la CTA sotto l'immagine.

**Comportamento reale del client:** `CampaignCreative.tsx` mette il poster `Image resizeMode=contain` in una View, poi un blocco nativo con titolo, body e `primary` CTA. Il layout deve funzionare con la parte inferiore occupata dalla CTA nativa. La X resta chrome dell'app. Non disegnare una seconda X o un bottone Google Play nell'asset.

**Non negoziabile:** non renderizzare uno screenshot finto. Se serve una schermata, catturarla dal compositore Remotion già esistente che usa i componenti React Native reali, oppure da dispositivo, mantenendo le icone, testi e valori corretti.

## 5. Composizione B — banner inbox 16:9 (1280 × 720)

**Scopo:** riconoscibilità in miniatura e click sulla scheda per aprire il poster.

- **Sinistra 55%:** icona ufficiale ben distinguibile e wordmark WakeCupPC; testo eventualmente solo `WakeCupPC`, non una frase di lunghezza non localizzata.
- **Destra 45%:** mascotte `ProductionMascot` in stato attivo e schematizzazione di `TutorialActivityPanel` già implementata (barra che si rinnova / ACTIVE verde), oppure `RealDeviceCard` reale in modalità running. Non un telefono generico con pulsanti inventati.
- **Sfondo:** canvas midnight, gradienti molto sobri/aurora coerenti con la direzione Remotion, mai texture tech casuali.
- **Niente pulsante Play, niente CTA duplicata:** tutta la scheda è una superficie tappabile gestita da CableCheck; non aggiungere `Apri ›`.
- **Leggibilità:** test sulla dimensione effettiva del banner mostrato nella pagina Novità Android; nessun testo funzionale inferiore a dimensione leggibile e niente frammenti ritagliati.

**Errore r3 da non ripetere:** inserire l'intero artwork quadrato al centro di una canvas 16:9, ridurlo fino a renderlo minuscolo e lasciare grandi bande vuote.

## 6. Copy editoriale e locali

Conservare campagna e copy **già convalidati** della r2, senza modificare arbitrariamente i claim. In italiano, i campi da mantenere sono:

- `title`: `Scopri WakeCupPC`
- `headline` nel fallback: `Il PC resta attivo.`
- `body`: `WakeCupPC usa il telefono come dispositivo Bluetooth HID e invia piccoli movimenti del mouse per mantenere attivo il PC. Non serve installare software sul computer; è richiesto il supporto HID.`
- `primary`: `Apri su Google Play`

Le altre cinque lingue provengono dallo stesso JSON sorgente r2: `en`, `es`, `fr`, `de`, `pt`. Il publisher mantiene i fallback. In tutte le lingue: niente claim sulla possibilità di risvegliare un PC già spento/sospeso, aggirare lock screen o nascondere attività.

**Slogan inglese opzionale** soltanto in un supporto/locale in cui compare **per intero e in ordine**:
`Your PC stays active.` → `You stay focused.` → `Or Unfocus.`
Non usare la punchline come parte grafica isolata né come testo comune ai sei locali.

## 7. Produzione controllata degli asset (senza AI)

1. Recuperare **file ufficiali e branch ufficiali** sopra riportati, senza cercare immagini a caso sul web.
2. Dal compositore Remotion, ottenere still/screenshot dei componenti **reali**: `ProductionMascot`, `RealDeviceCard`, `RealKeepAwakeControl`, `TutorialActivityPanel`. In alternativa usare screenshot diretti da WakeCupPC; segnare la provenienza.
3. Preparare un master grafico unico e due **layout distinti**; non fare zoom/crop cieco del vecchio JPEG.
4. Esportare soltanto `PNG/JPEG/WebP` validati, massimo `1,500,000` byte, 4.096 px per lato, 8 MP; target 960×1200 e 1280×720.
5. Verificare la somiglianza col repo facendo un confronto visivo affiancato tra asset esportati e video ufficiale. Conservare l'elenco delle fonti, hash, mock/still e locale.
6. Verificare su Android Collaudo con renderer `image_ad`: poster, inbox, overflow della X, CTA Play, source, fallback offline/legacy, asset cache, TalkBack.
7. Solo dopo l'esame visuale aggiornare la campagna alla `revision: 4`, `status: published`, `environments: [collaudo]`; pubblicare un **nuovo run dal branch main aggiornato** del publisher privato, non un rerun di un vecchio run, e verificare `published`. Nessuna produzione/FCM implicita.

## 8. Gate di accettazione

- [ ] I due file sono **nuovi adattamenti dai componenti originali**, non r3 ricolorata/ritagliata.
- [ ] Icona esattamente corrispondente a `assets/app-icon/icon.png`.
- [ ] La UI mostrata corrisponde al prodotto reale; nessun pulsante, screen o comportamento inventato.
- [ ] La funzione Keep Awake è l'elemento più evidente; touchpad è secondario.
- [ ] L'utente riconosce WakeCupPC anche senza leggere il body.
- [ ] Nessun testo sbagliato/tagliato; nessuna lingua incongruente.
- [ ] Poster non ripete CTA, titolo o body già renderizzati nativamente.
- [ ] Banner si legge nello storico Novità senza zoom e apre la modale.
- [ ] Hash e media budgets validati automaticamente; fallback HTML sicuro.
- [ ] CI, collaudo e screenshot approvati **prima** della pubblicazione.
- [ ] `Content-/published` mostra r4 solo per Collaudo; Produzione resta senza questa campagna.

## 9. Stato reale e confini

**r2:** approvata e distribuita (temporaneamente verde).  
**r3:** scartata e tolta dal catalogo tramite PR #9; byte storici in Git, non riutilizzabili come creativo approvato.  
**r4:** il presente documento è un **brief**, non contiene due asset finali e non autorizza publisher/merge automatici. Nessuna immagine AI richiesta o generata.

**Responsabilità:** il Developer Profile mantiene la campagna e i media. L'agente CableCheck non deve riscrivere il branding: verifica solo il rendering quando ci saranno asset r4 reali.
