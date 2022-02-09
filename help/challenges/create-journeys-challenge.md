---
title: Creare Percorsi - Sfida
description: Scopri le basi della costruzione di un percorso nell’area di lavoro del percorso.
kt: 8109
feature: Journeys
role: User
level: Beginner
source-git-commit: e75564c24f79eaecc1384fde978cc81cb2b9bdaf
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 1%

---


# Creare Percorsi - Sfida

## La storia

Luma, un&#39;azienda fittizia di abbigliamento atletico, sta cercando di promuovere la sua ultima collezione di abbigliamento e abbigliamento e di stimolare le vendite per i clienti esistenti. Il team di marketing Luma ti chiede di implementare una campagna di marketing per la raccolta estiva e casi d’uso aggiuntivi per migliorare la customer experience e aumentare la fidelizzazione.

La sfida consiste nel creare percorsi per implementare i seguenti casi d’uso:

1. Per promuovere la nuova raccolta estiva Luma, invia un annuncio di raccolta estiva a un segmento di clienti esistenti e-mail
2. Invia un&#39;e-mail di conferma dell&#39;ordine quando qualcuno completa un acquisto online
3. Invia un&#39;e-mail quando un cliente fidelizzato si sposta su un nuovo livello per congratularsi e informarlo dei suoi nuovi vantaggi
4. Quando un articolo precedentemente esaurito è di nuovo in magazzino, avvisa i clienti che avevano favorito l&#39;articolo esaurito con una chiamata per iniziare lo shopping ora che l&#39;articolo è di nuovo in magazzino

## LA TUA SFIDA

Crea i seguenti percorsi in Journey Optimizer:

### **Percorso #1 - Annuncio sulla collezione estiva**

Per promuovere la nuova raccolta estiva Luma, invia un annuncio di raccolta estiva a un segmento di e-mail dei clienti esistenti.

1. Invia un messaggio e-mail &quot;Luma - Nuovo annuncio di raccolta stagionale&quot; al segmento del cliente attivo, con il 10% del pubblico come gruppo di controllo.
2. Se un destinatario apre la *Luma - Annuncio della nuova collezione stagionale* invia un’e-mail entro due giorni, un messaggio e-mail successivo con contenuto più mirato:
   * I clienti maschi devono ricevere *Collezione Luma - maschile* email
   * Le donne devono ricevere *Collezione Luma - Donna* email
   * Gli altri clienti devono ricevere *Luma - 20% di sconto sulla raccolta* email
3. Dopo aver inviato le e-mail di destinazione di cui sopra, attendi un’ora, quindi ascolta l’e-mail da aprire.
4. Se l’e-mail di destinazione non viene aperta entro 2 giorni, invia *Luma - 20% di sconto sulle vendite* e-mail come tentativo finale di retargeting.
5. Una volta completato, metti il percorso in modalità di test e attiva il percorso da inviare a te stesso.

CRITERI DI SUCCESSO

Dovresti ricevere le seguenti e-mail:

* *Luma - Annuncio della nuova collezione stagionale*
* Se apri la prima e-mail di raccolta email: The Luma per uomini o donne se hai aggiunto il genere, se non l’e-mail di raccolta Luma 20% off
* Se non hai aperto la seconda e-mail: La *Luma - 20% di sconto sulle vendite* email

### **Percorso 2 - E-mail di conferma dell’ordine sulle transazioni**

Invia un&#39;e-mail di conferma dell&#39;ordine quando qualcuno completa un acquisto online.

>[!INFO]
>
>Se hai completato la [Creare e personalizzare la sfida dei messaggi](/help/challenges/create-and-personalize-emails-challenge.md), puoi saltare questo percorso e passare al Percorso 3.

1. Crea un percorso che viene attivato quando un cliente completa un acquisto web sul sito Luma per inviare l’e-mail &quot;Luma - Sito web - Conferma ordine&quot;.
2. Mappare informazioni contestuali dal *LumaOnlinePurchase* evento per personalizzare l’e-mail. Per personalizzare con le informazioni contestuali, devi duplicare la *Luma - Sito web - Conferma ordine* invia un&#39;e-mail con il tuo nome e usalo nel percorso.
3. Una volta completato, metti il percorso in modalità di test e attiva il percorso da inviare a te stesso. È possibile utilizzare &quot;LLWH06&quot; per la SKU del prodotto (Stock Keeping Unit) quando si attiva l’evento di test, oppure sfogliare i prodotti sul [Sito web Luma](https://publish1034.adobedemo.com/content/luma/us/en.html) per scegliere un prodotto diverso. Lo SKU si trova in ogni pagina del prodotto, ma lascia fuori il suffisso che indica colore/dimensione, ad esempio &quot;.1-XS&quot;

CRITERI DI SUCCESSO

Dovresti ricevere l’e-mail di conferma dell’acquisto personalizzato, con il prodotto specificato.

### **Percorso #3 - Diamond status upgrade email di benvenuto**

Invia un&#39;e-mail quando un cliente fidelizzato si sposta su un nuovo livello per congratularsi e informarlo dei suoi nuovi vantaggi.

1. Crea un percorso attivato quando un cliente si sposta nel nuovo livello di fedeltà Diamond (in particolare quando il cliente entra nel segmento definito per un nuovo membro a livello di rombo) per inviare l’e-mail &quot;Luma - Nuovo stato - Diamond - Transazionale&quot;
2. Una volta completato, mettere il percorso in modalità di test e attivare il percorso da inviare a se stessi  

CRITERI DI SUCCESSO

Dovresti ricevere l’e-mail personalizzata &quot;Luma - New Status- Diamond-Transacional&quot;.

### **Percorso #4 - E-mail di ripristino del prodotto**

Quando un articolo non disponibile in precedenza è di nuovo in magazzino, avvisa i clienti che avevano favorito l&#39;articolo non disponibile con una chiamata per iniziare lo shopping ora che l&#39;articolo è di nuovo in magazzino.

1. Crea un percorso che viene attivato quando il prodotto ABC123 è di nuovo in magazzino. Dovrebbe essere un&#39;e-mail (*Rifornimento del prodotto e-mail Luma*) per informare gli utenti che avevano privilegiato il prodotto in esaurimento. L&#39;e-mail ha un invito all&#39;azione per iniziare lo shopping.

   * Nel percorso, controlla se l’elemento riconcentrato si trova nell’elenco dei desideri del cliente prima di inviare l’e-mail.
   * Mappare informazioni contestuali dal *LumaProductRestock* evento per personalizzare l’e-mail

2. Per generare un evento elenco desideri per te, esegui la *Onboarding per studenti* Percorso . Utilizza *LLWH06* come SKU o altra SKU di scelta trovata sul [Sito web Luma](https://publish1034.adobedemo.com/content/luma/us/en.html).

3. Una volta completato, metti il percorso in modalità di test e attiva il percorso da inviare a te stesso. Assicurati di utilizzare lo stesso SKU nell&#39;evento di test utilizzato quando attivi l&#39;evento elenco desideri nel percorso &quot;Onboarding - Wishlist Event&quot;

CRITERI DI SUCCESSO

Dovresti ricevere il messaggio e-mail di ripristino del prodotto con il prodotto specificato nell&#39;evento elenco desideri e l&#39;evento di ripristino del test.

>[!INFO]
>
>[Controlla il tuo lavoro](/help/challenges/check-your-work/create-journeys.md) per vedere come dovrebbero essere i percorsi.
