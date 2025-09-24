---
title: Test della soluzione
description: Testare la soluzione
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: b7bad65d-c978-4981-a914-6cb039433c8b
source-git-commit: 71b42350370d12ce677bf075d8b48edcbe541ab4
workflow-type: tm+mt
source-wordcount: '348'
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
* Anche il percorso dovrebbe essere attivato. Per verificarlo, visualizza il rapporto sul percorso
* ![Rapporto percorsi](assets/journey-triggered-report.png)


