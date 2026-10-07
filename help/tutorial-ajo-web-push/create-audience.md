---
title: Crea pubblico
description: Definisci un segmento in Adobe Experience Platform che esegue il targeting degli utenti idonei a ricevere notifiche push.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00.000Z
jira: KT-20879
exl-id: 427bb35a-d607-48be-845d-9587c4cad86b
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
source-wordcount: '131'
ht-degree: 3%
---
# Creare un pubblico

Per creare un pubblico per la campagna, definisci un segmento in Adobe Experience Platform che esegue il targeting degli utenti idonei a ricevere notifiche push. In questo tutorial, gli utenti che dispongono di una sottoscrizione push attiva (esiste un token push), non hanno rinunciato alle notifiche (il flag di Inserisce nell&#39;elenco Bloccati di è falso) e sono associati alla configurazione dell’applicazione specificata (l’identificatore dell’applicazione è uguale a `my-first-push`). Questi utenti sono idonei a ricevere notifiche push web tramite campagne o percorsi in Adobe Journey Optimizer. Dopo aver creato il pubblico, accertati che sia stato valutato in modo che i profili siano compilati e pronti per il targeting.
Questo pubblico viene quindi utilizzato nella campagna per inviare messaggi web push pianificati solo agli utenti abbonati.

![create-audience](assets/push-audience.png)
