---
title: Personalizzazione delle offerte di pagine web con AJO Decisioning in base al pubblico
description: Scopri come utilizzare Adobe Journey Optimizer (AJO) Decisioning per distribuire offerte personalizzate su una pagina web sfruttando la segmentazione del pubblico integrata in Adobe Experience Platform (AEP).
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
source-git-commit: 9695a4db0d0caa44a8c7d49e069320309ffc40a6
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 1%

---


# Creazione di tipi di pubblico di AJO in base alle preferenze di investimento degli utenti (azioni, obbligazioni, CD)

Questo tutorial si basa su una configurazione della segmentazione del pubblico creata in precedenza utilizzando Adobe Experience Platform (AEP) Web SDK. Nell’esercitazione precedente, le preferenze dell’utente, ad esempio interesse per azioni, obbligazioni o certificati di deposito (CD), venivano acquisite e utilizzate per segmentare i singoli utenti in tipi di pubblico mirati in Adobe Experience Platform (AEP). Questo tutorial si basa su queste basi utilizzando Adobe Journey Optimizer (AJO) Decisioning per fornire offerte finanziarie personalizzate in tempo reale a tali tipi di pubblico, migliorando sia i risultati di coinvolgimento che quelli di conversione.

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





