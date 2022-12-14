---
title: Configurazione manuale della struttura dati
description: Crea i namespace di identità richiesti e definisci la struttura dati di esempio Luma.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
exl-id: de870229-d9a6-4051-9f76-13d402cce3b4
source-git-commit: db681243c066911af03b75f045a4dc4a990daa7d
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 7%

---

# Impostare manualmente i dati

In questa sezione vengono creati i namespace di identità richiesti e vengono definiti i [!DNL Luma] struttura dati di esempio creando [[!UICONTROL schemi]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=it).

>[!TIP]
>Guarda il tutorial video [Mappa le identità](/help/set-up-data/map-identities.md) prima di iniziare.

## Passaggio 1: Creare spazi dei nomi delle identità

In questo passaggio puoi creare spazi dei nomi delle identità per [!DNL Luma] campi di identità personalizzati denominati `lumaLoyaltyId`, `lumaCrmId`e `lumaProductSKU`. Gli spazi dei nomi di identità svolgono un ruolo fondamentale nella creazione di profili cliente in tempo reale, in quanto due valori corrispondenti nello stesso spazio dei nomi consentono a due origini dati di formare un grafico di identità.

Inizia creando un [!UICONTROL namespace] per [!DNL Luma Loyalty ID] schema:

1. Nell’interfaccia utente di Journey Optimizer, vai a ***[!UICONTROL Cliente]** > **[!UICONTROL Identità]** nella navigazione a sinistra.

1. Seleziona **[!UICONTROL Creare uno spazio dei nomi di identità]**.

1. Fornisci i seguenti dettagli:

   | Nome visualizzato | Simbolo di identità | Tipo |
   |---|---|---|
   | `Luma Loyalty ID` | `lumaLoyaltyId` | [!UICONTROL ID multi-dispositivo] |

1. Seleziona **[!UICONTROL Crea]**.

   ![Creare spazi dei nomi](assets/createNamespace.png)

1. Crea altri due namespace seguendo gli stessi passaggi:

   | Nome visualizzato | Simbolo di identità | Tipo |
   |---|---|---|
   | `Luma CRM ID` | `lumaCrmId` | [!UICONTROL ID multi-dispositivo] |
   | `Luma Product SKU` | `lumaProductSKU` | [!UICONTROL Identificatore non personale] |

## Passaggio 2: Creare schemi

In questo passaggio è possibile definire la struttura dei dati di esempio creando sei [[!UICONTROL schemi]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html):

