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
source-git-commit: b0c728e7dee77c16b2c0ad51f592d92f3f72491e
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 53%

---

# Laboratorio di Adobe Summit L731 - Scheda di riferimento rapido

In questa pagina sono presenti testi e collegamenti utilizzati nel Laboratorio di Adobe Summit L731. Consente di copiare e incollare il contenuto nei messaggi di Journey Optimizer.

## Esercizio 1.1: scaricare e installare l’app

Analizza il codice QR per scaricare l&#39;app

>[!BEGINTABS]

>[!TAB iOS]

![Codice QR per iOS](/help/assets/lab731-ios-qr-code.png)

Ti verrà chiesto di installare Testflight (passaggi da 1 a 4). Una volta installato Testflight seguire i passaggi da 5 a 8 per installare l&#39;app Vegas Stay:

<table>
<tr>
</tr>
<tr>
<td>
 <div>
      <p>
      <b>Passaggio 1 </b>
      <p>
      <a href="Step 1:">
        <img alt="volo di prova 1" src="../assets/l731-ios-install/ios-install-1.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Passaggio 2 </b>
      <p>
      <a href="Step 1:">
        <img alt="volo di prova 1" src="../assets/l731-ios-install/ios-install-2.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Passaggio 3 </b>
      <p>
      <a href="Step 1:">
        <img alt="volo di prova 1" src="../assets/l731-ios-install/ios-install-3.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Passaggio 4 </b>
      <p>
      <a href="Step 4">
        <img alt="volo di prova 1" src="../assets/l731-ios-install/ios-install-4.PNG"/>
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
      <a href="Step 1:">
        <img alt="volo di prova 1" src="../assets/l731-ios-install/ios-install-5.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Passaggio 6 </b>
      <p>
      <a href="Step 1:">
        <img alt="volo di prova 1" src="../assets/l731-ios-install/ios-install-6.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Passaggio 7 </b>
      <p>
      <a href="Step 1:">
        <img alt="volo di prova 1" src="../assets/l731-ios-install/ios-install-7.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Passaggio 8 </b>
      <p>
      <a href="Step 4">
        <img alt="volo di prova 1" src="../assets/l731-ios-install/ios-install-8.PNG"/>
      </a>
      </div>
  </td>
  </tr>
</table>

>[!TAB Android]

![Codice QR per Android](/help/assets/lab731-android-qr-code.png)

Se utilizzi il simulatore Android, utilizza questo collegamento: [https://ajolab.s3.amazonaws.com/ajolabapp-release.apk](https://ajolab.s3.amazonaws.com/ajolabapp-release.apk)

Poiché l’app non è registrata in Google Play Store, riceverai un messaggio di avviso:

![Schermata di avviso Android](/help/assets/lab731-install-android.png)

Fai clic su **Installa comunque**

>[!ENDTABS]

## Esercizio 1.3: accedere a Adobe Journey Optimizer

[Fai clic qui per accedere a Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home)

**Dettagli di accesso:**

* **Nome utente:** `L731+<your seat number>@summitlab.us` (esempio: L731+001@summitlab.us)
* **Password:** Adobe 2023!


## Esercizio 2.1 Creare una campagna in-app

| Campo | Testo | Collegamenti |
|----|----|----|
| Nome della campagna | `<your seat number> March Vegas Campaign` |  |
| Corrispondenza | booknow |  |
| Opzione URL del contenuto multimediale |  | https://mcfadyen.com/wp-content/uploads/2023/01/Adobe-Summit-2023-Banner.png |
| Titolo | Sta succedendo ed è live! |  |
| Corpo | Adobe Summit torna a Las Vegas dal 21 al 23 marzo 2023. Preparati ad ascoltare relatori stimolanti, sessioni per ampliare le competenze e nuove connessioni. |  |
| Pulsante | Prenota subito l’hotel e risparmia il 10% | lab://booking?suite=presidential&amp;discount=10 |
| Pulsante: evento interattivo | CTA in-app |  |
| URL di base |  | iOS: lab:// <br>Android&amp;: https://lab |


## Lezione 3 Creare un percorso omni-channel

**Etichetta percorso:**
`<your seat number>` - Percorso di benvenuto

>[!BEGINTABS]

>[!TAB Messaggio push]

**Etichetta:**
Messaggio di benvenuto

**Titolo:**\
Ti diamo il benvenuto a Las Vegas!

**Corpo:**\
Salta la fila e fai il check-in con l’app mobile

**Collegamento profondo:** lab://checkin

**Media:**

https://experienceleague.adobe.com/docs/journey-optimizer-learn/assets/vegas_online_check_in.jpg?lang=en


Questa è l’immagine che utilizziamo per la notifica push:

![Check-in online](/help/assets/vegas_online_check_in.jpg)

>[!TAB Messaggio SMS]

**Etichetta:**
Messaggio di benvenuto

**Messaggio:**
Benvenuto a Vegas Stay. Salta la fila e fai il check-in con l’app mobile: lab://checkin

>[!TAB Messaggio e-mail]

**Etichetta:**
Messaggio di conferma

**Oggetto:**
{{profile.person.name.firstName}}, hai effettuato il check-in, ora controlla le nostre offerte per il tuo soggiorno!

>[!ENDTABS]
