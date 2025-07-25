---
title: Creare tag Adobe Experience Platform
description: Creazione di tipi di pubblico di AJO in base alle preferenze di investimento degli utenti (azioni, obbligazioni, CD)
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 244fcb09-3b16-4e3b-b335-4e84bc93095e
source-git-commit: 40690024e5348dd3ac05f350e49a67a99d5e455e
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 3%

---

# Creazione di tag Adobe Experience Platform

I tag Adobe Experience Platform (precedentemente Adobe Launch) consentono di gestire e distribuire* tecnologie di marketing e analisi sul sito web senza dover modificare il codice del sito.

Questo [video descrive il processo di creazione dei tag esperienza Adobe](https://experienceleague.adobe.com/it/playlists/experience-platform-get-started-with-tags)

* Accedi a Raccolta dati
* Fai clic su Tag -> Nuova proprietà
* Creare un tag Adobe Experience Platform denominato Financial Advisors.

* Aggiungi le seguenti estensioni al tag
  ![tag-estensioni](assets/tags-extensions.png)

* Configurare Adobe Experience Platform Web SDK per l&#39;utilizzo dell&#39;ambiente corretto e del DataStream di Financial Advisors creato nel passaggio precedente.
  ![configurazione-sdk-web](assets/web-sdk-configuration.png)

* Non è necessaria alcuna configurazione aggiuntiva per Adobe Client Data Layer e le estensioni Core

## Creare elementi dati

Gli elementi dati vengono utilizzati per raccogliere, organizzare e distribuire dati in tecnologie marketing e pubblicitarie basate sul web.

Crea i seguenti elementi dati

| Nome elemento | Estensione | Tipo di elemento dati | Commenti aggiuntivi |
|------------------------------|-----------------------------------|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| StrumentoFinanziarioPreferito | Core | Custom Code | Vedi la nota seguente |
| Oggetto XDM | Adobe Experience Platform Web SDK | Oggetto XDM | Selezionare l&#39;ambiente e lo schema di Financial Advisors |


Per il codice personalizzato, apri l’editor di codice e copia e incolla il seguente codice

```javascript
return window.adobeDataLayer
  ?.slice()
  .reverse()
  .find(event => event.event === "assetClassSelection")
  ?.xdm?.FinancialInterest?.PreferredFinancialInstrument || "undefined";
```

## Spiegazione del codice

Osserva l’array adobeDataLayer (che memorizza gli eventi che si verificano sulla tua pagina web).

Creare una copia dell&#39;array utilizzando.slice() in modo che l&#39;originale non venga modificato.

Inverti l’ordine degli eventi per verificare prima gli eventi più recenti.

Trova il primo evento (a partire dal più recente) in cui event.event è esattamente &quot;assetClassSelection&quot;.

Se individuato, inserire i dati xdm dell&#39;evento e ottenere il valore da FinancialInterest.PreferredFinancialInstrument.

Se non viene trovato nulla, restituisce la stringa &quot;undefined&quot;,



## Crea regola

Il Generatore di regole nei tag di Adobe Experience Platform consente di definire quando e come eseguire azioni specifiche sul sito web in base al comportamento o agli eventi degli utenti.

* Crea una regola denominata Invia strumento finanziario preferito. Questa regola contiene un evento e un’azione


* Crea una configurazione di evento denominata Classe risorsa preferita selezionata, come illustrato di seguito. Questo evento ascolta gli eventi assetClassSelection.
  ![rule-event](assets/rule-event.png)


* Creare un’azione per inviare lo schema XDM aggiornato ad AEP
  ![invia-evento](assets/rule-send-event.png)

* La regola finale deve essere simile a quella riportata di seguito
  ![final-rule](assets/final-rule.png)

## Creare e distribuire i tag di AEP


Crea una nuova libreria e aggiungi a essa tutte le risorse modificate, come illustrato nelle schermate seguenti.

Aggiungi libreria

![new-library](assets/tag-add-library.png)

Creare una libreria

Nella schermata Crea libreria specifica il nome della libreria e l’ambiente.
Devi aggiungere tutte le risorse modificate a questa libreria
![libreria di tag](assets/tag-build-library.png)

Quindi fai clic sul pulsante Salva e genera in sviluppo per generare la libreria

## Includi tag AEP nella pagina HTML

Quando pubblichi una proprietà AEP Tags, Adobe ti fornisce un tag script che devi inserire all&#39;interno del tuo HTML ``` <head>``` o nella parte inferiore dei tag ``` <body>```.

* Vai alla proprietà Tags(Financial Advisors).

* Fai clic su Ambienti e sull’icona Installa dell’ambiente desiderato (ad esempio Sviluppo, Staging, Produzione).

* Prendi nota del codice incorporato. È necessario in una fase successiva di questa esercitazione.
