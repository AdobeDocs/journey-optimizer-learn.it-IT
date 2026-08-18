---
title: Introduzione alla fidelizzazione Journey Optimizer
description: Scopri come integrare la fidelizzazione Adobe Journey Optimizer, configurare una sfida, applicarla, visualizzarla e analizzarne le prestazioni.
topic: Get Started
role: User
level: Beginner
doc-type: Tutorial
jira: KT-21773
last-substantial-update: 2026-07-28T00:00:00Z
source-git-commit: c4e15de254bd2e087938bbe47b11068fa653dcf9
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 42%

---


# Introduzione alla fidelizzazione Journey Optimizer

Le sfide relative alla fedeltà ti consentono di creare programmi di fidelizzazione coinvolgenti e basati sulla gamification che influenzano il comportamento dei clienti e consolidano le relazioni con il brand. Crea sfide che premiano i clienti per azioni specifiche, da acquisti e recensioni di scrittura a coinvolgimento sui social media e amici di riferimento.

## Introduzione alla fedeltà

In questa sezione viene illustrata la fedeltà di Journey Optimizer: cos&#39;è, dove si trova sotto Adobe Journey Optimizer e il ciclo di vita della sfida, dalla configurazione all&#39;analisi.

<!--
CARDS

* https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty
  {description = Understand what Journey Optimizer Loyalty is, where it sits under AJO, and the challenge lifecycle.}

-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Discover Journey Optimizer Loyalty">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty" title="Scopri la fedeltà di Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496441/?format=jpeg&nocache=1787093383713" alt="Scopri la fedeltà di Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty" target="_blank" rel="referrer" title="Scopri la fedeltà di Journey Optimizer">Scopri la fedeltà di Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Scopri cos’è la fidelizzazione di Journey Optimizer, dove si trova sotto AJO, e la sfida del ciclo di vita.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/loyalty/discover-journey-optimizer-loyalty" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Guarda</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Imposta fedeltà

Questa sezione descrive la configurazione una tantum iniziale necessaria per iniziare a creare una sfida.


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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3497346/?format=jpeg&nocache=1787093384202" alt="Impostare un provider di premi fedeltà"
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

Questa sezione illustra come creare e configurare una sfida fedeltà end-to-end: tipo, struttura e pianificazione, attività e premi.


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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496471/?format=jpeg&nocache=1787093384582" alt="Configurare una sfida di fidelizzazione"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496442/?format=jpeg&nocache=1787093384597" alt="Crea attività per la tua sfida fedeltà"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496481/?format=jpeg&nocache=1787093384590" alt="Configurare i premi"
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
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496528/?format=jpeg&nocache=1787093384571" alt="Creare una sfida di fidelizzazione e approfondimenti con CX Enterprise Collaborator"
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

Questa sezione mostra come presentare ai clienti una sfida tramite schede di contenuti ed esperienze basate su codice.

<!--
CARDS

* ./apply-and-display-your-challenge/build-a-challenge-content-card.md
  {description = Learn how to build a challenge content card / code-based experience, covering opt-in and dynamic progress across the opt-in, progress, and completed stages, plus rewards and channel configuration.}
* ./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md
  {description = Learn how to configure multi-channel messaging for every stage of a loyalty challenge, from invitations and engagement messages to completion and reward notifications.}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Build a challenge content card">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./apply-and-display-your-challenge/build-a-challenge-content-card.md" title="Creare una scheda di contenuti di sfida" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3496529/?format=jpeg&nocache=1787093384966" alt="Creare una scheda di contenuti di sfida"
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
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up lifecycle messaging for your challenge">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="./apply-and-display-your-challenge/set-up-lifecycle-messaging-for-your-challenge.md" title="Configurare i messaggi del ciclo di vita in base alle esigenze" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3497455/?format=jpeg&nocache=1787093384955" alt="Configurare i messaggi del ciclo di vita in base alle esigenze"
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
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Analizzare e creare rapporti

Questa sezione mostra come misurare le prestazioni delle sfide di fidelizzazione una volta che sono live.

<!--
CARDS

* [./analyze-and-report/measure-performance-with-challenge-reports.md
  {description = Learn how to use challenge reports and performance dashboards to measure participation, completion rates, revenue attribution, and overall loyalty program performance.}
  -->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">

</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->
