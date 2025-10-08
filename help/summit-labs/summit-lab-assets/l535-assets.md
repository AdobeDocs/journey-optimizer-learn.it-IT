---
title: Scheda di riferimento L535
description: In questa pagina sono presenti testo e collegamenti utilizzati nel laboratorio dell’evento L535 Summit Lab.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: 1c3f4341-1293-463d-bee0-57440fcff23a
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 24%

---

# laboratorio Summit L535 - Scheda di riferimento

In questa pagina sono presenti testo e collegamenti utilizzati nel laboratorio dell’evento L535 Summit Lab. Consente di copiare e incollare il contenuto nei messaggi di Journey Optimizer.

## Collegamenti

* [Sito Web SecurFinancial](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U){target="_blank"}
* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys){target="_blank"}
* [Cartella di lavoro L535](/help/summit-labs/summit-lab-assets/assets/summit_lab_manual_l535-final-v4.pdf){target="_blank"}
* [Scarica l&#39;app](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html){target="_blank"}

## Copia e incolla per esercizi

### Esercizio 2.1 - Accesso a Journey Optimizer

Effettua l’accesso con i seguenti dettagli:

Indirizzo e-mail:    L535+*numero di posto*@adobeeventlab.com

Password:       Adobe4Summit


### Esercizio 2.3 - Comporre il messaggio e-mail

#### Prompt

```
Generate a welcome email for new SecurFinancial customers who just opened a new checking account. 
Add a call to action to install the SecurFinancial mobile app.
```

### Esercizio 3.1 - Applicare il contenuto dinamico al messaggio SMS

#### Codice

```
{%#if select _Push_details1 from profile.pushNotificationDetails where
_Push_details1.token.isNotNull()%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Open the
app
{%else%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Click here
to install the app: https://demo-systemnext.
s3.amazonaws.com/dxdemo/summit/index.html
{%/if%} 
```

### Esercizio 4.2 - Configurare i trattamenti

#### Titolo

```
Welcome to SecurFinancial
```

#### Corpo del testo

```
Did you know you can find an ATM near in the SecurFinancial app? Try it now!
```

#### URL

```
dxdemo://atm
```

### Esercizio 6: Schede di contenuto

#### Titolo

```
Welcome to SecurFinancial!
```

#### Corpo

```
Thank you for downloading the app. You can find ATMs, track your spending and more. All within the app.
```

#### URL file multimediale

```
https://demo-system-next.s3.amazonaws.com/assets/securfinancial/home-loan.jpg
```

#### Titolo pulsante

```
Find ATMs
```

#### URL di destinazione

```
dxdemo://atm
```

## Immagini

![Logo SecureFinancial](/help/summit-labs/summit-lab-assets/assets/SecureFinancial-logo.png)


![Telefono cellulare](/help/summit-labs/summit-lab-assets/assets/online-banking-app-01.png)
