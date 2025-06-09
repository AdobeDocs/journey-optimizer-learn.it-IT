---
title: Creare tag Adobe Experience Platform
description: Creazione di tipi di pubblico di AJO in base alle preferenze di investimento degli utenti (azioni, obbligazioni, CD)
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: dac6b373226bd0be2533cf859e4f250018cf568b
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---

# Creazione di tag AEP

I tag Adobe Experience Platform (precedentemente Adobe Launch) consentono di gestire e distribuire* tecnologie di marketing e analisi sul sito web senza dover modificare il codice del sito.

Questo [video descrive il processo di creazione dei tag esperienza Adobe](https://experienceleague.adobe.com/en/playlists/experience-platform-get-started-with-tags)

* Accedi a Raccolta dati
* Fai clic su Tag -> Nuova proprietà
* Crea un tag Adobe Experience Platform denominato _&#x200B;**personalization-on-weather**&#x200B;_.

* Aggiungi le seguenti estensioni al tag
  ![tag-estensioni](assets/tags-extensions1.png)

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

Quando pubblichi una proprietà AEP Tags, Adobe ti fornisce un tag script che devi inserire all&#39;interno del tuo HTML ``` <head>``` o nella parte inferiore dei tag ``` <body>```.

* Vai alla proprietà Tag (personalization-on-weather).

* Fai clic su Ambienti e sull’icona Installa dell’ambiente desiderato (ad esempio Sviluppo, Staging, Produzione).

* Prendi nota del codice incorporato. È necessario in una fase successiva di questa esercitazione.
