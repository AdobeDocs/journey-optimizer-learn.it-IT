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
source-git-commit: 51ab40981a42b0df56d3994f1155eb4ae7575b17
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 21%

---

# laboratorio Summit L535 - Scheda di riferimento

In questa pagina sono presenti testo e collegamenti utilizzati nel laboratorio dell’evento L535 Summit Lab. Consente di copiare e incollare il contenuto nei messaggi di Journey Optimizer.

## Collegamenti

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys)
* [Sito Web SecurFinancial](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U)
* [Scarica l&#39;app](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html)

## Esercizi

### Esercizio 2.3

**Messaggio di posta elettronica al passaggio 12**:

Genera un messaggio e-mail di benvenuto per il nuovo SecurFinancial
clienti che hanno appena aperto un nuovo conto di risparmio. Aggiungi un
Invito all&#39;azione per installare l&#39;app mobile SecurFinancial.

### Esercizio 3.1

**Passaggio 7**

```javascript
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


![Logo SecureFinancial](/help/summit-lab-assets/assets/SecureFinancial-logo.png)

![Telefono cellulare](/help/summit-lab-assets/assets/online-banking-app-01.png)


