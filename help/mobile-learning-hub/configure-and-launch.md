---
title: Configure and launch
description: Configure the mobile channels in Adobe Journey Optimizer (AJO) and Adobe Experience Platform (AEP), integrate with mobile apps, and ensure readiness for marketing campaign execution.
feature: Overview
role: Developer, Admin
level: Beginner, Intermediate
hide: false
index: true
jira: KT-19869
last-substantial-update: 2025-12-18T00:00:00Z
exl-id: d8ffe406-b54b-455f-bd41-7d1fef0a4714
source-git-commit: 3917e11cdf8c0450c19ce653a0964f6dc9da6a3c
workflow-type: tm+mt
source-wordcount: '2976'
ht-degree: 23%

---


# Configure and launch

For **administrators** and **mobile app developers**, this section shows how to configure and launch mobile and web channels in Adobe Journey Optimizer. It covers prerequisites, permissions, and platform support, then guides you through creating app-specific configurations.

>[!IMPORTANT]
>
> If you are new to Journey Optimizer and Experience Platform, familiarize yourself with the core concepts data management in Journey Optimizer by taking this course: [Engineer Data for Intelligent Journey Activation in Adobe Journey Optimizer](https://experienceleague.adobe.com/it/courses/ajo-engineer-data-for-intelligent-journey-activation){target="_blank"}
>

## Mobile capabilities in Adobe Journey Optimizer

Understand which mobile capabilities Adobe Journey Optimizer offers for developers, marketers, and product teams, including push messaging, in‑app messaging, and content personalization.

>[!VIDEO](https://video.tv.adobe.com/v/342103?quality=12&learn=on){transcript=true}


## Configurazione dei canali

### Mobile push and in-app

Mobile implementations in Journey Optimizer begin with the **Adobe Experience Platform Mobile SDK** integration in your app. SDKs are essential for data collection and interaction with Adobe Experience Platform (AEP) and its applications, such as Adobe Journey Optimizer (AJO).

#### What is the Mobile SDK:

The mobile SDK:

* Collects app events (screen views, taps, purchases, lifecycle events, etc.) and sends them to the **Adobe Experience Platform Edge Network**.
* Manages **identity** and **consent**, so Journey Optimizer can safely build and use customer profiles.
* Registers and updates **push tokens**, and sends **push and in‑app tracking events** back to Adobe Experience Platform.
* Integrates with the **[Journey Optimizer mobile extension](https://developer.adobe.com/client-sdks/edge/adobe-journey-optimizer)** so messages can be delivered, rendered, and measured end‑to‑end.

Without the Mobile SDK integrated in your app, Journey Optimizer cannot reliably:

* Deliver and track mobile push and in‑app messages.
* Render and track content cards.
* Use real‑time in‑app behavior to trigger journeys and personalize experiences.

#### Guided channel setup for new implementations

For new Mobile In-App and Push implementations, Guided Channel Setup is the recommended starting point. It reduces the risk of misconfigured datastreams or missing extensions and walks you through SDK validation with Assurance.

>[!PREREQUISITES]
>
>Make sure you have:
>
> * **Adobe Journey Optimizer** (AJO) provisioned for your org.
> * Adobe Experience Platform access with [Data Collection and Journey Optimizer permissions](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config#:~:text=Required%20permissions).
> * Admin rights in AJO for channel and configuration setup.
> * Access to your mobile app&#39;s source code (iOS, Android, or cross‑platform framework).
> * Your app has the required OS‑level capabilities enabled (for example, push permissions, notification service extensions, background modes).
> * If you are using the existing configuration option, please ensure that you are using the [current Adobe Experience Platform Mobile SDK versions](https://developer.adobe.com/client-sdks/home/current-sdk-versions/){target="_blank"}


>[!VIDEO](https://video.tv.adobe.com/v/3433053/?learn=on)

For more information see [Get started with guided channel setup](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config.html?lang=it){target="_blank"}


#### Manual configuration of the push channel

This following guides walk you through everything you need to manually configure and use push notifications effectively, from understanding the data flow and integrating with services like Firebase and Apple Push Notification Service (APNs) to setting up mobile apps and testing notifications.

<!--
CARDS
* https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/push-gs
{title = Push notification data flow and components}
{description = Learn how to setup and understand key services and workflows involved with push notifications in Journey Optimizer.}
{image = https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/media_1f6e99fa57e318230d92f5dde619c450690b5d27a.png?width=2000&format=webply&optimize=medium}
{target = _blank}

* https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/push-configuration
{image = https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/media_1134ddf9b0f7d39bb365d4884a1d603fd4aa5bbdf.png?width=2000&format=webply&optimize=small}
{target = _blank}
* https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/overview 
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Push notification data flow and components">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/push-gs" title="Push notification data flow and components" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/media_1f6e99fa57e318230d92f5dde619c450690b5d27a.png?width=400&format=webply&optimize=medium" alt="Push notification data flow and components"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/push-gs" target="_blank" rel="referrer" title="Push notification data flow and components">Push notification data flow and components</a>
                    </p>
                    <p class="is-size-6">Learn how to setup and understand key services and workflows involved with push notifications in Journey Optimizer.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/push-gs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Push notification configuration">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/push-configuration" title="Push notification configuration" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/media_1134ddf9b0f7d39bb365d4884a1d603fd4aa5bbdf.png?width=400&format=webply&optimize=small" alt="Push notification configuration"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/push-configuration" target="_blank" rel="referrer" title="Push notification configuration">Push notification configuration</a>
                    </p>
                    <p class="is-size-6">Learn how to configure your environment to send push notifications with Journey Optimizer</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/push-configuration" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement Adobe Experience Cloud in mobile apps tutorial">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/overview" title="Implement Adobe Experience Cloud in mobile apps tutorial" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="Implement Adobe Experience Cloud in mobile apps tutorial"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="Implement Adobe Experience Cloud in mobile apps tutorial">Tutorial sull’implementazione di Adobe Experience Cloud nelle app per dispositivi mobili</a>
                    </p>
                    <p class="is-size-6">Learn how to implement the Adobe Experience Cloud mobile applications. This tutorial guides you through an implementation of Experience Cloud applications in a sample Swift or Android app.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

#### Additional ressources


<!--
CARDS
* https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk
{target = _blank}
* https://developer.adobe.com/client-sdks/home/base/assurance
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Get the Adobe Experience Platform Mobile SDK">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" title="Get the Adobe Experience Platform Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Get the Adobe Experience Platform Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" target="_blank" rel="referrer" title="Get the Adobe Experience Platform Mobile SDK">Get the Adobe Experience Platform Mobile SDK</a>
                    </p>
                    <p class="is-size-6">A guide that explains how to install the Adobe Experience Platform Mobile SDK in your application.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Assurance overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://developer.adobe.com/client-sdks/home/base/assurance" title="Adobe Experience Platform Assurance overview" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://developer.adobe.com/shared/images/adobe-social-share.png" alt="Adobe Experience Platform Assurance overview"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://developer.adobe.com/client-sdks/home/base/assurance" target="_blank" rel="referrer" title="Adobe Experience Platform Assurance overview">Adobe Experience Platform Assurance overview</a>
                    </p>
                    <p class="is-size-6">An overview for the Adobe Experience Platform Assurance mobile extension.</p>
                </div>
                <a href="https://developer.adobe.com/client-sdks/home/base/assurance" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

#### Mobile SDK readiness checklist

Before handing the app to marketers, confirm in **[Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/){target="_blank"}** that:

>[!SUCCESS]
> 
> [ ] Core SDK + Journey Optimizer extensions are loaded,\
> [ ] Events are flowing on the correct datastream and datasets,\
> [ ]Identity and consent are present on all key events,\
> [ ] Push tokens and interactions are tracked, and\
> [ ] At least one test in‑app message or content card has been displayed and recorded as an impression.


### Schede di contenuto

<!--
CARDS
* https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp
{title = Configure content cards support in Mobile SDK}
{description = Learn how to integrate content cards in your mobile application using Messaging SDK.}
{image = https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/content-card/configure/media_17623afb1c5e280b7fb6861b4003d0ef8f8bea24d.jpg?width=2000&format=webply&optimize=medium}
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure content cards support in Mobile SDK">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" title="Configurare il supporto delle schede di contenuto nell’SDK per dispositivi mobili" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/content-card/configure/media_17623afb1c5e280b7fb6861b4003d0ef8f8bea24d.jpg?width=400&format=webply&optimize=medium" alt="Configurare il supporto delle schede di contenuto nell’SDK per dispositivi mobili"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" target="_blank" rel="referrer" title="Configurare il supporto delle schede di contenuto nell’SDK per dispositivi mobili">Configure content cards support in Mobile SDK</a>
                    </p>
                    <p class="is-size-6">Scopri come integrare le schede di contenuto nell’app mobile utilizzando Messaging SDK.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### WhatsApp

Come configurare il **canale WhatsApp**:

<!--
CARDS
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up the WhatsApp channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" title="Configurare il canale WhatsApp" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470268/?format=jpeg&nocache=1765310599408" alt="Configurare il canale WhatsApp"
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Osserva</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### SMS/MMS/RCS

Configura i **canali SMS/MMS/RCS** con i provider standard (Twilio, Synch o Infobip) o utilizzando un provider SMS personalizzato:

<!--
CARDS
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel
{target = _blank}
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider
{description = Learn how to configure custom SMS providers in Journey Optimizer, set up API credentials and webhooks, manage opt-in/opt-out keywords, and launch personalized campaigns.}
{target = _blank}
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces
{target = _blank}
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure SMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" title="Configurare le credenziali API SMS e le superfici di canale" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3413355?format=jpeg&nocache=1765310599850" alt="Configurare le credenziali API SMS e le superfici di canale"
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Osserva</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure a custom SMS provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" title="Configurare un provider SMS personalizzato" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1765310599834" alt="Configurare un provider SMS personalizzato"
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Osserva</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure MMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" title="Configurare le credenziali API MMS e le superfici di canale" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3428872/?format=jpeg&nocache=1765310599863" alt="Configurare le credenziali API MMS e le superfici di canale"
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Osserva</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up RCS in Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" title="Configurazione di RCS in Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464755/?format=jpeg&nocache=1765310600192" alt="Configurazione di RCS in Journey Optimizer"
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Osserva</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Assicurati la conformità alle leggi sulla privacy e alle linee guida sulla piattaforma.

<!--
CARDS
* https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/app-implementation/consent
* https://experienceleague.adobe.com/it/docs/journey-optimizer/using/privacy/privacy-landing-page{image=../mobile-learning-hub/assets/privacy.webp}{title = Privacy Features in Adobe Journey Optimizer}{description = Learn how to process privacy requests, audit user actions, manage consent, apply governance rules, and leverage advanced security options like Customer Managed Keys.}
{target = _blank}
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework
{target = _blank}
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables
{cta = Watch}
{target = _blank}
* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies
{target = _blank}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement consent for Platform Mobile SDK implementations">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/app-implementation/consent" title="Implementazione del consenso per le implementazioni di Platform Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/app-implementation/consent./media_12356d2400b5ad641e8356a6883441b38a129c968.png?width=400&format=png&optimize=medium" alt="Implementazione del consenso per le implementazioni di Platform Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/app-implementation/consent" target="_blank" rel="referrer" title="Implementazione del consenso per le implementazioni di Platform Mobile SDK">Implement consent for Platform Mobile SDK implementations</a>
                    </p>
                    <p class="is-size-6">Learn how to implement consent in a mobile app.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/app-implementation/consent" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Ulteriori informazioni</span>
                </a>
            </div>
        </div>
    </div>
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
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Funzioni di privacy di Adobe Journey Optimizer">Privacy Features in Adobe Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Learn how to process privacy requests, audit user actions, manage consent, apply governance rules, and leverage advanced security options like Customer Managed Keys.</p>
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29708/?format=jpeg&nocache=1765310600883" alt="Panoramica del Framework di governance dei dati"
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Osserva</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Classify data using labels">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" title="Classificare i dati usando le etichette" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/29709?format=jpeg&nocache=1765310600887" alt="Classificare i dati usando le etichette"
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Osserva</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create Data Usage Policies">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" title="Creare criteri di utilizzo dei dati" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/32977/?format=jpeg&nocache=1765310600676" alt="Creare criteri di utilizzo dei dati"
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
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Osserva</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->


## Common implementation pitfalls and how to avoid them

Most mobile issues originate in **SDK or data collection configuration**, not in the Journey Optimizer journeys or campaigns themselves. Use the table below to identify what&#39;s going wrong, then expand the corresponding section for details.

### Pitfalls at a glance

| # | Issue / symptom | Common pitfall | Fix at a glance |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | Guided Channel Setup fails; no or low traffic | [SDK versions or extensions not aligned](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | Update SDK/extension versions; validate in Assurance |
| 2 | Tracking batches fail; errors in AEP | [Datastreams or datasets misconfigured](#2-misconfigured-datastreams-or-datasets) | Mappatura di eventi su set di dati evento e profili su set di dati profilo |
| 3 | I percorsi non si attivano; personalizzazione dispari | [Identità o consenso mancante / incoerente](#3-missing-or-inconsistent-identity-and-consent) | Implementare identità e consenso di Edge; verificare in Assurance |
| 4 | Nessuna consegna push o apertura nei rapporti | [Registrazione o tracciamento del token push interrotto](#4-push-token-registration-and-tracking-not-wired-correctly) | Correggere la registrazione dei token e il tracciamento delle interazioni tramite SDK |
| 5 | Nessuna impression in-app nonostante le campagne attive | [Messaggi in-app o schede di contenuto non visualizzati](#5-in-app-messages-or-content-cards-not-displaying) | Verifica estensioni di messaggistica, trigger e risposte alle decisioni di Assurance |

### Linee guida dettagliate per insidia

Apri la insidia che corrisponde ai sintomi per vedere cosa controllare e come correggerlo.

+++ &#x200B;1. Versioni ed estensioni di SDK non allineate con i requisiti del canale
**Noterai**

* Le attività push o in-app non raggiungono il dispositivo.
* La configurazione guidata del canale o la convalida del canale non riesce.
* In Assurance mancano le estensioni Journey Optimizer, Edge o Identity.

**Cosa verificare**

* Stai utilizzando le versioni minime delle estensioni **Mobile Core** e **Journey Optimizer** richieste da Installazione guidata canale?
* In **Assurance**, in estensioni ed eventi:
   * Vengono caricate le estensioni previste?
   * Gli eventi vengono inviati ad Edge Network e confermati?

**Come correggere**

* Effettua l’aggiornamento alle versioni supportate delle estensioni Mobile SDK e Journey Optimizer.
* Rigenera l’app, riconnettiti ad Assurance ed esegui nuovamente la configurazione guidata del canale.

See: [Set up mobile and web](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config){target="_blank"}

+++

+++ 2. Misconfigured datastreams or datasets
**Noterai**

* Events or push tracking batches fail in Platform datasets.
* Data ingestion errors (for example, &quot;Updates are not supported for events&quot;).
* Push or in‑app reports show little or no tracking.

**Cosa verificare**

* Did anyone change **system schemas or datasets** created for Journey Optimizer tracking?
* In your **datastream**:
   * Are experience events mapped to an **event dataset**?
   * Are profile attributes mapped to a **profile dataset**?

**Come correggere**

* Do not edit system datasets/schemas created by AJO.
* Correct the datastream mapping (events → event dataset, profiles → profile dataset).
* Prefer Guided Channel Setup or the documented datastream steps instead of ad‑hoc changes.

See: [Push Notification flow in Adobe Journey Optimizer](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}

+++

+++ 3. Missing or inconsistent identity and consent
**Noterai**

* Journeys don&#39;t trigger as expected for app users.
* Personalization doesn&#39;t match the user&#39;s behavior in other channels.
* Events appear in Experience Platform, but profiles look fragmented.

**Cosa verificare**

* Is **Identity for Edge Network** implemented and sending a stable primary ID (for example, login ID)?
* Is **Consent for Edge Network** implemented and updated when preferences change?
* In **Assurance**:
   * Gli eventi in uscita includono valori di consenso?
   * Includono ECID e gli ID primari in modo coerente?

**Come correggere**

* Implementa o correggi **l&#39;identità per Edge Network** nell&#39;app.
* Implementa il **consenso per Edge Network** e collegalo all&#39;interfaccia utente di consenso della tua app.
* Ripeti il test in Assurance finché l’identità e il consenso non vengono visualizzati in tutti gli eventi rilevanti.

Vedere: [Implementare il consenso per le implementazioni di Platform Mobile SDK](https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/app-implementation/consent){target="_blank"}

+++

+++ &#x200B;4. Registrazione e tracciamento dei token push non collegati correttamente
**Noterai**

* Gli utenti non ricevono mai notifiche push, anche se vengono eseguite campagne o percorsi.
* I rapporti push non mostrano aperture, chiusure o interazioni.

**Cosa verificare**

* L’app registra il token push con l’estensione Journey Optimizer:
   * Alla prima installazione?
   * Dopo ogni aggiornamento dell’app?
   * Quando il sistema operativo aggiorna il token?
* Quando un utente apre o chiude una notifica, vengono visualizzati gli eventi di tracciamento in Assurance?

**Come correggere**

* Aggiungi o correggi il codice che:
   * Registra il token tramite l’estensione mobile Journey Optimizer ogni volta che viene creato o aggiornato.
   * Invia eventi di interazione push (azioni aperte, ignorate e personalizzate) tramite Mobile SDK.
* Utilizza Assurance per confermare che gli eventi di registrazione e tracciamento si attivano come previsto.

Vedere: [Flusso delle notifiche push in Adobe Journey Optimizer](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/push/push-config/push-gs){target="_blank"}

+++

+++ &#x200B;5. Messaggi in-app o schede di contenuto non visualizzate
**Noterai**

* I messaggi in-app o le schede di contenuto non vengono mai visualizzati, nonostante le campagne o i percorsi attivi.
* Il reporting mostra 0 impression.

**Cosa verificare**

* **Journey Optimizer Mobile Messaging / In-App Extension** e **Messaging SDK** sono installati e registrati nell&#39;app?
* Nella configurazione di **tag**:
   * Esistono regole che attivano le richieste sugli eventi corretti (ad esempio, visualizzazioni a schermo o eventi personalizzati)?
* In **Assurance**:
   * Quando questi eventi si attivano, vedi che le richieste di decisione in-app o nella scheda di contenuto si interrompono?
   * Vede le risposte che arrivano da Edge Network?

**Come correggere**

* Installa e registra le estensioni di messaggistica richieste.
* Aggiungi o correggi le regole che attivano le decisioni sugli eventi target (schermate, eventi personalizzati).
* Per le schede di contenuto, assicurati di:
   * Recupera le schede tramite le API di Messaggistica SDK.
   * Puoi eseguirne il rendering nell’interfaccia utente.
   * Tracciare le interazioni indietro tramite SDK.

Consulta:
* [Creare e inviare messaggi in-app](https://experienceleague.adobe.com/it/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp){target="_blank"}
* [Configurare il supporto delle schede di contenuto nell’SDK per dispositivi mobili](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp){target="_blank"}

+++

## Risorse aggiuntive

* [Utilizzo di CDN (Client Side Personalization, ODD) su dispositivi mobili per personalizzazioni più veloci (Blog)](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626?profile.language=it){target="_blank"}
* [Il segreto per la crescita e il coinvolgimento delle app mobili di livello successivo (sessione del summit)](https://business.adobe.com/it/summit/2025/sessions/the-secret-to-nextlevel-mobile-app-engagement-s603.html)
