---
title: Distribuzione di Personalization con contenuti JSON in Adobe Journey Optimizer
description: Sfrutta il tipo di contenuto JSON in Adobe Journey Optimizer (AJO) per creare esperienze di personalizzazione flessibili e basate sui dati.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-18T00:00:00Z
jira: KT-18387
recommendations: noDisplay, noCatalog
source-git-commit: 9f5b52063605832a9b00c05fb1a93bf60ec7686f
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Distribuzione di Personalization con contenuti JSON in Adobe Journey Optimizer

Questa sezione viene fornita come risorsa aggiuntiva per gli utenti avanzati che desiderano un maggiore controllo sul rendering delle offerte sul front-end.

L’utilizzo del tipo di contenuto JSON in un’esperienza basata su codice (CBE) consente di restituire dati di offerta strutturati e gestire il rendering in modo dinamico tramite JavaScript. Il tipo di contenuto JSON è particolarmente utile per gli scenari che richiedono layout personalizzati, logica condizionale o integrazione con dati contestuali, come meteo, posizione o tipo di dispositivo.

Anche se non richiesto per la consegna dell’offerta di base, questo approccio offre flessibilità agli sviluppatori che creano esperienze personalizzate e basate sui dati, al di là delle funzionalità di rendering standard di HTML.

## Crea un’esperienza basata su codice (CBE) con tipo di contenuto JSON.

Inizia creando una nuova esperienza basata su codice (CBE) in Adobe Journey Optimizer e imposta il formato del contenuto su JSON. Il tipo di contenuto indica ad AJO di restituire i dati dell’offerta strutturata (come offerText, immagini o metadati) come oggetto JSON anziché come HTML di cui è stato eseguito il rendering. Definisci la piattaforma (ad esempio Web), l’URL di destinazione in cui viene visualizzata l’offerta e la posizione sulla pagina (ad esempio un ID contenitore come offerContainer). Questa configurazione consente all’applicazione web di ricevere i dati delle offerte ed eseguirne il rendering dinamico tramite JavaScript.

![json-content-type](assets/cbe-json-content.png)

## Associare il CBE a una campagna con un criterio decisionale

Una volta creata l’esperienza basata su codice (CBE) con tipo di contenuto JSON, questa viene collegata a una campagna tramite un criterio decisionale. I criteri di decisione definiscono la logica per l’idoneità delle offerte, la classificazione e la consegna in base a dati di profilo o contestuali.

Quando si inseriscono i Criteri di decisione nell’editor di Personalization (ad esempio, per messaggi in-app o e-mail), è importante assicurarsi che l’output mantenga una struttura JSON valida.

Quando si inserisce un criterio di decisione nell&#39;editor di Personalization (PE) all&#39;interno di una campagna, Adobe Journey Optimizer genera automaticamente un ciclo Handlebars basato sul criterio selezionato. Ad esempio:
![default-code](assets/handlebar-code-default.png)
Questo ciclo scorre tutti gli elementi decisionali restituiti dal criterio e inserisce il campo offerText da ogni offerta. Questa struttura predefinita funziona bene per i tipi di contenuto HTML, ma quando si lavora con contenuto JSON, potrebbe essere necessario ristrutturarla per produrre un array JSON o un oggetto JSON valido, soprattutto se il risultato viene analizzato a livello di programmazione.

![codice ristrutturato](assets/restructured-code.png)

Questo modello Handlebars è progettato per generare un array JSON di oggetti di offerta, in cui ogni oggetto contiene un singolo campo offerText. Esegue un ciclo tra gli elementi decisionali restituiti dal criterio di decisione specificato e racchiude ogni offerText in un formato di oggetto JSON.

## Analizza risposta offerta JSON

La risposta di AJO contiene elementi decisionali personalizzati in formato JSON nella struttura `propositions[].items[].data.content[]`. Ogni contenuto include campi come offerText.

```javascript
(response.propositions || []).forEach(p => {
  (p.items || []).forEach(item => {
    const contents = item.data?.content || [];
    contents.forEach(contentItem => {
      const html = contentItem.offerText || "";
      const wrapper = document.createElement("div");
      wrapper.className = "offer";
      wrapper.innerHTML = html;
      document.getElementById("offerContainer").appendChild(wrapper);
    });
  });
});
```

### Risorse di esempio

Per aiutarti a iniziare, scarica il file HTML di esempio e il file JavaScript che mostrano come utilizzare le offerte basate su JSON ed eseguirne il rendering dinamico sulla tua pagina web.

[Codice JavaScript](assets/weather-related-offers-script-multiple-json.js)
[File HTML](assets/multiple-json.html)