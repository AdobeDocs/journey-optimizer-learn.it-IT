---
title: Configurazione manuale della struttura dati
description: Crea i namespace di identità richiesti e definisci la struttura dati di esempio Luma.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
source-git-commit: d82a80675230db561bc2fcb6613159bd5a898f32
workflow-type: tm+mt
source-wordcount: '1076'
ht-degree: 7%

---


# Impostare manualmente i dati

In questa sezione vengono creati i namespace di identità richiesti e vengono definiti i [!DNL Luma] struttura dati di esempio creando [[!UICONTROL schemi]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=it).

>[!TIP]
>Guarda il tutorial video [Mappa le identità](/help/set-up-data/map-identities.md) prima di iniziare.

## Passaggio 1: Creare spazi dei nomi delle identità

In questo passaggio puoi creare spazi dei nomi delle identità per [!DNL Luma] campi di identità personalizzati denominati `loyaltyId`, `crmId`e `lumaProduct`. Gli spazi dei nomi di identità svolgono un ruolo fondamentale nella creazione di profili cliente in tempo reale, in quanto due valori corrispondenti nello stesso spazio dei nomi consentono a due origini dati di formare un grafico di identità.

Per iniziare, crea uno spazio dei nomi per [!DNL Luma] schema fedeltà:

1. Nell’interfaccia utente di Platform, passa a **[!UICONTROL Identità]** nella navigazione a sinistra.

1. Seleziona **[!UICONTROL Creare uno spazio dei nomi di identità]**.

1. Fornisci i seguenti dettagli:

   | Nome visualizzato | Simbolo di identità | Tipo |
   |---|---|---|
   | `Luma Loyalty ID` | `lumaLoyalty` | [!UICONTROL ID multi-dispositivo] |

1. Seleziona **[!UICONTROL Crea]**.

   ![Creare spazi dei nomi](assets/createNamespace.png)

1. Crea altri due namespace seguendo gli stessi passaggi:

   | Nome visualizzato | Simbolo di identità | Tipo |
   |---|---|---|
   | `Luma CRM ID` | `lumaCRM` | [!UICONTROL ID multi-dispositivo] |
   | `Luma Product` | `lumaProduct` | [!UICONTROL Identificatore non personale] |

## Passaggio 2: Creare schemi

In questo passaggio è possibile definire la struttura dei dati di esempio creando sei [[!UICONTROL schemi]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html):

