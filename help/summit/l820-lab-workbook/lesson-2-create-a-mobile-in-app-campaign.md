---
title: Lezione 2 - Creare una campagna in-app mobile
description: Creare e attivare una campagna in-app mobile.
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14983
thumbnail: KT-14983.jpeg
exl-id: fe18eca7-229c-4867-ab34-1862bad63124
source-git-commit: 4f5c92f79eba3651b3633b7850e993160cb1f72c
workflow-type: tm+mt
source-wordcount: '1434'
ht-degree: 1%

---

# Lezione 2 - Creare una campagna in-app mobile

In questa lezione, puoi creare e attivare messaggi in-app mobili.

## Finalità di apprendimento

* Scopri come vengono attivati i messaggi in-app.
* Scopri come creare una campagna in-app mobile.
* Attiva un messaggio in-app.

## Esercizio 2.1 - Accesso a Journey Optimizer

1. Apri [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}
2. Effettua il login utilizzando i seguenti dettagli:
   <br>
   **Nome utente:** L820+**`<your seat number>`**@adobeeventlab.com
   **Password:**   Adobe 2024!
   <br>
I dettagli per l&#39;accesso sono disponibili sul desktop lab machine. Utilizza l’Adobe ID e la password.
   ![desktop](/help/summit/l820-lab-workbook/assets/desk-top.png)

   ![Schermata di accesso](/help/summit/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. È possibile saltare le due schermate successive:
   <br>
   ![Numero di telefono](/help/summit/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   ![Popup Personalization](/help/summit/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Devi aver effettuato l’accesso a Journey Optimizer e alla pagina home:
>
>![Home page AJO](/help/summit/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## Esercizio 2.2 Creare una campagna in-app mobile

In questo esercizio creerai una campagna di messaggistica in-app, che viene attivata, quando apri l’app.

1. In Journey Optimizer, nella barra di navigazione a sinistra, seleziona **[!UICONTROL Campagne]**.

1. Fai clic su **[!UICONTROL Crea campagna]**.

   ![Crea campagna](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. Nella pagina **[!UICONTROL Crea campagna]**, nella sezione **[!UICONTROL Azione]**, seleziona la casella di controllo **[!UICONTROL Messaggio in-app]**.

1. Dal menu a discesa **[!UICONTROL Invia a]**, selezionare **[!DNL Mobile]**.

1. Dal menu a discesa **[!UICONTROL Superficie app]**, seleziona **[!DNL Frecopa Mobile App]**.

1. Fai clic su **[!UICONTROL Crea]**.

   ![Superficie app](/help/summit/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>Ora dovresti essere nelle proprietà Campaign:
>
> ![Proprietà campagna](/help/summit/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## Esercizio 2.3 Configurare la campagna

### 2.3.1 [!UICONTROL Sezione proprietà]

Assegna un nome alla campagna. Assicurati di iniziare il nome con il numero di posto, in modo da poter trovare facilmente di nuovo la campagna.

Ad esempio, se il numero di posto è 99: `99 - Welcome Campaign`.

![sezione proprietà](/help/summit/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2 Configurare la regola di attivazione personalizzata

1. Scorri verso il basso fino alla sezione **[!UICONTROL Triggers]**, quindi fai clic su **[!UICONTROL Modifica trigger]**.

   ![modifica](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. Nel generatore di regole, fai clic su **[!UICONTROL Avvio applicazione]** e dal menu a discesa seleziona *Dati inviati a Platform*.
   ![Inviato a Data Platform](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. Aggiungere una condizione facendo clic su **[!UICONTROL Aggiungi condizione]**.

   ![aggiungi pulsante condizione](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. Dall&#39;elenco a discesa **[!UICONTROL Seleziona una caratteristica]**, seleziona il tipo di evento **[!UICONTROL XDM]**.

   ![Tipo di evento XDM](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. Nel seguente campo di testo, aggiungere un *`<custom string value>`* che si ricordi.

1. Per salvare il valore, fare clic su **[!UICONTROL Aggiungi**] `<custom string value>`.

   Questo valore di stringa personalizzato viene utilizzato in seguito per attivare il messaggio.

   >[!TIP]
   > L’aggiunta del numero di posto al valore della stringa personalizzata lo rende univoco e più facile da ricordare.
   > 
   > Ad esempio: `99exerciseTrigger`

   ![aggiungi valore stringa trigger personalizzato](/help/summit/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. Fai clic su **[!UICONTROL Fine]** in alto a destra.

>[!SUCCESS]
>
>Ora hai definito il messaggio in-app con un evento trigger personalizzato.
>
>![Campagna con trigger personalizzato definito](/help/summit/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3 Modificare il contenuto del messaggio in-app

Nella sezione **[!UICONTROL Azione]**, fai clic su **[!UICONTROL Modifica contenuto]**.

![Pulsante Modifica contenuto](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

Viene visualizzato l&#39;editor del messaggio in-app [!UICONTROL 1&rbrace; in cui puoi configurare il contenuto del messaggio in-app.]

#### 2.3.3.1 Layout

Seleziona il layout da applicare al messaggio.

Ad esempio, fai clic su **[!UICONTROL Modale]** per rendere il messaggio in-app un layout modale.

![pulsante modale](/help/summit/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2 Authoring del messaggio e pubblicazione della campagna

1. Nella sezione supporto, incolla il seguente URL: `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
Quando fai clic all’esterno del campo del valore, viene visualizzata l’immagine.

   ![file multimediali visualizzati nell&#39;anteprima](/help/summit/l820-lab-workbook/assets/3-1-3-2-media.png)

2. Nella seguente sezione **[!UICONTROL Contenuto]**, aggiungi nel testo personalizzato che vuoi visualizzare nel messaggio per **[!UICONTROL Intestazione]** e **[!UICONTROL Corpo]**.

   ![Intestazione e corpo](/help/summit/l820-lab-workbook/assets/3-1-3-2-content.png)

3. Opzioni aggiuntive:
   1. **Pulsanti:**

      ![Sezione pulsanti](/help/summit/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. In questa sezione dell’editor, puoi personalizzare il testo per il pulsante CTA modificando il campo Testo pulsante.

      2. Il campo **[!UICONTROL Interact event]** viene utilizzato per definire il valore passato all&#39;SDK quando l&#39;utente preme il CTA.

      3. Il campo **[!UICONTROL Target]** viene utilizzato per definire dove si desidera che il CTA porti l&#39;utente. Ciò include URL e collegamenti diretti. Ad esempio, è possibile aggiungere questo collegamento profondo a una pagina di prodotto come `dxdemo://exoticVibes`.

      4. È possibile aggiungere altri pulsanti premendo **[!UICONTROL + Pulsante Aggiungi]**.

      5. Quando si aggiunge un secondo pulsante al messaggio, è ora possibile modificare il layout del pulsante con la casella a discesa.


   2. **Formattazione avanzata**

      ![opzione di formattazione avanzata](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      L’attivazione di questa opzione offre ulteriori opzioni di personalizzazione nell’editor.

      1. Dimensione file multimediale
      1. Font
      1. Dimensione in punti
      1. Colore font
      1. Allineamento

      ![opzioni di formattazione avanzate](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **Scheda Impostazioni**

      Passando a questa scheda e nella sezione **[!UICONTROL Anteprima]**, puoi modificare la **Anteprima app**.
      <br>\
      ![Scheda Impostazioni](/help/summit/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. La sezione **[!UICONTROL Layout]** consente di utilizzare un&#39;immagine come sfondo o un colore a tinta unita.

      2. La sezione **[!UICONTROL Messaggio]** fornisce interazioni personalizzate che possono essere abilitate per il messaggio:
         1. Movimenti personalizzati
         2. Acquisizione interfaccia utente
         3. Acquisizione interfaccia utente personalizzata
         4. Dimensioni personalizzate
         5. Posizione personalizzata
         6. Animazione personalizzata
         7. Angolo arrotondato messaggio

   <br>
4. Al termine dell&#39;authoring dei contenuti e quando si è soddisfatti del messaggio, fare clic sul pulsante **[!UICONTROL Controlla per attivare]**.

   >[!SUCCESS]
   >
   > Hai completato l’authoring del messaggio in-app mobile. Dovresti essere sulla pagina **[!UICONTROL Rivedi per attivare]** la campagna.
   >
   >![verifica e attiva](/help/summit/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > Qui potrai visualizzare un riepilogo completo del messaggio.
   >
   > *Prendere nota del valore personalizzato utilizzato quando si attiva la regola. Questo valore verrà utilizzato per attivare il messaggio in-app. Il valore utilizzato si trova nell&#39;area di evidenziazione della pagina di riepilogo.*

   >[!NOTE]
   >Il trigger corrente per il messaggio in-app è l&#39;**evento di avvio applicazione predefinito che si verifica**. Ciò significa che il messaggio in-app viene attivato all&#39;avvio dell&#39;app. È possibile visualizzarlo nella **[!UICONTROL sezione Pianificazione]**.

5. Se hai terminato la revisione della campagna, premi il pulsante Attiva per pubblicarla.
   <br>
   ![attiva](/help/summit/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> Ora dovresti vedere la dashboard Campagne. Individua la campagna scorrendo o utilizzando la funzione di ricerca. Quando lo stato della campagna cambia in **[!UICONTROL Live]** (~1min), la campagna è stata pubblicata.
>
> ![Campagna pubblicata](/help/summit/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## Esercizio 2.4 Attivare il messaggio in-app mobile

Per aggiornare il payload e scaricare la campagna appena pubblicata:

1. Sul tuo dispositivo mobile, chiudi completamente l’app Fréscopa.
2. Riapri l’app Fréscopa.
3. Ora passa alla scheda Esercizio dell’app.

   ![Pulsante Esercizio](/help/summit/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. Nel campo di testo, digita il valore del trigger personalizzato definito in Campaign. Quindi premere Submit.


   ![modifica](/help/summit/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>Facendo clic su Invia, hai attivato manualmente un trigger e viene visualizzata la notifica in-app creata:
>
>![Messaggio in-app](/help/summit/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *In caso di problemi durante l&#39;attivazione del messaggio, verificare quanto segue:*
> 
> * *Nel campo Nome evento dell&#39;app mobile, assicurati di digitare nel valore della regola del trigger esattamente come era nella campagna.*
> * *Verificare che le lettere maiuscole siano corrette e che non sia presente uno spazio iniziale o finale.*
> * *Puoi cercare il valore della regola di attivazione utilizzato se torni alla pagina di revisione della campagna facendo clic di nuovo sulla campagna nel dashboard della campagna.*

Hai appena creato e pubblicato il tuo primo messaggio in-app Journey Optimizer.


## Esercizio aggiuntivo: Duplica campagna e Anteprima sul dispositivo

Le funzionalità **Duplica campagna** e **Anteprima sul dispositivo** sono funzionalità predefinite che consentono di duplicare le campagne e testare e rivedere i messaggi in-app direttamente sul dispositivo prima di attivarlo. Questo esercizio illustra come utilizzare questa funzione e visualizzare in anteprima il messaggio creato nell&#39;esercizio 3.1.

1. Apri la campagna appena creata facendo clic sul nome della campagna nella pagina del dashboard Campagne. Ti riporterà alla pagina **[!UICONTROL Rivedi campagna]**.
1. Premere il pulsante **[!UICONTROL Duplica]**. Verrà aperto un nuovo prompt per assegnare un nome alla nuova campagna da duplicare. Aggiungi un nuovo nome che si ricorda facilmente o ha usato il nome predefinito in cui **[!DNL _copy]** viene aggiunto per impostazione predefinita.

   ![campagna duplicata](/help/summit/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. Una volta premuto il pulsante Duplica, verrà creata la campagna duplicata e verrai reindirizzato al dashboard Campagne.
1. Una volta duplicata la campagna, apri la nuova campagna.

1. Puoi accedere alla funzione Anteprima sul dispositivo nella pagina **[!UICONTROL Revisione campagna]** o nel passaggio **[!UICONTROL Autore campagna]**.

   ![pulsante Anteprima sul dispositivo](/help/summit/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. Fare clic sul pulsante **[!UICONTROL avvia]** nella schermata di connessione al dispositivo.

   ![pulsante Start](/help/summit/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. Immettere l&#39;URL di base configurato per avviare l&#39;app Fréscopa: `dxdemo://`

   ![url anteprima](/help/summit/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. Seguire le istruzioni visualizzate sullo schermo:
   1. Scansiona il codice QR con il tuo dispositivo mobile e l’app Fréscopa si apre con una schermata che ti consente di inserire un pin visualizzato.
   2. Inserisci il pin mostrato in AJO nella schermata Assurance sul dispositivo e fai clic sul pulsante Connect (Connetti) che appare in basso a destra una volta inserito il pin.


   ![immetti il pin](/help/summit/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. Questo pop-up viene visualizzato sullo schermo del computer

   ![popup](/help/summit/l820-lab-workbook/assets/3-3-pop-up.png)

1. Fare clic sul pulsante Fine. In questo modo la finestra di dialogo verrà chiusa e il telefono sarà collegato a Anteprima sul dispositivo.


>[!SUCCESS]
>
> Il messaggio in-app viene visualizzato sul dispositivo.
>
> *Una volta connesso, il messaggio in-app dovrebbe essere visualizzato ogni volta, fai clic sul pulsante **[!UICONTROL Anteprima sul dispositivo]**.

## Risorse aggiuntive

**Video:**

* [Creare una campagna in-app](/help/channels/create-an-in-app-campaign.md)
* [Creare un messaggio in-app](/help/channels/author-in-app-messages.md)

**Documentazione del prodotto:**

* [Introduzione al canale in-app](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/in-app/get-started-in-app)
* [Creare un messaggio in-app mobile](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/in-app/create-in-app)
* [Creare contenuto in-app](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/in-app/design-in-app)
* [Controlla e invia la notifica in-app](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/in-app/send-in-app)
