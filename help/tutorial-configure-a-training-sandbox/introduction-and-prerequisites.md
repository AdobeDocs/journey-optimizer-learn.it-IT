---
title: Configurare una sandbox di formazione - introduzione
description: Scopri come configurare una sandbox a scopo di formazione. Segui i passaggi necessari per configurare gli schemi, acquisire dati di esempio e creare eventi.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
source-git-commit: 79249cf6ecd08c38c075a4e27fa9cf74073491af
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 5%

---


# Configurare una sandbox di formazione - Introduzione e prerequisiti

![Tutorial su banner: configurare una sandbox di formazione](./assets/ajo-banner-configure-training-sandbox.png)

Questa esercitazione è stata progettata per gli amministratori e i data engineer incaricati di fornire un ambiente di formazione Adobe Journey Optimizer. Scopri i passaggi necessari per configurare gli schemi, acquisire dati di esempio e creare eventi. Inoltre, creerai tre profili di test che consentono agli studenti di controllare il loro lavoro.

I dati di esempio forniti si basano su una società di abbigliamento atletico fittizia denominata _[!DNL Luma]_. [!DNL Luma] ha negozi in più paesi, una presenza online con un sito web e app mobili. [!DNL Luma] utilizza Adobe Journey Optimizer per fornire ai propri clienti esperienze personalizzate, contestuali ed connesse.

Al termine di questa esercitazione, disporrai di una sandbox che supporta la funzione [!DNL Luma] casi d&#39;uso coperti negli esercizi pratici nella [Sfide Journey Optimizer](/help/challenges/introduction-and-prerequisites.md) sezione .

## Prerequisiti

Prima di iniziare a configurare la sandbox di formazione, assicurati di disporre di:

1. Uno sviluppo dedicato [sandbox](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).
1. [Predefiniti messaggio e-mail](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/channel-configuration/set-up-email-channel.html?lang=en) configurato per il marketing e la messaggistica transazionale.
1. **[!UICONTROL Amministratore del percorso]** e **[!UICONTROL Data Manager]** diritti per la sandbox di addestramento.
1. Le [ID organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=it).

1. I file JSON con i dati di esempio, configurati nella tua istanza Journey Optimizer:

   1. Scarica la `luma-data.zip` file [qui](/help/tutorial-configure-a-training-sandbox/assets/luma-data.zip), che contiene tutti i file JSON richiesti per questa esercitazione.

   1. Dalla cartella dei download, sposta il `luma-data.zip` e decomprimere il file nella posizione desiderata sul computer.

      Ci devono essere tre file JSON: `luma-crm.json`, `luma-loyalty.json`, `luma-products.json`.

      Questi file contengono i dati di esempio inseriti nella sandbox.

   1. Apri ciascun file e trova **`yourOrganizationID`** e sostituiscilo con il tuo [ID organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en).

   1. Salva i file.

## Cominciamo

Inizia con [Configurazione manuale dei dati](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md). In questo passaggio si definisce la struttura dati necessaria. Una volta completata la configurazione dei dati, puoi inserire i dati nella sandbox e quindi configurare gli eventi.