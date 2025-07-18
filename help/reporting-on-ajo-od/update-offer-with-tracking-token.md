---
title: Tracciare e segnalare le offerte Adobe Journey Optimizer (AJO) distribuite tramite AJO Offer Decisioning
description: Questo tutorial estende un’implementazione Adobe Journey Optimizer (AJO) esistente che offre offerte personalizzate basate su dati contestuali come la temperatura. Illustra come acquisire gli eventi di impression e interazione e preparare i dati per il reporting in Journey Optimizer.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18526
source-git-commit: fa4795d92cf290b867df23277a297c99d6222224
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Aggiungere token di tracciamento agli elementi dell’offerta

Per modificare il codice nell’editor di personalizzazione, segui i passaggi seguenti:

Passa a _&#x200B;**Gestione Percorsi ->Campagne**&#x200B;_

Apri la campagna appropriata e fai clic sul pulsante _&#x200B;**Interrompi campagna**&#x200B;_ per interromperla.

Apri la campagna interrotta e fai clic sul pulsante _&#x200B;**Modifica campagna**&#x200B;_.

Fai clic sulla scheda _&#x200B;**Contenuto**&#x200B;_ e quindi sul pulsante _&#x200B;**Modifica codice**&#x200B;_ per aprire l&#39;editor di personalizzazione.

Aggiungi due nuovi attributi di dati al div, come mostrato nella schermata
![token di tracciamento](assets/offer-item-with-tracking-code.png)

Puoi aggiungere trackingToken ed ItemID facendo clic sull’icona Criterio decisione nella navigazione a sinistra, quindi espandere la struttura decisionale per selezionare itemID e trackingToken.
![token di tracciamento](assets/insert-tracking-token.png)

In questo modo ogni offerta sottoposta a rendering include un token di tracciamento dei dati, essenziale per il tracciamento accurato degli eventi di impression e clic.

Salva le modifiche e attiva la campagna.
