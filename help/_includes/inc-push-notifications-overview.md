---
source-git-commit: ac61c4d30929b559826b4a770fc10c26aec74830
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 2%

---

# Panoramica delle notifiche push

## Cosa sono le notifiche push?

Le **notifiche push** sono brevi messaggi che vengono visualizzati su un telefono, un tablet o un computer, anche quando l&#39;utente non utilizza l&#39;app che li ha inviati. Sono un modo per le app di &quot;colpirti sulla spalla&quot; e attirare la tua attenzione.

Ad esempio:

* Un’app per la spesa potrebbe segnalare una vendita importante.
* Un’app di consegna potrebbe comunicare che l’ordine è in arrivo.
* Un’app della compagnia aerea potrebbe comunicare che il volo è pronto per il check-in.

**Importante:** prima di poter inviare notifiche push, l&#39;utente deve concedere all&#39;app l&#39;autorizzazione (consenso). Questo accade in genere quando l’app viene aperta per la prima volta dopo averla scaricata, o successivamente se l’app lo richiede nuovamente durante l’uso. Senza l’autorizzazione dell’utente, l’app non può inviare notifiche push al dispositivo.

## Casi d’uso

Scegli le notifiche push come canale di messaggistica preferito quando devi:

| # | Beneficio | Perché | Casi d’uso di esempio |
|---|---------|-----|-------------------|
| 1 | Aggiornamenti sensibili al tempo | I messaggi push possono essere visualizzati nella schermata di blocco o come banner senza richiedere all’utente di aprire l’app. | <ul><li> Avvisi urgenti (interruzioni del servizio, avvisi di sicurezza)</li><li>Offerte sensibili al tempo (vendite flash)</li><li> Aggiornamenti in tempo reale (punteggi sportivi, consegna ordini)</ul> |
| 2 | Nuovo coinvolgimento | Il push può reinserire nell’app gli utenti inattivi inviando prompt personalizzati e pertinenti. | <ul><li> Promemoria per carrello abbandonato o sfogliare, ad esempio &quot;Hai lasciato degli articoli nel carrello. Paga ora con uno sconto del 10%&quot;.</li></ul> |
| 3 | Ridurre la dipendenza dai canali costosi | Il push è generalmente gratuito dopo aver creato l’infrastruttura, a differenza di SMS o e-mail in cui ci sono costi per messaggio. | <ul><li> Utilizza il push invece degli SMS a pagamento per aggiornamenti frequenti.</li></ul> |
| 4 | Consegna di contenuti avanzati e interattivi | Le API push moderne consentono di visualizzare immagini, video, azioni rapide (ad esempio, &quot;Accetta&quot; / &quot;Rifiuta&quot;) o collegamenti profondi a schermate di app specifiche. | <ul><li>Campagne di marketing con impatto visivo</li><li>Azioni utente rapide senza aprire completamente l’app.</li></ul> |
| 5 | Sfruttare le funzionalità native per i dispositivi | Le notifiche push si integrano con le funzioni del sistema operativo iOS/Android, come vibrazioni, suoni, badge e trigger di geofencing. | <ul><li> Offerte basate sulla posizione quando ci si trova vicino a un negozio</li><li> Promemoria attivati in momenti specifici.</li></ul> |
| 6 | Quando è probabile il consenso | Il push funziona solo per gli utenti che hanno esplicitamente acconsentito. Se l’app offre un valore elevato o il marchio ha già fiducia, i tassi di consenso possono essere elevati. | <ul><li> App con basi utente fedeli</li><li> Flussi di onboarding che spiegano il valore delle notifiche.</li></ul> |

## Quando *non* utilizzare il push come canale primario

* Bassi tassi di consenso o resistenza dell’utente alle notifiche.
* Necessità di contenuti in formato lungo (l’e-mail potrebbe essere migliore).
* Informazioni sensibili o altamente private (i messaggi push possono essere visualizzati su schermi di blocco).
* Gli utenti sono principalmente desktop e non nell’app mobile.
