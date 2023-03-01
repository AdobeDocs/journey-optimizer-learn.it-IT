---
title: 'Configurare una sandbox di formazione: introduzione'
description: Scopri come configurare una sandbox a scopo di formazione. Segui i passaggi necessari per configurare gli schemi, acquisire dati di esempio e creare eventi.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
hide: true
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: 2a671ad01f1cdb60c731a707b0584bf2f4262d9b
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 9%

---

# Configurare una sandbox di formazione: introduzione e prerequisiti

![Tutorial sui banner: configurare una sandbox di formazione](./assets/ajo-banner-configure-training-sandbox.png)

Questo tutorial è progettato per amministratori e data engineer che hanno il compito di fornire un Adobe [!DNL Journey Optimizer] ambiente di formazione. Scopri i passaggi necessari per configurare gli schemi, acquisire dati di esempio e creare eventi. Puoi anche creare tre profili di test che consentono agli Allievi di controllare il proprio lavoro.

I dati di esempio forniti si basano su un’azienda fittizia di abbigliamento sportivo denominata _[!DNL Luma]_. [!DNL Luma] dispone di negozi in più paesi, una presenza online con un sito web e app mobili. [!DNL Luma] utilizza Adobe Journey Optimizer per fornire ai propri clienti esperienze connesse, contestuali e personalizzate.

Al termine di questa esercitazione, avrai a disposizione una sandbox che supporta [!DNL Luma] casi d’uso trattati negli esercizi pratici in [Sfide Journey Optimizer](/help/challenges/introduction-and-prerequisites.md) sezione.

## Prerequisiti

Prima di iniziare a configurare la sandbox di formazione, assicurati di disporre dei seguenti elementi:

1. Uno sviluppo dedicato [sandbox](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).

1. [Predefiniti per messaggi e-mail](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=en) configurato per il marketing e la messaggistica transazionale.

1. **[!UICONTROL Amministratore percorso]** e **[!UICONTROL Gestione dati]** diritti per la sandbox di formazione.

1. Il tuo [ID organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=it).

1. I file JSON con i dati di esempio configurati per l’istanza di Journey Optimizer:

   1. Scarica il file `luma-sample-data.zip` file [qui](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip), che contiene tutti i file JSON necessari per questa esercitazione.

   1. Dalla cartella dei download, sposta `luma-data.zip` nel percorso desiderato sul computer e decomprimerlo.

      Questi file contengono i dati di esempio per la sandbox di formazione.

   1. Apri ogni file e individua **`yourOrganizationID`** e sostituirlo con il [ID organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=it).

   1. Salva i file.

## Iniziamo

Inizia con [Impostazione manuale dei dati](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md).

In questo passaggio puoi definire la struttura dati richiesta. Dopo aver completato la configurazione dei dati, puoi acquisire i dati nella sandbox e quindi impostare gli eventi.
