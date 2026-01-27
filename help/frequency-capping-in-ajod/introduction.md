---
title: Implementare il limite di frequenza per le offerte Adobe Journey Optimizer (AJO) distribuite tramite AJO Decisioning
description: Questa esercitazione estende un’implementazione esistente di Adobe Journey Optimizer (AJO) abilitando il limite di frequenza per le offerte servite tramite AJO Decisioning. Illustra come acquisire gli eventi di impression e interazione utilizzati nella quota limite.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
source-git-commit: 441fdbc33486f027c22d1b94e03919c5666ca003
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Implementare il limite di frequenza per le offerte Adobe Journey Optimizer (AJO) distribuite tramite AJO Decisioning

Questa esercitazione illustra come applicare il limite di frequenza alle offerte in Adobe Journey Optimizer per controllare la frequenza con cui gli utenti visualizzano la stessa offerta nel tempo.

Questo tutorial presuppone che tu abbia già configurato una campagna AJO seguendo il [tutorial sulla personalizzazione delle offerte in base alle condizioni meteo](https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction)

Acquisendo gli eventi decisioning.propositionDisplay e decisioning.propositionInteract tramite Adobe Web SDK e mappandoli sugli schemi XDM in Adobe Experience Platform (AEP), Adobe Journey Optimizer può tracciare con precisione le impression e le interazioni delle offerte, consentendo di limitare la frequenza con cui un’offerta viene mostrata a un utente.

## Prerequisiti per questa esercitazione

Prima di procedere, accertati di disporre di una campagna Adobe Journey Optimizer valida utilizzando Decisioning che serve attivamente le offerte a una superficie web.

Questa esercitazione presuppone che la consegna delle offerte funzioni già e si concentra esclusivamente sulla configurazione e sulla convalida del comportamento di quota limite.




