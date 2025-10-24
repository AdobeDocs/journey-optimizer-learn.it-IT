---
title: Creare un messaggio e-mail di benvenuto per lo stato di fedeltà - Sfida
description: Crea un percorso che invia automaticamente un’e-mail di benvenuto ai clienti quando raggiungono il livello di fedeltà.
jira: KT-8109
feature: Journeys
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: ht
source-wordcount: '403'
ht-degree: 100%

---

# Creare un messaggio e-mail di benvenuto per lo stato di fedeltà - sfida

| Sfida | Creare un messaggio e-mail di benvenuto di per lo stato di fedeltà |
|---|---|
| Persona | Gestione del percorso |
| Competenze richieste | <ul><li>[Creare segmenti](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=it)</li> <li>[Qualificazione segmento](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journeys/use-case-read-segment-qualification.html?lang=it)</li><li>[Importare contenuto HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=it)</li></ul> |
| Risorse da scaricare | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

{style="table-layout:auto"}

## Il contesto

Luma offre un programma fedeltà per attrarre e fidelizzare i propri clienti. Il programma offre quattro livelli diversi: bronzo, argento, oro e platino. Ogni livello di fedeltà riceve diversi premi, sconti e altri incentivi speciali come ricompensa per gli acquisti ripetuti.

Per mettere in evidenza lo stato platino speciale, Luma desidera inviare un’e-mail di benvenuto ai clienti quando raggiungono il livello platino.

## La tua sfida

Ti è stato chiesto di configurare un percorso che invia automaticamente un’e-mail di benvenuto ai clienti quando raggiungono il livello di fedeltà platino.

>[!BEGINTABS]

>[!TAB Attività]

Quando un cliente fidelizzato si qualifica per il livello platino, dovrebbe ricevere un’e-mail di congratulazioni in cui viene informato dei nuovi vantaggi. Il team creativo ha fornito un file HTML **[Luma - aggiornamento dello stato - e-mail di benvenuto](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** con il corpo dell’e-mail.

1. Crea un [!UICONTROL segmento] in Journey Optimizer denominato `Luma - platinum status`.

1. Crea un percorso denominato `Luma - New Status - platinum`.

   1. Un cliente entra nel percorso quando è idoneo per il livello di fedeltà platino.

   1. Il cliente deve ricevere un messaggio e-mail contrassegnato `Luma - Platinum Status - Welcome`, con l’oggetto `Welcome to Platinum Status, {firstName}!` e il corpo dell’e-mail fornito dal team creativo. Si tratta di un messaggio e-mail [!UICONTROL transazionale].

   1. Durante il caricamento del file HTML, noti che l’e-mail si riferisce allo stato “diamante”, anziché “platino”. Invece di richiedere un nuovo file al team creativo, aggiorna l’e-mail nell’[!UICONTROL E-mail Designer].

>[!TAB Criteri di successo]

Test del percorso:

1. Assicurati che l’[!UICONTROL Attività Leggi segmento] abbia lo [!UICONTROL spazio dei nomi] impostato su **[!DNL Luma CRM id(lumaCrmId)]**.

1. Sostituisci i [!UICONTROL parametri e-mail] predefiniti e impostali sul tuo indirizzo e-mail:
   * Nei **[!UICONTROL parametri e-mail]**, fai clic sul simbolo T (abilita sostituzione parametro)

   * Fai clic sul campo **[!UICONTROL Indirizzo]**.

   * Nella schermata successiva, aggiungi il tuo indirizzo e-mail tra parentesi: `"yourname@yourdomain"` nell’editor di espressioni e fai clic su **[!UICONTROL OK]**.

1. Imposta il percorso in modalità di test.

1. Seleziona **[!UICONTROL Attiva un evento]**.

1. Aggiungi il `CRM ID` seguente per `Stanleigh Stooke` nel campo **[!UICONTROL Identificatore profilo]**: `4f34057d9d9e792c28ba18ecae378e98`

**Risultato:** dovresti ricevere l’e-mail personalizzata *Luma - Stato platino - E-mail di benvenuto*.

L’e-mail dovrebbe essere così:

![Luma - aggiornamento dello stato - e-mail di benvenuto](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!TAB Verifica il tuo lavoro]

Il segmento dovrebbe essere così:

![Luma - stato platino- segmento](/help/challenges/assets/segment-luma-platinum-status.png)

Ecco come dovrebbe apparire il tuo percorso:

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)

>[!ENDTABS]