* [[!DNL Luma Loyalty]](#create-luma-loyalty-schema)

* [[!DNL Luma Products]](#create-luma-products-schema)

* [[!DNL Luma Product Inventory Events]](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Product Interactions]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Test Profiles]](#create-luma-crm-and-luma-product-interactions-schemas)

>[!TIP]
>
>Guarda il tutorial video: [Creare uno schema](/help/set-up-data/create-schema.md) prima di iniziare.

### Crea [!DNL Luma Loyalty] [!UICONTROL Schema] {#create-luma-loyalty-schema}

#### Creare lo schema

Inizia creando il [!DNL Luma Loyalty] schema:

1. Vai a **[!UICONTROL GESTIONE DATI]** > **[!UICONTROL Schemi]** nella navigazione a sinistra.

1. Seleziona **[!UICONTROL Crea schema]** in alto a destra.

1. Dal menu a discesa, seleziona **[!UICONTROL Profilo individuale XDM]**, poiché stai modellando gli attributi di un singolo cliente (punti, stato e così via).

   ![Creare uno schema](assets/loyaltyCreateSchema.png)

#### Aggiungi gruppi di campi esistenti

Viene quindi richiesto di aggiungere gruppi di campi allo schema. È necessario aggiungere tutti i campi agli schemi utilizzando i gruppi. Si stanno aggiungendo gruppi di campi esistenti e è necessario creare un gruppo di campi.

>[!NOTE]
>
>Se la [!UICONTROL Gruppi di campi] modale non si apre automaticamente nel [!UICONTROL Schemi] pagina, seleziona **[!UICONTROL Aggiungi]** (come illustrato nell’immagine seguente).

![Aggiungi gruppo di campi](assets/add_field_group.png)

1. Sulla **[!UICONTROL Aggiungi gruppi di campi]** abilitare i seguenti gruppi di campi:

   * **[!UICONTROL Dettagli demografici]** per i dati di base dei clienti quali nome e data di nascita.

   * **[!UICONTROL Dati di contatto personali]** per informazioni di contatto di base come indirizzo e-mail e numero di telefono.

   * **[!UICONTROL Dettagli fedeltà]** per i dettagli fedeltà quali punti, data di unione o stato. Il gruppo di campi fedeltà è molto in basso nell’elenco, quindi è più semplice cercarlo.

1. Seleziona **[!UICONTROL Aggiungi gruppo di campi]** per aggiungere tutti e tre i gruppi di campi allo schema.

   ![Seleziona gruppi di campi standard](assets/addstandardFieldGroups.png)

1. Selezionare il nodo principale dello schema.

1. Invio `Luma Loyalty` come [!UICONTROL Nome visualizzato].

#### Crea un [!UICONTROL gruppo di campi]

Per garantire la coerenza tra gli schemi, Adobe consiglia di gestire tutti gli identificatori di sistema in un unico gruppo:

1. Da **[!UICONTROL Composizione]** sezione [!UICONTROL Gruppi di campi], seleziona **[!UICONTROL Aggiungi]**.

1. Seleziona **[!UICONTROL Crea nuovo gruppo di campi]**.

1. Aggiungi `Luma Identifiers` come **[!UICONTROL Nome visualizzato]**.

1. Aggiungi `system identifiers for XDM Individual Profile class` come **[!UICONTROL Descrizione]**.

1. Seleziona **[!UICONTROL Aggiungi gruppi di campi]**.

   ![Crea nuovo gruppo di campi](assets/addnewfieldgroup.png)

#### Aggiungi campi al nuovo [!UICONTROL gruppo di campi]

Il nuovo gruppo di campi vuoto viene aggiunto allo schema. I pulsanti + consentono di aggiungere nuovi campi a qualsiasi posizione della gerarchia. In questo caso, è necessario aggiungere campi al livello principale:

1. Seleziona **[!UICONTROL +]** accanto al nome dello schema.

   Questo passaggio aggiunge un campo in **il tuo tenant id** per gestire i conflitti tra i campi personalizzati e quelli standard.

1. In **[!UICONTROL Proprietà campo]** barra laterale, aggiungi i dettagli del nuovo campo:

   * **Nome campo:** `systemIdentifier`

   * **[!UICONTROL Nome visualizzato]:** `System Identifier`

   * **Tipo:** Oggetto

   * **[!UICONTROL Assegna gruppo di campi]:** [!DNL Luma identifiers]

1. Seleziona **[!UICONTROL Applica]**.

   ![Aggiungi identificatore di sistema](assets/addsysteidentifier.png)

   Aggiungi due campi sotto `systemIdentifier` oggetto:

   | [!UICONTROL Nome campo] | [!UICONTROL Nome visualizzato] | [!UICONTROL Tipo] |
   |-------------|-----------|----------|
   | `loyaltyId` | `Loyalty ID` | [!UICONTROL Stringa] |
   | `crmId` | `CRM Id` | [!UICONTROL Stringa] |

![field](./assets/add_fields.png)

#### Imposta le identità

Ora hai lo spazio dei nomi e la [!DNL Luma] Schema fedeltà configurato. Prima di poter acquisire i dati, devi assegnare un’etichetta ai campi di identità. Ogni schema utilizzato con [!UICONTROL Profilo cliente in tempo reale] è necessario specificare un&#39;identità principale e ogni record acquisito deve avere un valore per quel campo.

1. Imposta la **identità principale**:

   Da `Luma Loyalty` schema:

   1. Seleziona la `Luma Identifiers` gruppo di campi.

   1. Seleziona la `loyaltyId` campo .

   1. In **[!UICONTROL Proprietà campo]**, abilita **[!UICONTROL Identità]** scatola.

   1. Abilita la **[!UICONTROL Identità principale]** scatola.

   1. Seleziona la `Luma Loyalty Id` namespace **[!UICONTROL Namespace Identity]** a discesa.

   1. Seleziona **[!UICONTROL Applica]**.

      ![identità principale](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

1. Imposta un **identità secondaria**:

   Da `Luma Loyalty` schema:

   1. Seleziona la `Luma Identifiers` gruppo di campi.

   2. Seleziona la `crmId` campo .

   3. In **[!UICONTROL Proprietà campo]**, abilita **[!UICONTROL Identità]** scatola.

   4. Seleziona la `Luma CRM Id` namespace **[!UICONTROL Namespace Identity]** a discesa.

   5. Seleziona **[!UICONTROL Applica]**.

#### Abilita per profilo e salva lo schema

1. Selezionare il nodo principale dello schema.

1. In [!UICONTROL Proprietà campo] abilita **[!UICONTROL Profilo]**.

   Lo schema dovrebbe essere simile al seguente:

   ![Schema fedeltà Luma](assets/lumaloyaltyschema.png)

1. Seleziona **[!UICONTROL Salva]**.

### Crea [!DNL Luma Products] [!UICONTROL Schema] {#create-luma-products-schema}

1. Vai a [!UICONTROL GESTIONE DATI] -> **[!UICONTROL Schemi]** nella navigazione a sinistra.

1. Seleziona la **[!UICONTROL Crea schema]** in alto a destra.

1. Dal menu a discesa, seleziona **[!UICONTROL Sfoglia tutti i tipi di schema]**, che consente di creare una classe.

1. Seleziona **[!UICONTROL Crea nuova classe].

1. Aggiungi il nome visualizzato: `Luma Products`.

1. Assegna la classe.

1. Crea un [!UICONTROL gruppo di campi]:

   * Nome visualizzato: `Luma Product Info`

1. Aggiungi il seguente campo al [!DNL Luma] [!UICONTROL Prodotto] Gruppo di campi informazioni.

   * Nome campo: `product`

   * Nome visualizzato: `Product`

   * Tipo: [!UICONTROL Oggetto]

   * Gruppo di campi: [!DNL Luma Product info]

1. Seleziona **[!UICONTROL Applica]**.

1. Aggiungi i campi seguenti al **[!DNL Product]** oggetto:

   | [!UICONTROL Nome campo] | [!UICONTROL Nome visualizzato] | [!UICONTROL Tipo] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL Stringa] |
   | `name` | `Name` | [!UICONTROL Stringa] |
   | `category` | `Category` | [!UICONTROL Stringa] |
   | `color` | `Color` | [!UICONTROL Stringa] |
   | `size` | `Size` | [!UICONTROL Stringa] |
   | `price` | `Price` | [!UICONTROL Doppio] |
   | `description` | `Description` | [!UICONTROL Stringa] |
   | `productImageURL` | `Product Image URL` | [!UICONTROL Stringa] |
   | `productURL` | `Product URL` | [!UICONTROL Stringa] |
   | `stockQuantity` | `Stock Quantity` | [!UICONTROL Stringa] |

1. Aggiungi il **[!UICONTROL Nome visualizzato]** `Luma Products` allo schema.

1. Seleziona **[!UICONTROL Salva]**.

### Crea [!DNL Luma Product Inventory Event] [!UICONTROL Schema] {#create-luma-product-inventory-event-schema}

1. Vai a **[!UICONTROL GESTIONE DATI]** -> **[!UICONTROL Schemi]** nella navigazione a sinistra.

1. Seleziona la **[!UICONTROL Crea schema]** in alto a destra.

1. Dal menu a discesa, seleziona **[!UICONTROL Sfoglia tutti i tipi di schema]**.

1. Seleziona **[!UICONTROL Crea nuova classe]**.

1. Aggiungi il nome visualizzato: `Business Event`.

1. Seleziona il tipo: *[!UICONTROL Serie temporali]*.

1. Assegna la classe.

1. Crea un [!UICONTROL gruppo di campi]:

   * Nome visualizzato: `Product Inventory Event Details`

1. Aggiungi il **[!UICONTROL Nome visualizzato]** `Luma Product Inventory Event Schema` allo schema.

1. Aggiungi il seguente campo al gruppo di campi Informazioni prodotto Luma:

   * Nome campo: `inventoryEvent`

   * Nome visualizzato: `Inventory Event`

   * Tipo: [!UICONTROL Oggetto]

   * Gruppo di campi: [!DNL Product Inventory Event Details]

1. Aggiungi i campi seguenti al **[!DNL Product Inventory Event Details]** oggetto:

   | [!UICONTROL Nome campo] | [!UICONTROL Nome visualizzato] | [!UICONTROL Tipo] |
   |-------------|-----------|----------|
   | `productId` | `Product ID` | [!UICONTROL Stringa] |
   | `sku` | `SKU` | [!UICONTROL Stringa] |
   | `stockEventType` | `Stock Event Type` | **[!UICONTROL Enum]** con `restock` e `outOfStock` come valori |

   1. per impostare `stockEventType` su Enum, selezionare il tipo: `string`.

   1. Scorri verso il basso fino alla parte inferiore del **[!UICONTROL Proprietà campo]**.

   1. Abilita **[!UICONTROL Enum]**.

   1. Invio **[!UICONTROL values] ([!UICONTROL etichetta)]**: `restock` (`restock`).

   1. Seleziona **[!UICONTROL Aggiungi riga]**.

   1. Invio **[!UICONTROL values] ([!UICONTROL etichetta)]**: `outOfStock` (`out of stock`).

   1. Seleziona **[!UICONTROL Applica]**.

      ![enum](assets/enum.png)

1. Imposta `productId` campo come **[!UICONTROL identità principale]** utilizzo **[!DNL Luma Product namespace]**.

1. Seleziona la `sku` e definire una relazione con `product.sku` nel campo **[!DNL Luma Products]** Schema:

   1. Scorri verso il basso fino alla parte inferiore del **[!UICONTROL Proprietà campo]**.

   1. Abilita **[!UICONTROL Relazione]**.

      1. **[!UICONTROL Schema di riferimento]**: [!DNL Luma Products].

      1. **[!UICONTROL Spazio dei nomi identità di riferimento]**: [!DNL Luma Product].
   1. Seleziona **[!UICONTROL Applica]**.

      Lo schema dovrebbe essere simile al seguente:

      ![Relazione SKU](assets/sku_relationship.png)


1. Abilita per **Profilo**.

1. Seleziona [!UICONTROL Salva] per salvare lo schema.

### Crea il [!DNL Luma CRM] e [!DNL Luma Product Interactions] schemi {#create-luma-crm-and-luma-product-interactions-schemas}

Crea i seguenti elementi aggiuntivi [!UICONTROL schemi]:

| [!UICONTROL Nome visualizzato] | [!DNL Luma CRM] | [!DNL Luma Product Interactions] | [!DNL Luma Test Profiles] |
|  ---| ------- | ---- |----|
| **[!UICONTROL Tipo]** | [!UICONTROL Profilo individuale XDM] | [!UICONTROL Evento esperienza XDM] | [!UICONTROL Profilo individuale XDM] |
| **[!UICONTROL Aggiungi gruppo di campi esistente]** | Identificatori Luma<br>Dettagli demografici<br>Dati di contatto personali | Mappa identità<br>Dettagli Commerce | Identificatori Luma<br>Dettagli demografici<br>Dati di contatto personali<br>Dettagli del test del profilo |
| **[!UICONTROL Relazione]** |  | *[!DNL productListItems.SKU]*:<br> Schema di riferimento *[!DNL Luma Products]* <br>[!DNL Reference identity namespace] *[!DNL Luma Product]* schema |
| **[!UICONTROL Identità principale] [!UICONTROL namespace])** | systemIdentifier.crmId<br>(ID CRM Luma) |  | personalEmail.address<br>(Email) |
| **[!UICONTROL Identità secondaria] [!UICONTROL namespace]** | personalEmail.address (Email)<br>mobilePhone.number (telefono) |  |
| **[!UICONTROL Abilita per profilo]** | sì | sì | sì |

## Passaggi successivi

Dopo aver creato la struttura dati, [creare set di dati e acquisire dati di esempio](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md).