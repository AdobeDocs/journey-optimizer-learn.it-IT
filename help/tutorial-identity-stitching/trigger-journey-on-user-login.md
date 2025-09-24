---
title: Attivare il Percorso Adobe Journey Optimizer tramite Adobe Web SDK
description: Scopri come avviare un percorso Adobe Journey Optimizer da eventi del sito come gli accessi degli utenti sfruttando AEP Web SDK configurato tramite i tag Adobe Experience Platform
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-09-24T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-19287
source-git-commit: c9d62ef509d557b2dfa49c698580df7c4942d299
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 1%

---

# Attivare il Percorso Adobe Journey Optimizer tramite Adobe Web SDK

In questa estensione del tutorial Unione identità, viene attivato il percorso Adobe Journey Optimizer che invia un’e-mail all’utente connesso utilizzando il suo profilo unito. **In questo articolo si presuppone che tu abbia familiarità con il canale di posta elettronica e che tu abbia creato contenuti per il canale di posta elettronica.**

## Crea configurazione canale di posta elettronica

* Accedi a _**Journey Optimizer**_
* Passa a _**Amministrazione -> Canali -> Crea configurazione canale**_
* Seleziona **E-mail** dall&#39;elenco dei canali. Fornisci un nome e una descrizione significativi.
* Inserisci le impostazioni e-mail.
* Fornisci i dettagli di esecuzione come mostrato di seguito. L’e-mail viene inviata all’indirizzo e-mail del profilo memorizzato nel campo
* ![canale-e-mail](assets/email-channel-execution.png)
* Attivare la configurazione del canale e-mail

## Crea evento

* Accedi a _**Journey Optimizer**_
* Passa a _**Amministrazione -> Configurazioni**_
* Fai clic sul pulsante Gestisci nella scheda Eventi e fai clic su Crea evento. Specificate i valori come mostrato di seguito
* ![evento-percorso](assets/journey-event.png)

* Verifica se il eventType dell’evento è uguale a UserLoggedIn. In questo caso, per semplicità, il nome dell&#39;evento e il tipo di evento sono gli stessi.`in(@event{event1.eventType}, ['UserLoggedIn'])`
* Salvare l’evento

## Crea percorso

* Accedi a _**Journey Optimizer**_
* Passa a _**Gestione Percorsi -> Percorsi -> Crea Percorso**_
* Trascina e rilascia l&#39;evento _**UserLoggedIn**_ nell&#39;area di lavoro
* Trascina e rilascia E-mail dal menu Azioni. Configura l’azione e-mail per utilizzare la configurazione del canale e-mail creata in precedenza
* Pubblica il percorso

## Modalità di attivazione del percorso

Il percorso viene attivato quando il payload dell’evento inviato tramite Web SDK corrisponde a quanto configurato nel percorso. In questo esempio, l&#39;evento e il tipo di evento sono **UserLoggedIn**



