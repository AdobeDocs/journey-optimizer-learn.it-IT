---
title: Tracciamento e reporting delle offerte di Adobe Journey Optimizer (AJO) distribuite tramite AJO Decisioning
description: Questo tutorial estende un’implementazione Adobe Journey Optimizer (AJO) esistente che offre offerte personalizzate basate su dati contestuali come la temperatura. Illustra come acquisire gli eventi di impression e interazione e preparare i dati per il reporting in Journey Optimizer.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
source-git-commit: bfeab1e933f2a510506c0ecf911df41e66cb959b
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# Tracciamento e reporting delle offerte di Adobe Journey Optimizer (AJO) distribuite tramite AJO Decisioning

Questo caso d’uso si concentra sull’abilitazione del reporting e dell’analisi delle prestazioni per le offerte distribuite tramite Adobe Journey Optimizer (AJO). Quando le offerte sono personalizzate e consegnate in base a segnali contestuali (come meteo o posizione), è essenziale tenere traccia sia delle impression che delle interazioni dell’utente per valutarne l’efficacia.

Acquisendo gli eventi decisioning.propositionDisplay e decisioning.propositionInteract tramite Adobe Web SDK e mappandoli su schemi XDM strutturati in Adobe Experience Platform (AEP), i dati di coinvolgimento a livello di offerta diventano disponibili per l’analisi. Questi dati possono quindi essere utilizzati in Customer Journey Analytics (CJA) per creare dashboard, misurare metriche chiave quali il tasso di click-through (CTR) e confrontare le prestazioni dell’offerta tra diversi segmenti di pubblico e condizioni contestuali.

L’obiettivo è fornire informazioni chiare e basate sui dati sulle prestazioni delle offerte personalizzate e informare le future strategie decisionali.



![dashboard di reporting](assets/dashboard-reporting.png)


## Prerequisiti per questa esercitazione

Prima di iniziare, completa l&#39;esercitazione [Personalizzazione delle offerte con dati meteo in tempo reale.](https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction) Stabilisce tutti i componenti fondamentali, tra cui:

- Integrazione con Web SDK
- Configurazione dell’offerta in Adobe Journey Optimizer (AJO)
- Decisioning utilizzando attributi contestuali come meteo e temperatura
- Rendering di offerte in tempo reale su una pagina web

Questo tutorial si basa direttamente su tale implementazione e si concentra specificamente sull’acquisizione delle impression e delle interazioni dell’offerta per il reporting e l’analisi in Journey Optimizer.
