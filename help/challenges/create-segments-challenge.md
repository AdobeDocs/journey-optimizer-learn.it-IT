---
title: 'Sfida 1: creare segmenti'
description: Applica ciò che hai imparato sulla creazione di segmenti e verifica le tue abilità.
kt: 8417
feature: Segments
role: User
level: Beginner
source-git-commit: 676f0b268f7f67d179bfa944b72cb68191640c74
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---


# Sfida 1: creare segmenti

## La storia

Luma, un&#39;azienda fittizia di abbigliamento atletico, sta cercando di promuovere la sua ultima collezione di abbigliamento e abbigliamento e di stimolare le vendite per i clienti esistenti. Per supportare la nuova campagna di raccolta, il team di marketing Luma ti chiede di creare la [segmenti](/help/set-up-resources/create-segments.md) necessari per generare il percorso per la campagna.

## La tua sfida

Crea i seguenti segmenti in Journey Optimizer.

### Segmento 1 - Clienti attivi

Crea un pubblico da indirizzare con il nuovo annuncio della raccolta estiva:

* Denomina questo segmento *nome utente - Clienti attivi*
* Il pubblico deve includere solo clienti Luma attivi. I clienti attivi sono definiti come clienti che hanno un livello nel programma fedeltà di Luma (argento, oro, platino o diamante)

**CRITERI DI SUCCESSO**

1. Nel generatore di segmenti puoi visualizzare il numero stimato di profili qualificati. Se lavori nella sandbox di addestramento, questo numero deve essere uguale o maggiore di 0.
2. È stato aggiunto al segmento un profilo di qualificazione:
   * Puoi verificare se un profilo è stato aggiunto al segmento passando a uno dei profili elencati nella scheda Dettaglio.
   * Nella pagina del profilo, controlla gli attributi per confermare che si qualificano, quindi controlla l’appartenenza al segmento.

+++**CONTROLLA IL TUO LAVORO**
Seleziona il livello (profilo singolo CDM >Fedeltà> Livello)

Questo è l’aspetto del segmento:

![Segmento 1 - Clienti attivi](/help/challenges/assets/C1-S1.png)

Controlla il codice nell&#39;angolo in basso a destra della schermata Modifica segmento, in Eventi. Il codice deve essere simile al seguente:

loyalty.tier.equals(&quot;diamond&quot;, false) o loyalty.tier.equals(&quot;gold&quot;, false) o loyalty.tier.equals(&quot;platinum&quot;, false) o loyalty.tier.equals(&quot;silver&quot;, false)

+++

## Segmento n. 2 - Elementi della lista dei desideri esauriti

Per indirizzare i potenziali clienti interessati quando i prodotti vengono riconcentrati, crea un pubblico composto da clienti

* che hanno aggiunto un elemento al loro elenco dei desideri (tipo di evento Salva per successivo)
* non era disponibile negli ultimi tre mesi,
* e non hanno successivamente acquistato l&#39;articolo.

Assegna un nome al segmento: *il tuo nome - Out-of-stock-Wishlist*

**CRITERI DI SUCCESSO**

TBD