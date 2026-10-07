---
title: Attivare il Percorso Adobe Journey Optimizer tramite Adobe Web SDK
description: Scopri come avviare un percorso Adobe Journey Optimizer da eventi del sito come gli accessi degli utenti tramite AEP Web SDK configurato tramite i tag di Adobe Experience Platform
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-09-24T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-19287
exl-id: c6d4f720-3780-4012-a2bd-8eae23599144
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
source-wordcount: '290'
ht-degree: 10%
---
# Attivare il Percorso Adobe Journey Optimizer tramite Adobe Web SDK

In questa estensione del tutorial Unione identità, viene attivato il percorso Adobe Journey Optimizer che invia un’e-mail all’utente connesso utilizzando il suo profilo unito. **In questo articolo si presuppone che tu abbia familiarità con il canale di posta elettronica e che tu abbia creato contenuti per il canale di posta elettronica.**

## Crea configurazione canale di posta elettronica

* Accedi a _&#x200B;**Journey Optimizer**&#x200B;_
* Passa a _&#x200B;**Amministrazione -> Canali -> Crea configurazione canale**&#x200B;_
* Seleziona **E-mail** dall&#39;elenco dei canali. Fornisci un nome e una descrizione significativi.
* Inserisci le impostazioni e-mail.
* Fornisci i dettagli di esecuzione come mostrato di seguito. L’e-mail viene inviata all’indirizzo e-mail del profilo memorizzato nel campo
* ![canale-e-mail](assets/email-channel-execution.png)
* Attivare la configurazione del canale e-mail

## Crea evento

* Accedi a _&#x200B;**Journey Optimizer**&#x200B;_
* Passa a _&#x200B;**Amministrazione -> Configurazioni**&#x200B;_
* Fai clic sul pulsante Gestisci nella scheda Eventi e fai clic su Crea evento. Specificate i valori come mostrato di seguito
* ![evento-percorso](assets/journey-event1.png)

* Verifica se il tipo di evento dell’evento è uguale a LoginEvent. Il tipo `LoginEvent` è impostato nel tag Adobe Experience Platform.
* Salvare l’evento

## Crea Percorso

* Accedi a _&#x200B;**Journey Optimizer**&#x200B;_
* Passa a _&#x200B;**Gestione Percorsi -> Percorsi -> Crea Percorso**&#x200B;_
* Trascina e rilascia l&#39;evento _&#x200B;**UserLoggedIn**&#x200B;_ nell&#39;area di lavoro
* Trascina e rilascia E-mail dal menu Azioni. Configura l’azione e-mail in modo che utilizzi la configurazione del canale e-mail creata in precedenza.
* Pubblica il percorso.

## Modalità di attivazione del percorso

Il percorso viene attivato quando il payload dell’evento inviato tramite Web SDK corrisponde a quanto configurato nel percorso. In questo esempio, il tipo di evento `UserLoggedIn` è `LoginEvent`.

* Verifica visualizzando il rapporto sul percorso
* ![Rapporto percorsi](assets/journey-triggered-report.png)
