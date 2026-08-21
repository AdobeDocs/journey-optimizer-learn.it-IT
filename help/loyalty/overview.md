---
title: Introduzione alla fidelizzazione Journey Optimizer
description: Scopri come integrare la fidelizzazione Adobe Journey Optimizer, configurare una sfida, applicarla, visualizzarla e analizzarne le prestazioni.
topic: Get Started
role: User
level: Beginner
doc-type: Tutorial
jira: KT-21773
last-substantial-update: 2026-07-28T00:00:00Z
source-git-commit: e168e56efe575659b5f48e97af77b899f8b6c962
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 43%

---


# Introduzione alla fidelizzazione Journey Optimizer

Le sfide relative alla fedeltà ti consentono di creare programmi di fidelizzazione coinvolgenti e basati sulla gamification che influenzano il comportamento dei clienti e consolidano le relazioni con il brand. Crea sfide che premiano i clienti per azioni specifiche, da acquisti e recensioni di scrittura a coinvolgimento sui social media e amici di riferimento.

## Introduzione alla fedeltà

Questa sezione presenta Journey Optimizer Loyalty, descrive cosa è, dove si inserisce all’interno di Adobe Journey Optimizer e il ciclo di vita delle sfide, dalla configurazione all’analisi.

<!--
CARDS

* https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty
  {description = Understand what Journey Optimizer Loyalty is, where it sits under AJO, and the challenge lifecycle.}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Discover Journey Optimizer Loyalty">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty" title="Scopri la fedeltà di Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496457/?captions=ita&format=jpeg&nocache=1787271612824" alt="Scopri la fedeltà di Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty" target="_blank" rel="referrer" title="Scopri la fedeltà di Journey Optimizer">Scopri la fedeltà di Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Scopri cos’è la fidelizzazione di Journey Optimizer, dove si trova sotto AJO, e la sfida del ciclo di vita.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Imposta fedeltà

Questa sezione descrive la configurazione una tantum necessaria prima di iniziare a creare le sfide.


<!--
CARDS

* ./set-up-loyalty/set-up-a-loyalty-reward-provider.md
  {description = Learn how to set up a reward provider, create reward definitions, and configure reward payloads so Adobe Journey Optimizer can issue loyalty rewards through your external rewards system.}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up a loyalty reward provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./set-up-loyalty/set-up-a-loyalty-reward-provider.md" title="Impostare un provider di premi fedeltà" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3497415/?captions=ita&format=jpeg&nocache=1787271613194" alt="Impostare un provider di premi fedeltà"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./set-up-loyalty/set-up-a-loyalty-reward-provider.md" target="_blank" rel="referrer" title="Impostare un provider di premi fedeltà">Imposta un provider di premi fedeltà</a>
                    </p>
                    <p class="is-size-6">Scopri come impostare un provider di premi, creare definizioni di premi e configurare payload di premi in modo che Adobe Journey Optimizer possa emettere premi fedeltà attraverso il sistema di premi esterno.</p>
                </div>
                <a href="./set-up-loyalty/set-up-a-loyalty-reward-provider.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Configurare la sfida

Questa sezione illustra come creare e configurare una sfida fedeltà end-to-end, includendo tipo, struttura e pianificazione, attività e premi.


<!--
CARDS

* ./configure-your-challenge/set-up-a-loyalty-challenge.md
  {description = Learn how to set up a loyalty challenge by selecting the right challenge type, configuring audiences and schedules, defining participation rules, and controlling how progress is tracked and rewarded.}
* ./configure-your-challenge/create-tasks.md
  {description = Learn how to set up tasks: purchase & spend, quantities, eligible items & exclusions, and reuse.}
* ./configure-your-challenge/configure-rewards.md
  {description = Learn how to configure rewards: provider, milestone vs. completion delivery, reward types & coupons.}
