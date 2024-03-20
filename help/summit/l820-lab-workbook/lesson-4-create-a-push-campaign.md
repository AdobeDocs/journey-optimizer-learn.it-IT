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
source-git-commit: c590b47ad3dfc54badbac0d8fcaff6b9dd053cc1
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 0%

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

1. In Journey Optimizer, nella barra di navigazione a sinistra, nella **[!UICONTROL GESTIONE PERCORSO]** sezione, seleziona **Campagne**.

1. Clic **[!UICONTROL Crea campagna]**.

   ![Crea campagna](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. Il giorno **[!UICONTROL Crea campagna]** pagina, nella  **[!UICONTROL Azione]** , seleziona la sezione **[!UICONTROL Notifica push]** casella di controllo.

1. Dalla sezione **[!UICONTROL Superficie app]** a discesa, seleziona *[!DNL Frecopa-Push]*.

1. Clic **[!UICONTROL Crea]** per creare una campagna push.

   ![Superficie app](/help/summit/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>Ora dovresti trovarti nella pagina delle proprietà di Campaign:
> ![Proprietà della campagna](/help/summit/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## Esercizio 4.2 - Configurare la campagna

In questa pagina puoi configurare le proprietà, il pubblico, le azioni e la pianificazione della campagna.

### 4.2.1. [!UICONTROL Sezione Proprietà]

Assegna un nome alla campagna. Assicurati di iniziare il nome con il tuo numero di posto, in modo da poter trovare facilmente la tua campagna quando la cerchi.

Ad esempio, se il numero di posto è 99: `99 - 10% Discount Campaign`.

### 4.2.2. **[!UICONTROL Sezione Pubblico]**

1. Nella sezione del pubblico, fai clic su **[!UICONTROL Seleziona pubblico]**.

   ![sezione del pubblico](/help/summit/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. Il giorno **[!UICONTROL Seleziona pubblico]** schermata, cerca il pubblico:

   **Lab - Seat`your seat number`**

1. Seleziona il pubblico, quindi fai clic su **[!UICONTROL Salva]**.

   ![selezione del pubblico](/help/summit/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 Modificare il contenuto della notifica push

In questo esercizio creerai e personalizzerai la notifica push.

1. In **[!UICONTROL Azione]** , fare clic sul pulsante **[!UICONTROL Modifica contenuto] pulsante**.

   ![Pulsante Modifica contenuto](/help/summit/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. Nella schermata successiva, a seconda del dispositivo mobile in uso, seleziona una delle seguenti opzioni: [!DNL iOS™] o [!DNL Android™] per configurare il contenuto.

>[!BEGINTABS]

>[!TAB iOS]

![Scheda iOS](/help/summit/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![Scheda Android](/help/summit/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1. [!UICONTROL Componi messaggio] sezione

1. **Componi il messaggio:** Puoi aggiungere il testo desiderato. Di seguito sono riportati alcuni esempi che è possibile utilizzare:

   * Titolo: `Get 10% off today!`
   * Corpo del testo: `Today only! Get 10% off on your House Blend coffee purchase!`

     ![Componi messaggio](/help/summit/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 Modifica del comportamento al clic del messaggio in **aprire una pagina di prodotto**

1. In **[!UICONTROL Comportamento al clic]** sezione, seleziona **[!UICONTROL Deeplink]** dal **[!UICONTROL Comportamento al clic del corpo]** a discesa.

1. Copia e incolla il seguente URL nel **Campo URL**:

   `dxdemo://exoticVibes`

   ![collegamento profondo](/help/summit/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 Aggiungere un’immagine al messaggio

1. In **[!UICONTROL Aggiungi file multimediali]** , fare clic su **[!UICONTROL Aggiungi file multimediali]**.

   ![aggiungi pulsanti multimediali](/help/summit/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. Il giorno **[!UICONTROL Seleziona risorse]** nella barra di navigazione a sinistra, apri la **Cartella Fréscopa** e selezionare un&#39;immagine da tale cartella.

   Ad esempio: `HouseBlend.png`

1. Fai clic sull’immagine e fai clic su **[!UICONTROL Seleziona] pulsante** per aggiungere l’immagine alla notifica push.

   ![seleziona immagine](/help/summit/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. Nella schermata di anteprima, fai clic su **[!UICONTROL Espandi visualizzazione]**.
   > 1. Visualizza l’anteprima del messaggio.
   > <br>
   >
   > ![espandi visualizzazione](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

### Esercizio bonus

Se hai completato questa parte dell’esercizio e hai ancora un po’ di tempo, prova l’esercizio bonus:

+++ Esercizio bonus

#### Personalizza il messaggio che stai inviando aggiungendo il nome del destinatario

1. Clic **finestra di dialogo di personalizzazione** accanto al **[!UICONTROL Corpo]** campo.

   ![pulsante di personalizzazione](/help/summit/l820-lab-workbook/assets/2-3-personalization-button.png)

1. Il giorno **finestra di dialogo di personalizzazione** , posizionare il cursore nel punto in cui si desidera aggiungere il nome nel testo.

1. Assicurati che **Attributi del profilo** sono selezionati nel menu di navigazione a sinistra.

   ![Attributo profilo](/help/summit/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. In **Campo di ricerca**, cerca: `first name`.

1. Clic **+** accanto al **Nome (Attributi profilo>Persona>Nome completo)** per aggiungere il campo di personalizzazione al testo.

   ![Cerca nome](/help/summit/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > Ecco come dovrebbe apparire il tuo testo:
   > 
   >![Token di personalizzazione](/help/summit/l820-lab-workbook/assets/2-3-personalization-token.png)

1. Clic **[!UICONTROL Salva]** per salvare la personalizzazione.


   >[!SUCCESS]
   >
   > 1. Nella schermata di anteprima, fai clic su **[!UICONTROL Espandi visualizzazione]**.
   > 1. Visualizza l’anteprima del messaggio.
   > 
   > ![espandi visualizzazione](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4. Revisione e attivazione

Se sei soddisfatto del contenuto del messaggio, puoi attivarlo:

1. Clic **[!UICONTROL Controlla per attivare]**.

   ![pulsante rivedi e attiva](/help/summit/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. Il giorno **[!UICONTROL Controlla per attivare]** schermata, fai clic su **[!UICONTROL Attiva]**.

   ![rivedi per attivare la schermata](/help/summit/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> Il giorno **Pagina panoramica delle campagne**, trova la campagna e controlla lo stato.
>
> ![stato della campagna](/help/summit/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> Lo stato cambia da elaborazione a live e diventa completato (l&#39;operazione potrebbe richiedere alcuni minuti).
> Una volta che lo stato è cambiato in completato:
>
> ![risultati push](/help/summit/l820-lab-workbook/assets/2-3-push-notification-result.png)


**Grazie!**

Grazie per la partecipazione. Inviaci un feedback su come abbiamo fatto e se il laboratorio ha soddisfatto le tue aspettative, completando il questionario Lab 820 Session nell’app Summit.

