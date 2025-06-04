---
title: Importare dati CRM di esempio nel set di dati del profilo di AEP
description: Importa record di esempio (ad esempio, con CRMID, e-mail, entrate, codice postale) per convalidare se AEP può unire correttamente tali profili con visitatori web anonimi in base a identificatori condivisi come ECID.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 33c8c386-f417-45a8-83cf-7312d415b47a
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 4%

---

# Importare dati CRM di esempio nel set di dati del profilo di AEP

Per iniziare l’unione delle identità, importa dati di profilo CRM di esempio in un set di dati associato a uno schema abilitato al profilo in Adobe Experience Platform

## Creare uno spazio dei nomi personalizzato

* Passa a Cliente -> Identità -> Crea spazio dei nomi identità
* Seleziona Singolo ID multi-dispositivo e fornisci il nome visualizzato e il simbolo di identità come mostrato nella schermata seguente.
  ![spazio dei nomi personalizzato](assets/custom-namespace.png)

## Creare uno schema abilitato per il profilo

Crea un singolo schema di profilo denominato **_FinWiseProfileSchema_**. Includi campi quali annualIncome, email, firstName, lastName e loyaltyStatus.
Aggiungere un campo di identità **_crmid_** nell&#39;oggetto SystemIdentifier. Contrassegna il campo crmid come identità e primario


![schema-profilo](assets/finwise-profile-schema.png)

## Preparare i dati di esempio

| crmId | firstName | lastName | e-mail | loyaltyStatus | zipCode | annualIncome |
|--------|-----------|----------|-------------------------|---------------|---------|--------------|
| FIN001 | Alice | Wong | alice.wong@example.com | Oro | 92128 | 120000 |
| FIN002 | Bob | Smith | bob.smith@example.com | Argento | 92126 | 85000 |
| FIN003 | Charlie | Kim | charlie.kim@example.com | Platino | 60614 | 175000 |
| FIN004 | Diana | Lee | diana.lee@example.com | Oro | 30303 | 98000 |
| FIN005 | Ethan | Marrone | ethan.brown@example.com | Bronzo | 75201 | 60000 |

## Acquisire il file CSV

* Crea un set di dati denominato **_FinWiseCustomerDataSetWithAnnualIncome_** in base allo **_FinWiseProfileSchema_** creato nel passaggio precedente

* Passa a Connessioni -> Origini -> Sistema locale
* Selezionare **_Aggiungi dati_** nel caricamento del file locale. Seleziona _**FinWiseCustomerDataSetWithAnnualIncome**_ come set di dati di destinazione.
  ![ingest-csv](assets/ingest-csv-into-dataset.png)
* Passa alla schermata successiva. Carica il [file csv](assets/finwise_profiles.csv) e verifica i mapping
  ![mappature](assets/mappings.png)

* Fai clic su Fine per avviare il processo di acquisizione dei dati

## Verifica profilo

* Passa a Cliente ->Profili e cerca ID CRM FinWise uguale a FIN001 o qualsiasi altro valore valido
  ![profilo di verifica](assets/verify-profiles.png)
