---
title: Unione delle identità in AEP
description: Stabilisci l’unione di identità tra un utente noto (CRMID) e un visitatore web anonimo (ECID), abilitando profili unificati per la personalizzazione in tempo reale e la funzone offer decisioning in Adobe Journey Optimizer (AJO).
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
jira: KT-18089
exl-id: d6a1201a-3779-4718-8ea8-b88f925f53b6
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 11%
---
# Unione delle identità in AEP

Nelle moderne esperienze cliente, è fondamentale unificare le identità degli utenti tra dispositivi e canali. Questo caso d’uso illustra come implementare l’unione di identità in Adobe Experience Platform (AEP) collegando un ID CRM noto, acquisito durante l’accesso dell’utente, all’Experience Cloud ID (ECID) anonimo generato da Adobe Web SDK. Unendo queste identità in tempo reale, AEP può creare un profilo cliente più completo che si estende sia su comportamenti anonimi che su dati autenticati. Questo consente di segmentare il pubblico, personalizzarlo e prendere decisioni più precise in strumenti come Adobe Journey Optimizer (AJO).

## Abilità richieste per l’esercitazione sull’unione delle identità

Per trarre il massimo da questa esercitazione, si consiglia di acquisire familiarità con quanto segue:

- **Concetti di base di Adobe Experience Platform (AEP)**\
  Informazioni su schemi, set di dati, identità, criteri di unione e profili in tempo reale.

- **Modellazione schema e identità**\
  Possibilità di configurare i campi di identità negli schemi basati su profili ed eventi.

- **Adobe Launch (Tag) e Web SDK (Alloy.js)**\
  Scopri come configurare elementi dati e regole per inviare dati ad AEP utilizzando il Web SDK.

- **Nozioni di base su JavaScript**\
  Funzionalità comode per acquisire l’input dell’utente, attivare gli eventi ed eseguire il debug delle chiamate API.

- **Strumenti di debug di AEP**\
  Possibilità di utilizzare AEP Debugger e il visualizzatore del grafico delle identità per convalidare l’unione di identità.

- **Acquisizione dei dati in AEP**\
  Familiarità con il caricamento di dati di esempio nei set di dati e con la garanzia della qualità dei dati.


