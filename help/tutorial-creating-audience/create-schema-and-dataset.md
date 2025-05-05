---
title: Configurare lo schema XDM, il set di dati, lo stream di dati e i tipi di pubblico in AEP
description: Creazione di schemi XDM, set di dati, stream di dati e tipi di pubblico
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---


# Configurare schema XDM, set di dati, stream di dati e tipi di pubblico in AEP

* Accedi a Adobe Experience Platform

* Crea in Journey Optimizer uno schema basato su eventi XDM denominato Financial Advisors. Se non sai creare uno schema, segui questa [documentazione](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/tutorials/create-schema-ui)

* Aggiungi la seguente struttura allo schema. L&#39;elemento PreferredFinancialInstrument memorizza la preferenza dell&#39;utente per Scorte, Obbligazioni, CD
  ![xdm-schema](assets/xdm-schema.png)

* L&#39;elemento PreferredFinancialInstrument ha valori enum definiti come illustrato di seguito
  ![enum-values](assets/enum-values.png)

* Assicurati che lo schema sia abilitato per il profilo.

## Creare un set di dati basato sullo schema

Un **set di dati in Adobe Experience Platform (AEP)** è un contenitore di archiviazione strutturato utilizzato per acquisire, archiviare e attivare dati in base a uno schema XDM definito.

* Creare un set di dati denominato _Set di dati di Financial Advisors_ in base allo schema XDM (Financial Advisors) creato nel passaggio precedente.

* Assicurati che il set di dati sia abilitato per il profilo

## Creare uno stream di dati

Un flusso di dati in Adobe Experience Platform è simile a una pipeline (o autostrada) sicura che connette il sito web o l’app ai servizi Adobe, consentendo il flusso dei dati e la reintroduzione di contenuti personalizzati.

* Vai a AEP > Datastreams (Stream di dati), quindi fai clic su New Datastream (Nuovo stream di dati). Denomina lo stream di dati _Flusso di dati di Financial Advisors_

* Fornisci i seguenti dettagli come mostrato nella schermata seguente
  ![flusso di dati](assets/datastream.png)
* Fai clic su Salva, quindi su Aggiungi mappatura e aggiungi il servizio Adobe Experience Platform e il set di dati dell’evento come mostrato
  ![datastream-mapping](assets/datastream-service.png)

* Scegli il set di dati evento appropriato (creato in precedenza).

* Salvare lo stream di dati

## Creare tipi di pubblico

I tipi di pubblico in Adobe Experience Platform sono gruppi di utenti creati in base alle loro azioni, preferenze o informazioni di profilo, per fornire esperienze personalizzate.

* Passa a Cliente -> Pubblico
* Creare tipi di pubblico utilizzando il metodo Genera regola

* Crea i seguenti 3 tipi di pubblico in AJO utilizzando l&#39;elemento PreferredFinancialInstrument dallo schema dell&#39;evento.

   * Clienti interessati alle scorte

   * Clienti interessati alle obbligazioni

   * Clienti interessati al CD

Assicurati che il metodo di valutazione per ogni pubblico sia impostato su Edge per la qualifica in tempo reale.

Le schermate seguenti sono utili per creare i tipi di pubblico.

![pubblico](assets/rule-based-audience.png)

![evento](assets/event-attribute.png)


![StrumentoFinanziarioPreferito](assets/stock-customers.png)

![edge-audience](assets/audience-edge.png)