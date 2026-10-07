---
title: Utilizzo di campi modulo modificabili nelle esperienze basate su codice di AJO
description: Scopri come creare blocchi di contenuto modificabili utilizzando campi modulo in linea nei modelli di esperienza basata su codice di Adobe Journey Optimizer, per offrire ai marketer contenuti dinamici e riutilizzabili per le campagne.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-22T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18416
exl-id: 0ba695d6-becb-440d-b0d0-de5b51b42562
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
source-wordcount: '221'
ht-degree: 22%
---
# Utilizzo di campi modulo modificabili nelle esperienze basate su codice di AJO

In molti percorsi di marketing, in particolare nelle industrie regolamentate, è essenziale includere una dichiarazione di non responsabilità legale che possa variare a seconda della campagna, della posizione geografica o del prodotto. Utilizzando un campo [modificabile](https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences) direttamente nell&#39;editor di AJO Personalization, gli addetti al marketing e i team legali possono mantenere il controllo completo sul testo della liberatoria senza coinvolgere gli sviluppatori o modificare la logica decisionale.

Questo consente aggiornamenti rapidi e garantisce la conformità in tutte le campagne, sfruttando al contempo contenuti decisi come le offerte.

## Inserire un campo modificabile nell’editor di personalizzazione

- Apri la campagna creata nel passaggio precedente.
- Fai clic su _**Modifica campagna**_
- Passa alla scheda _**Contenuto**_
- Fai clic su _**Modifica codice**_ e inserisci un campo modificabile denominato legalDisclaimer con un valore predefinito utilizzando la seguente sintassi nell&#39;editor di personalizzazione

- `{{#inline "legalDisclaimer" name="Legal Disclaimer"}} Legal Disclaimer will go here {{/inline}}`

- Utilizza la variabile `{{{legalDisclaimer}}}` nel modello come mostrato di seguito

- ![campi modificabili](assets/editable-fields.png)

- Gli addetti al marketing possono modificare facilmente il campo Dichiarazione di non responsabilità legale senza dover aprire l’editor di personalizzazione.
- ![editable-field-marketer](assets/editable-field-marketer-view.png)



## Pubblicare la campagna

Attiva la campagna per iniziare a consegnare offerte personalizzate in tempo reale.
