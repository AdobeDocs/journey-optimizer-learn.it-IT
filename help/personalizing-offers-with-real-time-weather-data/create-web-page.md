---
title: Testare la soluzione
description: Crea una semplice pagina web per testare la personalizzazione delle offerte contestuali utilizzando i dati sulla temperatura in tempo reale.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 609a5ddf-d6c6-4f19-bd7f-bca8c266b759
source-git-commit: 23832f2e59ca7558fd403f0a9753db3923023e6d
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Testare la soluzione

Per testare la soluzione end-to-end, i file [weather-offers.html](assets/weather-offers.html) e [weather-related-offers-script.js](assets/weather-related-offers-script.js) devono essere ospitati su un server web o su un servizio di hosting pubblico come le pagine Github. Ciò è necessario perché:
- L’API di geolocalizzazione del browser funziona solo tramite HTTPS o localhost

Per mantenere gli elementi organizzati e garantire il corretto funzionamento dei percorsi relativi, si consiglia di utilizzare la seguente struttura di cartelle per ospitare la soluzione:

![struttura-cartella](assets/folder-structure.png)

## Scarica i file forniti

[File HTML](assets/weather-offers.html)

[File JavaScript](assets/weather-related-offers-script.js)


## Aggiornare l’URL della superficie nel file javascript

Apri `weather-related-offers-script.js` e aggiorna ` "web://yourdomain.com/weather/weather-offers.html#offerContainer"` bt sostituendo `yourdomain.com` con il dominio effettivo in cui è ospitato il file HTML.

## Aggiornare la proprietà Adobe Experience Platform Tags

Apri il file weather-offers.html nell’editor di testo e sostituisci il tag script con il tag script della proprietà tag Adobe Experience Platform creata nel passaggio precedente di questa esercitazione. Assicurati di salvare il file

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```



## Funzionamento della pagina Web

Una pagina web viene creata per testare la personalizzazione delle offerte contestuali utilizzando i dati sulla temperatura in tempo reale. Quando un utente visita la pagina, il browser richiede l’accesso alla geolocalizzazione. Dopo l’approvazione, la pagina recupera i dettagli meteo correnti, come temperatura, condizione e città, tramite l’API OpenWeatherMap. Questi dati contestuali vengono visualizzati e inviati a Adobe Experience Platform utilizzando Adobe Web SDK (Alloy).

La chiamata sendEvent è configurata con renderDecisions: false, significa che le offerte restituite da Adobe Journey Optimizer vengono gestite manualmente. Lo script elabora la risposta di decisioning, decodifica il contenuto e inserisce dinamicamente l’offerta più rilevante in un contenitore designato (#offerContainer).

## Funzionamento di JavaScript

JavaScript recupera dinamicamente le informazioni meteo in base alla posizione dell’utente e utilizza Adobe Experience Platform (AEP) per distribuire offerte personalizzate. Ecco una suddivisione dei passaggi:

1. **Attende il caricamento della lega**

   Lo script assicura che Adobe Web SDK (Alloy) sia completamente caricato prima di effettuare qualsiasi richiesta di personalizzazione.

2. **Ottiene la posizione dell&#39;utente**

   Utilizza l’API di geolocalizzazione del browser per recuperare la latitudine e la longitudine correnti dell’utente.

3. **Recupera i dati meteo**

   Chiama l&#39;API OpenWeatherMap per ottenere i dettagli meteo correnti:

   Temperatura (in °F)

   Condizioni meteorologiche (ad esempio, &quot;Pioggia&quot;, &quot;Cancella&quot;)

   Nome città

   Umidità

4. **Visualizza informazioni meteo sulla pagina Web**

   Aggiorna il DOM con un messaggio come:

   &quot;La temperatura attuale a San Diego è di 72°F con il cielo sereno.&quot;

5. **Invia il contesto meteo ad AEP**

   Utilizza alloy(&quot;sendEvent&quot;) per inviare dati meteo contestuali ad AEP

   ```javascript
   xdm: {
   eventType: "decisioning.request",
   _techmarketingdemos: {
   temperature: temp,
   weatherConditions: condition,
   cityName: city
     }
   }
   ```

6. **Recupera ed esegue il rendering delle offerte**

   Riceve le offerte restituite da AJO.

   Decodifica il contenuto HTML.

   Inserisce dinamicamente le offerte nel <div id="offerContainer"> elemento.

