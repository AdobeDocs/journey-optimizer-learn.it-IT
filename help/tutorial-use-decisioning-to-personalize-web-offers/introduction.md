---
title: Utilizzare Decisioning per personalizzare le offerte web
description: Scopri come utilizzare Journey Optimizer (AJO) Decisioning per distribuire offerte personalizzate su una pagina web sfruttando la segmentazione del pubblico integrata in Experience Platform (AEP).
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
source-git-commit: 7d812f589172c5052a1e9bfcf6a99d0769a6c2c7
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 2%

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
