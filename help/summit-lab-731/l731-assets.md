---
title: Scheda di riferimento rapido L731
description: In questa pagina sono presenti testi e collegamenti utilizzati nel Laboratorio di Adobe Summit L731.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: ffc5e8c8-8729-4e7e-aa51-d74f91b0cf29
source-git-commit: 01869838bb08e0d7848934f345afdd54824aaa75
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 100%

---

# Laboratorio di Adobe Summit L731 - Scheda di riferimento rapido

In questa pagina sono presenti testi e collegamenti utilizzati nel Laboratorio di Adobe Summit L731. Consente di copiare e incollare il contenuto nei messaggi di Journey Optimizer.

## Esercizio 1.1: scaricare e installare l’app

Scansiona il QR code per scaricare l’app

>[!BEGINTABS]

>[!TAB iOS]

![QR code per iOS](/help/assets/lab731-ios-qr-code.png)

>[!IMPORTANT]
>
>Se viene richiesto il codice di riscatto, chiudi l’app TestFlight e scansiona nuovamente il codice QR.
>
>Consenti notifiche.
>

Ti verrà chiesto di installare Testflight, passaggi da 1 a 4. Una volta installato Testflight segui i passaggi da 5 a 8 per installare l’app Vegas Stay:

<table>
<tr>
</tr>
<tr>
<td>
 <div>
      <p>
      <b>Passaggio 1 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-1.png"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Passaggio 2 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-2.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Passaggio 3 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-3.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Passaggio 4 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-4.PNG"/>
      </a>
      </div>
  </td>
  </tr>
  <tr>
<td>
 <div>
      <p>
      <b>Passaggio 5 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-5.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
<b>Passaggio 6 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-6.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
<b>Passaggio 7 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-7.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
<b>Passaggio 8 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-8.PNG"/>
      </a>
      </div>
  </td>
  </tr>
</table>

>[!TAB Android]

![QR code per Android](/help/assets/lab731-android-qr-code.png)

Poiché l’app non è registrata in Google Play Store, riceverai un messaggio di avviso:

![Schermata di avviso Android](/help/assets/lab731-install-android.png)

Fai clic su **Installa comunque**

>[!ENDTABS]

## Esercizio 1: accedere a Adobe Journey Optimizer

[Fai clic qui per accedere a Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home){target="_blank"}

**Dettagli di accesso**

* **Nome utente:** `L731+<your seat number>@summitlab.us` (esempio: L731+001@summitlab.us)
* **Password:** Adobe2023.


## Esercizio 2: creare una campagna in-app

| Sezione | Campo | Testo | Collegamenti |
|----|----|----|----|
| **Proprietà** | Nome della campagna | `<your seat number> Vegas Stay Campaign` |  |
| **Triggers** | Stato | booknow |  |
| **Modifica contenuto:** contenuti multimediali | Opzione URL del contenuto multimediale |  | https://i.ibb.co/NstLhjW/Firefly-Poster-with-heading-Adobe-Max-84773.jpg |
| **Modifica contenuto:** contenuto | Titolo | Ottieni il tuo sconto early bird! |  |
| **Modifica contenuto:** contenuto | Corpo | Adobe Max ritorna a Las Vegas. Preparati ad ascoltare relatori stimolanti, sessioni per ampliare le competenze e nuove connessioni. Prenota subito la tua suite e ottieni uno sconto del 10%. |  |
| **Modifica contenuto:** pulsanti | Pulsante | Ottieni il tuo 10% di sconto! | lab://booking?suite=presidential&amp;discount=10 |
| **Modifica contenuto:** pulsanti | Evento di interazione | CTA in-app |  |
| **Anteprima su dispositivo** | URL di base da utilizzare per anteprima su dispositivo |  | **iOS:** lab:// <br>**Android**: https://lab |

## Esercizio 3: crea una notifica push

| Campo | Testo | Collegamenti |
|----|----|----|
| Nome della campagna | `<your seat number> Max Push Campaign` |  |
| Titolo | Ehi! |  |
| Corpo | Lo sapevi che Adobe Max sta tornando a Las Vegas? Prenota ora la tua camera e ottieni uno sconto del 10%. |  |
| Opzione URL del contenuto multimediale |  | https://i.ibb.co/1M0BnZn/Firefly-Big-conference-big-stage-with-ADBE-text-on-screen-40178.jpg |
