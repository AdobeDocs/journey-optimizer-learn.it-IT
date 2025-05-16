---
title: Unione delle identità in AEP
description: Stabilisci l’unione di identità tra un utente noto (CRMID) e un visitatore web anonimo (ECID), abilitando profili unificati per la personalizzazione in tempo reale e il Offer Decisioning in Adobe Journey Optimizer (AJO).
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---


# Descrizione del caso d’uso

Nelle moderne esperienze cliente, è fondamentale unificare le identità degli utenti tra dispositivi e canali. Questo caso d’uso illustra come implementare l’unione di identità in Adobe Experience Platform (AEP) collegando un ID CRM noto, acquisito durante l’accesso dell’utente, all’ID Experience Cloud anonimo (ECID) generato da Adobe Web SDK. Unendo queste identità in tempo reale, AEP può creare un profilo cliente più completo che si estende sia su comportamenti anonimi che su dati autenticati. Questo consente di segmentare il pubblico, personalizzarlo e prendere decisioni più precise in strumenti come Adobe Journey Optimizer (AJO).

