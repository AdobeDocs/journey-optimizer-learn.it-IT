---
title: Crea campagna
description: Crea una campagna per il targeting degli utenti che hanno acconsentito alla ricezione di notifiche push e consegna il messaggio all’ora pianificata.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 94fda23f-e26a-494b-8e5c-6c442bae61c4
source-git-commit: c339fe796af1e691cd3b1c98cd6ba8a8772551e4
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 1%

---

# Crea campagna

In questo passaggio, creerai una campagna in Adobe Journey Optimizer per inviare notifiche push web pianificate agli utenti che hanno acconsentito. La campagna è indirizzata a un pubblico idoneo e distribuisce messaggi in un momento predefinito, consentendo un coinvolgimento pianificato e basato sul pubblico.

* Accedi a Journey Optimizer
* Passa a Gestione Percorso | Campagne | Crea campagne

## Specificare le impostazioni della campagna


Specifica il nome della campagna

![nome-campagna](assets/campign-push-notification.png)

## Associa azione alla campagna

Associa la configurazione del canale push creata in precedenza in questa esercitazione

![campagna-azione](assets/campign-push-notification-action.png)

## Associa pubblico alla campagna

Associa il pubblico `AudienceForPush` alla campagna

![pubblico-campagna](assets/campign-push-notification-audience.png)

## Creare contenuti per la notifica push

Crea contenuti push di base per testare la notifica push. Specifica il titolo e il corpo del messaggio, come illustrato di seguito

![content-for-push-notification](assets/campign-push-notification-content.png)

## Pianificare la campagna

Pianificare la campagna in base alle tue esigenze

![campagna pianificata](assets/campign-push-notification-schedule.png)

Assicurati infine di attivare la campagna.

## Testare la campagna

Per testare la campagna, abilitare innanzitutto le notifiche nella pagina Web [ scegliendo di partecipare](http://localhost:3000) quando richiesto. Dopo aver acconsentito, attendi che la campagna venga eseguita all’orario pianificato. Durante l’esecuzione della campagna, dovresti ricevere la notifica push nel browser.
