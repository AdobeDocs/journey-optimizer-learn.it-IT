---
title: Configurare schema XDM, set di dati e stream di dati in AEP
description: Creazione di schema XDM, set di dati e stream di dati
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 1c7fe9e7-ab72-4d7b-960a-512d0e25808b
source-git-commit: 95a8abd08fbf57900870826112b01a8cd375fe96
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# Configurare schema XDM, set di dati e stream di dati in AEP

## Crea schema XDM

Per utilizzare Adobe Experience Platform Web SDK (Alloy.js) in una pagina web, i tag di AEP devono essere associati a uno stream di dati mappato a uno schema evento XDM. Il Web SDK (alloy.sendEvent) invia dati ad AEP come eventi esperienza, che devono essere conformi a uno schema XDM basato sulla classe XDM ExperienceEvent.

Per creare uno schema XDM

- Accedi a Adobe Experience Platform
- Passa a _&#x200B;**Gestione dati -> Schemi -> Crea schema**&#x200B;_

- Crea uno schema basato su evento XDM denominato **_Schema meteo_**. Se non sai creare uno schema, segui questa [documentazione](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/tutorials/create-schema-ui)


- Assicurati che lo schema presenti i seguenti campi con il tipo di dati appropriato.

- ![schema-meteo](assets/weather-schema.png)

- Aggiungere il gruppo di campi _&#x200B;**Dettagli Web**&#x200B;_ allo schema. Questo gruppo di campi è obbligatorio a scopo di reporting.

## Creare un set di dati basato sullo schema

Un **set di dati in Adobe Experience Platform (AEP)** è un contenitore di archiviazione strutturato utilizzato per acquisire, archiviare e attivare dati in base a uno schema XDM definito.

- Passa a _&#x200B;**Gestione dati -> Set di dati -> Crea set di dati**&#x200B;_
- Crea un set di dati denominato **_Set di dati-Schema-Meteo_** in base allo schema XDM(_&#x200B;**Schema-Meteo**&#x200B;_) creato nel passaggio precedente.


## Creare uno stream di dati

Un flusso di dati in Adobe Experience Platform è simile a una pipeline (o autostrada) sicura che connette il sito web o l’app ai servizi Adobe, consentendo il flusso dei dati e la reintroduzione di contenuti personalizzati.

- Passa a _&#x200B;**Raccolta dati > Flussi dati**&#x200B;_, quindi fai clic su Nuovo flusso dati. Denomina lo stream di dati **relativo al meteo-stream**


- Fornisci i seguenti dettagli come mostrato nella schermata seguente
  ![flusso di dati](assets/datastream.png)
- Fai clic su Salva, quindi su Aggiungi mappatura e aggiungi il servizio Adobe Experience Platform e il set di dati dell’evento con le caselle di controllo appropriate selezionate
  ![datastream-mapping](assets/datastream-service.png)

- Salva lo stream di dati.
