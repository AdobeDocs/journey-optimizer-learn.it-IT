---
title: Abilitare il limite di frequenza per una campagna AJO
description: In Adobe Journey Optimizer, il limite di frequenza viene applicato a livello di singola offerta e si basa sull’acquisizione di eventi di impression e clic. Questo richiede il tracciamento degli eventi decisioning.propositionDisplay e decisioning.propositionInteract che utilizzano Adobe Web SDK e il loro mapping a uno schema XDM Experience Event aggiornato in Adobe Experience Platform.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-18526
exl-id: 34027499-0037-4ea1-813b-51be15eafe24
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
source-wordcount: '230'
ht-degree: 0%
---
# Abilitare il limite di frequenza per una campagna AJO

La procedura seguente illustra come applicare il limite di frequenza alle offerte:

## Aggiornare lo schema dell’evento

* Aggiorna lo schema evento esistente aggiungendo il gruppo di campi come mostrato
* ![schema-evento](assets/schema.png)

## Aggiornare il limite di frequenza per l’offerta


* ![offerta](assets/offer-capping.png)

## Aggiungi token di tracciamento all’offerta

Modifica il criterio di decisione utilizzato nella campagna aggiungendo un’offerta di fallback
![fallback](assets/fallback.png)

Puoi aggiungere trackingToken ed ItemID facendo clic sull’icona Criterio decisione nella navigazione a sinistra, quindi espandere la struttura decisionale per selezionare itemID e trackingToken.

Aggiungi l’ID articolo e il token di tracciamento all’elemento div contenente l’offerta come mostrato di seguito
![id-and-tracking-token](assets/id-and-tracking-token.png)

In questo modo ogni offerta sottoposta a rendering include un token di tracciamento dei dati, essenziale per il tracciamento accurato degli eventi di impression e clic.


Attiva la campagna modificata.


## Inviare eventi di impression e tracciamento

Modifica il codice JavaScript esistente per acquisire e inviare gli eventi di impression e interazione dell’offerta a Adobe Experience Platform utilizzando Adobe Web SDK. Fai riferimento al [codice di esempio fornito qui.](capture-impression-click-events.md)
