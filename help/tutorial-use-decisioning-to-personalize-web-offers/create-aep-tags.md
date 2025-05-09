---
title: Creare tag Adobe Experience Platform
description: Creazione di tipi di pubblico di AJO in base alle preferenze di investimento degli utenti (azioni, obbligazioni, CD)
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17923
exl-id: 6823ce13-bc77-4e2b-89e0-606e403c15f2
source-git-commit: 2ca9ffee1a2326b8ae55a8e8de496a632fea79c8
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---

# Crea Adobe Experience Platform

Adobe Launch è configurato sulla pagina web per caricare Adobe Experience Platform Web SDK, consentendo la chiamata API sendEvent di attivare esperienze personalizzate. Questa configurazione assicura che le librerie lato client necessarie siano inizializzate correttamente, consentendo un’interazione in tempo reale con Adobe Journey Optimizer per la consegna delle offerte.

* Accedi a Raccolta dati
* Fai clic su Tag -> Nuova proprietà
* Crea un tag Adobe Experience Platform denominato servizio ECID.

* Aggiungi le seguenti estensioni al tag
  ![tag-estensioni](assets/ecid-tag.png)

* Assicurarsi di configurare Adobe Experience Platform Web SDK per l&#39;utilizzo dell&#39;ambiente corretto e del DataStream di Financial Advisors creato nell&#39;esercitazione precedente
  ![configurazione-sdk-web](assets/web-sdk-configuration.png)

* Non è necessaria alcuna configurazione aggiuntiva per Adobe Client Data Layer e le estensioni Core

## Crea elemento dati

L’elemento dati ECID in Adobe Launch viene creato solo a scopo di debug e test. Consente agli sviluppatori di visualizzare l’Experience Cloud ID assegnato alla sessione del browser di un utente, che può aiutare a convalidare l’unione di identità e garantire che le chiamate sendEvent siano associate al profilo corretto. Questo elemento non è necessario per il funzionamento della personalizzazione, ma è utile durante l’implementazione e il controllo qualità

![ecid](assets/ecid-data-element.png)


## Includi tag AEP nella pagina HTML

Creare e pubblicare i tag Adobe Experience Platform

Quando viene pubblicata una proprietà AEP Tags, Adobe fornisce un tag script che è necessario inserire all&#39;interno di HTML ``` <head>``` o nella parte inferiore dei tag ``` <body>```.

* Vai alla proprietà Tags(ECID Service).

* Fai clic su Ambienti e sull’icona Installa dell’ambiente desiderato (ad esempio Sviluppo, Staging, Produzione).

* Prendi nota del codice incorporato. Il codice deve essere inserito immediatamente prima del tag di chiusura ```</body>``` nella pagina HTML.
