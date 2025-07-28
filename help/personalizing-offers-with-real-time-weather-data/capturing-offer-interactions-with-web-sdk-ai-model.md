---
title: Acquisizione delle interazioni dell’offerta con Adobe Web SDK per la formazione sui modelli AI
description: Questo articolo fornisce indicazioni sull’acquisizione dei dati di interazione dell’utente, ad esempio impression e clic sull’offerta, tramite Adobe Experience Platform Web SDK (alloy.js). Questi dati fungono da base per l’addestramento di modelli di IA in Adobe Journey Optimizer (AJO) in modo intelligente per classificare le offerte in base al comportamento utente e ai segnali contestuali.
feature: Decisioning
topic: Integrations
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2025-07-08T00:00:00Z
jira: KT-18451
exl-id: 3cb280b3-71e5-4e91-9252-5679d794d4c4
source-git-commit: 6c4f33d1f55be298781cfb0958862f9710e3647a
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 3%

---

# Acquisizione delle interazioni dell’offerta con Adobe Web SDK per la formazione sui modelli AI

>[!NOTE]
>
> Completa questo articolo solo se intendi utilizzare in Adobe Journey Optimizer metodi di classificazione basati sull’intelligenza artificiale per personalizzare quale offerta viene visualizzata in base al coinvolgimento previsto.



Questo articolo illustra come acquisire eventi di interazione dell’offerta (come impression o clic) utilizzando Adobe Experience Platform Web SDK chiamando alloy(&quot;sendEvent,&quot; ...) direttamente nel codice JavaScript. I dati vengono acquisiti in AEP e utilizzati per addestrare i modelli di intelligenza artificiale in Adobe Journey Optimizer (AJO) per una classificazione delle offerte più intelligente in base al comportamento in tempo reale.

Per creare un modello di IA per la classificazione delle offerte in Adobe Journey Optimizer, il set di dati deve essere basato su uno schema che include il gruppo di campi Interazioni proposta. Questo gruppo di campi supporta eventi decisionali chiave come decisioning.propositionDisplay e decisioning.propositionInteract, insieme a campi obbligatori come involvedPropositions, display e interact.

Esistono due approcci validi per raggiungere questo obiettivo:

- Crea un nuovo schema, set di dati e flusso di dati configurati specificamente per il tracciamento delle interazioni
- Aggiornare uno schema esistente — operazione eseguita in questa esercitazione



## Aggiornare lo schema esistente per acquisire eventi di interazione dell’offerta

Invece di creare un nuovo schema, lo schema Experience Event esistente utilizzato per le offerte relative al meteo viene aggiornato per supportare il tracciamento delle interazioni.

In Adobe Experience Platform:

- Apri lo schema di _&#x200B;**evento meteo**&#x200B;_ esistente utilizzato per le offerte basate sul meteo.

- Aggiungi il gruppo di campi:
Evento esperienza - Interazioni proposte

Non è necessario creare un nuovo set di dati o un nuovo stream di dati; continua a utilizzare la configurazione esistente per le offerte meteo. Gli eventi inviati sono in linea con le aspettative di Adobe Journey Optimizer per la formazione dei modelli di intelligenza artificiale e il tracciamento delle prestazioni dell’offerta.


Continua a utilizzare il set di dati corrente (non è necessario crearne uno nuovo)

Lo stream di dati esistente è già configurato e in uso nella proprietà Tag di Adobe Experience Platform, dove non sono necessarie modifiche.

Il Web SDK indirizza automaticamente i nuovi eventi di interazione alla destinazione corretta.

Questa configurazione semplificata assicura che tutti gli eventi decisionali e meteo vengano acquisiti in un unico set di dati unificato, ideale per la formazione di modelli di intelligenza artificiale in Adobe Journey Optimizer.


## Acquisire gli eventi di visualizzazione delle offerte (impressioni)

La struttura HTML dell&#39;offerta è stata modificata per includere elementi interattivi, in particolare tag `<a>` e `<button>`, che consentono agli utenti di interagire con l&#39;offerta (ad esempio, pulsanti &quot;Offerta attestazione&quot; o &quot;Ulteriori informazioni&quot;).

