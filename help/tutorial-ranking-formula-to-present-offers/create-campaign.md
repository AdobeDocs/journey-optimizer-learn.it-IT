---
title: Creare una campagna
description: Scopri come una campagna AJO collega tipi di pubblico, criteri decisionali e canali per distribuire offerte personalizzate al momento giusto tra i punti di contatto dei clienti.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18188
exl-id: deb16dd5-23cd-495a-ac91-d22fd77f49bd
source-git-commit: 640faaf9a316b2ab3e2e7774b2c30612cf1b1dbe
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Creare una campagna

Per distribuire offerte personalizzate agli utenti sulla pagina web, è stata creata una campagna in Adobe Journey Optimizer e configurata con il canale web corretto. Questa configurazione assicura che le offerte vengano consegnate tramite decisioni in tempo reale agli utenti che interagiscono con il sito web.

All’interno di questa campagna, è stato definito un criterio di decisione per controllare la modalità di selezione delle offerte. La politica decisionale comprende una strategia di selezione che consiste in:

Una raccolta di articoli dell’offerta (ad esempio, basata sul codice postale o sul reddito),

Regole di idoneità che determinano le offerte valide per un utente e

Formula di classificazione che assegna punteggi alle offerte idonee per assegnare la priorità a quelle più rilevanti.

Quando un utente connesso visita il sito, viene inviata una richiesta di personalizzazione ad AJO. In base all’identità e agli attributi di profilo uniti dell’utente (come codice postale e reddito annuale), il criterio decisionale valuta tutte le offerte disponibili. Per determinare la corrispondenza migliore, applica la strategia di selezione e la logica di classificazione.

Il risultato è un set personalizzato di offerte, restituito come contenuto HTML e visualizzato all’utente in un carosello sul sito web, che crea un’esperienza personalizzata senza soluzione di continuità e in tempo reale.


## Passaggi di alto livello per creare una campagna in AJO

1. **Crea una configurazione canale**\
   Definisci dove e come vengono visualizzate le offerte (ad esempio, una pagina web con un’esperienza basata su codice).
   - Accedi a Percorsi Optimizer
Passa a _&#x200B;**Amministrazione ->Canali->Crea configurazione canale**&#x200B;_
   - **Nome**: `finwise-web-personalization`\
     Identifica questa configurazione per la consegna personalizzata delle offerte web di FinWise.

   - **Tipo di esperienza**: `Code-based experience`\
     Le offerte non vengono iniettate direttamente nel DOM. Al contrario, AJO restituisce HTML non elaborato che viene analizzato utilizzando JavaScript personalizzato.

   - **Piattaforma**: `Web`\
     Destinato specificamente ai browser web. Nessun canale mobile abilitato.


   - **URL pagina**: `http://localhost:3000/formula.html`\
     Il canale è configurato per una pagina di test specifica utilizzata durante lo sviluppo.

   - **Posizione a pagina**: `offers-div`\
     Le offerte restituite vengono analizzate dinamicamente e sottoposte a rendering in questo contenitore utilizzando la logica front-end.

   - **Formato contenuto**: `HTML`\
     Le offerte vengono distribuite come frammenti HTML non elaborati, che consentono il pieno controllo su come vengono formattate, filtrate e visualizzate.


2. **Avvia una nuova campagna**\
   Passa alla sezione Campagne e crea una nuova campagna di marketing pianificata. Assegna un nome appropriato alla campagna.


3. **Aggiungi azione**\
   Passa alla scheda _&#x200B;**Azioni**&#x200B;_
Aggiungi un’azione basata su codice e collega l’azione a una configurazione di canale creata in precedenza.



4. **Pubblico**\
   Passa alla scheda _&#x200B;**Pubblico**&#x200B;_
Tutti i visitatori (impostazione predefinita).

   Tipo di identità: ECID (Experience Cloud ID)
Questa impostazione utilizza l’ECID come identità principale per il riconoscimento degli utenti. Quando è attivo l’unione di identità, ECID viene collegato all’ID del sistema di gestione delle relazioni con i clienti per selezionare Personalized Targeting o creare un criterio di decisione che definisce la logica dell’offerta.

5. **Criteri di decisione**


   L&#39;azione è collegata a un **criterio di decisione** che definisce la modalità di selezione delle offerte e il numero di offerte restituite per la visualizzazione. Questo criterio utilizza una **strategia di selezione** creata in precedenza nell&#39;esercitazione.

   Per inserire il criterio di decisione, fai clic su **_Modifica contenuto_** nella scheda _&#x200B;**Azioni**&#x200B;_, quindi su **_Modifica codice_** per aprire l&#39;editor di personalizzazione.

   Seleziona l&#39;icona _&#x200B;**Criterio decisione**&#x200B;_ a sinistra e fai clic sul pulsante **Aggiungi criterio decisione** per aprire la schermata **Crea criterio decisione**. Specifica un nome significativo per il criterio di decisione e seleziona il numero di elementi che il criterio di decisione deve restituire. Il valore predefinito è 1.
Fai clic su **_avanti_** e aggiungi la strategia di selezione creata nel passaggio precedente al criterio di decisione, quindi fai clic su **avanti** per completare il processo di creazione del criterio di decisione. Assicurati di selezionare l’offerta di fallback appropriata.

6. **Inserisci criterio di decisione**

   Inserire il criterio di decisione appena creato facendo clic sul pulsante _&#x200B;**Inserisci criterio**&#x200B;_. Inserisce un ciclo for nell’editor di personalizzazione sul lato destro.
Posizionare il cursore tra ogni ciclo sulla riga due e inserire offerText spostandosi sull&#39;offerta espandendo `tenant name`

   Criterio di decisione inserito nell’editor di personalizzazione

   ![editor di personalizzazione](assets/personalization-editor.png)



   Il codice Handlebars esegue un ciclo tra le offerte restituite da un criterio di decisione specifico in Adobe Journey Optimizer e crea un `<div>` per ogni offerta. Ogni `<div>` utilizza un attributo di tag dati con il nome interno dell&#39;offerta per facilitare il gruppo carosello e organizzare le offerte per categoria per una navigazione fluida. Il contenuto all&#39;interno di ogni `<div>` visualizza il testo dell&#39;offerta personalizzata, consentendo una presentazione dinamica e visivamente segmentata di più offerte.

7. **Salva la campagna**

   Salva la campagna facendo clic sul pulsante _&#x200B;**Rivedi per attivare**&#x200B;_