* ./configure-your-challenge/create-a-challenge-and-get-insights-with-cx-enterprise-coworker.md
  {description = Learn how to use CX Enterprise Coworker to create, configure, and launch loyalty challenges using natural language, including audiences, rewards, schedules, and automated journey setup.}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up a loyalty challenge">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./configure-your-challenge/set-up-a-loyalty-challenge.md" title="Configurare una sfida di fidelizzazione" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496477/?captions=ita&format=jpeg&nocache=1787271613414" alt="Configurare una sfida di fidelizzazione"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./configure-your-challenge/set-up-a-loyalty-challenge.md" target="_blank" rel="referrer" title="Configurare una sfida di fidelizzazione">Imposta una sfida fedeltà</a>
                    </p>
                    <p class="is-size-6">Scopri come impostare una sfida di fidelizzazione selezionando il tipo di sfida corretto, configurando tipi di pubblico e pianificazioni, definendo regole di partecipazione e controllando come l’avanzamento viene tracciato e premiato.</p>
                </div>
                <a href="./configure-your-challenge/set-up-a-loyalty-challenge.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create tasks for your loyalty challenge">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./configure-your-challenge/create-tasks.md" title="Crea attività per la tua sfida fedeltà" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496448/?captions=ita&format=jpeg&nocache=1787271613396" alt="Crea attività per la tua sfida fedeltà"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./configure-your-challenge/create-tasks.md" target="_blank" rel="referrer" title="Crea attività per la tua sfida fedeltà">Crea attività per la tua sfida fedeltà</a>
                    </p>
                    <p class="is-size-6">Scopri come impostare le attività: acquisto e spesa, quantità, elementi ed esclusioni idonei e riutilizzo.</p>
                </div>
                <a href="./configure-your-challenge/create-tasks.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure rewards">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./configure-your-challenge/configure-rewards.md" title="Configurare i premi" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496487/?captions=ita&format=jpeg&nocache=1787271613404" alt="Configurare i premi"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./configure-your-challenge/configure-rewards.md" target="_blank" rel="referrer" title="Configurare i premi">Configura premi</a>
                    </p>
                    <p class="is-size-6">Scopri come configurare i premi: provider, milestone vs. completamento consegna, tipi di premio e coupon.</p>
                </div>
                <a href="./configure-your-challenge/configure-rewards.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create a loyalty challenge and surface insights with CX Enterprise Coworker">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./configure-your-challenge/create-a-challenge-and-get-insights-with-cx-enterprise-coworker.md" title="Creare una sfida di fidelizzazione e approfondimenti con CX Enterprise Collaborator" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496544/?captions=ita&format=jpeg&nocache=1787271613421" alt="Creare una sfida di fidelizzazione e approfondimenti con CX Enterprise Collaborator"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./configure-your-challenge/create-a-challenge-and-get-insights-with-cx-enterprise-coworker.md" target="_blank" rel="referrer" title="Creare una sfida di fidelizzazione e approfondimenti con CX Enterprise Collaborator">Crea una sfida di fidelizzazione e approfondimenti superficiali con CX Enterprise Coworker</a>
                    </p>
                    <p class="is-size-6">Scopri come utilizzare CX Enterprise Collaborator per creare, configurare e avviare le sfide di fidelizzazione utilizzando il linguaggio naturale, inclusi audience, premi, pianificazioni e configurazione automatica del percorso.</p>
                </div>
                <a href="./configure-your-challenge/create-a-challenge-and-get-insights-with-cx-enterprise-coworker.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Applicare e visualizzare la sfida

Questa sezione mostra come presentare ai clienti una sfida utilizzando schede di contenuti ed esperienze basate su codice.

<!--
CARDS

* ./apply-and-display-your-challenge/build-a-challenge-content-card.md
  {description = Learn how to build a challenge content card / code-based experience, covering opt-in and dynamic progress across the opt-in, progress, and completed stages, plus rewards and channel configuration.}
* ./apply-and-display-your-challenge/display-challenge-content-using-code-based-experience-channel.md
  {description = Learn how to use code-based experiences to promote loyalty challenges, display challenge progress, and deliver personalized content within your app using HTML or JSON.}
* ./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md
  {description = Learn how to configure multi-channel messaging for every stage of a loyalty challenge, from invitations and engagement messages to completion and reward notifications.}
