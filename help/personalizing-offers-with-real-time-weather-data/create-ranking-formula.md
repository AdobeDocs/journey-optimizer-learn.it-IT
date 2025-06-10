---
title: Crea formula di classificazione
description: Durante le decisioni sulle offerte viene utilizzata una formula di classificazione in Adobe Journey Optimizer, in particolare all’interno di una strategia di selezione per determinare l’ordine di priorità delle offerte idonee.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: c04a15418e31dc82597b7759386907013728bb0d
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# Crea formula di classificazione

Durante le decisioni sulle offerte viene utilizzata una formula di classificazione in Adobe Journey Optimizer, in particolare all’interno di una strategia di selezione per determinare l’ordine di priorità delle offerte idonee. La formula di classificazione entra in gioco dopo il filtro di idoneità, quando più offerte sono idonee per un determinato profilo, ma solo la prima (o poche) devono essere presentate in base alla logica di business o al contesto del profilo.

* Accedi a Journey Optimizer

* Passa a _&#x200B;**Decisioning ->Impostazione strategia ->Formule di classificazione ->Crea formula**&#x200B;_

Denomina la formula _&#x200B;**Meteo - Correlato - Offerte**&#x200B;_



Un criterio in una formula di classificazione si riferisce a una regola condizionale utilizzata per assegnare un punteggio a un’offerta. Questi criteri confrontano gli attributi dell’offerta e il contesto per determinare la rilevanza di un’offerta per un individuo specifico.

I seguenti 3 criteri sono definiti per filtrare le offerte e quindi assegnare un punteggio di classificazione all’offerta qualificata. I criteri vengono definiti utilizzando il generatore di criteri. I dati contestuali possono essere utilizzati anche per definire i criteri, come illustrato nella schermata seguente
![contxt-data](assets/context-data.png)

Tutti e 3 i criteri hanno utilizzato un attributo di offerta (tag) e un attributo di dati contestuali (temperatura) nella definizione dei criteri.

## Criterio uno

| **Tag offerta** | **Condizione dati contestuali** | **Logica punteggio** |
|------------------|---------------------|-------------------------------------|
| **caldo** | temperatura > 80 | score=Temperatura |


## Criterio 2

| **Tag meteo** | **Condizione dati contestuali** | **Logica punteggio** |
|------------------|---------------------------|----------------------------------------------|
| **primavera** | temperatura > 65 e &lt; 80 | score=temperatura × 4 |

## Terzo criterio

| **Tag meteo** | **Condizione dati contestuali** | **Logica punteggio** |
|------------------|---------------------------|----------------------------------------------|
| **freddo** | temperatura &lt; 65 | score =temperatura |
