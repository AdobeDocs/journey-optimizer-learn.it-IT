---
title: Configurare una sandbox di formazione - introduzione
description: Scopri come configurare una sandbox a scopo di formazione. Segui i passaggi necessari per configurare gli schemi, acquisire dati di esempio e creare eventi.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
hide: true
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: e377ddb8b84dccd503274caf9ffa3d4c73eedc28
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 9%

---

# Configurare una sandbox di formazione - Introduzione e prerequisiti

![Tutorial su banner: configurare una sandbox di formazione](./assets/ajo-banner-configure-training-sandbox.png)

Questa esercitazione è stata progettata per gli amministratori e i data engineer incaricati di fornire un ambiente di formazione Adobe Journey Optimizer. Scopri i passaggi necessari per configurare gli schemi, acquisire dati di esempio e creare eventi. Inoltre, creerai tre profili di test che consentono agli studenti di controllare il loro lavoro.

I dati di esempio forniti si basano su una società di abbigliamento atletico fittizia denominata _[!DNL Luma]_. [!DNL Luma] ha negozi in più paesi, una presenza online con un sito web e app mobili. [!DNL Luma] utilizza Adobe Journey Optimizer per fornire ai propri clienti esperienze connesse, contestuali e personalizzate.

Al termine di questa esercitazione, disporrai di una sandbox che supporta la funzione [!DNL Luma] casi d&#39;uso coperti negli esercizi pratici nella [Sfide Journey Optimizer](/help/challenges/introduction-and-prerequisites.md) sezione .

## Prerequisiti

Prima di iniziare a configurare la sandbox di formazione, assicurati di disporre di:

1. Uno sviluppo dedicato [sandbox](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).
1. [Predefiniti messaggio e-mail](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/channel-configuration/set-up-email-channel.html?lang=en) configurato per il marketing e la messaggistica transazionale.
1. **[!UICONTROL Amministratore del percorso]** e **[!UICONTROL Data Manager]** diritti per la sandbox di addestramento.
1. Le [ID organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=it).
1. I file JSON con i dati di esempio, configurati nella tua istanza Journey Optimizer:
   1. Scarica la `luma-sample-data.zip` file [qui](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip), che contiene tutti i file JSON richiesti per questa esercitazione.
   1. Dalla cartella dei download, sposta il `luma-data.zip` archiviare nel percorso desiderato del computer e decomprimerlo.Questi file contengono i dati di esempio per la sandbox di formazione.
   1. Apri ciascun file e trova **`yourOrganizationID`** e sostituiscilo con il tuo [ID organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=it).
   1. Salva i file.

## Cominciamo

Inizia con [Configurazione manuale dei dati](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md). In questo passaggio si definisce la struttura dati necessaria. Una volta completata la configurazione dei dati, puoi inserire i dati nella sandbox e quindi configurare gli eventi.
