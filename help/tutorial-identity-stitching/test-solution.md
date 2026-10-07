---
title: Test della soluzione
description: Testare la soluzione
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: b7bad65d-c978-4981-a914-6cb039433c8b
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 0%
---
# Testare l’unione di identità

Questa applicazione di esempio simula un flusso di accesso reale in cui le credenziali utente vengono convalidate sul lato server prima che l’ID del sistema di gestione delle relazioni con i clienti venga inviato a Adobe Experience Platform (AEP). Un server Node.js locale viene utilizzato per gestire in modo sicuro le pagine web, gestire la logica di autenticazione di base ed evitare restrizioni del browser (come l’accesso bloccato ai file locali o intestazioni CORS mancanti) che potrebbero interferire con le funzionalità di Adobe Launch o Web SDK. Questa configurazione garantisce un&#39;esperienza più simile a un ambiente di produzione reale.

## Installare node.js

Se non hai installato Node.js, scaricalo e [installalo da qui](https://nodejs.org/)

Verificare l&#39;installazione eseguendo:

`node -v`

`npm -v`

## Configurare la cartella del progetto

Crea una nuova directory per l’app di esempio utilizzando i seguenti comandi

`mkdir aep-demo`

`cd aep-demo`

## Inizializzare il progetto

`npm init -y`

## Installa Express (Web Server Framework)

`npm install express`

## Crea file server.js

```javascript
const express = require('express');
const path = require('path');
const app = express();
const PORT = 3000;

// Serve static files from the current directory
app.use(express.static(__dirname));

app.listen(PORT, () => {
  console.log(`Server is running at http://localhost:${PORT}`);
});
```

## Aggiungi HTML/Assets

Copia tutti i [file HTML e CSS](assets/login-app-files.zip) forniti in questa cartella. Copiare e incollare lo script AEP Tags nella sezione `<head>` del file index.html.

## Eseguire il server

`node server.js`

## Test

Apri l&#39;URL `http://localhost:3000`. Il login è con alice/pass123

## Utilizzare AEP Debugger

Adobe Experience Platform Debugger è una potente estensione del browser che consente di convalidare i dati inviati dal sito web a Adobe Experience Platform. È particolarmente utile per verificare se identityMap è configurato correttamente e trasmesso tramite Adobe Web SDK (alloy.js).

Utilizza AEP Debugger per testare gli eventi di accesso, verificare l’unione delle identità (ad esempio, il passaggio di ECID e CRMID) e assicurarsi che le regole dei tag e gli elementi dati di AEP vengano attivati come previsto. Fornisce visibilità in tempo reale sugli eventi in uscita, sulle informazioni di identità e sui payload XDM, elementi fondamentali per la risoluzione dei problemi di arricchimento dei profili e qualificazione del pubblico.

La schermata seguente mostra che l’ID &quot;FIN001&quot; viene passato correttamente.
![aep-debugger](assets/aep-debugger.png)

## Passaggi per verificare l’unione delle identità in AEP

* Accedi ad AEP
* Passa a Cliente -> Profili ->Sfoglia
* Cerca ID CRM FinWise = FIN001
* Apri il profilo e controlla la sezione Identità. Dovresti vedere sia il CRMID che l’ECID elencati.   Ciò conferma che le due identità sono state unite in un unico profilo.


