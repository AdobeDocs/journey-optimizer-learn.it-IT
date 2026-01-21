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
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# Implementare il limite di frequenza per le offerte Adobe Journey Optimizer (AJO) distribuite tramite AJO Decisioning

Questa esercitazione illustra come applicare il limite di frequenza alle offerte in Adobe Journey Optimizer per controllare la frequenza con cui gli utenti visualizzano la stessa offerta nel tempo.

Acquisendo gli eventi decisioning.propositionDisplay e decisioning.propositionInteract tramite Adobe Web SDK e mappandoli sugli schemi XDM in Adobe Experience Platform (AEP), Adobe Journey Optimizer può tracciare con precisione le impression e le interazioni delle offerte, consentendo di limitare la frequenza con cui un’offerta viene mostrata a un utente.

## Prerequisiti per questa esercitazione

Prima di procedere, accertati di disporre di una campagna Adobe Journey Optimizer valida utilizzando Decisioning che serve attivamente le offerte a una superficie web.

Questa esercitazione presuppone che la consegna delle offerte funzioni già e si concentra esclusivamente sulla configurazione e sulla convalida del comportamento di quota limite.


