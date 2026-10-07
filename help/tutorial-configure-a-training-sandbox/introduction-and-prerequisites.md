---
title: 'Configurare una sandbox di formazione: introduzione'
description: Scopri come configurare una sandbox a scopo di formazione. Segui i passaggi necessari per configurare gli schemi, acquisire dati di esempio e creare eventi.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
last-substantial-update: 2023-02-01T00:00:00.000Z
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
    internal-label: Data management activity
  - id: d556b755-390a-43f0-be32-a08cf6236126
    internal-label: Configuration
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
    internal-label: Administration
subfeature_v2:
  - id: d2e8a157-b3b0-4143-9ff3-809bf400be56
    internal-label: Sandboxes
  - id: efb19423-4da4-4fd1-88d8-5ee8c71ae766
    internal-label: Application settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 100%
---
# Configurare una sandbox di formazione: introduzione e prerequisiti

![Tutorial banner: configurare una sandbox di formazione](./assets/ajo-banner-configure-training-sandbox.png)

Questo tutorial è progettato per amministratori e gli ingegneri di dati che hanno il compito di fornire un [!DNL Journey Optimizer] ambiente di formazione di Adobe. Scopri i passaggi necessari per configurare gli schemi, acquisire dati di esempio e creare eventi. Si possono creare anche tre profili di test per consentire a chi apprende di controllare il proprio lavoro.

I dati di esempio forniti si basano su un’azienda di abbigliamento sportivo fittizia denominata _[!DNL Luma]_, [!DNL Luma] che dispone di negozi in più paesi, di una presenza online con un sito web e di app mobili. [!DNL Luma] utilizza Adobe Journey Optimizer per fornire ai propri clienti esperienze connesse, contestuali e personalizzate.

Al termine di questo tutorial, avrai a disposizione una sandbox che supporta i casi d’uso [!DNL Luma] trattati negli esercizi pratici nella sezione [Sfide di Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

## Prerequisiti

Prima di iniziare a configurare la sandbox di formazione, assicurati di disporre di:

1. uno sviluppo [sandbox](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=it) dedicato.

1. I [Predefiniti per messaggi e-mail](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=it) configurati per il marketing e la messaggistica transazionale.

1. Diritti di **[!UICONTROL amministratore del percorso]** e **[!UICONTROL gestore dati]** per la sandbox di formazione.

1. Il tuo [ID organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=it).

1. I file JSON con i dati di esempio configurati per l’istanza di Journey Optimizer:

   1. Scarica il file `luma-sample-data.zip` che contiene tutti i file JSON necessari per questo tutorial [qui](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip).

   1. Dalla cartella dei download, sposta il file `luma-data.zip` nella posizione desiderata nel tuo computer e decomprimilo.

      Questi file contengono i dati di esempio per la sandbox di formazione.

   1. Apri ogni file, individua **`yourOrganizationID`** e sostituiscilo con l’[ID organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=it).

   1. Salva i file.

## Introduzione

Inizia con l’[Impostazione dei dati manuale](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md).

In questo passaggio definisci la struttura dei dati da richiedere. Dopo aver completato la configurazione dei dati, i dati nella sandbox possono essere acquisiti e quindi è possibile impostare gli eventi.
