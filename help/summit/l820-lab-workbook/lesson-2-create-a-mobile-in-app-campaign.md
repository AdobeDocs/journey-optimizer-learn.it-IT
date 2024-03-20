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
source-git-commit: c509c768d07984d07ed2ec65634e000c54bb6ff1
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 0%

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
   ![Popup Personalizzazione](/help/summit/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Devi aver effettuato l’accesso a Journey Optimizer e alla pagina home:
>
>![Home page AJO](/help/summit/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## Esercizio 2.2 Creare una campagna in-app mobile

In questo esercizio creerai una campagna di messaggistica in-app, che viene attivata, quando apri l’app.

1. In Journey Optimizer, nella navigazione a sinistra, seleziona **[!UICONTROL Campagne]**.

1. Clic **[!UICONTROL Crea campagna]**.

   ![Crea campagna](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. Il giorno **[!UICONTROL Crea campagna]** pagina, nella  **[!UICONTROL Azione]** , seleziona la sezione **[!UICONTROL Messaggio in-app]** casella di controllo.

1. Dalla sezione **[!UICONTROL Invia a]** a discesa, seleziona **[!DNL Mobile]**.

1. Dalla sezione **[!UICONTROL Superficie app]** a discesa, seleziona **[!DNL Frecopa Mobile App]**.

1. Fai clic su **[!UICONTROL Crea]**.

   ![Superficie app](/help/summit/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>Ora dovresti essere nelle proprietà Campaign:
>
> ![Proprietà della campagna](/help/summit/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## Esercizio 2.3 Configurare la campagna

### 2.3.1. [!UICONTROL Sezione Proprietà]

Assegna un nome alla campagna. Assicurati di iniziare il nome con il numero di posto, in modo da poter trovare facilmente di nuovo la campagna.

Ad esempio, se il numero di posto è 99:  `99 - Welcome Campaign`.

![sezione proprietà](/help/summit/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2 Configurare la regola di attivazione personalizzata

1. Scorri verso il basso fino a **[!UICONTROL Sezione Triggers]**, quindi fai clic su **[!UICONTROL Modifica trigger]**.

   ![modifica](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. Nel generatore di regole, fai clic su **[!UICONTROL Avvio applicazione]** e dal menu a discesa seleziona  *Dati inviati a Platform*.
   ![Inviato a Data Platform](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. Aggiungere una condizione facendo clic su **[!UICONTROL Aggiungi condizione]**.

   ![pulsante aggiungi condizione](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. Dalla sezione **[!UICONTROL Seleziona una caratteristica]** a discesa, seleziona **[!UICONTROL Tipo di evento XDM]**.

   ![Tipo di evento XDM](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. Nel campo di testo seguente, aggiungi *`<custom string value>`* che tu possa ricordare.

1. Per salvare il valore, fai clic su **[!UICONTROL Aggiungi**] `<custom string value>`.

   Questo valore di stringa personalizzato viene utilizzato in seguito per attivare il messaggio.

   >[!TIP]
   > L’aggiunta del numero di posto al valore della stringa personalizzata lo rende univoco e più facile da ricordare.
   > 
   > Ad esempio: `99exerciseTrigger`

   ![aggiungi valore stringa trigger personalizzato](/help/summit/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. Clic **[!UICONTROL Fine]** in alto a destra.

>[!SUCCESS]
>
>Ora hai definito il messaggio in-app con un evento trigger personalizzato.
>
>![Campagna con trigger personalizzato definito](/help/summit/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3 Modificare il contenuto del messaggio in-app

In **[!UICONTROL Azione]** , fare clic su **[!UICONTROL Modifica contenuto]**.

![Pulsante Modifica contenuto](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

Il [!UICONTROL Messaggio in-app] viene visualizzato l’editor, in cui puoi configurare il contenuto del messaggio in-app.

#### 2.3.3.1 Layout

Seleziona il layout da applicare al messaggio.

Ad esempio, fai clic su **[!UICONTROL Modale]** per rendere il messaggio in-app un layout modale.

![pulsante modale](/help/summit/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2 Authoring del messaggio e pubblicazione della campagna

1. Nella sezione relativa ai file multimediali, incolla il seguente URL:  `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
Quando fai clic all’esterno del campo del valore, viene visualizzata l’immagine.

   ![file multimediali visualizzati nell’anteprima](/help/summit/l820-lab-workbook/assets/3-1-3-2-media.png)

2. Nei seguenti casi **[!UICONTROL Contenuto]** , aggiungi nel testo personalizzato che desideri visualizzare nel messaggio per il **[!UICONTROL Intestazione]** e **[!UICONTROL Corpo]**.

   ![Intestazione e corpo](/help/summit/l820-lab-workbook/assets/3-1-3-2-content.png)

3. Opzioni aggiuntive:
   1. **Pulsanti:**

      ![Sezione Pulsanti](/help/summit/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. In questa sezione dell’editor, puoi personalizzare il testo per il pulsante CTA modificando il campo Testo pulsante.

      2. Il **[!UICONTROL Evento di interazione]** Questo campo viene utilizzato per definire il valore passato all&#39;SDK quando l&#39;utente preme il CTA.

      3. Il **[!UICONTROL Target]** viene utilizzato per definire dove desideri che il CTA porti l’utente. Ciò include URL e collegamenti diretti. Ad esempio, puoi aggiungere questo collegamento profondo a una pagina di prodotto come `dxdemo://exoticVibes`.

      4. È possibile aggiungere altri pulsanti premendo **[!UICONTROL + Pulsante Aggiungi]**.

      5. Quando si aggiunge un secondo pulsante al messaggio, è ora possibile modificare il layout del pulsante con la casella a discesa.


   2. **Formattazione avanzata**

      ![attivazione/disattivazione formattazione avanzata](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      L’attivazione di questa opzione offre ulteriori opzioni di personalizzazione nell’editor.

      1. Dimensione file multimediale
      1. Font
      1. Dimensione Pt
      1. Colore font
      1. Allineamento

      ![opzioni di formattazione avanzate](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **Scheda Impostazioni**

      Passando a questa scheda e nella **[!UICONTROL Anteprima]** , è possibile modificare la sezione **Anteprima app**.
      <br>\
      ![Scheda Impostazioni](/help/summit/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. Il **[!UICONTROL Layout]** Questa sezione consente di utilizzare un&#39;immagine come sfondo o come colore a tinta unita.

      2. Il **[!UICONTROL Messaggio]** Questa sezione descrive le interazioni personalizzate che possono essere abilitate per il messaggio:
         1. Movimenti personalizzati
         2. Acquisizione interfaccia utente
         3. Acquisizione interfaccia utente personalizzata
         4. Dimensioni personalizzate
         5. Posizione personalizzata
         6. Animazione personalizzata
         7. Angolo rotondo del messaggio
   <br>
4. Al termine dell’authoring dei contenuti e quando il messaggio ti soddisfa, fai clic su **[!UICONTROL Controlla per attivare] pulsante**.

   >[!SUCCESS]
   >
   > Hai completato l’authoring del messaggio in-app mobile. Ora dovresti essere nella campagna **[!UICONTROL Controlla per attivare]** pagina.
   >
   >![rivedere e attivare](/help/summit/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > Qui potrai visualizzare un riepilogo completo del messaggio.
   >
   > *Tieni presente il valore personalizzato utilizzato quando attivi la regola. Questo valore verrà utilizzato per attivare il messaggio in-app. Il valore utilizzato si trova in nell’area di evidenziazione della pagina di riepilogo.*

   >[!NOTE]
   >Il trigger corrente per il messaggio in-app è quello predefinito **Si verifica un evento di avvio dell’applicazione**, il che significa che il messaggio in-app viene attivato all’avvio dell’app. È visibile in **[!UICONTROL Sezione Pianificazione]**.

5. Se hai terminato la revisione della campagna, premi il pulsante Attiva per pubblicarla.
   <br>
   ![attivare](/help/summit/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> Ora dovresti vedere la dashboard Campagne. Individua la campagna scorrendo o utilizzando la funzione di ricerca. Quando lo stato della campagna cambia in **[!UICONTROL Live]** (~1 min), la campagna è stata pubblicata.
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
> *In caso di problemi durante l’attivazione del messaggio, verifica quanto segue:*
> 
> * *Nel campo Nome evento dell’app mobile, accertati di digitare nel valore della regola del trigger esattamente come era nell’app Campaign.*
> * *Verificare che le maiuscole siano corrette e che non sia presente uno spazio iniziale o finale.*
> * *Puoi cercare il valore della regola di attivazione utilizzato se torni alla pagina di revisione della campagna facendo clic di nuovo sulla campagna nel dashboard della campagna.*

Hai appena creato e pubblicato il tuo primo messaggio in-app Journey Optimizer.


## Esercizio aggiuntivo: Duplica campagna e Anteprima sul dispositivo

Il **Duplica campagna** e **Anteprima sul dispositivo** Le funzioni sono funzionalità pronte all’uso che ti consentono di duplicare le campagne e di testare e rivedere i messaggi in-app direttamente sul dispositivo prima di attivarlo. Questo esercizio illustra come utilizzare questa funzione e visualizzare in anteprima il messaggio creato nell&#39;esercizio 3.1.

1. Apri la campagna appena creata facendo clic sul nome della campagna nella pagina del dashboard Campagne. Questo ti riporterà al **[!UICONTROL Rivedi campagna]** pagina.
1. Premere il tasto **[!UICONTROL Pulsante Duplica]**. Verrà aperto un nuovo prompt per assegnare un nome alla nuova campagna da duplicare. Aggiungi un nuovo nome che si ricorda facilmente o ha utilizzato il nome predefinito in cui **[!DNL _copy]** viene aggiunto per impostazione predefinita.

   ![campagna duplicata](/help/summit/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. Una volta premuto il pulsante Duplica, verrà creata la campagna duplicata e verrai reindirizzato al dashboard Campagne.
1. Una volta duplicata la campagna, apri la nuova campagna.

1. È possibile accedere alla funzione Anteprima sul dispositivo nella **[!UICONTROL Revisione della campagna]** pagina o sul **[!UICONTROL Autore della campagna]** passaggio.

   ![pulsante anteprima sul dispositivo](/help/summit/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. Quindi, fai clic su **[!UICONTROL pulsante di avvio]** dalla schermata connetti al dispositivo.

   ![pulsante di avvio](/help/summit/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. Immetti l’URL di base configurato per avviare l’app Fréscopa: `dxdemo://`

   ![url di anteprima](/help/summit/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. Seguire le istruzioni visualizzate sullo schermo:
   1. Scansiona il codice QR con il tuo dispositivo mobile e l’app Fréscopa si apre con una schermata che ti consente di inserire un pin visualizzato.
   2. Inserisci il pin mostrato in AJO nella schermata Assurance sul dispositivo e fai clic sul pulsante Connect (Connetti) che appare in basso a destra una volta inserito il pin.


   ![inserisci il pin](/help/summit/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. Questo pop-up viene visualizzato sullo schermo del computer

   ![pop-up](/help/summit/l820-lab-workbook/assets/3-3-pop-up.png)

1. Fare clic sul pulsante Fine. In questo modo la finestra di dialogo verrà chiusa e il telefono sarà collegato a Anteprima sul dispositivo.


>[!SUCCESS]
>
> Il messaggio in-app viene visualizzato sul dispositivo.
>
> *Una volta connesso, il messaggio in-app dovrebbe essere visualizzato ogni volta, fai clic sul pulsante **[!UICONTROL Anteprima sul dispositivo] pulsante**.*