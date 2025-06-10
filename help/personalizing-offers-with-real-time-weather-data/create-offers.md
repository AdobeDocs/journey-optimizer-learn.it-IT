---
title: Crea offerte per testare il decisioning e la classificazione dinamici.
description: Un elemento di offerta nelle decisioni rappresenta un singolo contenuto personalizzato, ad esempio un messaggio, un’immagine, una promozione o un consiglio, che può essere consegnato a un utente in base a regole e condizioni definite.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: c04a15418e31dc82597b7759386907013728bb0d
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---


# Creare offerte per testare il decisioning dinamico e la classificazione

Queste offerte sono progettate per testare il decisioning dinamico e la classificazione in base a input contestuali in tempo reale (come la temperatura), trasmessi tramite Adobe Web SDK (alloy(&quot;sendEvent&quot;)).

Prima di creare le offerte, lo schema Elemento offerta veniva esteso per includere un nuovo campo: offerText

![schema-offerta](assets/offer-schema.png).

Crea le tre offerte seguenti


## Offerta meteo caldo(Tag:hot)

Il testo dell’offerta per le offerte con meteo caldo

```html
<div data-tags="weather hot skincare sunscreen" style="border: 1px solid #e0e0e0; padding: 1.5rem; border-radius: 10px; background-color: #fff3e0;">   <h2 style="color: #e65100;">Protect Your Skin This Summer</h2>   <p>High temperatures mean high UV risk. Get <strong>20% off</strong> our dermatologist-recommended sunscreens and skin protection kits.</p>   <p>Offer valid this week only for areas with temperatures over 90°F.</p>   <a href="#" style="display:inline-block; margin-top:1rem; padding:0.75rem 1.5rem; background:#e65100; color:white; border-radius:5px; text-decoration:none;">Shop Sunscreen</a> </div>
```


## Offerta meteo mite(Tag:spring)

Il testo dell’offerta per il clima mite

```html
<div data-tags="ajo offer-mild-weather">   <h2 style="color: #2e7d32;">🌤️ Enjoy the Outdoors — Gear Up Now!</h2>   <p style="font-size: 1.1rem;">Perfect weather to be outside! Check out our selection of <strong>picnic sets, walking shoes, and fitness accessories</strong> for your next outdoor adventure.</p>   <p style="font-size: 1.1rem;">Get <strong>free shipping</strong> on all outdoor gear this week.</p>   <a href="#" style="display:inline-block;padding:0.75rem 1.5rem;background:#2e7d32;color:white;border-radius:6px;text-decoration:none;margin-top:1rem;">Explore Outdoor Picks</a> </div>
```

## Offerta tempo freddo(Tag:cold)

Il testo dell’offerta per l’offerta per il clima freddo

```html
<div class="offer-content" style="text-align: center; padding: 1rem;">   <img src="https://raw.githubusercontent.com/gbedekar489/gbedekar489.github.io/main/weather/pexels-romanp-16170.jpg"         alt="Winter clothing"         style="width: 100%; max-width: 400px; border-radius: 12px; margin-bottom: 1rem;">   <h2>Cold Weather, Hot Deals 🧤</h2>   <p>Stay warm in style with our exclusive <strong>25% off</strong> winter outerwear. From puffer jackets to wool scarves, find the perfect layers to beat the chill.</p>   <p><strong>Use code:</strong> <code>WINTER25</code> at checkout</p>   <p><em>Limited time offer. While supplies last.</em></p> </div>
```

### Crea raccolta

Passa a **_Decisioning -> Cataloghi ->Raccolta->Crea raccolta_**
Denomina la raccolta **Offerte correlate al meteo**

Raggruppa queste offerte in questa raccolta utilizzando il generatore di regole.

