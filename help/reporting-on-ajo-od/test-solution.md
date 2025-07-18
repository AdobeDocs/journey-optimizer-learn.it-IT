---
title: Testare la soluzione
description: Crea una semplice pagina web per acquisire gli eventi di impression e clic sulle offerte.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18526
source-git-commit: 69bc8aace3cc502a18e691584824176833413c7e
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Testare la soluzione

Per testare la soluzione end-to-end, i file [weather-offers.html](assets/weather-offers.html) e [capture-impressions-click-events.js](assets/capture-impressions-click-events.js) devono essere ospitati su un server web o un servizio di hosting pubblico come le pagine Github. Questo è necessario perché l’API di geolocalizzazione del browser funziona solo su HTTPS o localhost

## Scarica i file forniti

[File HTML](assets/weather-offers.html)

[File JavaScript](assets/capture-impressions-click-events.js)

## Aggiornare l’URL della superficie nel file javascript

Apri `capture-impressions-click-events.js` e aggiorna ` "web://yourdomain.com/weather/weather-offers.html#offerContainer"` sostituendo `yourdomain.com` con il dominio effettivo in cui è ospitato il file HTML.


## Aggiornare la proprietà Adobe Experience Platform Tags

Apri il file weather-offers.html nell’editor di testo e sostituisci il tag script con il tag script della proprietà tag Adobe Experience Platform creata nel passaggio precedente di questa esercitazione. Assicurati di salvare il file

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## Interagire con le offerte

- Aprire la pagina Web nel browser preferito.

- Consenti _&#x200B;**tracciamento località**&#x200B;_. Questo è necessario per ottenere i dettagli meteo in base alla tua posizione.

- Fai clic sul pulsante nelle offerte per attivare l’evento di interazione.

## Visualizzare il rapporto

- Accedi a Journey Optimizer

- Passa a Gestione Percorso ->Campagne

- Fai clic sulla campagna e seleziona il rapporto appropriato dal menu del rapporto.
