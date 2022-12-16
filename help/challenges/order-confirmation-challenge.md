---
title: Creare un messaggio e-mail di conferma dell’ordine
description: Verifica le tue conoscenze su come creare e personalizzare messaggi transazionali
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 4268144ade6588e48fc38cae7e542c227af96827
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 4%

---


# Creare un messaggio e-mail di conferma dell’ordine

![Conferma dell&#39;ordine](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| Sfida | Creare un messaggio e-mail transazionale di conferma dell’ordine |
|---|---|
| Persona | Percorsi Manager |
| Competenze richieste | <ul><li>[Creare contenuti e-mail con l’editor messaggi](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[Utilizzare informazioni contestuali sugli eventi per la personalizzazione](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[Utilizzare funzioni di assistenza per la personalizzazione](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| Risorse da scaricare | [Risorse di conferma dell’ordine](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## La storia

Luma, lancia il loro negozio online e vuole garantire una buona esperienza del cliente fornendo un&#39;e-mail di conferma dell&#39;ordine una volta che un cliente ha effettuato un ordine.



## La tua sfida

Crea un percorso che invia un’e-mail di conferma dell’ordine quando un cliente Luma completa un ordine online. Luma

>[!BEGINTABS]

>[!TAB Attività]

1. Crea un percorso denominato `Luma - Order Confirmation`
2. Utilizza l’evento : `LumaOnlinePurchase` come attivatore
3. Crea l’e-mail di conferma dell’ordine denominata `Luma - Order Confirmation`:

* Transazioni di categoria : assicurati di selezionare l’area dell’e-mail transazionale
* L’oggetto deve essere personalizzato con il nome del destinatario e deve includere la frase &quot;grazie per il tuo acquisto&quot;
* Utilizza la `Luma - Order summary` e modificalo:

L’e-mail deve essere strutturata come segue:
<table>
<tr>
<td>
  <div>
     <strong> Sezione intestazione</strong>
      </div>
  </td>
  <td>
    <strong>Logo Luma</strong>
      <p>
     <li>luma_logo.png</li>
    <li>Dovrebbe avere un collegamento al sito web luma: https://publish1034.adobedemo.com/content/luma/us/en.html</li>
    <p>
    </td>
  </tr>
  <tr>
  <td>
  <div>
    <strong>Sezione Conferma ordine
    </strong>
  </td>
  <td>
    <p>
    <strong>Testo</strong><p>
    <em>Ciao {nome}</em><p>
    <li>Allineamento: sinistra  </li>
   <li>Colore testo: rgb(69, 97, 162) #4461a2; 
   <li>font: 20 px</li>
   <div>
    <p>
     <em>Il tuo ordine è stato effettuato.
    <p>Una volta spedito il tuo pacchetto, ti invieremo un'e-mail con un numero di registrazione in modo da poter tenere traccia del tuo ordine.</p></em>
    </strong>
    </tr>
  </td>
 <td>
  <div>
     <strong> Sezione spedizione</strong>
      </div>
      <p><li>Sostituisci l'indirizzo hardcoded nel modello con l'indirizzo di spedizione 
      <li>I dettagli dell’indirizzo sono attributi contestuali dell’evento (strada, città, codice postale, stato)
      <li>Il nome e il cognome provengono dal profilo
      <li> Rimuovi lo sconto, il totale, l'arrivo</p>
  </td>
  <td>
  <p> Spedisci a:</p>
      <em>Cognome<br>
     Indirizzo</em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>Sezione Dettagli ordine</strong>
      </div>
       <p><li>Aggiungi questa sezione dopo <b>Spedisci a</b> la sezione <b>Visualizza ordine</b> pulsante .
      </p><br>
      <p><b>Suggerimenti:</b>
      <li>Informazioni sull’evento contestuali.
      <li>Utilizzare la funzione helper [!UICONTROL]: [!UICONTROL Ciascuno]
      <li>Passa al formato dell'editor di codice per aggiungere i dati contestuali.
      <li>Inserisci le informazioni nei contenitori utilizzando i tag DIV.
  </td>
  <td>
    <strong>Intestazione</strong>
    <p>
    <em>Ordine: `purchaseOrderNumber`</em>
    </p>
    <strong>Elenco dei prodotti ordinati:
  </strong>
  <p>Ogni elemento deve essere formattato come segue:
   <img alt="ordine" src="./assets/c2-order.png"> 
</p>
<strong>Immagine del prodotto:</strong>
<li>Classe: seggiolone
<li>stile: casella di bordo: min-height:40 px</li>
<li>margine superiore e inferiore:20px</li>
<li>margine sinistro:80px</li>
<li>raggio bordo:0px</li>
<li>Usa come immagine di sfondo per il contenitore</li>
<li>posizione di fondo: 0% 50%</li>
<li>dimensioni sfondo: 60 px</li>
<li>ripetizione in background: no-repeat</li>
<p>
<strong>Prezzo:</strong>
<li>Formato = H5</li>
<li>stile = ridimensionamento casella:bordo-casella</li>
<li>margine inferiore:5 px</li>
<li>margine superiore:0px;</li>
<p>
<strong>Nome e quantità:</strong>
<li>class=text-small</li>
<li>style=box-size: border-box</li>
<li>margine superiore: 5 px</li>
<li>colore: rgb(101, 106, 119)</li>
<li>font-size:14 px</li>
<p>
</td>
  </tr>
</table>


>[!TIP]
>
>Per consentire la risoluzione dei problemi dei percorsi, è consigliabile aggiungere un percorso alternativo a tutte le azioni del messaggio in caso di timeout o errore.

>[!TAB Criteri di successo]

Attiva il Percorso creato in modalità di test e invia l’e-mail a te stesso:

1. Mostrare i valori nascosti facendo clic sul simbolo dell&#39;occhio:
   1. Nei parametri e-mail fai clic sul simbolo T (abilita sostituzione parametro)
      ![Ignorare i parametri e-mail](/help/challenges/assets/c3-override-email-paramters.jpg)
   2. Fare clic nel campo Indirizzo
   3. Nella schermata successiva aggiungi il tuo indirizzo e-mail tra parentesi: *yourname@yourdomain* nell’editor espressioni e fai clic su ok.
2. Mettere il percorso in modalità di prova
3. Attiva l&#39;evento con i seguenti parametri:
   * Imposta l’identificatore del profilo su: Valore identità:`a8f14eab3b483c2b96171b575ecd90b1`
   * Tipo evento: commerce.purchase
   * Nome: Kit Yoga Sprite Companion
   * Quantità: 1
   * `Price Total:` 61
   * `Purchase Order Number:` 6253728
   * `SKU:` 24-WG080
   * `productImageURL:` <https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/luma-yoga-kit-2.jpg>
   * `City:` San Jose
   * `Postal Code:` 95110
   * `State`: CA
   * `Street:` 345 Park Ave

Dovresti ricevere l’e-mail di conferma dell’acquisto personalizzato, con il prodotto specificato.

* L’oggetto deve avere il nome del profilo di test: Leora
* La sezione dettagli ordine deve essere compilata con i dettagli ordine immessi durante il test

>[!TAB Controlla il tuo lavoro]

**Percorso**

![Percorso](/help/challenges/assets/c2-journey.png)


**E-mail**

**Oggetto:**

{{ profile.person.name.firstName }}, grazie per il tuo acquisto!

**Sezione di spedizione:**

Ecco come dovrebbe essere il tuo codice:

```javascript
{{ profile.person.name.firstName }} {{ profile.person.name.lastName }}
{{context.journey.events.454181416.commerce.shipping.address.street1}}
{{context.journey.events.454181416.commerce.shipping.address.city}}, {{context.journey.events.454181416.commerce.shipping.address.state}} {{context.journey.events.454181416.commerce.shipping.address.postalCode}}
```

*event.45481416* Sarà un numero diverso per te.

SUGGERIMENTO: Personalizzare separatamente ogni riga

**Sezione dettagli ordine:**

![Sezione dettagli ordine](/help/challenges/assets/c2-order-detail-section.png)

Ecco come dovrebbe essere il tuo codice:

Header:

```javascript
Order: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**Elenco dei prodotti:**

Utilizzare la funzione helper &quot;each&quot; per creare l&#39;elenco dei prodotti. Visualizzarli in una tabella. Ecco come dovrebbe essere il tuo codice:

```javascript
<div class="text-container" contenteditable="true">
  <p><span class="acr-expression-field" contenteditable="false">{{#each context.journey.events.454181416.productListItems as |product|}}
    </span></p>
  <div class="cart-item-chair" style="box-sizing:border-box;min-height:40px;padding-top:20px;padding-bottom:20px;padding-left:80px;border-radius:0px;background-image:url({{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}});background-position:0% 50%;background-size:60px;background-repeat:no-repeat;">
    <h5 style="box-sizing:border-box;margin-bottom:5px;font-size:16px;line-height:20px;margin-top:0px;">${{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</h5>
    <div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">{{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</div>
    <div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">Quantity: {{product.quantity}}</div>
  </div>
  <div class="divider-small" style="box-sizing:border-box;height:1px;margin-top:10px;margin-bottom:10px;background-color:rgb(209, 213, 223);"> </div>
  {{/each}}<p></p>
  <p></p>
</div>
```

**Totale prezzo:**

Totale:`${{context.journey.events.1627840522.commerce.order.priceTotal}}`

**Sezione Informazioni cliente**

![Indirizzo del cliente](assets/c2-customer-information.png)

La personalizzazione dovrebbe essere simile al seguente:

```javascript
{{profile.homeAddress.street1}}
{{profile.homeAddress.city}},{{profile.homeAddress.state}} {{profile.homeAddress.postalCode}}
```

>[!ENDTABS]