* ./apply-and-display-your-challenge/publish-a-challenge-and-generate-a-journey.md
  {description = Learn how to publish a challenge and automatically generate a journey. Discover how challenge communications are translated into journey orchestration, review the generated journey structure, and customize it with additional conditions, decisioning, or optimization logic.}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Build a challenge content card">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./apply-and-display-your-challenge/build-a-challenge-content-card.md" title="Creare una scheda di contenuti di sfida" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496535/?captions=ita&format=jpeg&nocache=1787271613834" alt="Creare una scheda di contenuti di sfida"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./apply-and-display-your-challenge/build-a-challenge-content-card.md" target="_blank" rel="referrer" title="Creare una scheda di contenuti di sfida">Crea una scheda di contenuti della sfida</a>
                    </p>
                    <p class="is-size-6">Scopri come creare un’esperienza basata su codice o su una scheda di contenuti problematici, che includa il consenso e l’avanzamento dinamico nelle fasi di consenso, avanzamento e completamento, oltre a premi e configurazione del canale.</p>
                </div>
                <a href="./apply-and-display-your-challenge/build-a-challenge-content-card.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Display challenge content using the code-based experience channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./apply-and-display-your-challenge/display-challenge-content-using-code-based-experience-channel.md" title="Visualizzare il contenuto della sfida utilizzando il canale di esperienza basato su codice" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3497471/?captions=ita&format=jpeg&nocache=1787271613831" alt="Visualizzare il contenuto della sfida utilizzando il canale di esperienza basato su codice"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./apply-and-display-your-challenge/display-challenge-content-using-code-based-experience-channel.md" target="_blank" rel="referrer" title="Visualizzare il contenuto della sfida utilizzando il canale di esperienza basato su codice">Visualizza il contenuto della sfida utilizzando il canale esperienza basato sul codice</a>
                    </p>
                    <p class="is-size-6">Scopri come utilizzare le esperienze basate su codice per promuovere le sfide di fedeltà, visualizzare l’avanzamento delle sfide e distribuire contenuti personalizzati all’interno dell’app utilizzando HTML o JSON.</p>
                </div>
                <a href="./apply-and-display-your-challenge/display-challenge-content-using-code-based-experience-channel.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up lifecycle messaging for your challenge">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md" title="Configurare i messaggi del ciclo di vita in base alle esigenze" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3497461/?captions=ita&format=jpeg&nocache=1787271613823" alt="Configurare i messaggi del ciclo di vita in base alle esigenze"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md" target="_blank" rel="referrer" title="Configurare i messaggi del ciclo di vita in base alle esigenze">Imposta i messaggi del ciclo di vita per la tua sfida</a>
                    </p>
                    <p class="is-size-6">Scopri come configurare la messaggistica multicanale per ogni fase di una sfida di fidelizzazione, dagli inviti e i messaggi di coinvolgimento alle notifiche di completamento e ricompensa.</p>
                </div>
                <a href="./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Publish a challenge and generate a journey">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./apply-and-display-your-challenge/publish-a-challenge-and-generate-a-journey.md" title="Pubblicare una sfida e generare un percorso" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3498577/?format=jpeg&nocache=1787271613828" alt="Pubblicare una sfida e generare un percorso"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./apply-and-display-your-challenge/publish-a-challenge-and-generate-a-journey.md" target="_blank" rel="referrer" title="Pubblicare una sfida e generare un percorso">Pubblica una sfida e genera un percorso</a>
                    </p>
                    <p class="is-size-6">Scopri come pubblicare una sfida e generare automaticamente un percorso. Scopri come le comunicazioni di sfida si traducono in orchestrazione del percorso, rivedi la struttura del percorso generata e personalizzala con condizioni aggiuntive, decisioni o logica di ottimizzazione.</p>
                </div>
                <a href="./apply-and-display-your-challenge/publish-a-challenge-and-generate-a-journey.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Analizzare e creare rapporti

Questa sezione illustra come misurare le prestazioni delle sfide di fidelizzazione una volta che sono state pubblicate.

<!--
CARDS

* ./analyze-and-report/measure-performance-with-challenge-reports.md
  {description = Learn how to use challenge reports and performance dashboards to measure participation, completion rates, revenue attribution, and overall loyalty program performance.}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Measure challenge performance with challenge reports">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./analyze-and-report/measure-performance-with-challenge-reports.md" title="Misurare le prestazioni di verifica con i rapporti sulle verifiche" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3497565/?captions=ita&format=jpeg&nocache=1787271614112" alt="Misurare le prestazioni di verifica con i rapporti sulle verifiche"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="./analyze-and-report/measure-performance-with-challenge-reports.md" target="_blank" rel="referrer" title="Misurare le prestazioni di verifica con i rapporti sulle verifiche">Misura le prestazioni della verifica con i report di verifica</a>
                    </p>
                    <p class="is-size-6">Scopri come utilizzare i rapporti sulle sfide e le dashboard delle prestazioni per misurare la partecipazione, i tassi di completamento, l’attribuzione dei ricavi e le prestazioni complessive del programma fedeltà.</p>
                </div>
                <a href="./analyze-and-report/measure-performance-with-challenge-reports.md" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->
