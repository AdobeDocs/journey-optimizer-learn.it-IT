---
title: Creare un messaggio e-mail di benvenuto per lo stato di fedeltà - sfida
description: Scopri le basi della costruzione di un percorso nell’area di lavoro del percorso.
kt: 8109
feature: Journeys
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: f7bfe367411f2bae23631ac4ecb34ad1d250381c
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 65%

---

# Creare un messaggio e-mail di benvenuto per lo stato di fedeltà - sfida

![E-mail di benvenuto per lo stato di fedeltà - Banner della sfida](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Sfida | Creare un messaggio e-mail di benvenuto di per lo stato di fedeltà |
|---|---|
| Persona | Gestione del percorso |
| Competenze richieste | <ul><li>[Creare segmenti](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=it)</li> <li>[Qualificazione del segmento](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html?lang=it)</li><li>[Importare contenuto HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=it)</li></ul> |
| Risorse da scaricare | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

{style=&quot;table-layout:auto&quot;}

## Il contesto

Luma offre un programma fedeltà per attrarre e fidelizzare i propri clienti. Il programma offre quattro livelli diversi: bronzo, argento, oro e platino. Ogni livello di fedeltà riceve diversi premi, sconti e altri incentivi speciali come ricompensa per gli acquisti ripetuti.

Per sottolineare lo stato speciale platino, Luma desidera inviare un’e-mail di benvenuto ai clienti quando raggiungono il livello platino.

## La tua sfida

Ti è stato chiesto di configurare un percorso che invia automaticamente un’e-mail di benvenuto ai clienti quando raggiungono il livello di fedeltà platino.

>[!BEGINTABS]

>[!TAB Attività]

Quando un cliente fidelizzato si qualifica per il livello platino, deve ricevere un’e-mail di congratulazioni per informarlo dei nuovi vantaggi. Il team creativo ha fornito un file HTML **[Luma - aggiornamento dello stato - e-mail di benvenuto](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** con il corpo dell’e-mail.

1. Crea un [!UICONTROL segmento] in Journey Optimizer denominato `Luma - platinum status`.

1. Crea un percorso denominato `Luma - New Status - platinum`.

   1. Un cliente entra nel percorso quando si qualifica per il livello di fedeltà platino.

   1. Il cliente deve ricevere un messaggio e-mail contrassegnato `Luma - Platinum Status - Welcome`, con l’oggetto `Welcome to Platinum Status, {firstName}!` e il corpo dell’e-mail fornito dal team creativo. Questo è un [!UICONTROL transazionale] e-mail.

   1. Durante il caricamento del file HTML, noti che l’e-mail si riferisce allo stato “diamante”, invece di “platino”. Invece di richiedere un nuovo file al team creativo, aggiorna l’e-mail nell’[!UICONTROL E-mail Designer].

>[!TAB Criteri di successo]

Test del percorso:

1. Assicurati che [!UICONTROL Attività Leggi segmento] ha [!UICONTROL namespace] imposta su **[!DNL Luma CRM id(lumaCrmId)]**.

1. Sostituisci i [!UICONTROL parametri e-mail] predefiniti e impostali sul tuo indirizzo e-mail:
   * In **[!UICONTROL Parametri e-mail]**, fare clic sul simbolo T (abilita sostituzione parametro)

   * Fai clic su **[!UICONTROL Indirizzo]** campo.

   * Nella schermata successiva, aggiungi il tuo indirizzo e-mail tra parentesi: `"yourname@yourdomain"` nell’editor espressioni, fai clic su **[!UICONTROL OK]**.

1. Imposta il percorso in modalità di test.

1. Seleziona **[!UICONTROL Attiva un evento]**.

1. Aggiungi quanto segue `CRM ID` per `Stanleigh Stooke` nel **[!UICONTROL Identificatore profilo]** campo: `4f34057d9d9e792c28ba18ecae378e98`

**Risultato:** Dovresti ricevere il *Luma - Stato platino - Benvenuti* e-mail.

Ecco come dovrebbe apparire la tua e-mail:

![Luma - aggiornamento dello stato - e-mail di benvenuto](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!TAB Verifica il tuo lavoro]

Il segmento dovrebbe essere così:

![Luma - stato platino- segmento](/help/challenges/assets/segment-luma-platinum-status.png)

Ecco come dovrebbe apparire il tuo percorso:

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)

>[!ENDTABS]
