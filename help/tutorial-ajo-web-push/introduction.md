---
title: Push web in AJO
description: Questo tutorial illustra come implementare le notifiche push web utilizzando Adobe Journey Optimizer (AJO). Scoprirai come acquisire il consenso degli utenti con il Web SDK, inviare notifiche tramite campagne pianificate e attivare messaggi push in tempo reale utilizzando un evento price.drop personalizzato con i tag di AEP.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00.000Z
jira: KT-20879
exl-id: 5cda28e4-ea2f-4277-8951-a23525ca655a
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: 66e1fd99-672d-5d64-aa58-eca107f0fbae
    internal-label: Push
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 0%
---
# Push web in Adobe Journey Optimizer

Le notifiche web push sono un modo potente per coinvolgere nuovamente gli utenti in tempo reale e questo tutorial illustra i passaggi necessari per implementarle con Adobe Journey Optimizer (AJO). Inizierai utilizzando il Web SDK per acquisire le preferenze di consenso degli utenti per le notifiche push, garantendo un’esperienza di abbonamento fluida e conforme. Successivamente, creerai una campagna per inviare notifiche push agli utenti che hanno acconsentito, abilitando il coinvolgimento basato sul pubblico. Infine, imparerai a sfruttare i tag di AEP per attivare un evento personalizzato di calo dei prezzi, che avvia un percorso in AJO e fornisce notifiche push tempestive e personalizzate in base al comportamento degli utenti in tempo reale.

Pagina web di esempio per consentire agli utenti di dare il consenso per le notifiche

![enable-notifications](assets/enable-notifications.png)

Pagina web di esempio per attivare l’evento di calo dei prezzi

![riduzione prezzo trigger](assets/trigger-price-drop-event.png)

## Prerequisiti

Questo tutorial è progettato per essere pratico e facile da seguire. Anche se non è richiesta alcuna competenza approfondita, sarà utile acquisire una conoscenza di base dei seguenti concetti:

- Adobe Journey Optimizer (creazione di percorsi o campagne)
- Raccolta dati di AEP (tag) e Web SDK
- Concetti di base di Adobe Experience Platform come schemi ed eventi
- Alcuni concetti di JavaScript e di sviluppo web generale
- Conoscenza di base di Node.js (per generare chiavi VAPID e gestire un endpoint di configurazione semplice)

Se sei alle prime armi con una di queste aree, non preoccuparti: il tutorial ti guiderà attraverso i passaggi chiave del percorso.
Questo tutorial si concentra sull’implementazione di un caso di utilizzo end-to-end di notifiche web push, in modo che una conoscenza pratica degli strumenti e dei concetti di cui sopra ti aiuterà a seguire il percorso in modo efficace.


## 🔔 Abilita notifiche browser

Se le notifiche sono bloccate o non vengono visualizzate, potrebbe essere necessario abilitarle nelle impostazioni del browser. Consulta le guide seguenti:

- **Google Chrome (Windows/macOS)**\
  <https://support.google.com/chrome/answer/3220216>

- **Microsoft Edge (Windows)**\
  <https://support.microsoft.com/en-us/microsoft-edge/manage-website-notifications-in-microsoft-edge>

- **Safari (macOS)**\
  <https://support.apple.com/guide/safari/customize-website-notifications-sfri40734/mac>

- **Safari (iPhone/iPad)**\
  <https://support.apple.com/en-us/HT213893>


## Applicazione di esempio


Per aiutarti a seguire il percorso, è disponibile un’applicazione di esempio completa.

- [Demo live - Consenso:](https://ajo-web-push.onrender.com/)

- [Evento di ribasso prezzo trigger:](https://ajo-web-push.onrender.com/price-drop-trigger.html)

- [Codice Source:](https://github.com/gbedekar489/ajo-web-push)

Puoi esplorare la demo live per vedere il flusso in azione o clonare l’archivio per eseguire il progetto localmente.
