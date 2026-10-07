---
title: Creazione di tipi di pubblico in Adobe Journey Optimizer
description: Scopri come definire e creare tipi di pubblico mirati in AJO per fornire ai clienti percorsi personalizzati e prendere decisioni in tempo reale
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
jira: KT-17923
exl-id: d90f1868-0514-49b2-832d-82460883b6e4
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%
---
# Creazione di tipi di pubblico in Adobe Journey Optimizer


I tipi di pubblico in Adobe Experience Platform sono gruppi di utenti creati in base alle loro azioni, preferenze o informazioni di profilo, per fornire esperienze personalizzate.

* Accedi a Journey Optimizer
* Passa a Cliente -> Pubblico ->Crea pubblico
* Creare tipi di pubblico utilizzando il metodo Genera regola

  ![pubblico](assets/rule-based-audience.png)

* Crea i seguenti 3 tipi di pubblico

  * Clienti interessati alle scorte

  * Clienti interessati alle obbligazioni

  * Clienti interessati al CD


* Assicurati che il metodo di valutazione per ogni pubblico sia impostato su _&#x200B;**Edge**&#x200B;_ per la qualifica in tempo reale.
  ![edge-audience](assets/audience-edge.png)

* Utilizzare il campo PreferredFinancialInstrument per segmentare gli utenti in base all&#39;interesse di investimento selezionato, ad esempio azioni, obbligazioni o CD

![evento](assets/event-attribute.png)

![StrumentoFinanziarioPreferito](assets/stock-customers.png)




>[!NOTE]
>
>&#x200B;>Se il campo PreferredFinancialInstrument non è visibile nella scheda degli eventi, fai clic sull’icona delle impostazioni e attiva Mostra lo schema XDM completo.



![toggle-full-xdm-schema](assets/show-custom-fields.png)
