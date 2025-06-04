---
title: Creare una pagina web per testare la soluzione
description: Pagina web per testare le offerte personalizzate distribuite tramite il decisioning.
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-31T00:00:00Z
jira: KT-18188
recommendations: noDisplay, noCatalog
exl-id: 6b1eec78-153c-4ea5-acfe-2dcc6f1e6078
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '334'
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
