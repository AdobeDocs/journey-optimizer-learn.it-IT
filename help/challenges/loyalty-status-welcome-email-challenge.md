---
title: Creare un messaggio e-mail di benvenuto per lo stato di fedeltà - Sfida
description: Scopri le basi della costruzione di un percorso nell’area di lavoro del percorso.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
source-git-commit: 957515149af1281d29a45b24ca499ef097656eb8
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 8%

---


# Creare un messaggio e-mail di benvenuto per lo stato di fedeltà - Sfida

![Messaggio e-mail di benvenuto per lo stato di fedeltà AJO - Banner della sfida](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Sfida | Creare un messaggio e-mail di benvenuto per lo stato di fedeltà |
|---|---|
| Persona | Percorsi Manager |
| Competenze richieste | <ul><li>[Creare contenuti e-mail con l’editor messaggi](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[Utilizzare informazioni contestuali sugli eventi per la personalizzazione](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[Utilizzare funzioni di assistenza per la personalizzazione](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| Risorse da scaricare | [Risorse di conferma dell’ordine](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## La storia

Luma offre un programma fedeltà come modo per attrarre e trattenere i propri clienti. Il programma offre quattro livelli diversi: Argento, oro, platino e diamante.

Ogni livello di fedeltà riceve diversi livelli o premi, sconti e altri incentivi speciali come ricompensa per la loro attività ripetuta.

Sottolineare lo stato speciale del diamante. Luma vuole inviare un’e-mail di benvenuto ai clienti, quando raggiungono il livello diamante.

## La tua sfida

Ti è stato chiesto di configurare un percorso che invia automaticamente un’e-mail di benvenuto ai clienti quando raggiungono il livello di fedeltà diamante.

>[!NOTE]
> Se lavori in una sandbox di formazione condivisa, è consigliabile aggiungere il nome o le iniziali come prefisso al nome di qualsiasi elemento creato.

### Crea un segmento Stato rombo luma.

Crea un segmento in Journey Optimizer denominato **il tuo nome - Luma - Diamante Status**.

### Crea Luma - Nuovo stato - Diamante - Messaggio e-mail transazionale

Creare un messaggio e-mail di benvenuto

1. Creare un messaggio e-mail transazionale denominato `(your name)_Luma – New Status – Diamond – Transactional email message`.
2. Assegna all’e-mail un oggetto `Welcome to Diamond Status, (recipient's first name)!`.
3. Utilizza il file HTML fornito **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** per il corpo dell’e-mail.


### **Percorso #3 - Diamond status upgrade email di benvenuto**

Invia un&#39;e-mail quando un cliente fidelizzato si sposta su un nuovo livello per congratularsi e informarlo dei suoi nuovi vantaggi.

1. Crea un percorso attivato quando un cliente si sposta nel nuovo livello di fedeltà Diamond (in particolare quando il cliente entra nel segmento definito per un nuovo membro a livello di rombo) per inviare l’e-mail &quot;Luma - Nuovo stato - Diamond - Transazionale&quot;
2. Una volta completato, mettere il percorso in modalità di test e attivare il percorso da inviare a se stessi  

CRITERI DI SUCCESSO

Dovresti ricevere l’e-mail personalizzata &quot;Luma - New Status- Diamond-Transacional&quot;.
