---
title: Creare un messaggio e-mail di benvenuto per lo stato di fedeltà - sfida
description: Scopri le basi della costruzione di un percorso nell’area di lavoro del percorso.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 7a178b9c523ead0cf27aaa87d25b3752ef53f519
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 100%

---

# Creare un messaggio e-mail di benvenuto per lo stato di fedeltà - sfida

![E-mail di benvenuto per lo stato di fedeltà - Banner della sfida](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Sfida | Creare un messaggio e-mail di benvenuto di per lo stato di fedeltà |
|---|---|
| Persona | Gestione del percorso |
| Competenze richieste | <ul><li>[Creare segmenti](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=it)</li> <li>[Qualificazione del segmento](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html?lang=it)</li><li>[Importare contenuto HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=it)</li></ul> |
| Risorse da scaricare | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

## Il contesto

Luma offre un programma fedeltà per attrarre e fidelizzare i propri clienti. Il programma offre quattro livelli diversi: bronzo, argento, oro e platino. Ogni livello di fedeltà riceve diversi premi, sconti e altri incentivi speciali come ricompensa per gli acquisti ripetuti.

Per sottolineare il livello speciale platino. Luma vuole inviare un’e-mail di benvenuto ai clienti quando raggiungono il livello platino.

## La tua sfida

Ti è stato chiesto di configurare un percorso che invia automaticamente un’e-mail di benvenuto ai clienti quando raggiungono il livello di fedeltà platino.

>[!BEGINTABS]

>[!TAB Attività]

Quando un cliente fidelizzato si qualifica per il livello platino, deve ricevere un e-mail di congratulazioni in cui viene informato sui nuovi vantaggi. Il team creativo ha fornito un file HTML **[Luma - aggiornamento dello stato - e-mail di benvenuto](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** con il corpo dell’e-mail.

1. Crea un [!UICONTROL segmento] in Journey Optimizer denominato `Luma – status upgrade`.
2. Crea un percorso denominato `Luma – New Status – platinum`.
   1. Un cliente entra nel percorso quando è idoneo per il livello di fedeltà platino.
   2. Il cliente deve ricevere un messaggio e-mail contrassegnato `Luma – Platinum Status - Welcome`, con l’oggetto `Welcome to Platinum Status, (recipient's first name)!` e il corpo dell’e-mail fornito dal team creativo. Si tratta di un messaggio e-mail [!UICONTROL transazionale].
   3. Durante il caricamento del file HTML, noti che l’e-mail si riferisce allo stato “diamante”, invece di “platino”. Invece di richiedere un nuovo file al team creativo, aggiorna l’e-mail in E-mail Designer.

>[!TAB Criteri di successo]

Test del percorso:

1. Assicurati che l’[!UICONTROL Attività Leggi segmento] abbia [!UICONTROL lo spazio dei nomi] impostato su **[!DNL Luma CRM id(lumaCrmId)]**
2. Sostituisci i [!UICONTROL parametri e-mail] predefiniti e impostali sul tuo indirizzo e-mail
   * Mostra i valori nascosti facendo clic sul simbolo a forma di occhio.
   * Nei [!UICONTROL parametri e-mail], fai clic sul simbolo T (abilita sostituzione parametro)

       ![Sostituisci parametri email](/help/challenges/assets/c3-override-email-paramters.jpg)
   
   * Fai clic sul [!UICONTROL campo Indirizzo]
   * Nella schermata successiva aggiungi il tuo indirizzo e-mail tra parentesi: `"yourname@yourdomain"` nell’editor di espressioni e fai clic su ok.


3. Imposta il percorso in modalità di test
4. Attiva un evento
5. Aggiungi il [!DNL CRM ID] seguente per `Stanleigh Stooke` nel campo [!UICONTROL Identificatore profilo]: `4f34057d9d9e792c28ba18ecae378e98`

**Risultato:** dovresti ricevere il messaggio personalizzato *Luma - Stato platino - Email di Benvenuto*.

>[!TAB Verifica il tuo lavoro]

Ecco come dovrebbe apparire il tuo percorso:

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)


Ecco come dovrebbe apparire la tua e-mail:

![Luma - aggiornamento dello stato - e-mail di benvenuto](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!ENDTABS]
