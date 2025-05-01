---
title: Creazione di tipi di pubblico
description: Creazione di tipi di pubblico di AJO in base alle preferenze di investimento degli utenti (azioni, obbligazioni, CD)
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: f970a1780b1bdf717675cd79c98a38ac422a679f
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---


# Creazione di tipi di pubblico di AJO in base alle preferenze di investimento degli utenti (azioni, obbligazioni, CD)

Questa esercitazione illustra come acquisire le preferenze degli utenti tramite un modulo web, inviare tali dati a Adobe Experience Platform (AEP) in tempo reale e qualificare dinamicamente gli utenti in tipi di pubblico mirati in base alle selezioni effettuate. Combinando Adobe Tags (Launch), AEP Web SDK (Alloy.js) e Edge Segmentation, potrai abilitare opportunità di personalizzazione immediata per i clienti interessati a Stock, Obbligazioni o Certificati di deposito (CD).

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

Gli utenti invieranno le loro preferenze tramite un modulo web e tali preferenze verranno acquisite tramite AEP Web SDK utilizzando Adobe Launch, consentendo la qualificazione del pubblico in tempo reale.

## Strumenti utilizzati

* Adobe Experience Platform (AEP)

* Tag Adobe Experience Platform

* AEP Web SDK (Alloy.js)

* Segmentazione di AEP Edge

* Una pagina Web con un modulo di preferenze





