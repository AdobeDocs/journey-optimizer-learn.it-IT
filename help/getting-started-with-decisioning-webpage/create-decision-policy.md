---
title: Crea criterio di decisione
description: Un criterio di decisione definisce la logica utilizzata per determinare quali offerte vengono consegnate a un utente durante la personalizzazione.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 186e4a7d-6077-401f-9958-2f955214bc35
source-git-commit: 6bf0c2487afff4811aa94e9591ae29c38af15d34
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---

# Crea criterio di decisione

I criteri di decisione sono contenitori per le offerte che sfruttano il motore di decisione per scegliere il contenuto migliore da distribuire, a seconda del pubblico.

Nell’editor di personalizzazione, fai clic sull’elemento Criterio di decisione nell’area di navigazione a sinistra, quindi su Aggiungi criterio di decisione

![create-decision-policy](assets/decision-policy.png)

Fai clic su Aggiungi per selezionare la strategia di selezione
Fai clic su Seleziona fallback per selezionare l’offerta di fallback.
Fai clic su Avanti per rivedere il criterio di decisione e su Crea per completare il processo di creazione del criterio di decisione.


![criterio-decisione](assets/decision-policy2.png)


## Utilizzare il criterio di decisione nell’editor di codice

Dall’editor di personalizzazione, fai clic su Inserisci criterio.Viene aggiunto il codice corrispondente al criterio di decisione.

In questa fase, puoi includere direttamente nel codice tutti gli attributi di decisione richiesti. Questi attributi sono definiti nello schema utilizzato dal catalogo delle offerte. Gli attributi standard sono organizzati nello spazio dei nomi __experience, mentre tutti gli attributi personalizzati specifici dell&#39;organizzazione sono memorizzati nello spazio dei nomi `_<imsOrg>`.

![using_decision_policy](assets/Insert-policy.png)

Questo codice esamina un elenco di offerte personalizzate scelte per l’utente e visualizza il testo di ciascuna offerta sulla pagina web. Mostra il messaggio (denominato offerText) di ogni offerta all’interno di un paragrafo, in modo che gli utenti possano visualizzare chiaramente i contenuti personalizzati.
Se non è disponibile alcuna offerta personalizzata, viene visualizzata un’offerta di fallback per garantire che lo spazio non venga lasciato vuoto.

Fai clic su Salva, quindi attiva la campagna.
