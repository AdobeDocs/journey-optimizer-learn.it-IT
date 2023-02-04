---
title: Configurare eventi
description: Configurare tre eventi necessari per le mani sulle sfide Journey Optimizer
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: a0f089635df6af8fce9127083ecf582a56b5d569
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 10%

---

# Configurare eventi

In questa sezione, puoi impostare i tre eventi necessari per gli esercizi pratici nel [Sfide Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

Il video seguente spiega come creare eventi:

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12)

## Creare l’evento di acquisto online Luma

Quando utilizzi questo evento, Journey Optimizer riceve informazioni quando una persona acquista online prodotti luma.

1. Crea un evento con i seguenti parametri:

   | [!UICONTROL Parametro] | [!UICONTROL Valore] |
   |-------------|-----------|
   | [!UICONTROL NOME] | `LumaOnlinePurchase` |
   | [!UICONTROL TIPO] | [!UICONTROL Unitario] |
   | [!UICONTROL Tipo ID evento] | [!UICONTROL Basato su regole] |
   | [!UICONTROL Schema] | `Luma Web Events Schema` |
   | [!UICONTROL Campi] | `eventType` <br>`commerce.order.priceTotal`<br>`commerce.order.purchaseOrderNumber`<br>`commerce.shipping.adress.street1`<br>`commerce.shipping.adress.city`<br>`commerce.shipping.adress.postalCode`<br>`commerce.shipping.adress.state`<br>`productListItems.quantity`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.name`<br>`productListItems.Luma Product Catalog Schema._your Organization_IDprice`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.imageURL`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.url` |

2. Aggiungi il [!UICONTROL Condizione ID evento]: `LumaOnlinePurchase.eventType is commerce.purchases`

   1. Seleziona l’icona a forma di matita per modificare il campo
   2. Sulla [!UICONTROL Aggiungere una condizione ID evento] modale, trascina e rilascia la `eventType` sull&#39;area di lavoro
   3. Seleziona `commerce.purchases`
   4. Seleziona ok sulla tela
   5. Seleziona ok sul modale

![Aggiungi condizione evento](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. Seleziona [!UICONTROL NAMESPACE]: `Luma CRM ID (lumaCrmId)`

2. Seleziona **[!UICONTROL Salva]**.

## Crea *[!DNL Luma Wishlist Add]* Evento

| [!UICONTROL Parametro] | [!UICONTROL Valore] |
|-------------|-----------|
| [!UICONTROL NOME] | `LumaWishlistAdd` |
| [!UICONTROL TIPO] | [!UICONTROL Unitario] |
| [!UICONTROL Tipo ID evento] | [!UICONTROL Basato su regole] |
| [!UICONTROL Schema] | `Luma Product Interactions` |
| [!UICONTROL Campi] | EventType<br>productListItem.Quantity<br><b>In Elenco prodotti > Prodotti Luma > _*[!DNL yourOrganizationID]* > Prodotto:</b> <br>Nome<br>Prezzo<br> ProductImageURL<br>ProductURL |
| [!UICONTROL Condizione] | [!DNL LumaWishlistAdd.eventType is commerce.saveForLaters] |
| [!UICONTROL Namespace] | Email(EMail) |

## Crea *[!DNL Luma Product Restock]* Evento

| [!UICONTROL Parametro] | [!UICONTROL Valore] |
|-------------|-----------|
| [!UICONTROL NOME] | `LumaProductRestock` |
| [!UICONTROL TIPO] | [!UICONTROL Business] |
| [!UICONTROL Schema] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL Campi] | SKU <br> stockEventType<br><b> yourOrganizationID > product:</b> <br>name<br>prezzo<br> ImageURL<br>descrizione |
| [!UICONTROL Condizione] | LumaProductRestock._`your organization's ID`.inventoryEvent.stockEventType è ripristinato |

## Congratulazioni

La tua sandbox è ora pronta per l&#39;uso!
