---
title: Creare tipi di pubblico tramite Web SDK
description: Questa esercitazione spiega come acquisire le preferenze degli utenti tramite un modulo web, inviare tali dati a Adobe Experience Platform (AEP) in tempo reale e qualificare dinamicamente gli utenti in tipi di pubblico mirati in base alle loro selezioni. Combinando Adobe Tags (Launch), AEP Web SDK (Alloy.js) e Edge Segmentation, puoi offrire opportunità di personalizzazione immediata ai clienti interessati a Stock, Obbligazioni o Certificati di deposito (CD).
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
jira: KT-17923
exl-id: ebaa3aa5-0a08-43fd-8d06-8e4b5d8dee05
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%
---
# Creare tipi di pubblico tramite Web SDK

Questa esercitazione spiega come acquisire le preferenze degli utenti tramite un modulo web, inviare tali dati a Adobe Experience Platform (AEP) in tempo reale e qualificare dinamicamente gli utenti in tipi di pubblico mirati in base alle loro selezioni. Combinando Adobe Tags (Launch), AEP Web SDK (Alloy.js) e Edge Segmentation, puoi offrire opportunità di personalizzazione immediata ai clienti interessati a Stock, Obbligazioni o Certificati di deposito (CD).

## Prerequisiti per questa esercitazione

* Accesso a Adobe Experience Platform

* Nozioni di base sui concetti di Adobe Experience Platform (profili, pubblico, set di dati)

* Familiarità con i tag di Adobe (Launch): configurazione di elementi dati e regole

* Conoscenza di base di JavaScript (lettura e scrittura di funzioni semplici)

* Possibilità di utilizzare gli strumenti di sviluppo del browser (schede Console e Rete)


## OBIETTIVO

L’obiettivo di questo tutorial è generare e qualificare tre tipi di pubblico distinti in Adobe Experience Platform (AEP):

* Clienti interessati alle scorte

* Clienti interessati alle Obbligazioni

* Clienti interessati ai CD

Gli utenti inviano le proprie preferenze tramite un modulo web e tali preferenze vengono acquisite tramite AEP Web SDK utilizzando Adobe Launch, consentendo la qualificazione del pubblico in tempo reale.

## Strumenti utilizzati

* Adobe Experience Platform (AEP)

* Tag Adobe Experience Platform

* AEP Web SDK (Alloy.js)

* Segmentazione di AEP Edge

* Una pagina Web con un modulo di preferenze
