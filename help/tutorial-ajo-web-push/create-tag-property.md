---
title: Crea proprietà tag
description: La proprietà tag invia i dati dal browser all’AEP tramite Web SDK.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-20879
exl-id: 108de002-f033-4b88-bee5-2b50463c345c
source-git-commit: 676c21ca09e0df8d404b05081d71b147755d65d5
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Crea proprietà tag

Nella seconda parte di questo tutorial, scoprirai come attivare le notifiche push in tempo reale inviando manualmente un evento price.drop personalizzato. Questo approccio utilizza la raccolta dati di AEP (tag) per acquisire l’evento dalla pagina web e inviarlo a Adobe Experience Platform. Una volta acquisito, l’evento attiva un percorso in Adobe Journey Optimizer, che consente di inviare notifiche push su richiesta in base alle azioni degli utenti o agli eventi di business.

Questa proprietà è configurata con AEP Web SDK, connesso a `WebPushDataStream` creato in precedenza nell&#39;esercitazione. La proprietà tag ascolta l&#39;evento `price.drop` su Adobe Data Layer e mappa i dettagli del prodotto pertinenti aggiornando l&#39;elemento dati ProductListItems. Una volta preparati i dati, una regola nella proprietà tag si attiva e invia l’evento price.drop ad AEP tramite Web SDK. Questo evento funge quindi da punto di ingresso per un percorso in Adobe Journey Optimizer, consentendo la consegna immediata di notifiche push in base al calo di prezzo.

## Elementi tag

ProductListItems per contenere i dettagli del prodotto

![elementi-tag](assets/product-list-items-element.png)

mapping xdmvariable a `schemaForPushNotification`

![xdm-variable](assets/xdmvariable-data-element.png)

## Crea regola

Ascolta l&#39;evento price.drop
![data-push-event](assets/tag-rule-event.png)

Aggiornare productListItems utilizzando la variabile di aggiornamento
![aggiorna-variabile](assets/update-variable.png)
Infine, invia l’evento price.drop ad AEP con la variabile xdmaggiornata
![invia-evento](assets/send-event.png)

Il codice JavaScript seguente invia l&#39;evento price.drop ai tag di AEP dalla pagina Web

```javascript
 <script>
      window.adobeDataLayer.push({
        event: "price.drop",
        productListItems: productListItems
      });
  </script>
```
