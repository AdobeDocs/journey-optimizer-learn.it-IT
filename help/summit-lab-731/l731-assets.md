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
source-git-commit: 28da398f6813b1926c79b5cd45f415e2cfa9f40f
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 67%

---

# Laboratorio di Adobe Summit L731 - Scheda di riferimento rapido

In questa pagina sono presenti testi e collegamenti utilizzati nel Laboratorio di Adobe Summit L731. Consente di copiare e incollare il contenuto nei messaggi di Journey Optimizer.

## Esercizio 1.1 - Scaricare e installare l’app

### iOS

![QR code per iOS](/help/assets/lab731-ios-qr-code.png)


## Esercizio 1.3: Accedere a Adobe Journey Optimizer

[Fai clic qui per accedere a Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home)

**Dettagli di accesso:**

* Nome utente: `L731+<your seat number>@summitlab.us` (esempio: L731+001@summitlab.us)
* Password: Adobe2023!


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
| URL di base |  | lab:// |



## Lezione 3 Creare un percorso omni-channel

| Messaggio | Titolo/Oggetto | Testo | Collegamento |
|----|----|----|----|----|
| Push | Benvenuti a Vegas Stay! | Salta la fila e fai il check-in con l’app mobile | lab://checkin |  |
| SMS |  | Ti diamo il benvenuto a Las Vegas. Salta la fila e fai il check-in con l’app mobile: lab://checkin |  |
| e-mail | {{profile.person.name.firstName}}, hai effettuato il check-in, ora controlla le nostre offerte per il tuo soggiorno! |  |  |


Questa è l’immagine che viene utilizzata per l’SMS e la notifica push:

![Check-in online](/help/assets/vegas_online_check_in.jpg)
