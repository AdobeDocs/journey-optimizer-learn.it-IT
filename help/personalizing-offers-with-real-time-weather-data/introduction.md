---
title: Personalizzazione delle offerte con i dati meteo in tempo reale in Adobe Journey Optimizer tramite Web SDK
description: Questo tutorial illustra come distribuire offerte dinamiche e in grado di riconoscere il meteo in Adobe Journey Optimizer utilizzando dati contestuali in tempo reale e l’API Personalization di Adobe Web SDK. Scopri come passare gli attributi del meteo (come temperatura e condizioni) dal sito web a Adobe Experience Platform, mapparli sullo schema dell’evento e utilizzarli nelle regole di decisione e nelle formule di classificazione per personalizzare le offerte al momento del caricamento della pagina. Ideale per gli esperti di marketing e gli sviluppatori che desiderano migliorare le esperienze digitali in un contesto ambientale in tempo reale.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18258
source-git-commit: 13c891c02a9a2da3ff742afaab7ceb449a417b5e
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# Descrizione del caso d’uso

L’utilizzo di dati relativi al meteo in Adobe Journey Optimizer (AJO) per distribuire le offerte consente alle aziende di personalizzare le esperienze dei clienti in base a condizioni ambientali reali e in tempo reale. Il tempo è un potente segnale contestuale. I bisogni e il comportamento delle persone cambiano a seconda del tempo. Utilizzando i dati meteo:

Distribuisci offerte pertinenti in linea con l’umore e l’ambiente del cliente

In una giornata calda, mostra un’offerta per bevande fredde o unità CA. In una giornata di pioggia, promuovere giacche o ombrelloni

Esempio di offerta basata sul meteo


![offerte meteo](assets/offers-use-case.png)



## Prerequisiti per questa esercitazione

* Accesso ad Experience Platform.

* Nozioni di base sui tag Adobe Experience Platform.

* Nozioni di base sui concetti di Experience Platform (profili, tipi di pubblico, set di dati).

* Familiarità con Journey Optimizer.

* Conoscenza di base di JavaScript (lettura e scrittura di funzioni semplici).

* Possibilità di utilizzare gli strumenti di sviluppo del browser (schede Console e Rete).
