---
title: Creare una pagina web per testare la soluzione
description: Pagina web per testare le offerte personalizzate distribuite tramite il decisioning.
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 72a67137-303d-4dfe-9b70-322c81e5fb27
source-git-commit: 9a35160921988103182815efd3551151c09b9bb4
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---

# Crea una pagina web per testare la soluzione

Questa pagina web è stata creata per testare le offerte personalizzate distribuite tramite Adobe Journey Optimizer Decisioning. Fornisce un ambiente controllato in cui è possibile attivare la chiamata sendEvent e riprodurre il contenuto dell’offerta restituito, consentendo di convalidare la configurazione della personalizzazione end-to-end e garantire che il processo decisionale funzioni come previsto.

Lo script seguente è responsabile del recupero e della visualizzazione di un’offerta personalizzata in una pagina web tramite Adobe Journey Optimizer.

1. Decodificare le entità HTML:

   È disponibile una funzione di assistenza che converte in modo sicuro eventuali caratteri speciali nel contenuto dell’offerta in HTML leggibile.

1. Esegui personalizzazione:

   Quando viene chiamato, invia una richiesta (`sendEvent`) al Web SDK di Adobe per ottenere contenuti personalizzati per un&#39;area specifica della pagina (l&#39;elemento `#ajo-offer`).

   Se viene restituita un’offerta, questa decodifica il HTML e lo inserisce nella pagina.

   Se non viene restituito nulla, registra un avviso.

1. Attendi SDK:

   Poiché la SDK (lega) di Adobe viene caricata in modo asincrono, lo script attende di essere completamente caricato prima di effettuare la richiesta.

   Controlla la lega ogni 200 millisecondi, fino a 20 volte, per evitare errori.

1. Al caricamento della pagina:

   Al termine del caricamento, lo script avvia il processo chiamando `waitForAlloy()`.



```javascript
< script >
    function decodeHtmlEntities(html) {
        const txt = document.createElement("textarea");
        txt.innerHTML = html;
        return txt.value;
    }


function runPersonalization() {
    console.log("🚀 Sending personalization request to AJO...");
    alloy("sendEvent", {
        renderDecisions: true,
        personalization: {
            surfaces: ["#ajo-offer"]
        }
    }).then(result => {
        console.log("🔍 Web SDK decision response:", result);

        const decision = result.propositions?.[0];
        const html = decision?.items?.[0]?.data?.content;

        const container = document.getElementById("ajo-offer");
        if (html && container) {
            const decodedHtml = decodeHtmlEntities(html);
            console.log("✅ Offer HTML content (decoded):", decodedHtml);
            container.innerHTML = decodedHtml;
        } else {
            console.warn("⚠️ No personalized offer returned.");
        }


    }).catch(error => {
        console.error("❌ sendEvent failed:", error);
    });
}

function waitForAlloy(callback, retries = 20) {
    if (typeof alloy === "function") {
        callback();
    } else if (retries > 0) {
        console.log("⌛ Waiting for Alloy...");
        setTimeout(() => waitForAlloy(callback, retries - 1), 200);
    } else {
        console.error("❌ alloy is not loaded after waiting.");
    }
}

// Trigger initial personalization on page load
document.addEventListener("DOMContentLoaded", function() {
    waitForAlloy(() => runPersonalization());
}); <
/script>
```

[La pagina HTML di esempio e le risorse correlate possono essere scaricate da qui](assets/web-page-assets.zip)
