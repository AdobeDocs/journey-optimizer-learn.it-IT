---
title: 'Configurare una sandbox di formazione: introduzione'
description: Scopri come configurare una sandbox per scopi di formazione. Segui i passaggi necessari per configurare gli schemi, acquisire dati di esempio e creare eventi.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: 81f5cc22d46f89ee1c7164a92988311ca6036b8b
workflow-type: tm+mt
source-wordcount: '338'
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