* [[!DNL Luma Loyalty Schema]](#create-luma-loyalty-schema)

* [[!DNL Luma Product catalog Schema]](#create-luma-product-catalog-schema)

* [[!DNL Luma Product Inventory Events]](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Web Events Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Test Profiles Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

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

1. Invio `Luma Loyalty Schema` come [!UICONTROL Nome visualizzato].

#### Crea un [!UICONTROL gruppo di campi]

Per garantire la coerenza tra gli schemi, Adobe consiglia di gestire tutti gli identificatori di sistema in un unico gruppo:

1. Da **[!UICONTROL Composizione]** sezione [!UICONTROL Gruppi di campi], seleziona **[!UICONTROL Aggiungi]**.

1. Seleziona **[!UICONTROL Crea nuovo gruppo di campi]**.

1. Aggiungi `Luma Identity Profile Field Group` come **[!UICONTROL Nome visualizzato]**.

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

Ora hai il [!UICONTROL namespace] e [!DNL Luma Loyalty schema] configurato. Prima di poter acquisire i dati, devi assegnare un’etichetta ai campi di identità. Ogni schema utilizzato con [!UICONTROL Profilo cliente in tempo reale] è necessario specificare un&#39;identità principale e ogni record acquisito deve avere un valore per quel campo.

1. Imposta la **identità principale**:

   Da **[!DNL Luma Loyalty Schema]**:

   1. Seleziona **[!DNL Luma Identity Profile Field Group]**.

   2. Seleziona la **[!DNL loyaltyId]** campo .

   3. In **[!UICONTROL Proprietà campo]**, abilita **[!UICONTROL Identità]** scatola.

   4. Abilita la **[!UICONTROL Identità principale]** scatola.

   5. Seleziona la `Luma Loyalty Id` namespace **[!UICONTROL Namespace Identity]** a discesa.

   6. Seleziona **[!UICONTROL Applica]**.

      ![identità principale](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

2. Imposta un **identità secondaria**:

   Da **[!DNL Luma Loyalty Schema]**:

   1. Seleziona **[!DNL Luma Identity Profile Field Group]**..

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

### Creazione [!DNL Luma Product catalog Schema] {#create-luma-product-catalog-schema}

1. Vai a [!UICONTROL GESTIONE DATI] -> **[!UICONTROL Schemi]** nella navigazione a sinistra.

1. Seleziona la **[!UICONTROL Crea schema]** in alto a destra.

1. Dal menu a discesa, seleziona **[!UICONTROL Sfoglia tutti i tipi di schema]**, che consente di creare una classe.

1. Seleziona **[!UICONTROL Crea nuova classe].

1. Aggiungi il nome visualizzato: `Luma Product Catalog Class`.

1. Assegna la classe.

1. Crea un [!UICONTROL gruppo di campi]:

   * Nome visualizzato: `Luma Product Catalog Field Group`

1. Aggiungi il seguente campo al **[!DNL Luma Product Catalog Field Group]**.

   * Nome campo: `product`

   * Nome visualizzato: `Product`

   * Tipo: [!UICONTROL Oggetto]

   * Gruppo di campi: [!DNL Luma Product Catalog Field Group]

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
   | `ImageURL` | `Image URL` | [!UICONTROL Stringa] |
   | `stockQuantity` | `Stock Quantity` | [!UICONTROL Stringa] |

1. Imposta la **[!DNL SKU]** come identità principale
1. Aggiungi il **[!UICONTROL Nome visualizzato]** `Luma Product Catalog Field Group` al [!UICONTROL gruppo di campi].

1. Seleziona **[!UICONTROL Salva]**.


### Creazione [!DNL Luma Product Inventory Event Schema] {#create-luma-product-inventory-event-schema}


1. Vai a **[!UICONTROL GESTIONE DATI]** -> **[!UICONTROL Schemi]** nella navigazione a sinistra.

1. Seleziona la **[!UICONTROL Crea schema]** in alto a destra.

1. Dal menu a discesa, seleziona **[!UICONTROL Sfoglia tutti i tipi di schema]**.

1. Seleziona **[!UICONTROL Crea nuova classe]**.

1. Aggiungi il nome visualizzato: `Luma Business Event Class`.

1. Seleziona il tipo: *[!UICONTROL Serie temporali]*.

1. Assegna la classe.

1. Crea un [!UICONTROL gruppo di campi]:

   * Nome visualizzato: `Luma Product Inventory Event Details Field Group`

1. Aggiungi il **[!UICONTROL Nome visualizzato]** `Luma Product Inventory Event Schema` allo schema.

1. Aggiungi il seguente campo al **[!DNL Luma Product Inventory Event Details Field Group]**:

   * Nome campo: `inventoryEvent`

   * Nome visualizzato: `Inventory Event`

   * Tipo: [!UICONTROL Oggetto]

   * Gruppo di campi: `Luma Product Inventory Event Details Field Group`

1. Aggiungi i campi seguenti al `Product Inventory Event Details` oggetto:

   | [!UICONTROL Nome campo] | [!UICONTROL Nome visualizzato] | [!UICONTROL Tipo] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL Stringa] |
   | `stockEventType` | `Stock Event Type` | [!UICONTROL Stringa] |

   1. per impostare `stockEventType` su Enum, selezionare il tipo: `string`.

   2. Scorri verso il basso fino alla parte inferiore del **[!UICONTROL Proprietà campo]**.

   3. Abilita **[!UICONTROL Enum]**.

   4. Invio **[!UICONTROL values] ([!UICONTROL etichetta)]**: `restock` (`restock`).

   5. Seleziona **[!UICONTROL Aggiungi riga]**.

   6. Invio **[!UICONTROL values] ([!UICONTROL etichetta)]**: `outOfStock` (`out of stock`).

   7. Seleziona **[!UICONTROL Applica]**.

      ![enum](assets/enum.png)

1. Imposta `productId` campo come **[!UICONTROL identità principale]** utilizzo **[!DNL Luma Product namespace]**.

1. Seleziona la `sku` e definire una relazione con `product.sku` nel campo **[!DNL Luma Product catalog Schema]** Schema:

   1. Scorri verso il basso fino alla parte inferiore del **[!UICONTROL Proprietà campo]**.

   2. Abilita **[!UICONTROL Relazione]**.

      1. **[!UICONTROL Schema di riferimento]**: [!DNL Luma Product catalog Schema].

      2. **[!UICONTROL Spazio dei nomi identità di riferimento]**: [!DNL Luma Product].
   3. Seleziona **[!UICONTROL Applica]**.

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
| **[!UICONTROL Relazione]** |  | *[!DNL productListItems.SKU]*:<br> Schema di riferimento *[!DNL Luma Product catalog Schema]* <br>[!DNL Reference identity namespace] *[!DNL Luma Product]* schema |
| **[!UICONTROL Identità principale] [!UICONTROL namespace])** | systemIdentifier.crmId<br>(ID CRM Luma) |  | personalEmail.address<br>(Email) |
| **[!UICONTROL Identità secondaria] [!UICONTROL namespace]** | personalEmail.address (Email)<br>mobilePhone.number (telefono) |  |
| **[!UICONTROL Abilita per profilo]** | sì | sì | sì |

## Passaggi successivi

Dopo aver creato la struttura dati, [creare set di dati e acquisire dati di esempio](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md).
