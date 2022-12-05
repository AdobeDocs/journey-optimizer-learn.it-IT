---
title: Creare un annuncio sulla collezione estiva - Sfida
description: Invia un annuncio della raccolta estiva a un segmento di clienti esistenti' per promuovere la nuova raccolta estiva Luma.
kt: 8109
role: User
level: Beginner
last-substantial-update: 2022-11-16T00:00:00Z
hide: true
exl-id: ae457be7-2c67-4950-a072-1d7030b0e17b
source-git-commit: 121faea2357883ad9672aee2eba1b7ab8278e5c2
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 2%

---

# Creare un annuncio sulla collezione estiva - Sfida

![Banner di annuncio della raccolta estiva AJO](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| Sfida | Creare un annuncio di raccolta estiva |
|---|---|
| Persona | Percorsi Manager |
| Competenze richieste | <ul><li>[Creare segmenti](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [Importare e creare contenuti e-mail HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[Caso d’uso: attività “Leggi segmento”](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Risorse da scaricare | [File e-mail di Raccolta stagionale](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## La storia

Luma, un&#39;azienda fittizia di abbigliamento atletico, sta cercando di promuovere la sua ultima collezione di abbigliamento e abbigliamento e di stimolare le vendite per i clienti esistenti. Luma sta lanciando la nuova raccolta estiva e desidera indirizzare in modo specifico diversi segmenti di clienti.

## La tua sfida

Il team di marketing Luma ti chiede di implementare una campagna di marketing di raccolta estiva in Journey Optimizer. La sfida è quella di:

* Crea un segmento che definisce i profili idonei a ricevere la promozione.
* Creare il percorso

### Passaggio 1: Definire il segmento - Clienti attivi

>[!BEGINTABS]

>[!TAB Attività]

#### Creare un segmento in Journey Optimizer

* Crea un segmento in Journey Optimizer denominato `Active Customers`.
* Il segmento deve includere solo clienti Luma attivi.
* I clienti attivi sono definiti come clienti che hanno un livello nel programma di fedeltà di Luma (argento, oro, platino o diamante).


>[!TAB Criteri di successo]

Nel generatore di segmenti puoi visualizzare il numero stimato di profili qualificati. Se lavori con i dati della sandbox di formazione, avrai a disposizione circa 753 profili qualificati su 1,29 K.

>[!NOTE]
>Possono essere necessarie fino a 24 ore per la visualizzazione dell’appartenenza al segmento per i profili esistenti, in quanto i profili esistenti devono essere riempiti in background.

**È stato aggiunto al segmento un profilo di qualificazione:**

Puoi controllare i profili aggiunti al segmento idonei accedendo a uno dei profili elencati nella vista Dettaglio del segmento.

Nella pagina del profilo, seleziona la [!UICONTROL Attributi] per confermare che sono idonei: Il livello dovrebbe essere argento, oro, platino o diamante.

![Attributi del profilo](assets/C1-S1-profile-attributes.png)

Puoi anche controllare la [!UICONTROL Iscrizione al segmento] scheda: È necessario elencare il segmento.

![Iscrizione al segmento](assets/C1-S1-profile-segment-membership.png)

>[!TAB Controlla il tuo lavoro]

Campi del segmento: [!UICONTROL Attributi] > [!UICONTROL Profilo individuale XDM] > [!UICONTROL Fedeltà] > [!UICONTROL Livello]

Questo è l’aspetto del segmento:

![Segmento - Clienti attivi](/help/challenges/assets/C1-S1.png)

Il codice deve essere simile al seguente:

```javascript
stringCompare("equals", loyalty.tier, ["diamond", "gold", "platinum", "silver"], false)
```

>[!ENDTABS]


### Passaggio 2: Crea l&#39;annuncio della raccolta Percorso - Estate

>[!BEGINTABS]

>[!TAB Attività]

#### Invia un annuncio di raccolta estiva

Un’agenzia ti ha fornito quattro file HTML con la progettazione per le e-mail:

* SeasonalCollectionEmail.html
* E-mail sulla collezione Luma Men’s Collection
* E-mail raccolta donne Luma
* Luma - 20% di sconto sull’e-mail di raccolta

1. [Scarica i file e-mail della Raccolta stagionale](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip).

2. Crea un percorso denominato `Luma - Summer collection announcement` sulla base delle seguenti linee guida:

   1. Invia *Luma - Annuncio della nuova collezione estiva* invia un&#39;e-mail a *Clienti attivi* segmento, che rappresenta il 10% del pubblico come gruppo di controllo
      * Titolo del messaggio `Luma - Summer Collection Announcement`.
      * Linea oggetto `(recipient's first name), the new Luma summer collection is here!`.
      * Utilizza il file HTML fornito *StagionaleCollectionEmail.html* per il corpo dell’e-mail.
   2. Attendi due giorni e invia un messaggio e-mail di follow-up con contenuto più mirato:
      * I clienti maschi devono ricevere **Collezione Luma Men** e-mail.
         * Titolo del messaggio: `Luma Men's Collection`
         * Oggetto: `(recipient's first name), explore Men's New athletic gear!`
         * Corpo e-mail: *MensCollectionEmail.html* per il corpo dell’e-mail.
      * Le donne devono ricevere **Collezione Luma femminile** e-mail.
         * Titolo del messaggio: `Luma Women's Collection`
         * Oggetto: `(recipient's first name), explore Luma's Women Collection!`
         * Corpo e-mail: *WomensCollectionEmail.html*
      * Gli altri clienti devono ricevere **Luma - 20% di sconto sulla raccolta** e-mail.
         * Titolo del messaggio: `Luma - 20 % off Collection`
         * Oggetto: `(recipient's first name), enjoy 20% off sales!`
         * Corpo e-mail: *20OffCollectionEmail.html*
   3. Dopo aver inviato le e-mail di destinazione di cui sopra, attendi due giorni per l’apertura dell’e-mail
   4. Se l’e-mail di destinazione non viene aperta entro 2 giorni, invia **Luma - E-mail raccolta 20 %off** come tentativo finale di retargeting


>[!TAB Criteri di successo]

#### Anteprima delle e-mail

**Messaggio e-mail n. 1 - Luma - Annuncio della raccolta estiva**

Visualizza l’anteprima del messaggio e-mail:

1. Aggiungi un profilo di test: Louise Petti:
   1. Spazio dei nomi identità: *ID CRM Luma*
   2. Valore identità: *d1f132f9f9502bba047a6ec86c4b61f9*

Risultato:
* L’oggetto dovrebbe riportare: Louise, la nuova collezione Luma è qui!
* Il corpo dell’e-mail deve corrispondere a quello visualizzato nell’anteprima: [Nuovo annuncio della collezione stagionale](/help/challenges/assets/email-assets/SeasonalCollectionEmail.html)


**Messaggio e-mail #2 - Collezione Luma Men**

Invia una prova a te stesso:

1. Aggiungi un profilo di test: Stanleigh Stooke:
   1. Spazio dei nomi identità: *ID CRM Luma*
   1. Valore identità: `4f34057d9d9e792c28ba18ecae378e98`
1. Seleziona il profilo di test: Stanleigh Stooke
1. Invia una prova a te stesso

Risultato:\
Dovresti ricevere un&#39;e-mail. L&#39;oggetto dovrebbe recitare &quot;Stanleigh, esplorare Uomo nuovo abbigliamento atletico!&quot; e il corpo dell’e-mail deve corrispondere a quello visualizzato nell’anteprima: [Collezione Luma Men](/help/challenges/assets/email-assets/MensCollectionEmail.html)

>[!NOTE]
>Può richiedere un paio di minuti per ricevere la prova.

**Messaggio e-mail #3 - Collezione Luma Women**

Visualizza in anteprima l’e-mail con il profilo di test &quot;Louise Petti&quot;.

* L’oggetto dovrebbe riportare: *Louise, esplora la Luma&#39;s Women Collection!*
* Il corpo dell’e-mail deve corrispondere a quello visualizzato nell’anteprima: [Collezione Luma femminile](/help/challenges/assets/email-assets/WomensCollectionEmail.html)


**Messaggio e-mail n. 4 - Luma 20 % di sconto sulla raccolta**

Visualizza in anteprima l’e-mail con il profilo di test &quot;Louise Petti&quot;.

* L’oggetto dovrebbe riportare: *Louise, goditi il 20% di sconto!*
* Il corpo dell’e-mail deve corrispondere a quello visualizzato nell’anteprima: [Luma 20 % di sconto sulla raccolta](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)

**Non dimenticarti di pubblicare le tue e-mail!**

#### Test del percorso

>[!IMPORTANT]
>
>Prima di impostare il percorso in modalità di test:
>
>1. Assicurati che lo spazio dei nomi dell’attività Leggi segmento sia impostato su **ID CRM Luma(lumaCrmId)**
>1. Per ogni e-mail, sovrascrivi i parametri E-mail predefiniti per le e-mail in modo che vengano inviati al tuo indirizzo e-mail:
   >    * Mostrare i valori nascosti facendo clic sul simbolo dell&#39;occhio.
   >    * Nei parametri E-mail, fai clic sul simbolo T (abilita sostituzione parametro)

      >
      >      ![Ignorare i parametri e-mail](/help/challenges/assets/c3-override-email-paramters.jpg)
   > 
   >    * Fare clic nel campo Indirizzo
   >    * Nella schermata successiva aggiungi il tuo indirizzo e-mail tra parentesi: `"yourname@yourdomain"` nell’editor espressioni e fai clic su ok.

>


Verifica il percorso e fai inviare le e-mail al tuo account:

1. Mettere il percorso in modalità di prova
2. Seleziona un singolo profilo alla volta
3. Tempo di attesa: Impostare il timer su 120 secondi (digitarlo nel campo).
4. Entrata del profilo del trigger
5. Puoi testare ogni ramo utilizzando uno dei seguenti indirizzi e-mail come identificatori di profilo:
   * Femmina: Louise Petti, Valore identità: *d1f132f9f9502bba047a6ec86c4b61f9*
   * Maschio: Stooke Stanleigh, valore Identity: `4f34057d9d9e792c28ba18ecae378e98`
   * Genere non specificato: Leora Dietsche, a8f14eab3b483c2b96171b575ecd90b1

6. Una volta attivata l’entrata del profilo, dovresti ricevere la prima e-mail, l’intestazione deve essere personalizzata in base al profilo scelto.
7. Il percorso dovrebbe continuare nel rispettivo ramo e dovresti ricevere la relativa e-mail (per esempio, se scegli Jenna, dovresti ricevere l’e-mail &quot;Luma Women’s Collection&quot;).
8. Apri la seconda e-mail e il percorso deve terminare
9. È possibile ripetere il passaggio 4. - 7. per tutti e tre i profili per verificare se tutti i rami funzionano correttamente.
10. Per verificare i timeout, impostare il tempo di attesa su 30 secondi e attivare nuovamente la voce.
11. Non aprire le e-mail che ricevi (non visualizzare in anteprima l’e-mail (!)) e lascia che il tempo di attesa giri.

Dovresti ricevere le seguenti e-mail:

* Luma - Annuncio della nuova collezione stagionale
* A seconda del profilo di test utilizzato, dovresti ricevere una delle seguenti e-mail:
   * Jenna: Collezione Luma femminile
   * Chris: Collezione Luma Men
   * Benny: Luma - 20% di sconto sulla raccolta
* Se non hai aperto la seconda e-mail: Luma - 20% Off Collection

>[!TAB Controlla il tuo lavoro]

Ecco come dovrebbe essere il tuo percorso:

![Percorso](/help/challenges/assets/c3-j1-journey.png)

**Condizione - Gruppo di controllo:**

![Gruppo di controllo](/help/challenges/assets/c3-j1-condition-control-group.png)

**Condizione - Genere:**\

![Condizione - Genere](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
