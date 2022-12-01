---
title: Sfida di rifornimento del prodotto
description: Applica ciò che hai imparato sulla creazione di segmenti e verifica le tue abilità.
kt: 8417
feature: Segments
role: User
level: Beginner
hide: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 0e83d8fbad6bd87ed25980251970898cb5b94bc0
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 2%

---

# Sfida di rifornimento del prodotto

| Sfida | Rifornimento del prodotto |
|---|---|
| Persona | Percorsi Manager |
| Competenze richieste | <ul><li>[Creare segmenti](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-segments.html?lang=en)</li><li> [Importare e creare contenuti e-mail HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/import-and-author-html-email-content.html?lang=en)</li><li>[Caso d’uso: attività “Leggi segmento”](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Risorse da scaricare | [File e-mail di Raccolta stagionale](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## La storia

Durante la navigazione nel sito web Luma, i clienti possono aggiungere prodotti di loro interesse a una lista di desideri. che consente a Luma di inviare ai clienti messaggi di marketing mirati e informazioni sui prodotti.

## La tua sfida

Luma ti chiede di implementare un percorso in Journey Optimizer che avvisa i clienti che hanno un articolo sulla loro lista dei desideri che era precedentemente esaurito, quando questo articolo è di nuovo in magazzino.

## Definire il segmento - Articoli della lista dei desideri esauriti

Per eseguire il targeting dei potenziali clienti interessati quando i prodotti vengono riconcentrati, crea un segmento composto da clienti

* Chi ha aggiunto almeno un elemento al proprio elenco di desideri (Usa tipo di evento: [!UICONTROL Salvataggio Di Commerce Per I Latenti])
* Che era **esaurito** negli ultimi tre mesi (utilizzare la quantità delle scorte = 0)
* E non hanno da allora acquistato l&#39;articolo.

Assegna un nome al segmento: *il tuo nome - Out-of-stock-Wishlist*

+++**CONTROLLA IL TUO LAVORO**

Questo è l’aspetto del segmento:

![Segmento - Articoli della lista dei desideri esauriti](/help/challenges/assets/C1-S2.png)

Clienti che hanno aggiunto una voce alla lista dei desideri che non era disponibile negli ultimi 3 mesi:

* Evento: Salva per i moduli più recenti
   * Includi almeno 1
   * Se la quantità delle scorte è 0

e da allora non hanno acquistato l&#39;articolo:

* Escludere tutti i tipi di evento Purchases in cui la SKU corrisponde alla SKU dalla **Salva per evento successivo**.

>[!TIP]
> * Seleziona lo SKU sotto Salva per Laters nel *Sfoglia variabili* sezione
> * Utilizza l’opzione di confronto quando rilascia lo SKU in Save for later nel campo event


Controlla il codice nell&#39;angolo in basso a destra della schermata Modifica segmento, in Eventi. Il codice deve essere simile al seguente:

Codice:
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

+++

### Crea e-mail - Rifornimento prodotto Luma

Comunica ai clienti che hanno aggiunto un articolo non disponibile con una chiamata per iniziare lo shopping ora che l’articolo è di nuovo in magazzino.

### Creare il percorso - Notifica di ripristino del prodotto

Quando un articolo precedentemente esaurito è di nuovo in magazzino, avvisa i clienti che hanno aggiunto un articolo non disponibile con una chiamata per iniziare lo shopping ora che l&#39;articolo è di nuovo in magazzino.

1. Crea un percorso chiamato &quot;your name_Luma - Product Restock&quot;
1. Il percorso deve essere attivato quando un prodotto è tornato in magazzino
1. Invia *Rifornimento prodotto Luma* invia a
1. Utenti che hanno aggiunto questo elemento alla propria lista dei desideri mentre era esaurito

>[!TIP]
>
> Utilizza l&#39;evento aziendale esistente. È necessario aggiungere una condizione che controlli che la SKU di ripristino sia inclusa nel salvataggio del tipo di evento (qualsiasi) per i secondi.

+++**CRITERI DI SUCCESSO**

Test del percorso:

1. Assicurati che l&#39;evento di qualificazione del segmento abbia Namespace = Email
1. Ignora i parametri e-mail predefiniti e impostali sul tuo indirizzo e-mail (vedi e-mail n. 1 per le istruzioni)
1. Impostare il percorso sulla modalità di prova
1. Attiva un evento - immetti i dati seguenti:

   * Descrizione: Dimenticate macchine fantasia e appartenenze costose - l&#39;Harmony Lumaflex Resistenza Kit è tutto ciò che serve per un allenamento incredibile. Il kit ha tutto il necessario per una serie di esercizi di rinforzo e tonificazione.
   * Nome: Armonia Lumaflex Band Kit
   * Prezzo: 22
   * ID prodotto: 24/UG03
   * URL immagine prodotto: https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jpSKU 24/UG03
   * Tipo evento stock: ribaltamento
   * Identificatore profilo: Jenna_Palmer9530@emailsim.io

Dovresti ricevere l’e-mail &quot;Luma Email Product Replenitution&quot; con i dettagli del prodotto e la personalizzazione per Jenna.

+++

+++**CONTROLLA IL TUO LAVORO**

Ecco come dovrebbe essere il tuo percorso:

![Percorso di rifornimento del prodotto](/help/challenges/assets/c3-j3-journey.png)

Condizione: Nella lista dei desideri

![Condizione - in wishlist](/help/challenges/assets/c3-j3-condition.png)

Codice condizione:

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```

+++
