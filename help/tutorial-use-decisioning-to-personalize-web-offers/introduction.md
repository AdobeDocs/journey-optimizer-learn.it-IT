---
title: Utilizzare il decisioning per personalizzare le offerte web
description: Scopri come utilizzare Adobe Journey Optimizer (AJO) Decisioning per distribuire offerte personalizzate su una pagina web sfruttando la segmentazione del pubblico integrata in Adobe Experience Platform (AEP).
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
source-git-commit: 2ca9ffee1a2326b8ae55a8e8de496a632fea79c8
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 1%

---

# Utilizzare il decisioning per personalizzare le offerte web

Questo tutorial si basa su una configurazione della segmentazione del pubblico creata in precedenza utilizzando Adobe Experience Platform (AEP) Web SDK. Nell&#39;[esercitazione precedente](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction), le preferenze utente, ad esempio gli interessi in azioni, obbligazioni o certificati di deposito (CD), sono state acquisite e utilizzate per segmentare i singoli utenti in tipi di pubblico mirati in Adobe Experience Platform (AEP). Questo tutorial si basa su queste basi utilizzando Adobe Journey Optimizer (AJO) Decisioning per fornire offerte finanziarie personalizzate in tempo reale a tali tipi di pubblico, migliorando sia i risultati di coinvolgimento che quelli di conversione.

Puoi testare le offerte personalizzate di AJO in tempo reale utilizzando il collegamento seguente.
[Fai clic qui per visualizzare la demo in tempo reale](https://gbedekar489.github.io/finwise/welcome.html). Nella pagina verranno visualizzate le offerte in tempo reale basate sulle preferenze di investimento.

## Prerequisiti per questa esercitazione

* Accesso a Adobe Experience Platform

* Nozioni di base sui concetti di Adobe Experience Platform (profili, pubblico, set di dati)

* Familiarità con Adobe Journey Optimizer

* Conoscenza di base di JavaScript (lettura e scrittura di funzioni semplici)

* Possibilità di utilizzare gli strumenti di sviluppo del browser (schede Console e Rete)


## OBIETTIVO

Questa esercitazione ti guida attraverso la distribuzione di offerte di investimento personalizzate, come azioni, obbligazioni o CD, su un sito web tramite Adobe Journey Optimizer (AJO). Sfruttando la segmentazione del pubblico e le strategie decisionali, scopri come garantire che ogni visitatore veda l’offerta più rilevante in base alle sue preferenze.

## Strumenti utilizzati

* Adobe Experience Platform (AEP)
* Adobe Journey Optimizer (AJO)
* Tag Adobe Experience Platform
* AEP Web SDK (Alloy.js)
* Segmentazione di AEP Edge
* Una pagina web per visualizzare le offerte
