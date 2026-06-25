---
title: Acquisire le autorizzazioni utente
description: Crea una pagina web per acquisire il consenso dell’utente alla ricezione di notifiche push.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00.000Z
jira: KT-20879
exl-id: 5897420a-7488-4d48-b56c-86a53d1d2395
TQID: 'https://experienceleague.adobe.com/O5xiLJ7UOQNYSkfpCa2umhCkxt1cKILsO4fOKxtVifM'
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
source-git-commit: 676c21ca09e0df8d404b05081d71b147755d65d5
workflow-type: tm+mt
source-wordcount: 219
ht-degree: 0%

---

# Acquisire le autorizzazioni utente

Questa pagina web acquisisce il consenso dell’utente alla ricezione di notifiche push. Chiede all’utente di abilitare le notifiche utilizzando l’API Notifications del browser e, una volta accettata, registra l’abbonamento push con Adobe Experience Platform utilizzando il Web SDK. In questo modo solo gli utenti che hanno prestato il consenso possono ricevere notifiche push tramite campagne e percorsi in Adobe Journey Optimizer.

Per abilitare le notifiche web push, la pagina carica innanzitutto un file di configurazione chiamando fetch(&quot;/config&quot;) all’interno di una funzione di inizializzazione. Questa configurazione è gestita da un’applicazione Node.js e include valori chiave quali ID dello stream di dati, ID organizzazione, chiave pubblica VAPID, ID app e ID del set di dati di tracciamento. Una volta caricata la configurazione, Adobe Web SDK viene inizializzato e il service worker viene registrato per supportare i messaggi push. Quando un utente fa clic su Abilita notifiche, il browser richiede l’autorizzazione utilizzando l’API per le notifiche web. Se l’autorizzazione è concessa, il Web SDK invia l’abbonamento push a Adobe Experience Platform e l’utente viene contrassegnato come acconsentito per 24 ore per evitare ripetuti prompt. È possibile provare questo flusso nella pagina Web locale shop-smart.html inclusa nell&#39;[applicazione di esempio](http://localhost:3000/) dopo l&#39;avvio del server.

![autorizzazioni-richiesta](assets/request-notifications.png)
