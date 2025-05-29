---
title: Crea formula di classificazione
description: Durante le decisioni sulle offerte viene utilizzata una formula di classificazione in Adobe Journey Optimizer, in particolare all’interno di una strategia di selezione per determinare l’ordine di priorità delle offerte idonee.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '253'
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
![criterio_uno](assets/criteria1.png)

Il criterio 1 contiene tre criteri:

* offerta._techmarketingdemos.offerDetails.zipCode == &quot;92128&quot; - controlla il CAP associato all’offerta.

* _techmarketingdemos.zipCode == &quot;92128&quot; - controlla il CAP nel profilo dell&#39;utente.

* _techmarketingdemos.annualIncome > 100000 - controlla il livello di reddito dal profilo dell’utente.

Se tutti questi criteri sono soddisfatti, l’offerta ottiene un punteggio di 40.






Criterio 2
![criteri_due](assets/criteria2.png)

Il criterio 2 contiene tre criteri:

* offerta._techmarketingdemos.offerDetails.zipCode == &quot;92126&quot; - controlla il CAP associato all’offerta.

* _techmarketingdemos.zipCode == &quot;92126&quot; - controlla il CAP nel profilo dell&#39;utente.

* _techmarketingdemos.annualIncome &lt; 100000 - controlla il livello di reddito dal profilo dell’utente.

Se tutti questi criteri sono soddisfatti, l’offerta ottiene un punteggio di 30.




