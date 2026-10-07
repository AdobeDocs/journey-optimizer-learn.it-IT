---
title: Creare una pagina web per testare la soluzione
description: Pagina web per testare le offerte personalizzate distribuite tramite il decisioning.
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-31T00:00:00.000Z
jira: KT-18188
recommendations: noDisplay, noCatalog
exl-id: 6b1eec78-153c-4ea5-acfe-2dcc6f1e6078
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
source-wordcount: '348'
ht-degree: 0%
---
# Creare una pagina web per testare la soluzione

Questa applicazione di esempio simula un flusso di accesso reale in cui le credenziali utente vengono convalidate sul lato server prima che l’ID del sistema di gestione delle relazioni con i clienti venga inviato a Adobe Experience Platform (AEP). Un server Node.js locale viene utilizzato per gestire in modo sicuro le pagine web, gestire la logica di autenticazione di base ed evitare restrizioni del browser (come l’accesso bloccato ai file locali o intestazioni CORS mancanti) che potrebbero interferire con le funzionalità di Adobe Launch o Web SDK. Questa configurazione garantisce un&#39;esperienza più simile a un ambiente di produzione reale.

Le offerte personalizzate vengono visualizzate solo dopo che l’utente ha effettuato l’accesso, nel qual caso viene completata l’unione di identità tra l’ID CRM dell’utente e l’ECID (Experience Cloud ID). Questa unione di identità assicura che Adobe Journey Optimizer (AJO) possa riconoscere con precisione il profilo e restituire le offerte mirate.

Dopo aver effettuato correttamente l’accesso, viene inviata una richiesta di personalizzazione ad AJO per recuperare le offerte disponibili per l’utente. Queste offerte vengono restituite come frammenti di HTML, ciascuno incorporato con un attributo di tag dati, ad esempio data-tags=&quot;ajo offer-Holiday-based-cd zip-92128 income-high&quot;, che include il nome dell’offerta e i dettagli di segmentazione come il codice postale e il livello di reddito.

JavaScript analizza quindi questi blocchi HTML e li racchiude in un contenitore di elementi carosello. Gli elementi sono disposti orizzontalmente all’interno di un carosello, consentendo una navigazione commutabile. I pulsanti Precedente e Successivo (◀ e ▶) consentono agli utenti di scorrere le offerte personalizzate una alla volta.

Questa configurazione offre un’esperienza reattiva e personalizzata, garantendo che ogni utente visualizzi le offerte relative al proprio profilo finanziario solo dopo che la propria identità è stata unita in modo sicuro tra le piattaforme.

## Prova questa soluzione

* Crea una cartella denominata ranking-formula nel progetto Node.js esistente.

* Decomprimi i [file forniti in questa cartella di formula di classificazione.](assets/ranking-formula.zip)

* Esegui l’app entrando nella cartella e avviando il server:
  * `cd ranking-formula`

  * `node server.js`


* Apri il browser e vai su http://localhost:3000/formula.html.

* Accedi con alice/pass123

Poiché Alice risiede nel codice postale 92128, vengono visualizzate offerte personalizzate per tale posizione.
