---
title: Creare e personalizzare i messaggi
description: Verifica le tue conoscenze su come creare e personalizzare le e-mail.
kt: 7531
feature: Journeys
role: User
level: Beginner
source-git-commit: 676f0b268f7f67d179bfa944b72cb68191640c74
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 0%

---


# Creare e personalizzare i messaggi

## La storia

Luma, un&#39;azienda fittizia di abbigliamento atletico, sta cercando di promuovere la sua ultima collezione di abbigliamento e abbigliamento e di stimolare le vendite per i clienti esistenti. Per supportare la campagna Nuova raccolta , il team di marketing Luma ti chiede di creare due messaggi e-mail che vengono inviati ai clienti come parte della campagna.

## La tua sfida

Crea le seguenti e-mail in Journey Optimizer

### Messaggio e-mail n. 1 - Annuncio della raccolta estiva

Crea un&#39;e-mail per annunciare l&#39;arrivo della nuova collezione Summer. Hai ricevuto un file HTML da un’agenzia con la progettazione per il corpo dell’e-mail: [StagionaleCollectionEmail.html](/help/challenges/assets/SeasonalCollectionEmail.html)

1. Creare un messaggio e-mail denominato *(Il tuo nome)_Luma - Nuova Collezione stagionale*
2. Assegna all’e-mail un oggetto: *(nome del destinatario), la nuova raccolta Luma è disponibile qui!*
3. Utilizza il file HTML fornito per il corpo dell’e-mail  

CRITERI DI SUCCESSO

Visualizza l’anteprima del messaggio e-mail utilizzando il profilo di test e invia una bozza a te stesso.

* L’oggetto deve contenere il proprio nome
* Il corpo dell’e-mail deve corrispondere a quello visualizzato nell’anteprima.

### Messaggio e-mail n. 2 - E-mail di conferma dell’ordine transazionale

Crea un’e-mail di conferma dell’ordine da inviare quando un cliente Luma completa un ordine online.  

1. Crea un messaggio e-mail intitolato &quot;(nome utente)_ Luma - Conferma ordine&quot;
2. L’oggetto deve essere personalizzato con il nome del destinatario e deve includere la frase &quot;grazie per il tuo acquisto&quot;
3. In conformità alla guida al marchio Luma, l’e-mail deve essere strutturata come segue:
   * Header:
      * Logo Luma (Luma_Logo.png)
      * Dimensioni 35%, sfondo bianco centrato  
      * Dovrebbe avere un collegamento al sito web luma: ```https://publish1034.adobedemo.com/content/luma/us/en.html``` 
   * Sezione 1 del corpo:  
      * Immagine:  
         * Luma - Transazionale - Conferma ordine 2.jpg
         * Margine: Superiore, inferiore (10)
      * Testo:
         * Intestazione: &quot;Grazie per il tuo acquisto!&quot;
         * Corpo: &quot;Il tuo ordine è stato posto. Una volta spedito il tuo pacchetto, ti invieremo un&#39;e-mail con un numero di registrazione in modo da poter tenere traccia del tuo ordine.&quot;
         * Allineamento: sinistra  
         * Spaziatura: sinistra(95), destra (95)
      * Un pulsante: &quot;Visualizza ordine&quot;
         * Colore di sfondo: rgb (25, 121, 195)
         * Colore testo: rgb (101, 106, 119); font: 14 px
         * Nessun bordo 
         * Altezza: 40 
         * Aggiungere un collegamento a un sito web desiderato  
         * Allinea a sinistra con il testo precedente (suggerimento: utilizzare il margine del contenitore)
      * Linea divisoria:
         * Colore linea:  #d3d3d3 rgb (211, 211, 211)
      * Testo:
         * *Siamo qui per aiutarvi. Se hai domande o hai bisogno di aiuto, fatecelo sapere.*
         * *Fateci sapere* dovrebbe essere presente un collegamento al supporto email: support.luma@emailcim.io  
   * Sezione 2: dettagli dell’ordine con le seguenti informazioni contestuali
      * Intestazione: numero ordine di acquisto
      * Elenco dei prodotti ordinati
      * Totale del prezzo del prodotto
      * Nome del prodotto
      * Quantità di prodotto
      * Prezzo totale dell&#39;ordine
   * Sezione 3: Informazioni sui clienti
      * Informazioni sui clienti di intestazione
      * Spedizione (nome, cognome, via1, città) e indirizzi di fatturazione (nome, cognome, via1, città), che devono essere elencati uno accanto all’altro (suggerimento: aggiungere due colonne per questa sezione). Deve compilare i dati dal profilo cliente.  
   * Piè di pagina
      * Collegamenti social media a Facebook e LinkedIn
      * Collegamento per annullare l’abbonamento
      * Colore testo:  #afaf rgb (175, 175, 175)

>[!IMPORTANT]
>
>La sezione dei dettagli dell’ordine contiene informazioni sull’evento contestuali. È possibile aggiungere le informazioni contestuali solo dopo l’aggiunta del messaggio a un flusso di lavoro. Non pubblicare l’e-mail prima di aggiungerla al flusso di lavoro e modificarla con le informazioni sull’evento contestuale! Utilizzare anche la funzione helper.

1. Crea un percorso che viene attivato quando un cliente completa un acquisto online sul sito web Luma per inviare il *(il tuo nome)_ Luma - Sito web - Conferma ordine* email

   * Chiama il percorso &quot;il tuo nome _Luma-Order Confirmation&quot;
   * Utilizza l’evento: LumaOnlinePurchase  

CRITERI DI SUCCESSO

1. Visualizza l’anteprima del messaggio utilizzando il profilo di test creato. La personalizzazione deve riflettere i dati nel profilo di test:  
   * L’oggetto deve iniziare con il nome del profilo di test 
   * Le informazioni sul cliente devono contenere il nome e il cognome del profilo di test e la città. Se non hai aggiunto l’indirizzo della strada, questo verrà visualizzato se il campo non viene lasciato vuoto. 
2. Pubblica l’e-mail e inviala a te stesso eseguendo il percorso creato in modalità di test: 
   * Seleziona il tipo di evento &quot;commerce.purchased&quot; 
   * Utilizzare &quot;LLWH06&quot; per la SKU del prodotto quando si attiva l’evento di test in modalità di test.  
   * Aggiungi eventuali informazioni aggiuntive  
   * URL immagine: https://publish1034.adobedemo.com/content/dam/luma/en/products/women/tops/hoodies-&amp;-sweatshirts/wh06-purple_main.jpg 
   * Dovresti ricevere l’e-mail e tutti i campi di personalizzazione devono essere compilati correttamente.

PRONTO A FINIRE?

[Controlla il tuo lavoro](/help/challenges/check-your-work/create-and-personalize-emails.md) per vedere come dovrebbero essere le e-mail create.
