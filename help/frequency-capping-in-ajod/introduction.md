---
title: Implementare il limite di frequenza per le offerte Adobe Journey Optimizer (AJO) distribuite tramite AJO Decisioning
description: Questa esercitazione estende un’implementazione esistente di Adobe Journey Optimizer (AJO) abilitando il limite di frequenza per le offerte servite tramite AJO Decisioning. Illustra come acquisire gli eventi di impression e interazione utilizzati nella quota limite.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 7%
---
# Implementare il limite di frequenza per le offerte Adobe Journey Optimizer (AJO) distribuite tramite AJO Decisioning

Questa esercitazione illustra come applicare il limite di frequenza alle offerte in Adobe Journey Optimizer per controllare la frequenza con cui gli utenti visualizzano la stessa offerta nel tempo.

Questo tutorial presuppone che tu abbia già configurato una campagna AJO seguendo il [tutorial sulla personalizzazione delle offerte in base alle condizioni meteo](https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction)

Acquisendo gli eventi decisioning.propositionDisplay e decisioning.propositionInteract tramite Adobe Web SDK e mappandoli sugli schemi XDM in Adobe Experience Platform (AEP), Adobe Journey Optimizer può tracciare con precisione le impression e le interazioni delle offerte, consentendo di limitare la frequenza con cui un’offerta viene mostrata a un utente.

## Prerequisiti per questa esercitazione

Prima di procedere, accertati di disporre di una campagna Adobe Journey Optimizer valida utilizzando Decisioning che serve attivamente le offerte a una superficie web.

Questa esercitazione presuppone che la consegna delle offerte funzioni già e si concentra esclusivamente sulla configurazione e sulla convalida del comportamento di quota limite.