Ogni pulsante include un attributo data-offer-id in modo che l’interazione corrispondente possa essere tracciata correttamente.



Per registrare quando le offerte vengono mostrate agli utenti, il file JavaScript esistente utilizzato per il rendering delle offerte meteo è stato aggiornato per includere il tracciamento degli eventi di visualizzazione.

Ora quando vengono visualizzate una o più offerte, viene inviato un evento decisioning.propositionDisplay utilizzando Adobe Web SDK (alloy.sendEvent). Questo evento include la visualizzazione richiesta: 1 flag e fa riferimento alle proposte interessate.


```javascript
alloy("sendEvent", {
                    xdm: {
                      _id: generateUUID(),
                      timestamp: new Date().toISOString(),
                      eventType: "decisioning.propositionInteract",
                      identityMap: {
                        ECID: [{
                          id: ecidValue,
                          authenticatedState: "ambiguous",
                          primary: true
                        }]
                      },
                      _experience: {
                        decisioning: {
                          propositionEventType: {
                            interact: 1
                          },
                          propositionAction: {
                            id: offerId,
                            tokens: [trackingToken]
                          },
                          propositions: window.latestPropositions
                        }
                      }
                    }
                  });
```

## Acquisire eventi di clic su un’offerta (interazioni)

Per tenere traccia del momento in cui un utente fa clic su un&#39;offerta, abbiamo aggiornato il JavaScript esistente in modo da rilevare i clic sugli elementi `<a>` e `<button>` di cui è stato eseguito il rendering all&#39;interno del contenitore delle offerte.

Quando viene rilevato un clic, viene inviato un evento decisioning.propositionInteract utilizzando Adobe Web SDK. L’evento include la necessaria interazione: 1 flag e fa riferimento all’ID offerta specifico e all’ambito decisionale.

```javascript
// Attach click tracking to <a> and <button> elements
child.querySelectorAll("a, button").forEach(el => {
                el.addEventListener("click", () => {
                  const ecidValue = getECID();
                  if (!ecidValue || !offerId || !trackingToken) {
                    console.warn("Girish!!!!  Missing ECID, offerId, or trackingToken. Interaction event not sent.");
                    return;
                  }

                  alloy("sendEvent", {
                    xdm: {
                      _id: generateUUID(),
                      timestamp: new Date().toISOString(),
                      eventType: "decisioning.propositionInteract",
                      identityMap: {
                        ECID: [{
                          id: ecidValue,
                          authenticatedState: "ambiguous",
                          primary: true
                        }]
                      },
                      _experience: {
                        decisioning: {
                          propositionEventType: {
                            interact: 1
                          },
                          propositionAction: {
                            id: offerId,
                            tokens: [trackingToken]
                          },
                          propositions: window.latestPropositions
                        }
                      }
                    }
                  });
                });
              });
```

## Creare un modello di intelligenza artificiale per la classificazione delle offerte in Adobe Journey Optimizer Offer Decisioning

Con, impression e clic delle offerte acquisiti tramite il Web SDK e memorizzati in Adobe Experience Platform, questi dati possono essere utilizzati per addestrare un modello di intelligenza artificiale che prevede quali offerte sono più probabili per stimolare il coinvolgimento.

A questo modello di IA si fa riferimento in una formula di classificazione o in una strategia di selezione per determinare quali offerte hanno priorità per ogni utente.
- Accedi a Journey Optimizer
- Passa a Decisioning > Impostazione strategia > Modelli di intelligenza artificiale > Crea modello di intelligenza artificiale
- Assicurati di utilizzare il set di dati corretto
  ![modello ai](assets/ai-model.png)
- Salva e attiva il modello di intelligenza artificiale.
- Aggiorna la strategia di selezione creata nel passaggio precedente per utilizzare il modello di IA per il metodo di classificazione
  ![aggiorna-strategia-selezione](assets/update-selection-strategy.png)

## Testare la soluzione

Includi il [file JavaScript aggiornato](assets/ai-model.js) nella [pagina Web esistente](assets/weather-offers.html)
