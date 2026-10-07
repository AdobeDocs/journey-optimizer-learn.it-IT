---
title: Creare tag Adobe Experience Platform
description: Creazione di tipi di pubblico di AJO in base alle preferenze di investimento degli utenti (azioni, obbligazioni, CD)
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 04fad076-e897-4831-9147-768721858a80
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
source-wordcount: '286'
ht-degree: 0%
---
# Creazione di tag Adobe Experience Platform

I tag Adobe Experience Platform (precedentemente Adobe Launch) consentono di gestire e distribuire* tecnologie di marketing e analisi sul sito web senza dover modificare il codice del sito.

Questo [video descrive il processo di creazione dei tag esperienza Adobe](https://experienceleague.adobe.com/en/playlists/experience-platform-get-started-with-tags)

* Accedi a Raccolta dati
* Fai clic su _**Tag -> Nuova proprietà**
* Crea un tag Adobe Experience Platform denominato _**personalization-on-weather**_.
* Aggiungi le seguenti estensioni al tag

![tag-estensioni](assets/tags-extensions1.png)

* Aggiungi un elemento dati denominato &quot;ECID&quot; come mostrato di seguito. Questo elemento dati viene utilizzato successivamente nel reporting

![ecid-data-element](assets/ecid-data-element.png)

* Assicurarsi di configurare Adobe Experience Platform Web SDK in modo che utilizzi l&#39;ambiente corretto e lo **stream di dati correlato al meteo** creato nel passaggio precedente.

![configurazione-sdk-web](assets/tags-extensions.png)



## Creare e distribuire i tag di AEP


Crea una nuova libreria e aggiungi a essa tutte le risorse modificate, come illustrato nelle schermate seguenti.

**Aggiungi libreria**

![new-library](assets/tag-add-library.png)

**Crea una libreria**

Nella schermata Crea libreria specifica il nome della libreria e l’ambiente.

Aggiungi tutte le risorse modificate a questa libreria
![libreria di tag](assets/tag-build-library.png)

Quindi fai clic sul pulsante Salva e genera in sviluppo per generare la libreria

## Includi tag AEP nella pagina HTML

Quando pubblichi una proprietà AEP Tags, Adobe ti fornisce un tag script che devi inserire all&#39;interno del tuo HTML ` <head>` o nella parte inferiore dei tag ` <body>`.

1. Vai alla proprietà Tag (personalization-on-weather).
2. Fai clic su Ambienti e sull’icona Installa dell’ambiente desiderato (ad esempio Sviluppo, Staging, Produzione).
3. Prendi nota del codice incorporato. È necessario in una fase successiva di questa esercitazione.
