---
title: Importare dati CRM di esempio nel set di dati del profilo di AEP
description: Importa record di esempio (ad esempio, con CRMID, e-mail, entrate, codice postale) per convalidare se AEP può unire correttamente tali profili con visitatori web anonimi in base a identificatori condivisi come ECID.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '291'
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

| crmId | firstName | lastName | e-mail | loyaltyStatus | annualIncome |
|--------|-----------|----------|---------------------------|---------------|--------------|
| FIN001 | Alice | Wong | alice.wong@example.com | Oro | 336104 |
| FIN002 | Brian | Smith | brian.smith@example.com | Argento | 191065 |
| FIN003 | Cathy | Johnson | cathy.johnson@example.com | Bronzo | 117015 |
| FIN004 | David | Lee | david.lee@example.com | Bronzo | 61869 |
| FIN005 | Eva | Martinez | eva.martinez@example.com | Argento | 191371 |
| FIN006 | Frank | Marrone | frank.brown@example.com | Argento | 196132 |
| FIN007 | Grace | Kim | grace.kim@example.com | Oro | 309851 |
| FIN008 | Henry | Davis | henry.davis@example.com | Oro | 318378 |
| FIN009 | Isla | Clark | isla.clark@example.com | Argento | 181776 |
| FIN010 | Jack | Lopez | jack.lopez@example.com | Argento | 186643 |

## Acquisire il file CSV

* Crea un set di dati denominato **_FinWiseCustomerDataSetWithAnnualIncome_** in base allo **_FinWiseProfileSchema_** creato nel passaggio precedente

* Passa a Connessioni -> Origini -> Sistema locale
* Selezionare **_Aggiungi dati_** nel caricamento del file locale. Seleziona _**FinWiseCustomerDataSetWithAnnualIncome**_ come set di dati di destinazione.
  ![ingest-csv](assets/ingest-csv-into-dataset.png)
* Passa alla schermata successiva. Carica il [file csv](assets/sample_crm_data.csv) e verifica i mapping
  ![mappature](assets/mappings.png)

* Fai clic su Fine per avviare il processo di acquisizione dei dati

## Verifica profilo

* Passa a Cliente ->Profili e cerca ID CRM FinWise uguale a FIN001 o qualsiasi altro valore valido
  ![profilo di verifica](assets/verify-profiles.png)
