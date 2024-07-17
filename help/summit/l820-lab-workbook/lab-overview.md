---
title: Lab Workbook - L820 - Creare momenti mobili personalizzati con Adobe Journey Optimizer
description: Esplora vari scenari mobili e scopri come implementare esperienze personalizzate per web e dispositivi mobili con Journey Optimizer.
feature: Overview
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
jira: KT-14977
thumbnail: KT-14977.jpeg
last-substantial-update: 2024-03-26T00:00:00Z
exl-id: e6d029f9-c936-427b-9d6e-4e296fd3c3ce
source-git-commit: b4eb509d50afeea02eac937be85643aa22370249
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# CARTELLA DI LAVORO LAB

![Adobe Summit - testo alternativo](/help/summit/l820-lab-workbook/assets/adobe-summit.png "Adobe Summit")

## L820 - Creare momenti mobili personalizzati con Adobe Journey Optimizer

In questo laboratorio pratico puoi esplorare vari scenari mobili e imparare a implementare esperienze personalizzate per web e dispositivi mobili con Journey Optimizer.


>[!IMPORTANT]
>
>Evita di pubblicare sui social media foto o screenshot della sessione.
><br>
>**Adobe di riservatezza**
>Le informazioni e le informazioni sui prodotti che abbiamo condiviso oggi in questo laboratorio sono informazioni riservate di Adobe.
>I partecipanti non possono riprodurre, utilizzare, diffondere o divulgare informazioni riservate a nessuna persona o entità.
>Le informazioni sul prodotto sono fornite a solo scopo informativo, non garantiscono alcuna funzionalità o caratteristica futura e sono soggette a modifiche in qualsiasi momento. Di conseguenza, tali funzionalità del prodotto non fanno in alcun modo parte del tuo contratto con Adobe né sono in alcun modo vincolate a te.
><br>
>**Esclusione di responsabilità**
>Adobe offre un accesso anticipato alle funzioni, che sfruttano la tecnologia di intelligenza artificiale generativa. Queste funzioni sono ancora in fase di sviluppo e possono produrre risposte impreviste o imprecise. Apprezziamo il tuo feedback nell&#39;introduzione di questa funzione sul mercato.


### Punti chiave da eliminare

* Scopri la varietà di esperienze mobili supportate.
* Configurare una campagna push.
* Scopri come configurare le campagne in-app per dispositivi mobili.
* Configurare i messaggi web in-app.
* Verifica i tuoi scenari personalizzati.

### Prerequisiti

* Conoscere il proprio numero di posto: è possibile trovare il proprio numero di posto sulla scrivania della macchina da laboratorio:

![Postazione numero](/help/summit/l820-lab-workbook/assets/locate-seat-number.png)
È necessario accedere a:

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"} - i dettagli di accesso vengono forniti durante gli esercizi.
* [Sito Web Fréscopa](https://dsn.adobe.com/p/adobe-summit-2024?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsImlzc3VlciI6InNoYXJlZC1saW5rIiwiYXJnb24iOnsiYWNjZXNzIjoicmVhZC1wcm9qZWN0IiwicHJvamVjdElkIjoiYWRvYmUtc3VtbWl0LTIwMjQifSwiaWF0IjoxNzEwNTI0MTIwLCJleHAiOjE3MTIzMzg1MjB9.q2uGVst6HjJw8SCWl-3pViNzepkdGnNCvGqZnbbkTsY){target="_blank"}


### Comprendere il caso di utilizzo

Fréscopa, azienda dinamica e innovativa, è specializzata nel rivoluzionare l’esperienza del caffè attraverso la sua unica miscela di servizi di abbonamento al caffè e una vasta gamma di prodotti correlati al caffè disponibili sul suo sito web e sulla sua app mobile. Con l&#39;impegno di offrire qualità e sapore eccezionali, Fréscopa si rivolge agli appassionati di caffè in cerca di convenienza e opzioni premium.

Il cuore dell&#39;attività di Fréscopa risiede nei suoi servizi di abbonamento al caffè, che forniscono ai clienti una selezione curata di chicchi di alta qualità consegnati direttamente a casa loro. Questo approccio personalizzato garantisce agli amanti del caffè un’esperienza fresca e piacevole in base alle loro preferenze.

A complemento dei suoi servizi di abbonamento, il sito web e l&#39;app mobile di Fréscopa offrono una gamma completa di prodotti correlati al caffè, consentendo ai clienti di esplorare e migliorare i loro rituali del caffè. Dalle attrezzature per la produzione della birra agli accessori artigianali, Fréscopa offre un unico punto vendita per gli appassionati di caffè che cercano qualità e convenienza.

L&#39;impegno di Fréscopa per l&#39;eccellenza si estende oltre i suoi prodotti, in quanto l&#39;azienda si dedica alla creazione di un percorso di clienti fluido e piacevole. La combinazione di tecnologie innovative e un approccio incentrato sul cliente posiziona Fréscopa in prima linea nell&#39;industria del caffè in evoluzione. In sostanza, Fréscopa incarna la fusione di passione e tecnologia, ridefinendo il modo in cui gli individui sperimentano e godono il loro caffè. Con un focus sulla qualità, la comodità e le offerte personalizzate, Fréscopa invita gli appassionati di caffè a intraprendere un percorso di gusto, consegnato direttamente alla loro porta.
