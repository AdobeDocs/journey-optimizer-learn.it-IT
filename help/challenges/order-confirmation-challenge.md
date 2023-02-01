---
title: Crea un messaggio e-mail di conferma dell’ordine
description: Verifica le tue conoscenze su come creare e personalizzare messaggi transazionali
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 70815c3cd30de22aad7ec667b8baf9b4c8642491
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 82%

---


# Crea un messaggio e-mail di conferma dell’ordine

![Conferma dell’ordine](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| Sfida | Crea un messaggio e-mail transazionale di conferma dell’ordine |
|---|---|
| Persona | Gestione del percorso |
| Competenze richieste | <ul><li>[Creare contenuti e-mail con l’editor messaggi](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=it)</li> <li>[Utilizzare informazioni contestuali sugli eventi per la personalizzazione](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=it)</li><li>[Utilizzare funzioni di assistenza per la personalizzazione](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=it)</li></ul> |
| Risorse da scaricare | [Risorse di conferma dell’ordine](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## Il contesto

Luma, lancia il proprio negozio online e vuole garantire un’ottima esperienza cliente fornendo un’e-mail di conferma dell’ordine una volta che un cliente ha effettuato un ordine.



## La tua sfida

Crea un percorso che invia un’e-mail di conferma dell’ordine quando un cliente Luma completa un ordine online.

>[!BEGINTABS]

>[!TAB Attività]

1. Crea un percorso denominato `Luma - Order Confirmation`
2. Utilizza l’evento : `LumaOnlinePurchase`
3. Crea l’e-mail di conferma dell’ordine denominata `Luma - Order Confirmation`:

* Transazioni di categoria: assicurati di selezionare l’area dell’e-mail transazionale
* L’oggetto deve essere personalizzato con il nome del destinatario e deve includere la frase “grazie per il tuo acquisto”
* Utilizza il modello `Luma - Order summary` e modificalo:
   * Rimuovi `You may also like` sezioni
   * Aggiungi il collegamento per annullare l’abbonamento nella parte inferiore dell’e-mail

L’e-mail deve essere strutturata nel modo seguente:
<table>
<tr>
<td>
  <div>
     <strong>Sezione intestazione</strong>
      </div>
  </td>
  <td>
      <p>
     <li>luma_logo.png</li>
    <li>Deve avere un collegamento al sito web luma: https://publish1034.adobedemo.com/content/luma/us/en.html</li>
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
    <em>Ciao {firstName}</em><p>
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
      <li>Sostituisci l’indirizzo hardcoded nel modello con il <b>indirizzo di spedizione</b>
      <li>I dettagli dell’indirizzo sono attributi contestuali dell’evento (strada 1, città, codice postale, stato)
      <li> Rimuovi lo sconto, il totale, l’arrivo</p>
  </td>
  <td>
  <p> Spedisci a:</p>
      <em>{firstName} {lastName}<br>
     {Via 1}<br>
     {City}, {State} {postalCode}<br></em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>Sezione Dettagli ordine</strong>
      </div>
       <p><li>Aggiungi questa sezione sotto la <b>Spedisci a</b> sezione .
      </p><br>
      <p><b>Suggerimenti:</b>
      <li>Usa il componente struttura `1:2 column left` per questa sezione
      <li>Si tratta di informazioni contestuali sull’evento.
      <li>Utilizza la [!UICONTROL helper function]: [!UICONTROL Each]
      <li>Passa al formato dell’editor di codice per aggiungere i dati contestuali.
  </td>
  <td>
    <strong>Intestazione</strong>
    <p>
    <em>Ordine: `purchaseOrderNumber`</em>
    </p>
    <strong>Elenco dei prodotti che sono stati ordinati:
 </strong>
  <p>Ogni elemento deve essere formattato come segue:
 <img alt="ordine" src="./assets/c2-order.png"> 
</p>
</td>
  </tr>
</table>


>[!TIP]
>
>Per consentire la risoluzione dei problemi dei percorsi, è consigliabile aggiungere un percorso alternativo a tutte le azioni del messaggio in caso di timeout o errore.

>[!TAB Criteri di successo]

Attiva il Percorso creato in modalità di test e invia l’e-mail a te stesso:

1. Mostra i valori nascosti facendo clic sul simbolo a forma di occhio:
   1. Nei parametri e-mail fai clic sul simbolo T (abilita sostituzione parametro)
      ![Sostituire i parametri e-mail](/help/challenges/assets/c3-override-email-paramters.jpg)
   2. Fai clic sul campo Indirizzo
   3. Nella schermata successiva aggiungi il tuo indirizzo e-mail tra parentesi: *yourname@yourdomain* nell’editor di espressioni e fai clic su ok.
2. Metti il percorso in modalità di test
3. Attiva l’evento con i seguenti parametri:
   * Imposta l’identificatore del profilo su: Valore identità:`a8f14eab3b483c2b96171b575ecd90b1`
   * Tipo evento: commerce.purchases
   * `Quantity`: 1
   * `Price Total:` 69
   * `Purchase Order Number:` 6253728
   * `SKU:` LLMH09
   * `City:` Washington
   * `Postal Code:` 20099
   * `State`: DC
   * `Street:` Terrazza Thierer

Dovresti ricevere l’e-mail di conferma dell’acquisto personalizzato con il prodotto specificato.

* L’oggetto deve avere il nome del profilo di test: Leora
* La sezione dettagli ordine deve essere compilata con i dettagli ordine immessi durante il test

>[!TAB Verifica il tuo lavoro]

**Percorso**

![Percorso](/help/challenges/assets/c2-journey.png)


**E-mail**

**Oggetto:**

Grazie per il tuo acquisto, {{ profile.person.name.firstName }}!

Questo è l’aspetto del corpo dell’e-mail:

![E-mail](//help/challenges/assets/c2-email.png)

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

Utilizza la funzione “ciascuno” per creare l’elenco dei prodotti. Visualizzale in una tabella. Questo è l&#39;aspetto del codice (con le variabili specifiche come l&#39;ID evento - invece di `454181416` e la tua organizzazione I anziché `techmarketingdemos` ):

```javascript
{{#each context.journey.events.454181416.productListItems as |product|}}<tr> <th class="colspan33"><div class="acr-fragment acr-component image-container" data-component-id="image" style="width:100%;text-align:center;" contenteditable="false"><!--[if mso]><table cellpadding="0" cellspacing="0" border="0" width="100%"><tr><td style="text-align: center;" ><![endif]--><img src="{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}}" style="height:auto;width:100%;" height="233" width="233"><!--[if mso]></td></tr></table><![endif]--></div></th> <th class="colspan66"><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p><span style="font-weight:700;">{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</span></p></div></div><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p>${{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</p><p>Quantity: {{context.journey.events.454181416.productListItems.quantity}}</p></div></div></th></tr> {{/each}}
```

**Totale prezzo:**

Totale:`${{context.journey.events.1627840522.commerce.order.priceTotal}}.00`


>[!ENDTABS]