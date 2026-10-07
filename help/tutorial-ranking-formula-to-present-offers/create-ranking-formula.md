---
title: Crea formula di classificazione
description: Durante le decisioni sulle offerte viene utilizzata una formula di classificazione in Adobe Journey Optimizer, in particolare all’interno di una strategia di selezione per determinare l’ordine di priorità delle offerte idonee.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18188
exl-id: eee1b86e-b33f-408e-9faf-90317bc5e861
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
source-wordcount: '346'
ht-degree: 0%
---
# Crea formula di classificazione

Durante le decisioni sulle offerte viene utilizzata una formula di classificazione in Adobe Journey Optimizer, in particolare all’interno di una strategia di selezione per determinare l’ordine di priorità delle offerte idonee. La formula di classificazione entra in gioco dopo il filtro di idoneità, quando più offerte sono idonee per un determinato profilo, ma solo la prima (o poche) devono essere presentate in base alla logica di business o al contesto del profilo.

* Accedi a Journey Optimizer

* Decisioning ->Impostazione strategia ->Formule di classificazione ->Crea formula

Formula di classificazione
![nome_descrizione](assets/formuala-ranking.png)

Un criterio in una formula di classificazione si riferisce a una regola condizionale utilizzata per assegnare un punteggio a un’offerta. Questi criteri confrontano gli attributi dell’offerta con il profilo o il contesto per determinare la rilevanza di un’offerta per un individuo specifico.



Criterio 1

Questa condizione filtra gli elementi decisionali (offerte) **per includere solo** le offerte con tag &quot;IncomeLevel&quot;.
Queste offerte filtrate procederanno quindi al passaggio successivo, ad esempio la classificazione o la consegna, in base alla logica aggiuntiva definita dall’utente.
![criterio_uno](assets/income-related-formula.png)


L’espressione seguente viene utilizzata per creare il punteggio di classificazione

```pql
if(   offer._techmarketingdemos.offerDetails.zipCode = _techmarketingdemos.zipCode,   _techmarketingdemos.annualIncome / 1000 + 10000,   if(     not offer._techmarketingdemos.offerDetails.zipCode,     _techmarketingdemos.annualIncome / 1000,     -9999   ) )
```

Funzionamento della formula

* Se l’offerta ha lo stesso codice postale dell’utente, assegnagli un punteggio molto alto in modo che venga selezionata per prima.

* Se l’offerta non ha alcun codice postale (si tratta di un’offerta generale), assegnale un punteggio normale in base al reddito dell’utente.

* Se l’offerta ha un codice postale diverso da quello dell’utente, assegna un punteggio molto basso in modo che non sia selezionata.

In questo modo, il sistema:

* Tenta sempre di mostrare prima un’offerta con corrispondenza ZIP,

* Torna a un’offerta generale se non viene trovata alcuna corrispondenza ed evita di mostrare offerte destinate ad altri codici postali.


Se un elemento dell’offerta non soddisfa nessuno dei criteri di filtro (ad esempio non dispone del tag &quot;IncomeLevel&quot;), l’offerta riceve un punteggio di classificazione predefinito di 10.




