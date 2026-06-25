---
title: Crea pubblico
description: Definisci un segmento in Adobe Experience Platform che esegue il targeting degli utenti idonei a ricevere notifiche push.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 427bb35a-d607-48be-845d-9587c4cad86b
source-git-commit: 676c21ca09e0df8d404b05081d71b147755d65d5
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---

# Creare un pubblico

Per creare un pubblico per la campagna, definisci un segmento in Adobe Experience Platform che esegue il targeting degli utenti idonei a ricevere notifiche push. In questo tutorial, gli utenti che dispongono di una sottoscrizione push attiva (esiste un token push), non hanno rinunciato alle notifiche (il flag di Inserisce nell&#39;elenco Bloccati di è falso) e sono associati alla configurazione dell’applicazione specificata (l’identificatore dell’applicazione è uguale a `my-first-push`). Questi utenti sono idonei a ricevere notifiche push web tramite campagne o percorsi in Adobe Journey Optimizer. Dopo aver creato il pubblico, accertati che sia stato valutato in modo che i profili siano compilati e pronti per il targeting.
Questo pubblico viene quindi utilizzato nella campagna per inviare messaggi web push pianificati solo agli utenti abbonati.

![create-audience](assets/push-audience.png)
