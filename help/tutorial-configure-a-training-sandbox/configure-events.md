---
title: Configurare gli eventi
description: Configurare tre eventi necessari per le sfide pratiche di Journey Optimizer
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: fd9d277be00449155c49b3809fe647d7342b6acd
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 98%

---

# Configurare gli eventi

In questa sezione, puoi impostare i tre eventi necessari per gli esercizi pratici in [Sfide di Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

Il video seguente spiega come creare gli eventi:

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12&learn=on){transcript=true}

## Creare l’evento di acquisto online Luma

Utilizzando questo evento, Journey Optimizer riceve informazioni quando una persona acquista prodotti Luma online.

1. Crea un evento con i seguenti parametri:

   | [!UICONTROL Parametro] | [!UICONTROL Valore] |
   |-------------|-----------|
   | [!UICONTROL NOME] | `LumaOnlinePurchase` |
   | [!UICONTROL TIPO] | [!UICONTROL Unitario] |
   | [!UICONTROL Tipo ID evento] | [!UICONTROL Basato su regole] |
   | [!UICONTROL Schema] | `Luma Web Events Schema` |
   | [!UICONTROL Campi] | `eventType` <br>`commerce.order.priceTotal`<br>`commerce.order.purchaseOrderNumber`<br>`commerce.shipping.adress.street1`<br>`commerce.shipping.adress.city`<br>`commerce.shipping.adress.postalCode`<br>`commerce.shipping.adress.state`<br>`productListItems.quantity`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.name`<br>`productListItems.Luma Product Catalog Schema._your Organization_IDprice`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.imageURL`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.url` |

1. Aggiungi la [!UICONTROL Condizione ID evento]: `LumaOnlinePurchase.eventType is commerce.purchases`:

   1. Seleziona l’icona della matita per modificare il campo.

   1. Nella finestra modale **[!UICONTROL Aggiungi una condizione per l’ID evento]**, trascina e rilascia il tipo di evento `eventType` nell’area di lavoro.
   1. Seleziona `commerce.purchases`.
   1. Seleziona **[!UICONTROL OK]** nell’area di lavoro.
   1. Seleziona **[!UICONTROL OK]** nella finestra modale.

   ![Aggiungere una condizione evento](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. Seleziona [!UICONTROL SPAZIO DEI NOMI]: `Luma CRM ID (lumaCrmId)`

1. Seleziona **[!UICONTROL Salva]**.

## Creare l’evento *[!DNL Luma Product Restock]*

| [!UICONTROL Parametro] | [!UICONTROL Valore] |
|-------------|-----------|
| [!UICONTROL NOME] | `LumaProductRestock` |
| [!UICONTROL TIPO] | [!UICONTROL Business] |
| [!UICONTROL Schema] | [!DNL Luma Product Inventory Event Schema] |
| [!UICONTROL Campi] | SKU <br> stockEventType<br><b>LumaProductCatalogSchema._yourOrganizationID.product :</b> <br>nome<br>prezzo<br> ImageURL<br>descrizione |
| [!UICONTROL Condizione] | LumaProductRestock._`your organization's ID`.inventoryEvent.stockEventType è il rifornimento |

Congratulazioni! Ora la sandbox è pronta per l’uso.
