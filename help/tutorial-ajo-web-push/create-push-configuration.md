---
title: Creare un canale push
description: La configurazione del canale push definisce il modo in cui vengono inviate le notifiche push web, incluse le impostazioni dell’applicazione e i dettagli specifici della piattaforma. Inoltre, collega la configurazione push alle credenziali richieste, ad esempio le chiavi VAPID, consentendo ad AJO di inviare notifiche agli utenti abbonati.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-20879
exl-id: 0a8be7eb-9962-466a-9fcc-022cb84c7b0a
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
source-wordcount: '242'
ht-degree: 0%
---
# Creare un canale push

Il primo passaggio consiste nel creare un canale push in Adobe Journey Optimizer. Come parte di questa configurazione, dovrai generare le chiavi VAPID, necessarie per autenticare e abilitare le notifiche push web. Queste chiavi vengono quindi utilizzate nella configurazione del canale push, consentendo ad AJO di inviare in modo sicuro le notifiche agli utenti abbonati.

## Genera chiavi VAPID

VAPID (Voluntary Application Server Identification) è uno standard web push che consente al server di identificarsi nei servizi push (come Chrome, Edge, ecc.) utilizzando coppie di chiavi pubblica/privata, in modo che il provider push sappia chi sta inviando la notifica.

Viene generato utilizzando uno strumento come web-push generate-vapid-keys, che crea una chiave pubblica (condivisa con il browser) e una chiave privata (mantenuta sul server) utilizzate insieme per autenticare e inviare in modo sicuro i messaggi push.

Per questa esercitazione abbiamo utilizzato Node.js per generare le chiavi VAPID.

Verifica che Node.js sia installato. Quindi esegui il seguente comando

`npm install web-push -g `

![Web-push](assets/install-web-push.png)

`web-push generate-vapid-keys`

![vapid](assets/vapid-keys.png)

## Crea credenziali push

* Accedi a Journey Optimizer

* Passa ad Amministrazione | Canali | IMPOSTAZIONI PUSH | Credenziali push| Crea credenziali push

* ![credenziali push](assets/push-credential.png)

## Crea configurazione canale

* Accedi a Journey Optimizer

* Passa ad Amministrazione | Canali | Crea configurazione canale
  ![configurazione-canale](assets/push-channel.png)
