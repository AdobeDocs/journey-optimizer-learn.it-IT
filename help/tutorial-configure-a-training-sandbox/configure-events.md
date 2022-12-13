---
title: Configurare eventi
description: Configurare tre eventi necessari per le mani sulle sfide Journey Optimizer
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: 08dfd48d34fac09d05e57438728e1afa5f6cdef9
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 8%

---

# Configurare eventi

In questa sezione, puoi impostare i tre eventi necessari per gli esercizi pratici nel [Sfide Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

Guarda il video [Creare eventi](/help/set-up-journeys/create-events.md) per informazioni su come creare eventi.

## Creare l’evento di acquisto online Luma

1. Dalla navigazione a sinistra, passa a [!UICONTROL AMMINISTRAZIONE] e seleziona *[!UICONTROL Configurazione]*
1. Da [!UICONTROL Dashboard], seleziona *[!UICONTROL Gestione*]* Eventi

![Gestire gli eventi](assets/create-events.png)

1. Fai clic su *[!UICONTROL Crea evento]*
1. Compila i dettagli e i parametri dell’evento:

   | [!UICONTROL Parametro] | [!UICONTROL Valore] |
   |-------------|-----------|
   | [!UICONTROL NOME] | `LumaOnlinePurchase` |
   | [!UICONTROL TIPO] | [!UICONTROL Unitario] |
   | [!UICONTROL Tipo ID evento] | [!UICONTROL Basato su regole] |
   | [!UICONTROL Schema] | Interazioni prodotto Luma |
   | [!UICONTROL Campi] | EventType <br>Order.priceTotal<br>purchaseOrderNumber<br>productListItems.Quantity<br><b>In Elementi Elenco Prodotti > Schema Catalogo Prodotti Luma > _*[!DNL yourOrganizationID]* > Prodotto:</b> <br> Nome<br>Prezzo<br>ProductImageURL<br>ProductURL |

1. Aggiungi il [!UICONTROL Condizione ID evento]: **[!DNL LumaOnlinePurchase.eventType is commerce.purchases]**

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

## Crea *[!DNL Luma Product Restock] Evento

| [!UICONTROL Parametro] | [!UICONTROL Valore] |
|-------------|-----------|
| [!UICONTROL NOME] | `LumaProductRestock` |
| [!UICONTROL TIPO] | [!UICONTROL Business] |
| [!UICONTROL Schema] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL Campi] | productID <br> stockEventType<br><b>In Prodotto > Prodotti Luma > *[!DNL yourOrganizationID]* > Prodotto:</b> <br>Nome<br>Prezzo<br> ProductImageURL<br>Descrizione |
| [!UICONTROL Condizione] | LumaProductRestock._`your organization's ID`.inventoryEvent.stockEventType è ripristinato |

## Congratulazioni

La tua sandbox è ora pronta per l&#39;uso!
