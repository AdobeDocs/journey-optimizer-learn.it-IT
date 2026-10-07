---
title: Inviare CRMID a Adobe Experience Platform
description: Creare i tag Adobe Experience Platform per inviare il codice CRMID ricevuto dal browser a Adobe Experience Platform
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 894ad6b7-c4b4-465e-8535-3fdcd77e00eb
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 9%
---
# Inviare CRMID a Adobe Experience Platform

I tag Adobe Experience Platform vengono utilizzati per inviare il CRMID a Adobe Experience Platform (AEP) perché fornisce un meccanismo flessibile e basato su eventi per la trasmissione dei dati di identità direttamente dal browser. L’invio di CRMID dopo l’accesso dell’utente consente ad AEP di collegare l’ECID anonimo al profilo di gestione delle relazioni con i clienti noto, consentendo un’unione precisa delle identità. Questo collegamento costituisce la base per la creazione di profili cliente unificati, la qualificazione dei tipi di pubblico e la distribuzione di esperienze personalizzate in tempo reale in Adobe Journey Optimizer (AJO).

È stata creata una proprietà Experience Platform Tags denominata _**FinWise**_. Le seguenti estensioni sono state aggiunte alla proprietà Tags

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

Crea una regola denominata LoginEvent con l&#39;evento e le azioni seguenti

Evento
![evento](assets/data-pushed-event1.png)

Azione Aggiorna variabile
![aggiorna-variabile](assets/update-variable1.png)
Azione Invia evento
![invia-evento](assets/send-event1.png)

## Salva e genera

Salva le modifiche, crea e genera la libreria.
