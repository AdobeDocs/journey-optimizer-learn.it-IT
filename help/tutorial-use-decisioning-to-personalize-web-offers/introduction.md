---
title: Utilizzare Decisioning per personalizzare le offerte web
description: Scopri come utilizzare Journey Optimizer (AJO) Decisioning per distribuire offerte personalizzate su una pagina web sfruttando la segmentazione del pubblico integrata in Experience Platform (AEP).
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00.000Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
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
source-wordcount: '239'
ht-degree: 7%
---
# Utilizzare Decisioning per personalizzare le offerte web

Questo tutorial si basa su una configurazione della segmentazione del pubblico creata in precedenza utilizzando Adobe Experience Platform (AEP) Web SDK. Nell&#39;[esercitazione precedente](https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction), le preferenze utente, ad esempio gli interessi in azioni, obbligazioni o certificati di deposito (CD), sono state acquisite e utilizzate per segmentare i singoli utenti in tipi di pubblico mirati in Experience Platform. Questo tutorial si basa su queste basi utilizzando Adobe Journey Optimizer (AJO) Decisioning per fornire offerte finanziarie personalizzate in tempo reale a tali tipi di pubblico, migliorando sia i risultati di coinvolgimento che quelli di conversione.


## Prerequisiti per questa esercitazione

* Accesso ad Experience Platform

* Nozioni di base sui concetti di Experience Platform (profili, pubblico, set di dati)

* Familiarità con Journey Optimizer

* Conoscenza di base di JavaScript (lettura e scrittura di funzioni semplici)

* Possibilità di utilizzare gli strumenti di sviluppo del browser (schede Console e Rete)


## Obiettivo

Questa esercitazione ti guida attraverso la distribuzione di offerte di investimento personalizzate, come azioni, obbligazioni o CD, su un sito web tramite Journey Optimizer. Sfruttando le strategie di segmentazione del pubblico e di decisione, scopri come garantire che ogni visitatore veda l’offerta più rilevante in base alle sue preferenze.

## Strumenti utilizzati

* Adobe Experience Platform (AEP)
* Adobe Journey Optimizer (AJO)
* Tag Adobe Experience Platform
* AEP Web SDK (`Alloy.js`)
* Segmentazione di AEP Edge
* Una pagina web per visualizzare le offerte
