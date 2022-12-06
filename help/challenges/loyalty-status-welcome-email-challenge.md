---
title: Creare un messaggio e-mail di benvenuto per lo stato di fedeltà - Sfida
description: Scopri le basi della costruzione di un percorso nell’area di lavoro del percorso.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 7ef41f1ddd9369d45b60e1e257121ef4daabbc0e
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 4%

---

# Creare un messaggio e-mail di benvenuto per lo stato di fedeltà - Sfida

![E-mail di benvenuto sullo stato della fedeltà - Banner della sfida](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Sfida | Creare un messaggio e-mail di benvenuto per lo stato di fedeltà |
|---|---|
| Persona | Percorsi Manager |
| Competenze richieste | <ul><li>[Creare segmenti](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html)</li> <li>[Qualificazione del segmento](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html)</li><li>[Importare contenuto HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html)</li></ul> |
| Risorse da scaricare | [platinumStatusEmail.zip](/help/challenges/assets/email-assets/platinumStatusEmail.zip) |

## La storia

Luma offre un programma fedeltà come modo per attrarre e trattenere i propri clienti. Il programma offre quattro livelli diversi: Bronzo, argento, oro e platino. Ogni livello di fedeltà riceve diversi livelli o premi, sconti e altri incentivi speciali come ricompensa per la loro attività ripetuta.

Sottolineare lo stato speciale del platino. Luma vuole inviare un’e-mail di benvenuto ai clienti, quando raggiungono il livello di platino.

## La tua sfida

Ti è stato chiesto di configurare un percorso che invia automaticamente un’e-mail di benvenuto ai clienti quando raggiungono il livello di fedeltà platinum.

>[!BEGINTABS]

>[!TAB Attività]

Quando un cliente fidelizzato si qualifica per il livello platino, dovrebbe ricevere e-mail per congratularsi e informarli dei suoi nuovi vantaggi. Il team creativo ha fornito un file HTML **[Luma - aggiornamento dello stato - benvenuto eMail](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** con il corpo dell’e-mail.

1. Crea un [!UICONTROL segmento] in Journey Optimizer denominato `Luma – status upgrade`.
2. Crea un percorso denominato `Luma – New Status – platinum`.
   1. Un cliente entra nel percorso quando si qualifica per il livello di fedeltà platino.
   2. Il cliente deve ricevere un messaggio e-mail contrassegnato `Luma – Platinum Status - Welcome`, con l&#39;oggetto `Welcome to Platinum Status, (recipient's first name)!` con il corpo dell’e-mail fornito dal team creativo.
   3. Quando carichi il file HTML, noterai che l’e-mail si riferisce allo stato &quot;diamante&quot;, invece di &quot;platino&quot;. Invece di richiedere un nuovo file al team creativo, aggiorna l’e-mail in E-mail Designer.

>[SUGGERISCI!]
> Assicurati che Luma - Stato Platinum - E-mail di benvenuto sia[!UICONTROL transazionale].


>[!TAB Criteri di successo]

Test del percorso:

1. Assicurati che il [!UICONTROL Attività Leggi segmento] ha [!UICONTROL namespace] impostato su **[!DNL Luma CRM id(lumaCrmId)]**
2. Ignora impostazioni predefinite [!UICONTROL parametri e-mail] e impostalo sul tuo indirizzo e-mail

+++ Fai clic qui per ulteriori informazioni su come ignorare il [!Parametri e-mail UICONTROL].

* Mostrare i valori nascosti facendo clic sul simbolo dell&#39;occhio.
* In [!UICONTROL Parametri e-mail], fai clic sul simbolo T (abilita sostituzione parametro)

![Ignorare i parametri e-mail](/help/challenges/assets/c3-override-email-paramters.jpg)

* Fai clic su [!UICONTROL Campo indirizzo]
* Nella schermata successiva aggiungi il tuo indirizzo e-mail tra parentesi: `"yourname@yourdomain"` nell’editor espressioni e fai clic su ok.
+++

1. Impostare il percorso sulla modalità di prova
2. Attiva un evento
3. Aggiungi quanto segue [!DNL CRM ID] per [!DNL Stanleigh Stooke] nel [!UICONTROL Identificatore profilo] campo: `4f34057d9d9e792c28ba18ecae378e98`

Dovresti ricevere il *Luma - Stato platino - Benvenuto* e-mail.

>[!TAB Controlla il tuo lavoro]

Ecco come dovrebbe essere il tuo percorso:

![platinum-status-upgrade-percorso](/help/challenges/assets/journey-luma-status-upgrade.png)


Questo è l’aspetto dell’e-mail:

![Luma - aggiornamento dello stato - benvenuto eMail](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!ENDTABS]
