---
source-git-commit: ab619c80bcc5df95af8e80c664c42e5c281bc648
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---
# Messaggi in-app

## Cosa sono i messaggi in-app?

I messaggi in-app vengono visualizzati all’interno dell’app mobile mentre un utente è attivamente coinvolto. Questi messaggi in stile sovrapposizione vengono visualizzati come banner, pop-up o schede direttamente sull’interfaccia dell’app. Non vengono visualizzati nella schermata di blocco o all’esterno dell’ambiente dell’app.

I messaggi in-app vengono attivati da specifiche azioni o condizioni dell’utente, ad esempio la visualizzazione di una schermata specifica, il completamento di un acquisto o la qualificazione per un segmento di pubblico mirato.


Gli esempi includono:

* Un gioco che mostra un pop-up che introduce una nuova funzione nel momento in cui l&#39;utente lo sblocca.
* Un’app di acquisto che mostra un banner con un codice coupon mentre l’utente esplora i prodotti.
* Un’app social che suggerisce nuovi account da seguire in base all’attività corrente

## Casi d’uso

| **Vantaggi** | **Perché** | **Casi d&#39;uso di esempio** |
|----------------------------------|------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| Coinvolgimento elevato degli utenti | Acquisisce gli utenti mentre sono attivi nell’app, garantendo una visibilità e un’azione migliori | <ul><li>Procedure dettagliate sull’onboarding</li><li>Annunci sulle funzioni</li><li>Popup di supporto in tempo reale</li></ul> |
| Rilevante dal punto di vista contestuale | Consente di attivare i messaggi in base al comportamento dell’utente, rendendoli tempestivi e personalizzati | <ul><li> Vendita in upselling dopo l’utilizzo delle funzioni</li><li> Spigoli di inattività</li><li> Messaggi di errore o di successo</li></ul> |
| Consegna in tempo reale | Consente la comunicazione immediata per gli aggiornamenti critici o sensibili al tempo | <ul><li> Interruzioni del sistema</li><li>Conferme transazioni</li><li>Errori di pagamento</li></ul> |
| Nessuna dipendenza da canali esterni | Mantiene l’esperienza utente contenuta nel prodotto senza ricorrere a e-mail/SMS | <ul><li> Promemoria per il completamento dell’esercitazione</li><li>Avvisi di scadenza della prova</li></ul> |
| Migliore potenziale di conversione | I messaggi inseriti nel contesto vengono convertiti meglio dei messaggi fuori piattaforma | <ul><li> Richieste di aggiornamento dopo aver raggiunto i limiti del piano</li><li>Sondaggi in-app</li></ul> |
| Personalizzazione e segmentazione | Può essere personalizzato in base ai dati utente o agli eventi dell’app | <ul><li> Messaggi personalizzati per livello utente o livello attività</li><li> Avvisi specifici per ruolo </li></ul> |
| Non intrusivo (se ben progettato) | Permette una comunicazione sottile ma efficace senza interrompere il flusso degli utenti | <ul><li> Descrizione</li><li>Slide-in con aggiornamenti</li><li>Spingi widget chat</li></ul> |


## Quando *non* utilizzare la comunicazione in-app

* **L&#39;utente non sta utilizzando attivamente l&#39;app**\
  I messaggi in-app non vengono visualizzati se l’utente non ha attualmente effettuato l’accesso o non interagisce con il prodotto. Al suo posto, utilizza e-mail o push.
* **Problemi critici o sensibili al tempo che richiedono attenzione immediata**\
  Per i messaggi urgenti (ad esempio, avvisi di sicurezza, errori di pagamento), utilizza canali in grado di raggiungere l’utente all’esterno dell’app, come SMS o e-mail.
* **Comunicazioni legali o normative**\
  I messaggi relativi alla conformità (ad es. aggiornamenti dei termini, modifiche delle policy) possono richiedere la consegna e la conferma della lettura, più adatti alle e-mail.
* **Campagne di riattivazione o riconquista dell&#39;account**\
  Se l’utente è inattivo o abbandonato, non vedrà i messaggi in-app. Utilizza le campagne di ricoinvolgimento tramite e-mail o notifiche push.
* **Aggiornamenti transazionali a volume elevato**\
  Notifiche come gli aggiornamenti delle spedizioni o le ricevute vengono spesso inviate meglio tramite e-mail per maggiore comodità e praticità.
* **L&#39;uso eccessivo provoca cecità o fastidio al banner**\
  Il bombardamento degli utenti con troppi messaggi in-app può danneggiare l’esperienza utente e portare a frustrazione o messaggi ignorati.
* **Nessuna connettività/scenario offline**\
  In-app si basa sul fatto che l’utente è online e durante la sessione: non sarà utile in ambienti offline-first.

