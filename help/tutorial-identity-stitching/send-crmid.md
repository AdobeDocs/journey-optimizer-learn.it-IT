---
title: Creare l’applicazione di esempio per simulare l’attività di accesso
description: Creare un esempio di applicazione Node.js per simulare un flusso di accesso
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: e080149c-0ac0-4559-b99d-ebad9f03b98b
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%
---
# Creare l’applicazione di esempio per simulare l’attività di accesso

Questa applicazione di esempio, generata e distribuita su un server Node.js, illustra come inviare un ID CRM a Adobe Experience Platform (AEP) quando un utente effettua l’accesso. L’applicazione simula un flusso di accesso in cui le credenziali utente vengono convalidate sul lato server. Dopo aver effettuato correttamente l’accesso, l’ID CRM dell’utente viene recuperato e inviato ad adobeDataLayer, attivando una regola corrispondente nei Tag di Adobe Experience Platform (precedentemente Adobe Launch).

La funzione attachLoginHandler associa un listener di eventi di invio a un modulo di accesso. All’invio del modulo, impedisce l’azione predefinita, convalida le credenziali rispetto all’oggetto di un utente predefinito e recupera l’ID del sistema di gestione delle relazioni con i clienti, se valido. La funzione invia un evento userloggedin con l’ID del sistema di gestione delle relazioni con i clienti e lo stato di autenticazione ad adobeDataLayer, e Adobe Experience Platform Tags lo seleziona per inviare i dati a Adobe Experience Platform (AEP).


```javascript
function attachLoginHandler() {
    const form = document.getElementById("loginForm");
    if (!form) return;

    form.addEventListener("submit", function(e) {
        e.preventDefault();
        const username = document.getElementById("username").value;
        const password = document.getElementById("password").value;

        if (users[username] && users[username].password === password) {
            const crmid = users[username].crmid;
            window.adobeDataLayer = window.adobeDataLayer || [];
            debugger;
            window.adobeDataLayer.push({
                event: "UserLoggedIn",
                user: {
                    crmid: crmid,
                    authenticatedState: "authenticated"
                }
            });
        }
    });
}
```

Lo script dei tag di Adobe Experience Platform è incluso nella sezione `<head>` della pagina HTML utilizzando un tag `<script>`, in genere simile al seguente:

`<script src="https://assets.adobedtm.com/b5eu4857867/4e4d84957/launch-b69e276bb9b5-development.min.js" async crossorigin="anonymous"></script>`

Lo script AEP Tags è stato ottenuto pubblicando una proprietà abilitata per Web SDK creata nel passaggio precedente e copiando il codice da incorporare dalla scheda Ambienti.
