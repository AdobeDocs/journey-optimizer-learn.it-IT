---
title: Crea un messaggio e-mail di conferma dell’ordine
description: Verifica le tue conoscenze su come creare e personalizzare messaggi transazionali.
kt: 7531
feature: Journeys
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: f7bfe367411f2bae23631ac4ecb34ad1d250381c
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---


# Crea un messaggio e-mail di conferma dell’ordine

![Conferma dell’ordine](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| Sfida | Crea un messaggio e-mail transazionale di conferma dell’ordine |
|---|---|
| Persona | Gestione del percorso |
| Competenze richieste | <ul><li>[Creare contenuti e-mail con l’editor messaggi](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/create-content-with-the-email-designer.html?lang=it)</li> <li>[Utilizzare informazioni contestuali sugli eventi per la personalizzazione](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=it)</li><li>[Utilizzare funzioni di assistenza per la personalizzazione](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=it)</li></ul> |
| Risorse da scaricare | [Risorse di conferma dell’ordine](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

{style="table-layout:auto"}

## Il contesto

Luma sta lanciando il suo negozio online e vuole garantire un&#39;ottima esperienza del cliente. Una volta che un cliente ha effettuato un ordine, gli viene inviata un’e-mail di conferma.

## La tua sfida

Crea un percorso che invia un’e-mail di conferma dell’ordine quando un cliente Luma completa un ordine online.

>[!BEGINTABS]

>[!TAB Attività]

1. Crea un percorso denominato `Luma - Order Confirmation`.

1. Utilizza l’evento: `LumaOnlinePurchase`.

1. Crea un’e-mail **transazionale** denominata `Luma - Order Confirmation`.

   * L’oggetto “Grazie per il tuo acquisto, `FirstName`”

   * Utilizza il modello `Luma - Order summary` e modificalo:

      * Rimuovi le sezioni `You may also like`

      * Aggiungi il collegamento per annullare l’abbonamento nella parte inferiore dell’e-mail

L’e-mail deve essere strutturata nel modo seguente:
<table>
<tr>
<td>
  <div>
     <strong>Sezione Intestazione</strong>
      </div>
  </td>
  <td>
      <p>
     <li>luma_logo.png</li>
    <li>Deve avere un collegamento al sito web luma: https://luma.enablementadobe.com/content/luma/us/en.html</li>
    <p>
    </td>
  </tr>
  <tr>
  <td>
  <div>
    <strong>Sezione Conferma dell’ordine
 </strong>
  </td>
  <td>
    <p>
    <strong>Testo</strong><p>
    <em>Ciao {firstName},</em><p>
   <div>
    <p>
     <em>Il tuo ordine è stato effettuato.
    <p>Una volta spedito il tuo pacchetto, ti invieremo un’e-mail con un numero di tracciamento in modo da poter tenere traccia del tuo ordine.</p></em>
    </strong>
    </tr>
  </td>
 <td>
  <div>
     <strong>Sezione spedizione</strong>
      </div>
      <p>
      <li>Il nome e il cognome provengono dal profilo
      <li>Sostituisci l’indirizzo codificato nel modello con <b>l’indirizzo di spedizione</b>
      <li>I dettagli dell’indirizzo sono attributi contestuali dell’evento (via 1, città, codice postale, stato)
      <li> Rimuovi <i>sconto, totale, arrivo</i></p>
  </td>
  <td>
  <p> Spedisci a:</p>
      <em>{firstName} {lastName}<br>
     {Street 1}<br>
     {City}, {State} {postalCode}<br></em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>Sezione Dettagli ordine</strong>
      </div>
       <p><li>Aggiungi questa sezione sotto la sezione <b>Spedisci a</b>.
      </p><br>
      <p><b>Suggerimenti:</b>
      <li>Utilizza il componente della struttura <b>Colonna 1:2 a sinistra</b> per questa sezione
      <li>Si tratta di informazioni contestuali sull’evento.
      <li>Utilizza la [!UICONTROL helper function]: [!UICONTROL Each]
      <li>Passa al formato dell’editor di codice per aggiungere i dati contestuali.
  </td>
  <td>
    <strong>Intestazione</strong>
    <p>
  Ordine: <em>{purchaseOrderNumber}</em>
    </p>
    <strong>Elenco dei prodotti che sono stati ordinati:
 </strong>
  <p>Elenca ogni prodotto nell’ordine con un’immagine, il prezzo e il nome.
  <p>Il layout di ciascun elemento deve essere simile al seguente:
   <img alt="ordine" src="./assets/c2-order.png"> 
<p><b>Aggiungi il collegamento al carrello</b>
<p>Sostituisci l’ID ordine nell’URL con il numero dell’ordine di acquisto:
   <i>https://luma.enablementadobe.com/content/luma/us/en/user/account/order-history/order-details.html?orderId=90845952-c2ea-4872-8466-5289183e4607</i>
</td>
  </tr>
</table>

>[!TIP]
>
>Per consentire la risoluzione dei problemi dei percorsi, è consigliabile aggiungere un percorso alternativo a tutte le azioni del messaggio in caso di timeout o errore.

>[!TAB Criteri di successo]

Attiva il percorso creato in modalità di test e invia l’e-mail a te stesso:

1. Prima di passare alla modalità di prova, sovrascrivi i parametri e-mail da inviare all’e-mail di prova al tuo indirizzo e-mail:
   1. Apri la visualizzazione dei dettagli dell’e-mail.
   1. Nella sezione dei parametri e-mail fai clic sul simbolo T (abilita sostituzione parametro)
   1. Fai clic sul campo Indirizzo
   1. Nella schermata successiva aggiungi il tuo indirizzo e-mail tra parentesi: *“yourname@yourdomain”* nell’editor di espressioni e fai clic su ok.
1. Metti il percorso in modalità di test
1. Attiva l’evento con i seguenti parametri:
   * Imposta l’identificatore del profilo su: Valore identità:`a8f14eab3b483c2b96171b575ecd90b1`
   * Tipo evento: commerce.purchases
   * `Quantity`: 1
   * `Price Total:` 69
   * `Purchase Order Number:` 90845952-c2ea-4872-8466-5289183e4607
   * `SKU:` LLMH09
   * `City:`San Jose
   * `Postal Code:` 95119
   * `State`: CA
   * `Street:` 245 Park Avenue

Dovresti ricevere l’e-mail di conferma dell’acquisto personalizzata.

* L’oggetto deve avere il nome del profilo di test: Leora

* Il corpo della tua e-mail dovrebbe essere così:

![E-mail](/help/challenges/assets/c2-email.png)

>[!TAB Verifica il tuo lavoro]

**Percorso**

![Percorso](/help/challenges/assets/c2-journey.png)


**E-mail**

**Oggetto:**

Grazie per l’acquisto, {{ profile.person.name.firstName }}!

**Sezione spedizione:**

Ecco come dovrebbe apparire il tuo codice:

```javascript
{{ profile.person.name.firstName }} {{ profile.person.name.lastName }}
{{context.journey.events.454181416.commerce.shipping.address.street1}}
{{context.journey.events.454181416.commerce.shipping.address.city}}, {{context.journey.events.454181416.commerce.shipping.address.state}} {{context.journey.events.454181416.commerce.shipping.address.postalCode}}
```

*event.45481416* sarà un numero diverso per te.

SUGGERIMENTO: personalizza separatamente ogni riga

**Sezione dettagli ordine:**

Ecco come dovrebbe apparire il tuo codice:

Intestazione:

```javascript
Order #: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**Elenco dei prodotti:**

Utilizza la funzione “ciascuno” per creare l’elenco dei prodotti. Visualizzale in una tabella. Il codice dovrebbe essere così (con le variabili specifiche come l’ID evento - invece di `454181416` e la tua organizzazione I anziché `techmarketingdemos` ):

```javascript
{{#each context.journey.events.454181416.productListItems as |product|}}<tr> <th class="colspan33"><div class="acr-fragment acr-component image-container" data-component-id="image" style="width:100%;text-align:center;" contenteditable="false"><!--[if mso]><table cellpadding="0" cellspacing="0" border="0" width="100%"><tr><td style="text-align: center;" ><![endif]--><img src="{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}}" style="height:auto;width:100%;" height="233" width="233"><!--[if mso]></td></tr></table><![endif]--></div></th> <th class="colspan66"><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p><span style="font-weight:700;">{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</span></p></div></div><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p>${{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</p></div></div></th></tr> {{/each}}
```

**Pulsante Visualizza ordine:**

`https://luma.enablementadobe.com/content/luma/us/en/user/account/order-history/order-details.html?orderId={{context.journey.events.454181416.commerce.order.purchaseOrderNumber}}`

**Totale prezzo:**

Totale:`${{context.journey.events.1627840522.commerce.order.priceTotal}}.00`


>[!ENDTABS]