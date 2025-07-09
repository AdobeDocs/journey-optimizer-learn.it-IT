---
title: Acquisizione delle interazioni dell’offerta con Adobe Web SDK per la formazione sui modelli AI
description: Questo articolo si concentra sull’acquisizione dei dati di interazione dell’utente, come impression e clic sull’offerta, mediante Adobe Experience Platform Web SDK (alloy.js). Questi dati fungono da base per la formazione dei modelli di intelligenza artificiale in Adobe Journey Optimizer (AJO) per classificare in modo intelligente le offerte in base al comportamento degli utenti e ai segnali contestuali.
feature: Decisioning
topic: Integrations
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2025-07-08T00:00:00Z
jira: KT-18451
source-git-commit: dfb280df3453e7811dffd95b9af664b873a9af31
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---


# Acquisizione delle interazioni dell’offerta con Adobe Web SDK per la formazione sui modelli AI

Questo articolo illustra come acquisire eventi di interazione dell’offerta (come impression o clic) utilizzando Adobe Experience Platform Web SDK chiamando alloy(&quot;sendEvent&quot;, ...) direttamente nel codice JavaScript. I dati verranno acquisiti in AEP e utilizzati per addestrare i modelli di intelligenza artificiale in Adobe Journey Optimizer (AJO) per una classificazione delle offerte più intelligente in base al comportamento in tempo reale.

## Prerequisiti

Prima di iniziare, assicurati che siano presenti i seguenti elementi:

- Una proprietà funzionante di Adobe Launch con l’estensione Adobe Experience Platform Web SDK installata.

- [datastream](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset) configurato e mappato alla sandbox AEP.

- Un sito web in cui viene distribuito Launch.


## Creare schemi e set di dati per eventi di interazione dell’offerta

Per raccogliere eventi di esperienza, devi innanzitutto creare un set di dati in cui verranno inviati questi eventi.

Segui i passaggi indicati in questo [articolo per creare lo schema e il set di dati richiesti](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset)

## Creare uno stream di dati in AEP

![flusso di dati](assets/ai-model-data-stream.png)
Aggiungere il servizio Adobe Experience Platform allo stream di dati
![data-stream-service](assets/data-stream-service.png)

## Configurare il tag Adobe Experience Platform con Web SDK

Nelle impostazioni dell’estensione:

Configurare l’estensione Adobe Experience Platform Web SDK per utilizzare lo stream di dati creato
