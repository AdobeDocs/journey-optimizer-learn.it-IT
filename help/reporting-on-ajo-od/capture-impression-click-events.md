---
title: Acquisire impression ed eventi di interazione
description: Acquisisci gli eventi di impression e interazione e prepara i dati per il reporting in Journey Optimizer.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
recommendations: noDisplay, noCatalog
last-substantial-update: 2025-07-18T00:00:00Z
jira: KT-18526
source-git-commit: 69bc8aace3cc502a18e691584824176833413c7e
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Acquisire impression ed eventi di interazione

Per abilitare il reporting sulle impression e sui clic delle offerte di AJO, è necessario configurare i seguenti componenti:
>[!NOTE]
>
> Questi prerequisiti sono già stati completati nella sezione Crea schema e set di dati dell&#39;[esercitazione precedente](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/create-schema-and-dataset)

## &#x200B;1. Set di dati in Adobe Experience Platform (AEP)

- Un set di dati basato su uno schema **XDM ExperienceEvent**.

Lo schema deve includere `Web Details` gruppo di campi che acquisisce l&#39;URL della pagina, il referente, ecc.

## &#x200B;2. Configurazione dello stream di dati

- È necessario creare uno **stream di dati** in Adobe Experience Platform.
- Questo flusso di dati deve essere collegato al set di dati configurato in precedenza per garantire che tutti gli eventi Web SDK vengano correttamente acquisiti nella destinazione corretta.

## &#x200B;3. Adobe Experience Platform Tags, proprietà

- Estensione AEP Web SDK configurata per utilizzare lo stream di dati creato nel passaggio precedente.
- Servizio Experience Cloud ID configurato
- Alla proprietà viene aggiunto l’elemento dati ECID
- Implementato sul sito in cui viene eseguito il rendering delle offerte.


Per abilitare il reporting sulle prestazioni delle offerte, il primo passaggio consiste nell’acquisire quando le offerte vengono visualizzate (impression) e quando ne viene fatto clic (interazioni). Questi eventi forniscono le basi per misurare il coinvolgimento, calcolare i tassi di click-through e analizzare l’efficacia dell’offerta in Adobe Experience Platform.

La funzione alloy(&quot;sendEvent&quot;) viene utilizzata per registrare le interazioni dell’utente con le offerte restituite da Adobe Journey Optimizer (AJO).

Il payload sendEvent acquisisce le interazioni delle offerte includendo il tipo di evento (decisioning.propositionDisplay per le impression o decisioning.propositionInteract per i clic), un ID evento univoco, una marca temporale e un’identità utente (identityMap). Include inoltre l’elenco delle offerte (proposte) visualizzate o su cui è stato fatto clic, insieme ai token di tracciamento per garantire un’attribuzione accurata. Questa struttura consente di generare rapporti e ottimizzare le prestazioni dell’offerta personalizzata in Adobe Journey Optimizer.

Vengono acquisiti due tipi di eventi di interazione:

## Evento di impression

Un’impression si verifica quando viene eseguito il rendering di un’offerta sulla pagina e questa diventa visibile all’utente. L’evento viene tracciato utilizzando il tipo di evento decisioning.propositionDisplay.


```javascript
 alloy("sendEvent", {
            xdm: {
              _id: generateUUID(),
              timestamp: new Date().toISOString(),
              eventType: "decisioning.propositionDisplay",
              identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
                      authenticatedState: "authenticated",
                      primary: true
                    }]
                  },
              _experience: {
                decisioning: {
                  propositionEventType: {
                    display: 1
                  },
                  
                   propositions: window.latestPropositions
                  
                }
              }
            }
          });
        }
```

## Interazione offerta

Quando un utente fa clic su un call-to-action (CTA) all’interno dell’offerta di cui è stato eseguito il rendering, viene registrata un’interazione. L’evento viene tracciato utilizzando il tipo di evento decisioning.propositionInteract.

```javascript
alloy("sendEvent", {
                xdm: {
                  _id: generateUUID(),
                  timestamp: new Date().toISOString(),
                  eventType: "decisioning.propositionInteract",
                  identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
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
              })
```

L’inclusione di proposte negli eventi di clic e impression è essenziale per ottenere rapporti accurati sulle offerte in Adobe Journey Optimizer. Queste proposte rappresentano le offerte esatte che sono state presentate all’utente, consentendo ad Adobe di attribuire le interazioni dell’utente (ad esempio, impression o clic) alle specifiche decisioni prese dal sistema.

Ogni offerta all’interno di una proposta include un token di tracciamento, che è un identificatore univoco generato da Adobe. Questo token deve essere trasmesso esattamente come ricevuto, senza modifiche, nell’evento di clic o impression corrispondente. La corrispondenza dei token di tracciamento garantisce che Adobe possa associare con precisione l’azione dell’utente alla decisione di offerta corretta, abilitando il reporting a valle e l’ottimizzazione basata sull’intelligenza artificiale.
