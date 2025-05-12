---
title: Configurare Schema XDM, Set di dati e Stream di dati in AEP
description: Creazione di schema XDM, set di dati e stream di dati
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
exl-id: 0efa418a-5b4f-4012-a6fc-afaa34a59285
source-git-commit: 15b2379c251ed0d7583a01fb6af67815322456cf
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Configurare schema XDM, set di dati e stream di dati in AEP

## Crea schema XDM

* Accedi a Adobe Experience Platform
* Gestione dati -> Schemi -> Crea schema

* Creare uno schema basato su eventi XDM denominato _Financial Advisors_. Se non sai creare uno schema, segui questa [documentazione](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)

* Aggiungi la seguente struttura allo schema. L&#39;elemento PreferredFinancialInstrument memorizza la preferenza dell&#39;utente per Scorte, Obbligazioni, CD. **__techmarketingdemos_**&#x200B;è l&#39;ID tenant e sarà diverso nell&#39;ambiente.
  ![xdm-schema](assets/xdm-schema.png)

* L&#39;elemento PreferredFinancialInstrument ha valori enum definiti come illustrato di seguito
  ![enum-values](assets/enum-values.png)

* Assicurati che lo schema sia abilitato per il profilo.

## Creare un set di dati basato sullo schema

Un **set di dati in Adobe Experience Platform (AEP)** è un contenitore di archiviazione strutturato utilizzato per acquisire, archiviare e attivare dati in base a uno schema XDM definito.


* Gestione dati -> Set di dati -> Crea set di dati
* Creare un set di dati denominato _Set di dati di Financial Advisors_ in base allo schema XDM (Financial Advisors) creato nel passaggio precedente.

* Assicurati che il set di dati sia abilitato per il profilo

## Creare uno stream di dati

Un flusso di dati in Adobe Experience Platform è simile a una pipeline (o autostrada) sicura che connette il sito web o l’app ai servizi Adobe, consentendo il flusso dei dati e la reintroduzione di contenuti personalizzati.

* Data Collection > Datastreams, quindi fai clic su New Datastream. Denomina lo stream di dati _Flusso di dati di Financial Advisors_

* Fornisci i seguenti dettagli come mostrato nella schermata seguente
  ![flusso di dati](assets/datastream.png)
* Fai clic su Salva, quindi su Aggiungi mappatura e aggiungi il servizio Adobe Experience Platform e il set di dati dell’evento come mostrato
  ![datastream-mapping](assets/datastream-service.png)

* Scegli il set di dati evento appropriato (creato in precedenza).

* Salvare lo stream di dati

