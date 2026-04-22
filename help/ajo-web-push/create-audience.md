---
title: Creare un pubblico
description: Definisci un segmento in Adobe Experience Platform che esegue il targeting degli utenti idonei a ricevere notifiche push.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 3%

---

# Creare un pubblico

Per creare un pubblico per la campagna, definisci un segmento in Adobe Experience Platform che esegue il targeting degli utenti idonei a ricevere notifiche push. In questo tutorial, gli utenti che dispongono di una sottoscrizione push attiva (esiste un token push), non hanno rinunciato alle notifiche (il flag di Inserisce nell&#39;elenco Bloccati di è falso) e sono associati alla configurazione dell’applicazione specificata (l’identificatore dell’applicazione è uguale a `my-first-push`). Questi utenti sono idonei a ricevere notifiche push web tramite campagne o percorsi in Adobe Journey Optimizer. Dopo aver creato il pubblico, accertati che sia stato valutato in modo che i profili siano compilati e pronti per il targeting.
Questo pubblico viene quindi utilizzato nella campagna per inviare messaggi web push pianificati solo agli utenti abbonati.

![create-audience](assets/push-audience.png)

