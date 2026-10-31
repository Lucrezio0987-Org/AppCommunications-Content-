# Campagne visuali v2 — prototipo collaudo

La creatività è proprietà del repository editoriale pubblico. Il nuovo client CableCheck riconosce `campaigns.<locale>.json` sotto `published/docs/v2/<environment>/`. Le notizie v1 continuano a funzionare.

La campagna di prova usa HTML/CSS **senza JavaScript, collegamenti, form, immagini esterne o API native**. Il client disabilita JavaScript e blocca ogni navigazione della WebView. Chiudere la locandina e gestire i pulsanti è responsabilità dell'app.

La sorgente include due template (verticale e orizzontale) e le localizzazioni. Il publisher v2 dovrà validare il contratto, effettuare escaping dei campi localizzati, verificare contenuti e dimensioni, compilare i poster e generare i feed. La pubblicazione di prova può essere effettuata manualmente in collaudo finché il publisher privato v2 non è pronto. **Non distribuire campagne in produzione** con questa procedura.

L'editor visivo futuro opera sui template e sui contenuti; non deve introdurre script o risorse esterne. Il prefisso `content/campaigns` è separato dalle notizie v1.
