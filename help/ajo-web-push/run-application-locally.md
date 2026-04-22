---
title: Eseguire l'applicazione localmente
description: Configurando l’applicazione di esempio a livello locale per esplorare il flusso delle notifiche push web tramite AJO.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Eseguire l&#39;applicazione localmente

Questa pagina ti guida attraverso la configurazione locale dell’applicazione di esempio, in modo da poter testare ed esplorare il flusso di notifiche push web tramite Adobe Journey Optimizer. L’archivio verrà clonato, verranno configurate le variabili di ambiente e verrà eseguita l’applicazione sul sistema locale.


Per eseguire l&#39;applicazione di esempio nel sistema locale, eseguire la procedura seguente.

## &#x200B;1. Installare Node.js

Verifica che nel sistema sia installato **Node.js (versione 16 o successiva)**.

Puoi [scaricarlo qui:](https://nodejs.org/)

Verificare l&#39;installazione

```node -v```

```npm -v```


## &#x200B;2. Clonare l’archivio

```git clone https://github.com/gbedekar489/ajo-web-push.git```

```cd ajo-web-push```

## &#x200B;3. Installare le dipendenze

```npm install```

## &#x200B;4. Configurare le variabili di ambiente

Crea un file .env nella directory principale e aggiungi quanto segue:

```
DATASTREAM_ID=your_datastream_id
ORG_ID=your_org_id
VAPID_PUBLIC_KEY=your_vapid_public_key
APP_ID=your_app_id
DATASET_ID=your_profile_dataset_id
PORT=3000
```

Quando vengono eseguiti in locale, questi valori vengono letti dal file .env. In produzione (ad esempio, Rendering), sono configurate come variabili di ambiente.