---
title: Creare un criterio di decisione
description: Utilizza un criterio di decisione per definire la logica necessaria per determinare quali offerte vengono distribuite a un utente durante la personalizzazione.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 186e4a7d-6077-401f-9958-2f955214bc35
source-git-commit: 9a35160921988103182815efd3551151c09b9bb4
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# Creare un criterio di decisione

I criteri di decisione sono contenitori per le offerte che sfruttano il motore [!UICONTROL Decisioning] per scegliere il contenuto migliore da distribuire, a seconda del pubblico.

1. Nell&#39;editor di personalizzazione, fai clic su **[!UICONTROL Criterio di decisione]** nell&#39;area di navigazione a sinistra, quindi fai clic su **[!UICONTROL Aggiungi criterio di decisione]**.

   ![create-decision-policy](assets/decision-policy.png)

1. Fare clic su **[!UICONTROL Aggiungi]** per selezionare la strategia di selezione.

   ![criterio-decisione](assets/decision-policy2.png)

1. Fai clic su **[!UICONTROL Seleziona fallback]** per selezionare l&#39;offerta di fallback.
1. Fai clic su **[!UICONTROL Avanti]** per rivedere il criterio di decisione.
1. Fai clic su **[!UICONTROL Crea]** per completare il processo di creazione del criterio decisionale.

## Utilizzare il criterio di decisione nell’editor di codice

1. Nell&#39;editor di personalizzazione fare clic su **[!UICONTROL Inserisci criterio]**.

   Viene aggiunto il codice corrispondente al criterio di decisione.

   In questa fase, puoi includere direttamente nel codice tutti gli attributi di decisione richiesti. Questi attributi sono definiti nello schema utilizzato dal catalogo delle offerte. Gli attributi standard sono organizzati nello spazio dei nomi `__experience`, mentre tutti gli attributi personalizzati specifici dell&#39;organizzazione sono memorizzati nello spazio dei nomi `_<imsOrg>`.

   ![using_decision_policy](assets/Insert-policy.png)

   Questo codice esamina un elenco di offerte personalizzate scelte per l’utente e visualizza il testo di ciascuna offerta sulla pagina web. Mostra il messaggio (denominato `offerText`) di ogni offerta all&#39;interno di un paragrafo, in modo che gli utenti possano visualizzare chiaramente i contenuti personalizzati.

   Se non è disponibile alcuna offerta personalizzata, viene visualizzata un’offerta di fallback per garantire che lo spazio non venga lasciato vuoto.

1. Fai clic su **[!UICONTROL Salva]**, quindi attiva la campagna.
