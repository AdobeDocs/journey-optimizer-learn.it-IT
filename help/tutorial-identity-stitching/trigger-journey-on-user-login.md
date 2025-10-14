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
source-git-commit: 6927cade07790603e711f4e6e4c3f6982a56e6f5
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

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

## Crea percorso

* Accedi a _&#x200B;**Journey Optimizer**&#x200B;_
* Passa a _&#x200B;**Gestione Percorsi -> Percorsi -> Crea Percorso**&#x200B;_
* Trascina e rilascia l&#39;evento _&#x200B;**UserLoggedIn**&#x200B;_ nell&#39;area di lavoro
* Trascina e rilascia E-mail dal menu Azioni. Configura l’azione e-mail in modo che utilizzi la configurazione del canale e-mail creata in precedenza.
* Pubblica il percorso.

## Modalità di attivazione del percorso

Il percorso viene attivato quando il payload dell’evento inviato tramite Web SDK corrisponde a quanto configurato nel percorso. In questo esempio, il tipo di evento `UserLoggedIn` è `LoginEvent`.

* Verifica visualizzando il rapporto sul percorso
* ![Rapporto percorsi](assets/journey-triggered-report.png)




