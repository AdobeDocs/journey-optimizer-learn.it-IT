---
title: Crea stream di dati
description: Questa pagina ti guida attraverso la creazione di un flusso di dati in Adobe Experience Platform, necessario per raccogliere dati dal Web SDK e inviarli ad AEP e Adobe Journey Optimizer. Lo stream di dati funge da connessione tra l’applicazione web e i servizi Adobe, consentendo l’elaborazione dei dati di abbonamento push ed evento.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: d419f6a4-67d5-46b5-9ae7-5a317300d1ad
source-git-commit: 676c21ca09e0df8d404b05081d71b147755d65d5
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# Crea stream di dati

Un flusso di dati in Adobe Experience Platform (AEP) funge da endpoint che riceve i dati inviati dal Web SDK. Indirizza questi dati ai servizi configurati come AEP, Adobe Analytics o Adobe Journey Optimizer. In questa esercitazione, lo stream di dati viene utilizzato per inviare dati di abbonamento push web ed eventi price.drop ad AEP per l’attivazione.

## Creare uno schema eventi per il tracciamento delle notifiche push

Crea un nuovo schema ExperienceEvent XDM denominato `SchemaForPushNotification`. Aggiungere i gruppi di campi `Push Notification Tracking` e `Commerce Details` a questo schema. I campi del gruppo di campi Dettagli Commerce verranno utilizzati per acquisire informazioni sul prodotto e attivare l’evento price.drop personalizzato.

![schema-evento](assets/event-schema.png)

## Crea uno schema di profilo per salvare il consenso dell’utente

Per questa esercitazione verrà utilizzato il predefinito `AJO Push Profile Schema`. Questo schema memorizza i dettagli dell’abbonamento push dell’utente, incluso il token push necessario per inviare le notifiche push web.

![schema_profilo](assets/profile-schema.png)

## Creare set di dati per lo schema

Creare un set di dati denominato `DataSetForPushNotification` utilizzando lo schema evento creato in precedenza. Per i dati di profilo, utilizza `AJO Push Profile Dataset` preconfigurato, associato allo schema di profilo push. Prendere nota dell&#39;ID `DataSetForPushNotification`, poiché sarà necessario in seguito nell&#39;esercitazione durante la configurazione dell&#39;applicazione tramite il file .env.

## Creare uno stream di dati utilizzando il set di dati evento e profilo

Crea un nuovo stream di dati denominato WebPushDataStream utilizzando i set di dati evento e profilo creati nel passaggio precedente. Prendi nota dell’ID dello stream di dati, poiché sarà necessario in un secondo momento nell’esercitazione durante la configurazione dell’applicazione tramite il file .env.

![flusso di dati](assets/datastream.png)
