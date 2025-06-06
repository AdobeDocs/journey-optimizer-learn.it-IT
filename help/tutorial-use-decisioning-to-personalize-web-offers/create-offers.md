---
title: Creare un’offerta
description: Un elemento di offerta nelle decisioni rappresenta un singolo contenuto personalizzato, ad esempio un messaggio, un’immagine, una promozione o un consiglio, che può essere consegnato a un utente in base a regole e condizioni definite.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: d705992a-0d47-4bb9-b3d8-b925974e64cb
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 1%

---

# Creare un’offerta

Un elemento di offerta in AJO rappresenta un singolo contenuto personalizzato. Il contenuto può essere una promozione, un messaggio o un consiglio inviato a un utente in base alla logica decisionale.

Quando crei un elemento di offerta in AJO, questo deve essere basato su uno [!UICONTROL Schema di decisione]. Questo schema definisce la struttura e i campi disponibili nell’offerta, ad esempio titolo, descrizione, imageURL, offerText e così via.

Questo schema:

* Standardizza il modello di contenuto per tutte le offerte di una raccolta.

* Consente campi di personalizzazione coerenti tra gli elementi dell’offerta.

* Abilita le strategie di selezione per far corrispondere le regole con i contenuti strutturati

## Modificare lo schema

1. Accedi a Journey Optimizer.
1. Fai clic su **[!UICONTROL Decisioning]** > **[!UICONTROL Cataloghi]** > **[!UICONTROL Modifica schema]**.
1. Aggiungere un elemento di tipo `string` denominato `offerItem` come illustrato di seguito

   ![schema-decisioni](assets/offer-schema.png)

## Creare un elemento dell’offerta

1. Fai clic su **[!UICONTROL Decisioning]** > **[!UICONTROL Cataloghi]** > **[!UICONTROL Crea elemento]**.

1. Creare tre offerte: `Love Stocks`, `Love Bonds` e `Love CD`.

   Per ogni offerta, copia e incolla il testo dell’offerta corrispondente fornito alla fine di questo articolo nell’articolo dell’offerta appropriata.

1. Assegna alle offerte un tag con il tag creato nel passaggio precedente.
1. Aggiungi il pubblico appropriato a ogni offerta.
   ![idoneità-offerta](assets/offer-eligibility.png)
1. Approva le offerte.

Offerta completata con attributi standard e personalizzati definiti:

![offerta di titoli d&#39;amore](assets/love-bonds.png)

**Testo offerta scorte amore**

```html
<div style="font-family: Arial, sans-serif; background-color: #f9f9f9; border: 1px solid #ddd; padding: 1.5rem; border-radius: 8px; max-width: 600px; margin: auto;">   <h3 style="color: #1a73e8; margin-top: 0;">📈 Open a Stock Trading Account & Get $100 in Bonus Stock</h3>   <p style="font-size: 1rem; color: #333;">     Ready to start building your portfolio? Open a new stock trading account with us and receive a      <strong>$100 bonus in stock</strong> — on us.   </p>   <ul style="padding-left: 1.25rem; color: #444;">     <li>🧾 No account minimums — start investing with as little as $1</li>     <li>📉 $0 commissions on online stock trades</li>     <li>📊 Access to powerful trading tools and real-time analytics</li>     <li>🎓 Free educational resources to help you invest confidently</li>   </ul>   <p style="color: #333;">     It's never been easier to start trading. Join thousands of investors who trust us to help them grow their wealth.   </p>   <a href="https://yourbrokerage.com/open-account"      style="display: inline-block; margin-top: 1rem; padding: 0.75rem 1.5rem; background-color: #1a73e8; color: white; text-decoration: none; border-radius: 5px; font-weight: bold;">      🚀 Open Your Account Today   </a> </div>
```

**Testo offerta obbligazioni d&#39;amore**

```html
<div style="font-family: Arial, sans-serif; background-color: #f9f9f9; border: 1px solid #ddd; padding: 1.5rem; border-radius: 8px; max-width: 600px; margin: auto;">   <h3 style="color: #6c757d; margin-top: 0;">🏦 Invest in Stability: Explore Our Premium Bond Options</h3>   <p style="font-size: 1rem; color: #333;">     Looking for consistent income with lower risk? Our carefully selected bonds offer predictable returns and help balance your investment portfolio.   </p>   <ul style="padding-left: 1.25rem; color: #444;">     <li>📉 Lower volatility than stocks — ideal for income-focused investors</li>     <li>💵 Earn interest payments monthly, quarterly, or annually</li>     <li>🔍 Choose from government, municipal, or corporate bonds</li>     <li>🎁 Open a bond investment account today and receive a <strong>$50 interest credit</strong></li>   </ul>   <p style="color: #333;">     Whether you're preparing for retirement or just want a reliable stream of income, bonds offer a solid foundation for your financial strategy.   </p>   <a href="https://yourfirm.com/open-bond-account"      style="display: inline-block; margin-top: 1rem; padding: 0.75rem 1.5rem; background-color: #6c757d; color: white; text-decoration: none; border-radius: 5px; font-weight: bold;">      🧾 Open a Bond Account   </a> </div>
```

**Testo offerta CD amore**

```html
<div style="font-family: Arial, sans-serif; background-color: #f9f9f9; border: 1px solid #ddd; padding: 1.5rem; border-radius: 8px; max-width: 600px; margin: auto;">   <h3 style="color: #28a745; margin-top: 0;">💰 Lock in a 5.25% APY — Open Your CD Account Today</h3>   <p style="font-size: 1rem; color: #333;">     Secure your savings with a high-yield Certificate of Deposit. For a limited time, enjoy a      <strong>guaranteed 5.25% annual percentage yield (APY)</strong> on 12-month CDs.   </p>   <ul style="padding-left: 1.25rem; color: #444;">     <li>🔒 Guaranteed returns with FDIC insurance</li>     <li>📈 Lock in today's high rates before they change</li>     <li>💼 Flexible terms from 6 to 24 months</li>     <li>🎁 Open with just $500 and get a $50 bonus</li>   </ul>   <p style="color: #333;">     Whether you're saving for a short-term goal or building a conservative income strategy, our CDs offer peace of mind and predictable growth.   </p>   <a href="https://yourbank.com/open-cd"      style="display: inline-block; margin-top: 1rem; padding: 0.75rem 1.5rem; background-color: #28a745; color: white; text-decoration: none; border-radius: 5px; font-weight: bold;">      💼 Open a CD Account   </a> </div>
```
