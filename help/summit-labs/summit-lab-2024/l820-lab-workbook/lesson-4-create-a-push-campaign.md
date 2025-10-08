---
title: Lezione 4 - Creare una campagna push
description: Esamina i dati del profilo e scopri come creare e inviare ai tipi di pubblico una notifica push in Journey Optimizer.
feature: Push
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14980
exl-id: 0f82d6a5-18c0-45f2-968e-a678fc2d5768
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 2%

---

# Lezione 4 - Creare una campagna push

Nell&#39;esercizio precedente, eri un appassionato di caffè, un cliente Fréscopa. Hai interagito con il brand attraverso il loro sito web e l’app Fréscopa e hai ricevuto molti messaggi transazionali. Questi messaggi vengono attivati tramite l’interazione dell’utente con il sito web o l’applicazione.

In questo esercizio, metterai il cappello all’addetto marketing e implementerai una campagna di marketing per Frésopa, che utilizzerà il canale push per eseguire il targeting degli utenti dell’app Fréscopa. Le notifiche push vengono utilizzate per informare gli utenti dell’app, anche quando non utilizzano l’app, ma anche per coinvolgerli nuovamente nell’app. L&#39;obiettivo è quello di incentivare il cliente ad acquistare la miscela di casa, offrendo uno sconto del 10%.

## Finalità di apprendimento

* Scopri come creare una campagna push.
* Scopri come progettare un messaggio push.

<br>

## Esercizio 4.1 - Creare una campagna push

In questo esercizio creerai la campagna push, progetterai e personalizzerai la notifica push, inviandola al tuo dispositivo.

1. In Journey Optimizer, nella barra di navigazione a sinistra, nella sezione **[!UICONTROL GESTIONE PERCORSI]**, seleziona **Campagne**.

