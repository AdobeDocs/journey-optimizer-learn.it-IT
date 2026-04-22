---
title: Creare un canale push
description: La configurazione del canale push definisce il modo in cui vengono inviate le notifiche push web, incluse le impostazioni dell’applicazione e i dettagli specifici della piattaforma. Inoltre, collega la configurazione push alle credenziali richieste, ad esempio le chiavi VAPID, consentendo ad AJO di inviare notifiche agli utenti abbonati.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Creare un canale push

Il primo passaggio consiste nel creare un canale push in Adobe Journey Optimizer. Come parte di questa configurazione, dovrai generare le chiavi VAPID, necessarie per autenticare e abilitare le notifiche push web. Queste chiavi vengono quindi utilizzate nella configurazione del canale push, consentendo ad AJO di inviare in modo sicuro le notifiche agli utenti abbonati.

## Genera chiavi VAPID

VAPID (Voluntary Application Server Identification) è uno standard web push che consente al server di identificarsi nei servizi push (come Chrome, Edge, ecc.) utilizzando coppie di chiavi pubblica/privata, in modo che il provider push sappia chi sta inviando la notifica.

Viene generato utilizzando uno strumento come web-push generate-vapid-keys, che crea una chiave pubblica (condivisa con il browser) e una chiave privata (mantenuta sul server) utilizzate insieme per autenticare e inviare in modo sicuro i messaggi push.

Per questa esercitazione abbiamo utilizzato Node.js per generare le chiavi VAPID.

Verifica che Node.js sia installato. Quindi esegui il seguente comando
```npm install web-push -g ```

![Web-push](assets/install-web-push.png)

```web-push generate-vapid-keys```

![vapid](assets/vapid-keys.png)

## Crea credenziali push

* Accedi a Journey Optimizer

* Passa ad Amministrazione | Canali | IMPOSTAZIONI PUSH | Credenziali push| Crea credenziali push

* ![credenziali push](assets/push-credential.png)

## Crea configurazione canale

* Accedi a Journey Optimizer

* Passa ad Amministrazione | Canali | Crea configurazione canale
  ![configurazione-canale](assets/push-channel.png)
