---
title: Scheda di riferimento L731
description: In questa pagina sono presenti testi e collegamenti utilizzati nel Laboratorio di Adobe Summit L731.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: ffc5e8c8-8729-4e7e-aa51-d74f91b0cf29
source-git-commit: 16a2a4ab090b96f52555b543cd9d1924dc9f09cb
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 49%

---

# Laboratorio di Adobe Summit L731 - Scheda di riferimento rapido

In questa pagina sono presenti testi e collegamenti utilizzati nel Laboratorio di Adobe Summit L731. Consente di copiare e incollare il contenuto nei messaggi di Journey Optimizer.

## Esercizio 1.1 - Scaricare e installare l’app

Esegui la scansione del codice QR per scaricare l’app

>[!BEGINTABS]

>[!TAB iOS]

![QR code per iOS](/help/assets/lab731-ios-qr-code.png)

>[!TAB Android]

![QR code per Android](/help/assets/lab731-ios-qr-code.png)

>[!ENDTABS]

## Esercizio 1.3: Accedere a Adobe Journey Optimizer

[Fai clic qui per accedere a Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home)

**Dettagli di accesso:**

* **Nome utente:** `L731+<your seat number>@summitlab.us` (esempio: L731+001@summitlab.us)
* **Password:** Adobe 2023!


## Esercizio 2.1 Creare una campagna in-app

| Campo | Testo | Collegamenti |
|----|----|----|
| Nome campagna | `<your seat number> March Vegas Campaign` |  |
| Matcher | booknow |  |
| Opzione URL del contenuto multimediale |  | https://mcfadyen.com/wp-content/uploads/2023/01/Adobe-Summit-2023-Banner.png |
| Titolo | Sta accadendo ed è in diretta! |  |
| Corpo | Adobe Summit torna a Las Vegas dal 21 al 23 marzo 2023. Preparati ad ascoltare relatori stimolanti, sessioni per ampliare le competenze e nuove connessioni. |  |
| Pulsante | Prenota subito l’hotel e risparmia il 10% | lab://booking?suite=presidential&amp;discount=10 |
| Pulsante: evento interattivo | CTA in-app |  |
| URL di base |  | iOS: lab:// <br>Android: https://lab |


## Lezione 3 Creare un percorso omni-channel

>[!BEGINTABS]

>[!TAB Messaggio push]

**Titolo:**\
Benvenuti a Vegas Stay!

**Corpo:**\
Salta la fila e fai il check-in con l’app mobile

**Deeplink:** lab://checkin

**Media:**

https://experienceleague.adobe.com/docs/journey-optimizer-learn/assets/vegas_online_check_in.jpg?lang=en


Questa è l’immagine che utilizziamo per la notifica push:

![Check-in online](/help/assets/vegas_online_check_in.jpg)

|SMS| ||| |e-mail|{{profile.person.name.firstName}}, hai effettuato il check-in, ora controlla le nostre offerte per il tuo soggiorno!||

>[!TAB Messaggio SMS]

**Messaggio:**
Benvenuti a Vegas Stay. Salta la fila e fai il check-in con l’app mobile: lab://checkin

>[!TAB Messaggio e-mail]

**Oggetto:**
{{profile.person.name.firstName}}, hai effettuato il check-in, ora controlla le nostre offerte per il tuo soggiorno!

>[!ENDTABS]