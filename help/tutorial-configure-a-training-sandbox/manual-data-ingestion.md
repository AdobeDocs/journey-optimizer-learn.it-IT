---
title: Inserire i dati manualmente
description: Crea manualmente set di dati e acquisisci dati di esempio.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
source-git-commit: 93c5191d9bc0e5cc81d5892251df73251e6c6ea7
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 8%

---


# Inserire i dati manualmente

Questa sezione descrive i passaggi necessari per creare set di dati e acquisire dati di esempio.

>[!TIP]
>
> Guarda il tutorial video [Creare set di dati e acquisire dati](/help/set-up-data/create-datasets-and-ingest-data.md) prima di iniziare.

Ne creerai cinque [!UICONTROL set di dati] basato sulla Luma [!UICONTROL schemi] creato in [sezione precedente](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md). Una volta creati i set di dati, puoi acquisire i dati dai file JSON scaricati e modificati. (Vedi [Introduzione e prerequisiti](/help/tutorial-configure-a-training-sandbox/introduction-and-prerequisites.md) per istruzioni).

## Creare il primo set di dati

Creare un set di dati denominato *[!DNL Luma Loyalty Data]* da [!DNL Luma Loyalty schema]

1. Dalla navigazione a sinistra, sotto [!UICONTROL GESTIONE DATI], seleziona **[!UICONTROL Set di dati]**.

1. Seleziona **[!UICONTROL Creare un set di dati]**.

   ![Creare un set di dati](assets/create-dataset.png)

1. Nella pagina successiva, seleziona [!UICONTROL Creare un set di dati dallo schema].

   ![Creare un set di dati da uno schema](assets/create-dataset-from-schema.png)

1. Nella pagina successiva, cerca il *[!DNL Luma Loyalty]* schema creato in precedenza.

1. Seleziona *[!DNL Luma Loyalty]*.

1. Fai clic su **[!UICONTROL Avanti]**.

   ![Ricerca e selezione dello schema](assets/create-dataset-select-schema.png)

1. Configura il set di dati:

   * Nome: `Luma Loyalty Data`

1. Fai clic su **[!UICONTROL Fine]**.

   ![Configurare il set di dati](assets/create-dataset-configure.png)

## Inserire dati di esempio

Dopo aver creato un set di dati, puoi inserire i dati nel set di dati.

1. Sulla [!DNL Luma Loyalty Data] , scorri verso il basso nella parte inferiore del pannello di destra fino al [!UICONTROL AGGIUNGI DATI] e abilita:

   * **[!UICONTROL Diagnostica degli errori]** e

   * **[!UICONTROL Acquisizione parziale]**

   ![Acquisisci dati](assets/ingest-data.png)

1. Trascina e rilascia la `luma-loyalty.json` per caricare dati di esempio nel set di dati.

1. Aggiorna la pagina e controlla lo stato del batch per confermare che il file sia stato acquisito correttamente.

   375 record avrebbero dovuto essere acquisiti. L’acquisizione dei dati potrebbe richiedere un paio di minuti.

>[!TIP]
>
>Se il batch non riesce, assicurati di aver sostituito l&#39;ID organizzazione nel `luma-loyalty.json` file con il tuo [ID organizzazione](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=it).

## Crea cinque ulteriori [!UICONTROL set di dati]

Quindi, crea i seguenti cinque ulteriori [!UICONTROL set di dati] e inserire i dati nel `Luma CRM Data`, `Luma Products Data`e `Luma Test Profiles` set di dati.

| Nome set di dati | Da schema | File da acquisire | Record |
| -----| ------ | -------| ------- |
| `Luma CRM Data` | `Luma CRM` | `luma-crm.json` | 500 |
| `Luma Products Data` | `Luma Products` | `luma-products.json` | 92 |
| `Luma Product Interactions Data` | `Luma Product Interactions` | Nessuno | 0 |
| `Luma Product Inventory Events` | `Luma Product Inventory Events` | Nessuno | 0 |
| `Luma Test Profiles` | `Luma Test Profiles` | `luma-test-profiles.json` | 3 |

## Passaggi successivi

Hai creato tutti i set di dati richiesti e acquisito i dati di esempio. La fase finale è [configurare eventi](/help/tutorial-configure-a-training-sandbox/configure-events.md).
