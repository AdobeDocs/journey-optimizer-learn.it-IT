---
title: Testare la soluzione
description: Crea una semplice pagina web per acquisire gli eventi di impression e clic sulle offerte.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18526
exl-id: 6b6c66d3-218d-4f5b-adb0-a2eca05989ab
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
source-wordcount: '241'
ht-degree: 0%
---
# Testare la soluzione

## Distribuire le risorse di esempio

Se non hai installato Node.js, scaricalo e [installalo da qui](https://nodejs.org/)

Verificare l&#39;installazione eseguendo:

`node -v`

`npm -v`

## Configurare la cartella del progetto

Crea una nuova directory per l’app di esempio utilizzando i seguenti comandi:

`mkdir frequency-capping `

`cd frequency-capping `

## Inizializzare il progetto

`npm init -y`

## Installare i framework richiesti

`npm install express`

## Copiare i file di risorse

* Decomprimere e inserire il contenuto di [server.zip](assets/server.zip) nella cartella `frequency-capping`.
* Estrai il contenuto di [public.zip](assets/public.zip)nella cartella &#39;frequency-capping&#39;

## Aggiornare l’URL della superficie nel file javascript

Apri `frequency-capping.js` che si trova in `public\scripts` e aggiorna la proprietà delle superfici in modo che corrisponda alla configurazione del canale utilizzata nella campagna

## Avvia nodo server JS

Spostarsi nella cartella `c:\frequency-capping`. Esegui il comando `node server.js` per avviare il server node js sulla porta 3000


## Aggiornare la proprietà Adobe Experience Platform Tags

Apri il file `frequency-capping.html` che si trova nella cartella `public` nell&#39;editor di testo e sostituisci il tag script con il tag script della proprietà tag Adobe Experience Platform creata nel passaggio precedente di questa esercitazione. Assicurati di salvare il file

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## Interagire con le offerte

* Apri la [pagina Web](http://localhost:3000) nel browser preferito.
* Interagisci con l’offerta
* Aggiorna la pagina
* A seconda delle regole del limite di frequenza, dovresti vedere una nuova offerta

## Visualizzare il rapporto

* Accedi a Journey Optimizer
* Passa a Gestione Percorso ->Campagne
* Fai clic sulla campagna e seleziona il rapporto appropriato dal menu del rapporto.
