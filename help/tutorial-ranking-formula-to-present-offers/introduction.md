---
title: Personalizzare le offerte con formule di ranking basate sul reddito e sul codice postale
description: Utilizza le formule di ranking di Adobe Journey Optimizer per distribuire in modo dinamico le offerte finanziarie più rilevanti, personalizzate in base al codice postale e al livello di reddito di ciascun utente, per un coinvolgimento più elevato e una personalizzazione più intelligente.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-27T00:00:00.000Z
jira: KT-18188
exl-id: 11685f7c-8048-4318-9c28-71bd7da8f7ff
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
source-wordcount: '338'
ht-degree: 16%
---
# Personalizzare le offerte con formule di classificazione basate sul codice postale dell’utente e sul reddito

Questo caso d’uso illustra come distribuire offerte finanziarie personalizzate sfruttando attributi utente come il codice postale e il reddito annuale in Adobe Journey Optimizer. Utilizzando formule di classificazione, le offerte ricevono un punteggio intelligente e un ordine di priorità in base a promozioni specifiche per la posizione e all’idoneità basata sul reddito. Ad esempio, i CD ad alto rendimento possono essere promossi agli utenti con codici postali ricchi, mentre agli investitori emergenti vengono mostrate opzioni di investimento diversificate. Le formule di classificazione garantiscono che ogni utente riceva offerte pertinenti e finanziariamente appropriate. I criteri di classificazione sono definiti utilizzando gli attributi di profilo, i segnali contestuali e i modelli di IA opzionali per migliorare ulteriormente la precisione delle decisioni. Le offerte vengono consegnate in tempo reale tramite canali web o e-mail, aumentando il coinvolgimento e la conversione. Questo approccio combina logica di business e personalizzazione basata sui dati per migliorare l’esperienza utente e l’impatto sul marketing.

## Prerequisiti

Questo tutorial si basa sui concetti chiave di Adobe Journey Optimizer e Adobe Experience Platform. Prima di procedere, accertati che siano soddisfatti i seguenti prerequisiti:

* [Tutorial sull&#39;unione delle identità](https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorial-on-identity-stitching-in-aep/introduction) completato. Gli ID del sistema di gestione delle relazioni con i clienti sono stati associati agli ECID in Adobe Experience Platform.

* Conoscenza della creazione di elementi di offerta in AJO, inclusa la definizione del contenuto, la configurazione dei metadati e le regole di idoneità.

* Ha familiarità con la configurazione dei canali (ad esempio web o e-mail) per la consegna delle offerte.

* Conoscenza della creazione e dell’attivazione di campagne in AJO.

* Conoscenza dell’utilizzo di Adobe Launch (Tag) per distribuire il Web SDK e inviare eventi contenenti dati di identità e profilo.

Questo tutorial illustra i passaggi successivi in offer decisioning:

* Creazione di un metodo di classificazione utilizzando gli attributi del profilo, ad esempio il codice postale e il reddito annuale.

* Definizione di una strategia di selezione per raggruppare le offerte e assegnare loro una priorità.

* Creare una politica decisionale per fornire l’offerta più rilevante a ogni individuo.
