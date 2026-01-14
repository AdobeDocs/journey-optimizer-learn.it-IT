---
title: Testare la soluzione
description: Crea un percorso per l’invio di e-mail all’invio del modulo
feature: Journeys
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-12-25T00:00:00Z
jira: KT-20014
source-git-commit: 319b1cd4a037807a944e5fb6438e47b5fcf4c1c4
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Testare la soluzione


Testare la soluzione
>[!VIDEO](https://video.tv.adobe.com/v/3478554?captions=ita)

## Distribuire le risorse di esempio

Se non hai installato Node.js, scaricalo e [installalo da qui](https://nodejs.org/)

Verificare l&#39;installazione eseguendo:

`node -v`

`npm -v`

## Configurare la cartella del progetto

Crea una nuova directory per l’app di esempio utilizzando i seguenti comandi:

`mkdir trigger-journey `

`cd trigger-journey`

## Inizializzare il progetto

`npm init -y`

## Installare i framework richiesti

`npm install express dotenv axios cors`

## Copiare i file di risorse

* Decomprimere e inserire il contenuto di [project-root.zip](assets/project-root.zip) nella cartella `trigger-journey`.

* Crea una cartella denominata `public` nella cartella `trigger-journey`
* aggiornare il file `.env` con i valori appropriati. Questi valori sono disponibili dal comando cURL scaricato durante la creazione della connessione HTTP Source.
* Decomprimi il contenuto di [index.zip](assets/index.zip) nella cartella `public`

## Eseguire il server

Assicurarsi di essere nella directory `trigger-journey`.
Esegui il comando `node server.js`
Puntare il browser alla [pagina Web](http://localhost:3000/)
Compila e invia il modulo. Il percorso viene attivato e viene inviata un’e-mail all’ID e-mail inserito nel modulo.


