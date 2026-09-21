---
source-git-commit: fc279f2ff41f624e4a6a0c4c930cedfcc2745dc5
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 3%
---
# Attività live

## Che cos’è

**Attività live** ti consentono di distribuire aggiornamenti in tempo reale e costanti che informano i clienti man mano che un&#39;attività progredisce, ad esempio un ordine in fase di preparazione, una consegna in transito o una corsa. Invece di inviare una nuova notifica per ogni aggiornamento, viene creata una singola attività live, quindi aggiornata e terminata in base all’evoluzione dell’attività, mantenendo la schermata di blocco o l’ombra di notifica del cliente sincronizzata con quanto sta accadendo.

Adobe Journey Optimizer supporta le attività live su entrambe le principali piattaforme mobili:

* **[Attività iOS Live](/help/channels/ios-live-activities.md)**: aggiornamenti completi e in tempo reale nella schermata di blocco di iPhone e in Dynamic Island.
* **[Android Live Updates](/help/channels/android-live-updates.md)**: aggiornamenti in tempo reale e costanti nell&#39;area di notifica di Android.

Per configurare Mobile SDK e utilizzare le API per avviare, aggiornare e terminare esperienze live nei tuoi percorsi di clienti, consulta [Configurare Live Activity](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/live-activity/configure-live-activity/mobile-live-configuration-sdk){target="_blank"}.

## Casi d’uso

Scegli le attività live come canale preferito quando devi:

| # | Beneficio | Il motivo | Casi d’uso di esempio |
|---|---------|-----|-------------------|
| 1 | Panoramica dei progressi in corso | Gli aggiornamenti vengono visualizzati direttamente nella schermata di blocco o nell’ombra di notifica/isola dinamica, senza che l’utente apra l’app | <ul><li>Tracciamento delle consegne alimentari</li><li>Stato di sospensione</li><li>Punteggi sportivi live</li></ul> |
| 2 | Riduzione dell&#39;affaticamento delle notifiche | Una singola attività viene aggiornata sul posto invece di attivare notifiche push ripetute | <ul><li>Fasi di preparazione e consegna dell’ordine</li><li>Aggiornamenti all’imbarco e al gate di imbarco</li></ul> |
| 3 | Contesto critico in termini di tempo e di breve durata | Ideale per attività con un inizio e una fine chiari | <ul><li>Conti alla rovescia del ritiro di Curbside</li><li>Sessioni di allenamento o timer</li></ul> |
| 4 | Interfaccia utente nativa e intuitiva | Utilizza superfici native per il sistema operativo (Dynamic Island, Lock Screen, ombra di notifica) per un’esperienza di elevata visibilità e a basso attrito | <ul><li>Tracciamento dei pacchetti</li><li>Aggiornamenti in coda o in attesa</li></ul> |

## Quando *non* utilizzare le attività live

* Per gli stati a esecuzione prolungata o aperti senza una fine chiara, termina l’attività una volta completato il processo sottostante.
* Per contenuti promozionali o di marketing: utilizza al loro posto notifiche push, messaggi in-app o schede di contenuto.
* Quando la cadenza degli aggiornamenti è molto elevata, gli aggiornamenti frequenti possono essere limitati dal sistema operativo o risultare rumorosi per l’utente.
* Se la tua app non supporta le versioni minime del sistema operativo richieste per le attività di iOS Live o per gli aggiornamenti di Android Live.