1. Fai clic su **[!UICONTROL Crea campagna]**.

   ![Crea campagna](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. Nella pagina **[!UICONTROL Crea campagna]**, nella sezione **[!UICONTROL Azione]**, seleziona la casella di controllo **[!UICONTROL Notifica push]**.

1. Dal menu a discesa **[!UICONTROL Superficie app]**, seleziona *[!DNL Frecopa-Push]*.

1. Fai clic su **[!UICONTROL Crea]** per creare una campagna push.

   ![Superficie app](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>Ora dovresti trovarti nella pagina delle proprietà di Campaign:
>&#x200B;> ![Proprietà campagna](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## Esercizio 4.2 - Configurare la campagna

In questa pagina puoi configurare le proprietà, il pubblico, le azioni e la pianificazione della campagna.

### 4.2.1 [!UICONTROL Sezione proprietà]

Assegna un nome alla campagna. Assicurati di iniziare il nome con il tuo numero di posto, in modo da poter trovare facilmente la tua campagna quando la cerchi.

Ad esempio, se il numero di posto è 99: `99 - 10% Discount Campaign`.

### 4.2.2 **[!UICONTROL Sezione pubblico]**

1. Nella sezione del pubblico, fai clic su **[!UICONTROL Seleziona pubblico]**.

   ![sezione pubblico](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. Nella schermata **[!UICONTROL Seleziona pubblico]**, cerca il pubblico:

   **Lab - Postazione`your seat number`**

1. Seleziona il pubblico, quindi fai clic su **[!UICONTROL Salva]**.

   ![selezione pubblico](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 Modificare il contenuto della notifica push

In questo esercizio creerai e personalizzerai la notifica push.

1. Nella sezione **[!UICONTROL Azione]**, fai clic sul pulsante **[!UICONTROL Modifica contenuto]**.

   ![Pulsante Modifica contenuto](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. Nella schermata successiva, a seconda del dispositivo mobile in uso, selezionare la scheda [!DNL iOS™] o [!DNL Android™] per configurare il contenuto.

>[!BEGINTABS]

>[!TAB iOS]

![Scheda iOS](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![Scheda Android](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1 [!UICONTROL Componi messaggio] sezione

1. **Componi il messaggio:** Puoi aggiungere il testo desiderato. Di seguito sono riportati alcuni esempi che è possibile utilizzare:

   * Titolo: `Get 10% off today!`
   * Corpo del testo: `Today only! Get 10% off on your House Blend coffee purchase!`

     ![Componi messaggio](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 Modifica il comportamento al clic del messaggio in **apri una pagina di prodotto**

1. Nella sezione **[!UICONTROL Comportamento al clic]**, seleziona **[!UICONTROL Deeplink]** dal menu a discesa **[!UICONTROL Comportamento al clic del corpo]**.

1. Copia e incolla il seguente URL nel campo **URL**:

   `dxdemo://exoticVibes`

   ![collegamento profondo](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 Aggiungi un&#39;immagine al messaggio

1. Nella sezione **[!UICONTROL Aggiungi file multimediali]**, fare clic su **[!UICONTROL Aggiungi file multimediali]**.

   ![aggiungi pulsanti multimediali](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. Nella schermata **[!UICONTROL Seleziona Assets]**, nella barra di navigazione a sinistra, apri la cartella **Fréscopa** e seleziona un&#39;immagine da tale cartella.

   Ad esempio: `HouseBlend.png`

1. Fai clic sull&#39;immagine e sul pulsante **[!UICONTROL Seleziona]** per aggiungerla alla notifica push.

   ![seleziona immagine](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. Nella schermata di anteprima, fare clic su **[!UICONTROL Espandi visualizzazione]**.
   > 1. Visualizza l’anteprima del messaggio.
   > <br>
   >
   > ![espandi visualizzazione](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-3-expand-view.png)

### Esercizio bonus

Se hai completato questa parte dell’esercizio e hai ancora un po’ di tempo, prova l’esercizio bonus:

+++ Esercizio bonus

#### Personalizza il messaggio che stai inviando aggiungendo il nome del destinatario

1. Fai clic su **finestra di dialogo per la personalizzazione** accanto al campo **[!UICONTROL Corpo]**.

   ![pulsante di personalizzazione](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-personalization-button.png)

1. Nella schermata **finestra di dialogo per la personalizzazione**, posizionare il cursore nel punto in cui si desidera aggiungere il nome nel testo.

1. Verifica che **Attributi profilo** siano selezionati nel menu di navigazione a sinistra.

   ![Attributo profilo](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. Nel **campo di ricerca**, cercare: `first name`.

1. Fai clic su **+** accanto a **Nome (attributi profilo>Persona>Nome completo)** per aggiungere il campo di personalizzazione al testo.

   ![Cerca nome](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > Ecco come dovrebbe apparire il tuo testo:
   > 
   >![Token Personalization](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-personalization-token.png)

1. Fai clic su **[!UICONTROL Salva]** per salvare la personalizzazione.


   >[!SUCCESS]
   >
   > 1. Nella schermata di anteprima, fare clic su **[!UICONTROL Espandi visualizzazione]**.
   > 1. Visualizza l’anteprima del messaggio.
   > 
   > ![espandi visualizzazione](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4. Revisione e attivazione

Se sei soddisfatto del contenuto del messaggio, puoi attivarlo:

1. Fai clic su **[!UICONTROL Rivedi per attivare]**.

   ![pulsante di revisione e attivazione](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. Nella schermata **[!UICONTROL Rivedi per attivare]**, fai clic su **[!UICONTROL Attiva]**.

   ![rivedi per attivare la schermata](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> Nella pagina **Panoramica campagne**, individua la campagna e controlla lo stato.
>
> ![stato campagna](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> Lo stato cambia da elaborazione a live e diventa completato (l&#39;operazione potrebbe richiedere alcuni minuti).
> &#x200B;> Una volta che lo stato è cambiato in completato:
>
> ![risultati push](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-push-notification-result.png)

## Risorse aggiuntive

**Video:**

* [Configurare e inviare una campagna push](/help/channels/create-a-push-campaign.md)

**Documentazione del prodotto:**

* [Introduzione alla notifica push](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/push/get-started-push)
* [Creare una notifica push](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/push/create-push)
* [Progettare una notifica push](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/push/design-push)
* [Verifica e invia la notifica push](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/push/send-push)
