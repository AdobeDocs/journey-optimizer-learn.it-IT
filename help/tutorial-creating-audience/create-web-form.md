---
title: Creare un modulo web
description: Crea un modulo nella pagina HTML per consentire agli utenti di selezionare le preferenze di investimento
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 0%

---

# Creare un modulo web

Il seguente modulo di HTML è stato creato per acquisire le preferenze degli utenti
![html-form](assets/web-form.png)

Quando un utente fa clic sul pulsante sulla pagina web, la preferenza finanziaria selezionata (ad esempio Stock, Obbligazioni o CD) viene acquisita e inviata ad Adobe Data Layer. Questo evento (assetClassSelection) memorizza la scelta dell’utente in tempo reale. Adobe Launch ascolta quindi questo evento, recupera l’opzione di investimento selezionata (PreferredFinancialInstrument) e può attivare azioni quali l’invio dei dati a Adobe Experience Platform (AEP) o l’aggiornamento delle regole di personalizzazione

Il seguente JavaScript è stato scritto per gestire l’invio del modulo

```javascript
function handleSubmission() {
  window.adobeDataLayer = window.adobeDataLayer || [];

  const selectedAssetClass = document.querySelector('input[name="assetclass"]:checked');
  const errorMessage = document.getElementById("error-message");
  const messageBox = document.getElementById("message");

  if (!selectedAssetClass) {
    errorMessage.textContent = "Please select a financial instrument.";
    messageBox.textContent = "";
    return;
  }

  errorMessage.textContent = "";

  const subscriptionEvent = {
    event: "assetClassSelection",
    xdm: {
      eventType: "assetClassSelection",
      eventID: "investment_preference_event",
      timestamp: new Date().toISOString(),
      FinancialInterest: {
        PreferredFinancialInstrument: selectedAssetClass.value
      }
    }
  };

  console.log("📩 Sending asset class data to AEP:", subscriptionEvent);
  window.adobeDataLayer.push(subscriptionEvent);

  // ✅ Show thank-you message
  messageBox.textContent = `Thank you for selecting "${selectedAssetClass.value}". We'll use this to personalize your experience.`;
}
```

[Il modulo HTML di esempio viene fornito come parte di questa esercitazione](assets/webform.zip)
