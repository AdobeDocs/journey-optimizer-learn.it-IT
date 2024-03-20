---
title: Lezione 3 - Creare una campagna web in-app
description: Creare e attivare una campagna web in-app.
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-13983
thumbnail: KT-13983.jpeg
source-git-commit: c509c768d07984d07ed2ec65634e000c54bb6ff1
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 0%

---



# Lezione 3 - Creare una campagna web in-app

Dopo aver creato le esperienze mobili per l’app, in questa lezione crei una delle esperienze che hai visto sul sito Fréscopa. Puoi creare una campagna in-app web. Puoi progettare e personalizzare un messaggio e definire un trigger che attiva il messaggio.

## Obiettivi di apprendimento

* Scopri come creare una campagna in-app web.
* Attiva un messaggio in-app.

## Esercizio 3.1 Creare una campagna web in-app

In questo esercizio creerai la campagna e definirai su quale pagina web apparirà il messaggio in-app.

1. In Journey Optimizer, nella barra di navigazione a sinistra, sotto **GESTIONE PERCORSO** seleziona **Campagne**.

1. Clic **Crea campagna**.

   ![CreateCampaign](/help/summit/l820-lab-workbook/assets/4-1-create-campaign.png)

1. Il giorno **Crea campagna** pagina, nella **Azione** , seleziona la sezione **Messaggio in-app** casella di controllo.

1. Dalla sezione **Invia a** a discesa, seleziona **Web.**

1. Immetti il seguente URL: **https://dsn.adobe.com/web/adobe-summit-2024/exercise** - *Pagina Web in cui verrà visualizzato il messaggio.*

   ![URL in-app](/help/summit/l820-lab-workbook/assets/4-1-1-in-app-url.png)

1. Fai clic su **[!UICONTROL Crea]**.

## Esercizio 3.2 Configurare la campagna

In questa pagina, definisci le proprietà della campagna e l’evento che attiva la visualizzazione del messaggio in-app nella pagina web. Lascia tutte le altre impostazioni sul valore predefinito. Per questo esercizio non è necessario definire un pubblico specifico.

### 3.2.1. [!UICONTROL Sezione Proprietà]

1. In **Proprietà** , assegna alla tua campagna un **Nome**:

   >[!NOTE]
   > Assicurati di iniziare il nome con il tuo numero di posto, in modo da poter
   > trova la tua campagna in un secondo momento.
   > 
   > Ad esempio, se il numero di posto è 99: 
   >
   > ![Nome proprietà](/help/summit/l820-lab-workbook/assets/4-1-2-properties-name.png)


### 3.2.2 Configurare la regola di attivazione personalizzata

In questa sezione definisci i trigger che attivano la visualizzazione del messaggio sul sito web. Puoi definire un trigger univoco che ti consente di inviare il messaggio solo a te stesso.

1. Scorri verso il basso fino a **[!UICONTROL Sezione Triggers]**, quindi fai clic su **[!UICONTROL Modifica trigger]**.

   ![modifica](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. Nel generatore di regole, fai clic su **[!UICONTROL Avvio applicazione]** e dal menu a discesa seleziona  *Dati inviati a Platform*.
   ![elenco a discesa evento trigger](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. Aggiungere una condizione facendo clic su **[!UICONTROL + Aggiungi condizione]**.

   ![pulsante aggiungi condizione](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. Dalla sezione **[!UICONTROL Seleziona una caratteristica]** a discesa, seleziona **[!UICONTROL Tipo di evento XDM]**.

   ![Tipo di evento XDM](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)


1. Nel campo di testo seguente, aggiungi *`<custom string value>`* che si ricorda e premere **[!UICONTROL Aggiungi]** `<custom string value>` per salvare il valore.

   Questo valore di stringa personalizzato viene utilizzato in seguito per attivare il messaggio.

   >[!TIP]
   > L’aggiunta del numero di posto al valore della stringa personalizzata lo renderà univoco e più facile da ricordare.
   > 
   > Ad esempio: `99web`
   > 

   ![aggiungi valore stringa trigger personalizzato](/help/summit/l820-lab-workbook/assets/4-1-2-add-custom-trigger-dropdown.png)

1. Premere il tasto **[!UICONTROL Fine]** in alto a destra.

>[!SUCCESS]
>
>Hai ora definito il messaggio web in-app con un evento trigger personalizzato.
>
>![Campagna web con trigger personalizzato definito](/help/summit/l820-lab-workbook/assets/4-1-2-2-web-campaign-with-custom-trigger.png)


### 3.2.3 Modificare il contenuto del messaggio in-app

In questa sezione puoi definire il contenuto, la progettazione e il layout del messaggio.

1. Fai clic su **Modifica contenuto** pulsante in **Azione** per accedere al costrutto di authoring.

   ![Pulsante Modifica contenuto](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

1. Il processo di authoring è lo stesso che hai completato negli esercizi in-app per dispositivi mobili sopra riportati. Modifica liberamente il messaggio con il tuo titolo, corpo e contenuto multimediale.

   Se utilizzi il layout modale o a schermo intero, puoi aggiungere un pulsante. Puoi utilizzare questo URL per aprire la pagina del prodotto: **https://dsn.adobe.com/web/adobe-summit-2024/P2WsaDPf_**

1. Al termine della modifica del messaggio, fai clic su **[!UICONTROL Controlla per attivare]**.

1. Se tutto sembra a posto nella schermata di revisione, fai clic su **[!UICONTROL Attiva]** per pubblicare il messaggio Web in-app.

1. Viene visualizzata di nuovo la dashboard di Campaign.

   Unità di attesa a cui cambia lo stato della campagna **Live** prima di passare al punto 4.1.4.

## Esercizio 3.3 Attivare il messaggio in-app web

1. Visitare il sito Web di Fréscopa e accedere al **Esercizio** sul browser.

   ![Collegamento esercizi web](/help/summit/l820-lab-workbook/assets/4-2-frescopa-web-exercise-link.png)

1. Assicurati di aggiornare la pagina web.

1. Digita il valore di stringa univoco definito nella campagna.

   ![pagina di esercizio](/help/summit/l820-lab-workbook/assets/4-2-exercise-page.png)

1. Fai clic su **[!UICONTROL Invia]**.

>[!SUCCESS]
>
>Facendo clic sul pulsante Invia con il valore univoco, il messaggio Web in-app verrà attivato. Dovresti visualizzare il messaggio in-app web sullo schermo.
>
>Questo esercizio simulava un evento di invio XDM personalizzato che hai visto attraverso la tua esperienza cliente Fréscopa.
