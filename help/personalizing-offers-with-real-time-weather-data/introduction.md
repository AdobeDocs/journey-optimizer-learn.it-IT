---
title: Personalizzazione di offerte con dati meteo in tempo reale in Adobe Journey Optimizer tramite Web SDK
description: Questo tutorial illustra come distribuire offerte dinamiche e in base al meteo in Adobe Journey Optimizer utilizzando dati contestuali in tempo reale e l’API di personalizzazione di Adobe Web SDK. Scoprirai come passare gli attributi del meteo (come temperatura e condizioni) dal tuo sito web ad Adobe Experience Platform, mapparli sullo schema degli eventi e utilizzarli nelle regole di decisione e nelle formule di ranking per personalizzare le offerte al momento del caricamento della pagina. Ideale per i marketer e gli sviluppatori che desiderano migliorare le esperienze digitali nel contesto di un ambiente in tempo reale.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10
jira: KT-18258
exl-id: f40dd541-470c-4f42-8181-eb1c277ebaa3
source-git-commit: b4cf9b677c6bc142e1013649db16b3a70b405052
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 42%
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
