---
title: Configurare e avviare
description: Configura i canali mobili in Adobe Journey Optimizer (AJO) e Adobe Experience Platform (AEP), integrali con le app mobili e assicurati che siano pronti per l’esecuzione della campagna di marketing.
feature: Overview
role: Developer, Admin
level: Beginner, Intermediate
hide: true
index: false
last-substantial-update: 2025-08-22T00:00:00Z
exl-id: d8ffe406-b54b-455f-bd41-7d1fef0a4714
source-git-commit: 371aa72d04f44777938ba3152cdea4d9cee24889
workflow-type: tm+mt
source-wordcount: '2561'
ht-degree: 15%

---


# Configurare e avviare

Configura i canali mobili in Adobe Journey Optimizer e Adobe Experience Platform, integrali con le app mobili e assicurati che siano pronti per l’esecuzione della campagna di marketing.

>[!NOTE]
>
> Se hai poca esperienza con Journey Optimizer e Experience Platform, acquisisci familiarità con i concetti di base della gestione dei dati in Journey Optimizer seguendo questo corso:
>
> [Dati tecnici per attivazione intelligente del Percorso in Adobe Journey Optimizer](https://experienceleague.adobe.com/it/courses/ajo-engineer-data-for-intelligent-journey-activation)
>*Scopri come impostare e gestire i dati del profilo cliente in tempo reale per Journey Optimizer utilizzando Experience Platform. Comprendere la modellazione dati, la mappatura identità e l&#39;acquisizione dati per creare profili unificati per percorsi di clienti personalizzati.*


## Funzionalità mobili in Adobe Journey Optimizer

Scopri le funzionalità mobili che Adobe Journey Optimizer offre a sviluppatori, addetti al marketing e team di prodotto, tra cui messaggi push, messaggi in-app e personalizzazione dei contenuti.

>[!VIDEO](https://video.tv.adobe.com/v/342103?quality=12&learn=on){transcript=true}


## Configurazione di app e SDK per dispositivi mobili

Le implementazioni per dispositivi mobili in Journey Optimizer iniziano con l&#39;integrazione di **Adobe Experience Platform Mobile SDK** nell&#39;app. Gli SDK sono essenziali per la raccolta dei dati e l’interazione con Adobe Experience Platform (AEP) e le sue applicazioni, come Adobe Journey Optimizer (AJO).

Il SDK per dispositivi mobili:

- Raccoglie eventi dell&#39;app (visualizzazioni a schermo, tocchi, acquisti, eventi del ciclo di vita, ecc.) e li invia a **Adobe Experience Platform Edge Network**.
- Gestisce **identity** e **consent**, in modo che Journey Optimizer possa creare e utilizzare in modo sicuro i profili cliente.
- Registra e aggiorna **token push** e invia nuovamente **eventi di tracciamento push e in-app** a Adobe Experience Platform.
- Si integra con **estensioni Journey Optimizer per dispositivi mobili** (push, in-app, schede di contenuto, gestione delle decisioni) in modo da poter inviare, eseguire il rendering e misurare i messaggi end-to-end.

Senza il Mobile SDK integrato nell’app, Journey Optimizer non può:

- Distribuisci e tieni traccia dei messaggi push e in-app mobili.
- Eseguire il rendering e tenere traccia delle schede di contenuto.
- Utilizza il comportamento in-app in tempo reale per attivare percorsi e personalizzare esperienze.


>[!PREREQUISITES]
>
>Assicurati di avere:
>
> - È stato eseguito il provisioning di Adobe Journey Optimizer (AJO) per la tua organizzazione.
> - Accesso a Adobe Experience Platform con le autorizzazioni Raccolta dati e Journey Optimizer.
> - Diritti di amministratore in AJO per la configurazione del canale e della configurazione.
> - Accesso al codice sorgente dell’app mobile (iOS, Android o framework multipiattaforma).
> - L’app dispone delle funzionalità richieste a livello di sistema operativo abilitate (ad esempio, autorizzazioni push, estensioni del servizio di notifica, modalità in background).


### Componenti SDK per dispositivi mobili richiesti per Journey Optimizer

Per utilizzare i canali mobili di Journey Optimizer (push, in-app, schede di contenuto, esperienze basate su codice), devi installare e configurare un set di estensioni **core** e **specifiche per canale** nella tua app mobile:

>[!BEGINTABS]

>[!TAB Core]

#### Estensioni core (necessarie per tutti i casi d’uso per dispositivi mobili)

| Scopo | Esempi di estensione (iOS / Android) | Note |
|----------------------|-----------------------------------------------|-------|
| Hub eventi e servizi | Mobile Core/AEP Core, servizi AEP | Base per tutte le altre estensioni. Fornisce hub eventi, reti, storage e stato condiviso. |
| Edge Network | Adobe Experience Platform Edge Network | Invia eventi app all&#39;Edge Network di Adobe Experience Platform. |
| Identità | Identità per Edge Network | Gestisce ECID e altre identità utilizzate per profilo e segmentazione. |
| Consenso | Consenso per Edge Network | Raccoglie e applica le preferenze di consenso dell’utente. |
| Assurance | Adobe Experience Platform Assurance | Utilizzato per convalidare ed eseguire il debug end-to-end della configurazione di SDK e canali. |

>[!TAB Specifico per canale]

#### Estensioni specifiche per il canale per Journey Optimizer

| Canale / funzionalità | Estensioni chiave aggiuntive (sopra il core) | Quali sono le funzionalità |
|------------------------|---------------------------------------------------------------------|------------------|
| Notifiche push | Estensione Journey Optimizer per dispositivi mobili (push) | Registra e aggiorna i token push, invia eventi di tracciamento push, collegati alla configurazione push di AJO. |
| Messaggistica in-app | Estensione Journey Optimizer per dispositivi mobili (in-app), componenti dell’interfaccia utente di messaggistica | Recupera e visualizza i messaggi in-app nel contesto, invia impression ed eventi di interazione. |
| Schede di contenuto | Messaggistica SDK con supporto per le schede di contenuto | Recupera, esegui il rendering e tieni traccia delle schede di contenuto per ottenere rapporti accurati su Journey Optimizer. |
| Esperienze basate su codice | Estensioni Journey Optimizer/decisioning o API server di Edge | Prendi decisioni per &quot;superfici&quot; specifiche nell’app; l’app controlla il rendering del contenuto. |

>[!ENDTABS]

#### Proprietà e configurazione dei tag per dispositivi mobili

Puoi configurare queste estensioni in una **[proprietà tag mobile](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)** in Raccolta dati AEP -> Tag.

Questa proprietà controlla:

- Quali estensioni Mobile SDK sono installate.
- Quali eventi nell’app attivano le chiamate all’Edge Network.
- Come vengono mappati i dati in XDM e inoltrati alle soluzioni Adobe (Journey Optimizer, Analytics, ecc.).

Puoi [creare e configurare questa proprietà mobile manualmente](https://experienceleague.adobe.com/it/docs/platform-learn/data-collection/tags/create-a-property) oppure per Mobile In-App e Push puoi utilizzare la **[Configurazione guidata canale](https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)** per creare automaticamente la proprietà tag, lo stream di dati e la configurazione del canale richiesti per iOS e Android.

&#x200B;> [!TIP]
>  
> Per le nuove implementazioni, **[Configurazione guidata canale](https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)** è il punto di partenza consigliato. Riduce il rischio di flussi di dati non configurati correttamente o di estensioni mancanti e illustra la convalida di SDK con Assurance.

#### Guida introduttiva a Mobile SDK:

<!-- CARDS
* https://experienceleague.adobe.com/it/docs/platform-learn/data-collection/mobile-sdk/overview
    {description = Learn how Adobe Experience Platform Mobile SDK powers end-to-end engagement in your mobile applications.}
* https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/overview
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Mobile SDK overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/platform-learn/data-collection/mobile-sdk/overview" title="Panoramica di Adobe Experience Platform Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/28948?format=jpeg&nocache=1763661968458" alt="Panoramica di Adobe Experience Platform Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" title="Panoramica di Adobe Experience Platform Mobile SDK">Panoramica di Adobe Experience Platform Mobile SDK</a>
                    </p>
                    <p class="is-size-6">Scopri in che modo Adobe Experience Platform Mobile SDK potenzia il coinvolgimento end-to-end nelle tue applicazioni mobili.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement Adobe Experience Cloud in mobile apps tutorial">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/overview" title="Tutorial sull’implementazione di Adobe Experience Cloud nelle app per dispositivi mobili" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="Tutorial sull’implementazione di Adobe Experience Cloud nelle app per dispositivi mobili"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="Tutorial sull’implementazione di Adobe Experience Cloud nelle app per dispositivi mobili">Tutorial sull’implementazione di Adobe Experience Cloud nelle app per dispositivi mobili</a>
                    </p>
                    <p class="is-size-6">Scopri come implementare le app mobili Adobe Experience Cloud. Questa esercitazione ti guida attraverso l’implementazione di applicazioni Experience Cloud in un’app Swift o Android di esempio.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

#### Riferimenti per sviluppatori:

<!-- CARDS
* https://developer.adobe.com/client-sdks/home/
* https://developer.adobe.com/client-sdks/home/current-sdk-versions/
* https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/
* https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/
* https://developer.adobe.com/client-sdks/home/getting-started/track-events/
* https://developer.adobe.com/client-sdks/home/base/assurance/
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Mobile SDK overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/" title="Panoramica di Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Panoramica di Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/" target="_blank" rel="referrer" title="Panoramica di Mobile SDK">Panoramica di Mobile SDK</a>
                    </p>
                    <p class="is-size-6">Pagina di panoramica della documentazione di Adobe Experience Platform Mobile SDK.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Current SDK versions">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/current-sdk-versions/" title="Versioni correnti di SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Versioni correnti di SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/current-sdk-versions/" target="_blank" rel="referrer" title="Versioni correnti di SDK">Versioni correnti di SDK</a>
                    </p>
                    <p class="is-size-6">Panoramica che mostra le estensioni per dispositivi mobili attualmente disponibili, insieme alle relative versioni, per ogni piattaforma.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/current-sdk-versions/" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up a mobile property">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/" title="Configurare una proprietà mobile" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Configurare una proprietà mobile"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/" target="_blank" rel="referrer" title="Configurare una proprietà mobile">Configura una proprietà mobile</a>
                    </p>
                    <p class="is-size-6">Una guida che spiega come impostare una proprietà mobile creando la proprietà, installando estensioni e pubblicando la configurazione. Il completamento di questo processo consente di utilizzare Mobile SDK.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Get the Adobe Experience Platform Mobile SDK">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/" title="Scarica Adobe Experience Platform Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Scarica Adobe Experience Platform Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/" target="_blank" rel="referrer" title="Scarica Adobe Experience Platform Mobile SDK">Ottieni Adobe Experience Platform Mobile SDK</a>
                    </p>
                    <p class="is-size-6">Guida che spiega come installare Adobe Experience Platform Mobile SDK nell’applicazione.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Track events">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/getting-started/track-events/" title="Tracciare gli eventi" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Tracciare gli eventi"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/getting-started/track-events/" target="_blank" rel="referrer" title="Tracciare gli eventi">Traccia eventi</a>
                    </p>
                    <p class="is-size-6">Una guida che spiega come tenere traccia degli eventi utilizzando Adobe Experience Platform Mobile SDK.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/getting-started/track-events/" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Assurance overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/base/assurance/" title="Panoramica di Adobe Experience Platform Assurance" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Panoramica di Adobe Experience Platform Assurance"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/base/assurance/" target="_blank" rel="referrer" title="Panoramica di Adobe Experience Platform Assurance">Panoramica di Adobe Experience Platform Assurance</a>
                    </p>
                    <p class="is-size-6">Panoramica dell’estensione Adobe Experience Platform Assurance per dispositivi mobili.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/base/assurance/" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

>[!SUCCESS]
>
>**Elenco di controllo preparazione a Mobile SDK**
>
> [ ] Core SDK installato (Core, Edge, Identity, Consent, Assurance).
> [ Sono state aggiunte ] estensioni Journey Optimizer per dispositivi mobili per i canali che utilizzerai (push, in-app, schede di contenuto, basate su codice).
> [ ] Datastream configurato correttamente per i set di dati evento e profilo.
> [ Identità e consenso di ] implementati e convalidati con Assurance.
> [ ] registrazione e tracciamento dei token push convalidati end-to-end.
> [ ] schede in-app e/o di contenuto visualizzate convalidate su un dispositivo.
> [ ] installazione guidata del canale utilizzata per le nuove implementazioni o configurazione allineata manualmente ai passaggi documentati.


## Configurazione canale Adobe Journey Optimizer

### In-app, push e WhatsApp

Configura i **canali mobili** utilizzando la funzionalità di configurazione guidata dei canali. Come configurare il **canale WhatsApp**:

<!-- CARDS
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup
 {description = Learn how to quickly set up and validate web and mobile channels across Experience Platform, Journey Optimizer, and Data Collection, and configure a push notification for a sample iOS marketing app.}
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Guided channel setup">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" title="Configurazione guidata del canale" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3433053/?format=jpeg&nocache=1763661970550" alt="Configurazione guidata del canale"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" title="Configurazione guidata del canale">Configurazione guidata del canale</a>
                    </p>
                    <p class="is-size-6">Scopri come impostare e convalidare rapidamente i canali web e mobili tra Experience Platform, Journey Optimizer e Data Collection e come configurare una notifica push per un’app di marketing iOS di esempio.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up the WhatsApp channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" title="Configurare il canale WhatsApp" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470268/?format=jpeg&nocache=1763661970579" alt="Configurare il canale WhatsApp"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" title="Configurare il canale WhatsApp">Configurare il canale WhatsApp</a>
                    </p>
                    <p class="is-size-6">Questo tutorial illustra come configurare il canale WhatsApp in Adobe Journey Optimizer per abilitare la messaggistica aziendale in tempo reale.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### SMS/MMS/RCS

Configura i **canali SMS/MMS/RCS** con i provider standard (Twilio, Synch o Infobip) o utilizzando un provider SMS personalizzato:

<!-- CARDS
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider
{description = Learn how to configure custom SMS providers in Journey Optimizer, set up API credentials and webhooks, manage opt-in/opt-out keywords, and launch personalized campaigns.}
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure SMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" title="Configurare le credenziali API SMS e le superfici di canale" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3413355?format=jpeg&nocache=1763661971419" alt="Configurare le credenziali API SMS e le superfici di canale"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" title="Configurare le credenziali API SMS e le superfici di canale">Configurare le credenziali API SMS e le superfici di canale</a>
                    </p>
                    <p class="is-size-6">Scopri come collegare Journey Optimizer a un fornitore di servizi SMS e come creare una superficie del canale SMS.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure a custom SMS provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" title="Configurare un provider SMS personalizzato" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1763661971435" alt="Configurare un provider SMS personalizzato"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" title="Configurare un provider SMS personalizzato">Configurare un provider SMS personalizzato</a>
                    </p>
                    <p class="is-size-6">Scopri come configurare provider SMS personalizzati in Journey Optimizer, configurare credenziali API e webhook, gestire parole chiave di consenso/rinuncia e avviare campagne personalizzate.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure MMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" title="Configurare le credenziali API MMS e le superfici di canale" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3428872/?format=jpeg&nocache=1763661971338" alt="Configurare le credenziali API MMS e le superfici di canale"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" title="Configurare le credenziali API MMS e le superfici di canale">Configurare le credenziali API MMS e le superfici di canale</a>
                    </p>
                    <p class="is-size-6">Scopri come collegare Journey Optimizer a un fornitore di servizi MMS e come creare una superficie di canale MMS.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up RCS in Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" title="Configurazione di RCS in Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464755/?format=jpeg&nocache=1763661971296" alt="Configurazione di RCS in Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" title="Configurazione di RCS in Journey Optimizer">Configurazione di RCS in Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Scopri come configurare e inviare messaggi RCS interattivi e in linea con il brand in Adobe Journey Optimizer utilizzando un provider SMS personalizzato. Questo tutorial illustra come configurare credenziali API, webhook e configurazioni di canale e quindi creare un percorso per offrire esperienze di messaggistica avanzate personalizzate all’interno dell’app di messaggistica nativa.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Assicurati la conformità alle leggi sulla privacy e alle linee guida sulla piattaforma.

<!-- CARDS
* https://experienceleague.adobe.com/it/docs/journey-optimizer/using/privacy/privacy-landing-page{image=../mobile-learning-hub/assets/privacy.webp}{title = Privacy Features in Adobe Journey Optimizer}{description = Learn how to process privacy requests, audit user actions, manage consent, apply governance rules, and leverage advanced security options like Customer Managed Keys.}
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables{cta = Watch}
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Privacy Features in Adobe Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/privacy/privacy-landing-page" title="Funzioni di privacy di Adobe Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../mobile-learning-hub/assets/privacy.webp" alt="Funzioni di privacy di Adobe Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Funzioni di privacy di Adobe Journey Optimizer">Funzionalità privacy in Adobe Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Scopri come elaborare le richieste di privacy, controllare le azioni degli utenti, gestire il consenso, applicare le regole di governance e sfruttare opzioni di sicurezza avanzate come Chiavi gestite dal cliente.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Data Governance Framework Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" title="Panoramica del Framework di governance dei dati" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29708/?format=jpeg&nocache=1763661972554" alt="Panoramica del Framework di governance dei dati"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" title="Panoramica del Framework di governance dei dati">Panoramica del Framework di governance dei dati</a>
                    </p>
                    <p class="is-size-6">Comprendere le funzioni di governance di Adobe Experience Platform.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Classify data using labels">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" title="Classificare i dati usando le etichette" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29709?format=jpeg&nocache=1763661972557" alt="Classificare i dati usando le etichette"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" title="Classificare i dati usando le etichette">Classificare i dati tramite etichette</a>
                    </p>
                    <p class="is-size-6">Scopri come applicare le etichette agli schemi e ai set di dati.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create Data Usage Policies">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" title="Creare criteri di utilizzo dei dati" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/32977/?format=jpeg&nocache=1763661972555" alt="Creare criteri di utilizzo dei dati"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" title="Creare criteri di utilizzo dei dati">Creare criteri di utilizzo dei dati</a>
                    </p>
                    <p class="is-size-6">Scopri come creare e gestire i criteri di utilizzo dei dati.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Problemi di implementazione comuni e come evitarli

La maggior parte dei problemi relativi ai dispositivi mobili ha origine nella configurazione di **SDK o raccolta dati**, non nei percorsi o nelle campagne Journey Optimizer. Utilizza la tabella seguente per identificare cosa non funziona, quindi espandi la sezione corrispondente per i dettagli.

### Insidie a colpo d&#39;occhio

| # | Problema/sintomo | Insidia comune | Panoramica delle correzioni |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | La configurazione guidata del canale non riesce; traffico assente o ridotto | [Versioni o estensioni di SDK non allineate](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | Aggiornare le versioni di SDK/estensione; convalidare in Assurance |
| 2 | Tracciamento dei batch non riuscito; errori in AEP | [Configurazione errata di flussi di dati o set di dati](#2-misconfigured-datastreams-or-datasets) | Mappatura di eventi su set di dati evento e profili su set di dati profilo |
| 3 | I percorsi non si attivano; personalizzazione dispari | [Identità o consenso mancante / incoerente](#3-missing-or-inconsistent-identity-and-consent) | Implementare identità e consenso di Edge; verificare in Assurance |
| 4 | Nessuna consegna push o apertura nei rapporti | [Registrazione o tracciamento del token push interrotto](#4-push-token-registration-and-tracking-not-wired-correctly) | Correggere la registrazione dei token e il tracciamento delle interazioni tramite SDK |
| 5 | Nessuna impression in-app nonostante le campagne attive | [Messaggi in-app o schede di contenuto non visualizzati](#5-in-app-messages-or-content-cards-not-displaying) | Verifica estensioni di messaggistica, trigger e risposte alle decisioni di Assurance |

### Linee guida dettagliate per insidia

Apri la insidia che corrisponde ai sintomi per vedere cosa controllare e come correggerlo.

<details id="1-sdk-versions-and-extensions-not-aligned-with-channel-requirements">
<summary><strong>1. Versioni ed estensioni di SDK non allineate con i requisiti del canale</strong></summary>

**Noterai**

- Le attività push o in-app non raggiungono il dispositivo.
- La configurazione guidata del canale o la convalida del canale non riesce.
- In Assurance mancano le estensioni Journey Optimizer, Edge o Identity.

**Cosa verificare**

- Stai utilizzando le versioni minime delle estensioni **Mobile Core** e **Journey Optimizer** richieste da Installazione guidata canale?
- In **Assurance**, in estensioni ed eventi:
   - Vengono caricate le estensioni previste?
   - Gli eventi vengono inviati ad Edge Network e confermati?

**Come correggere**

- Effettua l’aggiornamento alle versioni supportate delle estensioni Mobile SDK e Journey Optimizer.
- Rigenera l’app, riconnettiti ad Assurance ed esegui nuovamente la configurazione guidata del canale.

Vedere: [Configurazione di dispositivi mobili e Web](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config)

</details>


<details id="2-misconfigured-datastreams-or-datasets">
<summary><strong>2. Datastream o set di dati non configurati correttamente</strong></summary>

**Noterai**

- Gli eventi o i batch di tracciamento push non riescono nei set di dati di Platform.
- Errori di acquisizione dei dati (ad esempio, &quot;Gli aggiornamenti non sono supportati per gli eventi&quot;).
- I rapporti push o in-app mostrano un tracciamento minimo o nullo.

**Cosa verificare**

- Qualcuno ha modificato **schemi o set di dati di sistema** creati per il tracciamento di Journey Optimizer?
- Nel **flusso di dati**:
   - Gli eventi esperienza sono mappati a un **set di dati evento**?
   - Gli attributi del profilo sono mappati a un **set di dati del profilo**?

**Come correggere**

- Non modificare i set di dati/schemi di sistema creati da AJO.
- Correggi la mappatura dello stream di dati (eventi → set di dati evento, profili → set di dati profilo).
- Preferisci la configurazione guidata del canale o i passaggi documentati dello stream di dati invece di modifiche ad hoc.

Vedere: [Flusso delle notifiche push in Adobe Journey Optimizer](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="3-missing-or-inconsistent-identity-and-consent">
<summary><strong>3. Identità e consenso mancanti o incoerenti</strong></summary>

**Noterai**

- I percorsi non si attivano come previsto per gli utenti dell’app.
- Personalization non corrisponde al comportamento dell’utente su altri canali.
- Gli eventi vengono visualizzati in Experience Platform, ma i profili sembrano frammentati.

**Cosa verificare**

- **Identità per Edge Network** implementata e invio di un ID primario stabile (ad esempio, ID di accesso)?
- **Il consenso per Edge Network** è implementato e aggiornato quando le preferenze cambiano?
- In **Assurance**:
   - Gli eventi in uscita includono valori di consenso?
   - Includono ECID e gli ID primari in modo coerente?

**Come correggere**

- Implementa o correggi **l&#39;identità per Edge Network** nell&#39;app.
- Implementa il **consenso per Edge Network** e collegalo all&#39;interfaccia utente di consenso della tua app.
- Ripeti il test in Assurance finché l’identità e il consenso non vengono visualizzati in tutti gli eventi rilevanti.

Vedere: [Implementare il consenso per le implementazioni di Platform Mobile SDK](https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/app-implementation/consent)

</details>


<details id="4-push-token-registration-and-tracking-not-wired-correctly">
<summary><strong>4. Registrazione e tracciamento dei token push non collegati correttamente</strong></summary>

**Noterai**

- Gli utenti non ricevono mai notifiche push, anche se vengono eseguite campagne o percorsi.
- I rapporti push non mostrano aperture, chiusure o interazioni.

**Cosa verificare**

- L’app registra il token push con l’estensione Journey Optimizer:
   - Alla prima installazione?
   - Dopo ogni aggiornamento dell’app?
   - Quando il sistema operativo aggiorna il token?
- Quando un utente apre o chiude una notifica, vengono visualizzati gli eventi di tracciamento in Assurance?

**Come correggere**

- Aggiungi o correggi il codice che:
   - Registra il token tramite l’estensione mobile Journey Optimizer ogni volta che viene creato o aggiornato.
   - Invia eventi di interazione push (azioni aperte, ignorate e personalizzate) tramite Mobile SDK.
- Utilizza Assurance per confermare che gli eventi di registrazione e tracciamento si attivano come previsto.

Vedere: [Flusso delle notifiche push in Adobe Journey Optimizer](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="5-in-app-messages-or-content-cards-not-displaying">
<summary><strong>5. Messaggi in-app o schede di contenuto non visualizzati</strong></summary>

**Noterai**

- I messaggi in-app o le schede di contenuto non vengono mai visualizzati, nonostante le campagne o i percorsi attivi.
- Il reporting mostra 0 impression.

**Cosa verificare**

- **Journey Optimizer Mobile Messaging / In-App Extension** e **Messaging SDK** sono installati e registrati nell&#39;app?
- Nella configurazione di **tag**:
   - Esistono regole che attivano le richieste sugli eventi corretti (ad esempio, visualizzazioni a schermo o eventi personalizzati)?
- In **Assurance**:
   - Quando questi eventi si attivano, vedi che le richieste di decisione in-app o nella scheda di contenuto si interrompono?
   - Vede le risposte che arrivano da Edge Network?

**Come correggere**

- Installa e registra le estensioni di messaggistica richieste.
- Aggiungi o correggi le regole che attivano le decisioni sugli eventi target (schermate, eventi personalizzati).
- Per le schede di contenuto, assicurati di:
   - Recupera le schede tramite le API di Messaggistica SDK.
   - Puoi eseguirne il rendering nell’interfaccia utente.
   - Tracciare le interazioni indietro tramite SDK.

Consulta:
- [Creare e inviare messaggi in-app](https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp)
- [Configurare il supporto per le schede di contenuto in Mobile SDK](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp)

</details>

>[!SUCCESS]
>
> **Elenco di controllo preparazione a una riga**
>
> Prima di consegnare l&#39;app agli addetti al marketing, verifica in **[Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/)** che:
> 
> [ ] estensioni Core SDK + Journey Optimizer caricate,\
> [ ] eventi scorrono nel flusso di dati e nei set di dati corretti,\
> [ ]Identità e consenso sono presenti in tutti gli eventi chiave,\
> [ ] token di push e interazioni tracciati, e\
> [ ] Almeno un messaggio in-app di prova o una scheda di contenuto è stato visualizzato e registrato come impression.

## Post di blog

- [Utilizzo di ODD (Client Side Personalization) basato su CDN su dispositivi mobili per personalizzazioni più veloci.](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626)
- [Mobile Activation per Adobe Experience Cloud](https://experienceleaguecommunities.adobe.com/t5/adobe-target-blogs/mobile-activation-for-adobe-experience-cloud/ba-p/541595)
