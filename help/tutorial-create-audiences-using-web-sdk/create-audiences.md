---
title: Creazione di tipi di pubblico in Adobe Journey Optimizer
description: Scopri come definire e creare tipi di pubblico mirati in AJO per fornire ai clienti percorsi personalizzati e prendere decisioni in tempo reale
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: ba83be3caf214d2daaa8c99556d246686ff3f0cb
workflow-type: tm+mt
source-wordcount: '148'
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


