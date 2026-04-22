---
title: Debug di Web push in AJO
description: Questa pagina fornisce suggerimenti utili per eseguire il debug del flusso di notifica push web, inclusa la verifica delle richieste di Web SDK,
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# Debug di Web push in AJO

Questa pagina fornisce suggerimenti utili per eseguire il debug del flusso di notifica push web, tra cui la verifica delle richieste di Web SDK, la verifica dell’ECID e del profilo utente in AEP e la garanzia che eventi come price.drop siano inviati e ricevuti correttamente.

- **Utilizza Adobe Experience Platform Debugger (estensione Chrome)**\
  Installa l&#39;estensione [AEP Debugger per Chrome](https://chrome.google.com/webstore/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob) per controllare più facilmente l&#39;attività di Web SDK:

Questo strumento consente di:
- Visualizzare le richieste e le risposte di Web SDK\
- Controllare l’ECID (Experience Cloud ID)\
- Convalidare la configurazione e i payload dello stream di dati

- **Verifica se l&#39;utente è identificato (ECID)**\
  Utilizza AEP Debugger o la console del browser per confermare la generazione di un ECID. Questo ID viene utilizzato per tenere traccia dell’utente in AEP e AJO.

- **Utilizzare la scheda Rete per verificare le richieste**\
  Apri la **scheda Rete** negli strumenti per sviluppatori del browser e applica un filtro per le richieste effettuate dal Web SDK (cerca `/collect` o `interact`).
   - Le richieste di conferma vengono inviate al caricamento della pagina e quando vengono attivate le azioni
   - Verifica che l&#39;evento `price.drop` sia incluso nel payload

- **Cerca il profilo utente in AEP**\
  Utilizza l’ECID per cercare il profilo dell’utente in Adobe Experience Platform. Questo aiuta a confermare che l’utente è riconosciuto e che i suoi dati (come l’abbonamento push) vengono memorizzati correttamente.

- **Verificare che l&#39;evento `price.drop` sia stato ricevuto**\
  Dopo aver attivato l’evento dalla pagina web, archivia AEP se l’evento è stato acquisito e associato allo stesso ECID.
Controlla il codice JSON dell&#39;evento message.feedback per `feedback.status`. Il valore dello stato deve essere `sent`
  ![calo di prezzo](assets/price-drop-profile-event.png)

- **Conferma notifiche push abilitate**\
  Assicurati che:
   - L’utente ha accettato la richiesta di notifica del browser
   - Un token push esiste nel profilo dell’utente

- **Verifica la configurazione del percorso**\
  Assicurarsi che il percorso sia pubblicato e configurato per l&#39;ascolto dell&#39;evento `price.drop`.

