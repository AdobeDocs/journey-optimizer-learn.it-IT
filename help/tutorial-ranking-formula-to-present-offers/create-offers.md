---
title: Creare offerte basate sulla posizione con targeting del codice postale
description: Un elemento di offerta nelle decisioni rappresenta un singolo contenuto personalizzato, ad esempio un messaggio, un’immagine, una promozione o un consiglio, che può essere consegnato a un utente in base a regole e condizioni definite.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---


# Creare offerte basate sulla posizione con targeting del codice postale

Prima di creare le offerte, lo schema Elemento offerta veniva esteso per includere un nuovo campo: zipcode. Questo campo personalizzato consente a ogni offerta di essere esplicitamente taggata con il relativo codice postale di destinazione, consentendo un filtro basato sulla posizione e una classificazione durante il processo decisionale.

Con lo schema aggiornato, sono state create due offerte personalizzate:

* Offerta 1: &quot;Piani d&#39;investimento flessibili per Mira Mesa (92126)&quot;
Questa offerta, personalizzata per i giovani professionisti e per i residenti specializzati nella tecnologia in 92126, promuove opzioni di investimento flessibili come ETF e fondi comuni di investimento mirati alla crescita a lungo termine. Il campo zipcode è impostato su 92126.

* Offerta 2: &quot;CD ad alto rendimento per Rancho Bernardo (92128)&quot;
Destinata a persone finanziariamente stabili e pronte per il pensionamento in 92128, questa offerta dispone di certificati di deposito ad alto rendimento (CD) con rendimenti garantiti. Il campo zipcode è impostato su 92128.

Queste offerte ora sono arricchite con metadati di posizione, che li rendono idonei alla selezione dinamica e alla classificazione in base ai codici ZIP del profilo utente nei passaggi successivi.

La schermata seguente mostra gli attributi personalizzati aggiunti allo schema dell’elemento dell’offerta.

![offerte-metadati](assets/offers-meta-data.png)


## Offerta per 92126

Testo dell’offerta per le offerte 92126 codice postale

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #f9f9f9; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">   <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">     Boost Your Financial Game with Smart Investment Options   </h2>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     In Mira Mesa (92126), ambition meets opportunity. Whether you're building wealth or just getting started, our     <strong>diversified investment plans</strong> — including <strong>tech-focused ETFs</strong> and     <strong>flexible mutual funds</strong> — are designed to grow with your goals.   </p>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Enjoy expert guidance, low fees, and strategies built for busy professionals who want more from their money — without the hassle.   </p>   <a href="#start-investing" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">     Start Investing Smarter   </a> </div>
```


## Offerta per 92128

Testo dell’offerta per le offerte 92128 codice postale

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #fdfdfd; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">   <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">     Grow Your Savings with Confidence – Exclusive CD Rates for 92128   </h2>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Live in Rancho Bernardo? Take advantage of your financial momentum with our <strong>high-yield Certificates of Deposit</strong>, offering up to <strong>5.25% APY</strong>.     Designed for peace of mind and smart growth, our flexible CD options let you lock in guaranteed returns while enjoying the stability you deserve.   </p>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Whether you're planning retirement or simply securing your future, this offer is tailored for residents like you.   </p>   <a href="#explore-cd-options" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">     Explore CD Options   </a> </div>
```

## Offerta generica (offerta di fallback)

Testo dell’offerta per Offerta generica, senza alcun codice postale associato all’offerta

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #ffffff; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">
  <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">
    Invest Smarter: Build Wealth with Flexible Financial Plans
  </h2>
  <p style="color: #333; font-size: 1rem; line-height: 1.6;">
    Looking to take control of your financial future? Our flexible investment solutions are designed to meet a wide range of goals — from growing savings to planning for retirement.
    Choose from diversified mutual funds, ETFs, and professionally managed portfolios, all with expert guidance and minimal hassle.
  </p>
  <p style="color: #333; font-size: 1rem; line-height: 1.6;">
    Whether just starting out or optimizing an existing strategy, this offer provides the tools to invest with confidence — no matter where you live.
  </p>
  <a href="#explore-investment-plans" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">
    Explore Investment Plans
  </a>
</div>
```

Raggruppa queste offerte in una raccolta denominata **_GenericOffers_**

Le offerte sono disponibili per tutti i visitatori, il che significa che non esistono vincoli di idoneità rigidi; la formula di classificazione diventa quindi critica per determinare quale offerta deve essere visualizzata in base al contesto del profilo.
Poiché le regole di idoneità non filtrano le offerte, tutte e tre sono trattate come candidati.
La strategia di selezione recupera tutti e tre.
La formula di classificazione li classifica in base agli attributi di profilo (come zipcode e annualIncome) per scegliere quello migliore.



