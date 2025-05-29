---
title: Creare una campagna
description: Scopri come una campagna AJO collega tipi di pubblico, criteri decisionali e canali per distribuire offerte personalizzate al momento giusto tra i punti di contatto dei clienti.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 1%

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
   - **Nome**: `finwise-web-personalization`\
     Identifica questa configurazione per la consegna personalizzata delle offerte web di FinWise.

   - **Piattaforma**: `Web`\
     Destinato specificamente ai browser web. Nessun canale mobile abilitato.

   - **Tipo di esperienza**: `Code-based experience`\
     Le offerte non vengono iniettate direttamente nel DOM. Al contrario, AJO restituisce HTML non elaborato che viene analizzato utilizzando JavaScript personalizzato.

   - **URL pagina**: `http://localhost:3000/formula.html`\
     Il canale è configurato per una pagina di test specifica utilizzata durante lo sviluppo.

   - **Posizione a pagina**: `offers-div`\
     Le offerte restituite vengono analizzate dinamicamente e sottoposte a rendering in questo contenitore utilizzando la logica front-end.

   - **Formato contenuto**: `HTML`\
     Le offerte vengono distribuite come frammenti HTML non elaborati, che consentono il pieno controllo su come vengono formattate, filtrate e visualizzate.


2. **Avvia una nuova campagna**\
   Passa alla sezione Campagne e crea una nuova campagna con il canale web.

3. **Aggiungi azione**\
   Aggiungi un’azione basata su codice e collega l’azione a una configurazione di canale creata in precedenza.



4. **Pubblico**\
   Tutti i visitatori (impostazione predefinita).

   Tipo di identità: ECID (Experience Cloud ID)
Questa impostazione utilizza l’ECID come identità principale per il riconoscimento degli utenti. Quando è attivo l’unione di identità, ECID viene collegato all’ID del sistema di gestione delle relazioni con i clienti per selezionare Personalized Targeting o creare un criterio di decisione che definisce la logica dell’offerta.

5. **Criteri di decisione**


   L&#39;azione è collegata a un **criterio di decisione** che definisce la modalità di selezione delle offerte e il numero di offerte restituite per la visualizzazione. Questo criterio utilizza una **strategia di selezione** creata in precedenza nell&#39;esercitazione.

   La strategia di selezione è **basata su formule**, ovvero utilizza una formula di classificazione per assegnare punteggi alle offerte idonee e determinare quali devono essere prioritarie.

   La strategia comprende:

   - **Raccolta offerte**\
     Un set predefinito di offerte rilevanti per la campagna, ad esempio offerte specifiche per il codice postale o basate sul reddito.

   - **Regole di idoneità**\
     Idoneità impostata su **_Tutti i visitatori_**

   - **Formula di classificazione**\
     Un’espressione logica che valuta ogni offerta idonea. L’esperienza personalizzata esegue il rendering dell’offerta con il punteggio più alto.



6. **Pubblica la campagna**\
   Attiva la campagna per iniziare a consegnare offerte personalizzate in tempo reale.





