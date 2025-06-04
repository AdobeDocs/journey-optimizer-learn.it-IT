---
title: Inviare CRMID a Adobe Experience Platform
description: Creare i tag Adobe Experience Platform per inviare il codice CRMID ricevuto dal browser a Adobe Experience Platform
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 894ad6b7-c4b4-465e-8535-3fdcd77e00eb
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 9%

---

# Inviare CRMID a Adobe Experience Platform

Adobe Launch (Tag) viene utilizzato per inviare il CRMID a Adobe Experience Platform (AEP) perché fornisce un meccanismo flessibile e basato su eventi per la trasmissione dei dati di identità direttamente dal browser. L’invio di CRMID dopo l’accesso dell’utente consente ad AEP di collegare l’ECID anonimo al profilo di gestione delle relazioni con i clienti noto, consentendo un’unione precisa delle identità. Questo collegamento costituisce la base per la creazione di profili cliente unificati, la qualificazione dei tipi di pubblico e la distribuzione di esperienze personalizzate in tempo reale in Adobe Journey Optimizer (AJO).

Viene creata una proprietà AEP Tags denominata FinWise. Le seguenti estensioni sono state aggiunte alla proprietà Tags

![tag-estensioni](assets/tags-extensions.png)

Configura l&#39;estensione AEP Web SDK utilizzando il flusso di dati Financial Advisors creato nel passaggio precedente.
Il servizio Experience Cloud ID è un’estensione opzionale aggiunta alla proprietà tag a scopo di debug.

## Tag elementi dati

Crea i seguenti elementi dati

| Elemento dati | Estensione | Tipo di elemento dati | Impostazioni personalizzate |
|--------------|-----------------------------------|---------------------------|----------------------------------------|
| crmid | Adobe Client Data Layer | Stato calcolato del livello dati | user.crmid |
| ECID | Servizio Experience Cloud ID | ECID |                                        |
| identità | Adobe Experience Platform Web SDK | Mappa identità | ![immagine](assets/identity-settings.png) |
| Variabile XDMV | Adobe Experience Platform Web SDK | Variable | ![immagine](assets/xdmvariable.png) |

## Crea regola

Crea una regola denominata userLoggedin con l&#39;evento e le azioni seguenti

Evento
![evento](assets/data-pushed-event.png)

Azione Aggiorna variabile
![aggiorna-variabile](assets/update-variable.png)
Azione Invia evento
![send-event](assets/send-event.png)

## Salva e genera

Salva le modifiche, crea e genera la libreria.
