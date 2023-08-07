---
title: Sfida per il riassortimento del prodotto
description: Applica ciò che hai imparato sulla creazione di segmenti e verifica le tue abilità.
jira: KT-8417
feature: Segments
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 5c763ec877c75c07132f4cc714d63695e12638dc
workflow-type: ht
source-wordcount: '580'
ht-degree: 100%

---

# Sfida per il riassortimento del prodotto

| Sfida | Riassortimento del prodotto |
|---|---|
| Persona | Gestione del percorso |
| Competenze richieste | <ul><li>[Creare segmenti](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=it)</li><li> [Importare e creare contenuti e-mail HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=it)</li><li>[Caso d’uso: attività “Leggi segmento”](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=it)</li> |
| Risorse da scaricare | [File e-mail di rifornimento del prodotto](/help/challenges/assets/email-assets/ProductRestockEmail.html.zip) |

## Il contesto

Durante la navigazione nel sito web Luma, i clienti possono aggiungere prodotti di loro interesse a una lista di desideri, che consente a Luma di inviare ai clienti messaggi di marketing mirati e informazioni sui prodotti.

## La tua sfida

Luma chiede di implementare un percorso in Journey Optimizer che avvisa i clienti con un articolo sulla lista dei desideri precedentemente esaurito, quando questo articolo è di nuovo disponibile. Il team creativo fornisce il [file e-mail di rifornimento del prodotto](/help/challenges/assets/email-assets/ProductRestockEmail.html.zip).

>[!BEGINTABS]

>[!TAB Attività]

## 1. Definisci il segmento - Articoli esauriti nella lista dei desideri

Quando i prodotti vengono riassortiti, per eseguire il targeting della clientela potenziale interessata, crea un pubblico costituito da clienti:

* che hanno aggiunto almeno un elemento alla loro lista dei desideri (utilizza tipo di evento: [!UICONTROL Salva per dopo di Commerce])
* elemento che era esaurito negli ultimi tre mesi (utilizza quantità di stock = 0)
* e che non lo hanno ancora acquistato.

>[!TIP]
>Escludi tutti i tipi di evento Acquisti in cui la referenza di magazzino corrisponde a quella dall’*evento Salva per dopo*. Puoi trovare il campo nella sezione *Sfoglia variabili*.

Assegna un nome al segmento: `Out-of-stock-Wishlist`


### 2. Crea il percorso - Notifica di rifornimento prodotto

Quando un articolo precedentemente esaurito è di nuovo disponibile, avvisa i clienti che hanno aggiunto un articolo esaurito con una chiamata per iniziare lo shopping ora che l’articolo è di nuovo disponibile.

1. Chiama il percorso: `Product Restock`
2. Il percorso deve essere attivato quando un prodotto è di nuovo disponiblie
3. Invia *e-mail di rifornimento del prodotto* a
4. utenti che hanno aggiunto questo elemento alla propria lista dei desideri quando era esaurito

>[!TAB Criteri di successo]

Test del percorso:

1. Assicurati che l’evento del segmento letto abbia lo spazio dei nomi = `Luma CRM ID`
1. Sostituisci i parametri e-mail predefiniti e impostali sul tuo indirizzo e-mail (consulta e-mail #1 per le istruzioni)
1. Imposta il percorso in modalità di test
1. Attiva un evento - immetti i dati seguenti:

   * Descrizione: dimenticate i macchinari sofisticati e gli abbonamenti costosi - Harmony Lumaflex Strength Band Kit è tutto ciò che serve per un allenamento incredibile. Il kit presenta tutto il necessario per una serie di esercizi rinforzanti e tonificanti.
   * Nome: Harmony Lumaflex Strength Band Kit
   * Prezzo: 22
   * ID prodotto: 24/UG03
   * URL immagine prodotto: https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jp SKU: 24-UG03
   * Tipo evento magazzino: riassortimento
   * Identificatore profilo: Jenna_Palmer9530@emailsim.io

Dovresti ricevere l’e-mail “Email Luma Riassortimento prodotto” con i dettagli del prodotto e la personalizzazione per Jenna.

>[!TAB Verifica il tuo lavoro]

Ecco come dovrebbe apparire il tuo segmento:

![Segmento - Articoli esauriti sulla lista dei desideri](/help/challenges/assets/C1-S2.png)


Ecco come dovrebbe apparire il tuo percorso:

![Percorso di riassortimento del prodotto](/help/challenges/assets/c3-j3-journey.png)

Condizione: nella lista dei desideri

![Condizione - nella lista dei desideri](/help/challenges/assets/c3-j3-condition.png)

Codice condizione:

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```


>[!TIP]
> * Seleziona lo SKU in Salva per dopo nella sezione *Sfoglia variabili*
> * Utilizza l’opzione di confronto quando rilasci lo SKU in Salva per dopo nel campo evento

Sotto Eventi, verifica il codice nell’angolo in basso a destra della schermata Modifica segmento. Il codice deve essere simile al seguente:

Codice:
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

>[!ENDTABS]

### Crea e-mail - Riassortimento prodotto Luma

Comunica ai clienti che hanno aggiunto un articolo esaurito con una chiamata per iniziare lo shopping ora che l’articolo è di nuovo disponibile.



>[!TIP]
>
> Utilizza l’evento di business esistente. È necessario aggiungere una condizione per verificare che la referenza di magazzino di riassortimento sia inclusa in qualsiasi tipo di evento Salva per dopo.
>




