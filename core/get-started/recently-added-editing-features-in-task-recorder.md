---
title: Nyligen tillagda redigeringsfunktioner i Uppgiftsinspelare
description: "Om du använder Uppgiftsinspelare för att skapa uppgiftsguider kan du redigera filerna mer effektivt med hjälp av den funktion som beskrivs i wikin."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core
ms.custom: 266464
ms.assetid: b4640e67-4b92-4855-8041-1bfc71aadc47
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: c4f9ac515eab6ed8b194fc8985f6d3fae40ced38
ms.lasthandoff: 03/31/2017


---

# <a name="recently-added-editing-features-in-task-recorder"></a>Nyligen tillagda redigeringsfunktioner i Uppgiftsinspelare

Om du använder Uppgiftsinspelare för att skapa uppgiftsguider kan du redigera filerna mer effektivt med hjälp av den funktion som beskrivs i wikin.

Dessa funktioner är tillgängliga på menyn **Inställningar &gt; Uppgiftsinspelare &gt; Redigera inspelning**.

-   Infoga steg utan att hela filen spelas in igen.
-   Flytta steg under en underuppgift utan att spela in hela filen igen.
-   Komprimera fälten Inspelningens namn och beskrivning.

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Infoga steg utan att spela in hela filen igen.
Du kan nu lägga till ett steg var som helst i en uppgiftsguide utan att spela in hela filen igen.

1.  Välj det steg som du vill att det nya steget ska läggas till efter. Kontrollera att steget har markerats.

Du måste ha rätt sida öppen för att uppgiftsinspelaren ska infoga ett steg. Rätt sida är den sida på vilken det nya steget inträffar. Uppgiftsinspelaren har en mekanism som avgör vad som är den aktiva sidan och inaktiverar funktionen om inte rätt sida är öppen. 

[![tg1](./media/tg1.png)](./media/tg1.png) 


När du är på rätt sida blir **Infoga steg** tillgängligt.

[![tg2](./media/tg2-231x300.png)](./media/tg2.png)

2. Klicka på **Infoga steg**.

När du klickar på **Infoga steg** växlar Uppgiftsinspelare till inspelningsläge. Alla åtgärder som vidtas i användargränssnittet spelas nu in och läggs på plats som steg.

3. Klicka på **Stoppa**.

Du kan upprepa processen och lägga till så många steg eller flytta så många underuppgifter som behövs (se nedan om underuppgifter).

4. När du är klar med redigeringen av uppgiftsguiden klickar du på **Redigeringen är slutförd**, och väljer sedan något av alternativen för att spara eller publicera uppgiftsguide.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Flytta steg under en underuppgift utan att spela in hela filen igen
Du kan flytta steg under en underuppgift utan att spela upp eller spela in hela filen igen. Du kan också flytta underuppgiftens steg eller det avslutande steget för underuppgiften om du vill gruppera ett befintligt block med steg.

1.  Välj steget eller underuppgiftssteget som du vill flytta. Kontrollera att steget har markerats.
2.  Klicka på ellipsen och klick på **Flytta steg till efter**.

[![tg3](./media/tg3.png)](./media/tg3.png)

3. Välj det steg eller underuppgiftssteg till vilket du vill flytta steget eller underuppgiftssteget efter. Uppgiftsinspelaren flyttar steget.

4. För att flytta underuppgiftssteget, markerar det, klicka på ellipsen, klickar på **Flytta steg till efter**, och välj sedan steget efter vilket du vill att underuppgiftssteget ska placeras.

Om du vill att det första steget i uppgiftsguiden ska vara inom en underuppgift, skapa ett underuppgiftssteg som det andra steget, och flytta sedan in det första steget i det. Du kan lägga till eller flytta så många steg eller underuppgifter som behövs.

5. När du är klar med redigeringen av uppgiftsguiden klickar du på **Redigeringen är slutförd**, och väljer sedan något av alternativen för att spara eller publicera uppgiftsguide.

## <a name="collapse-recording-name-and-description"></a>Komprimera Inspelningens namn och beskrivning
Du kan expandera och komprimera fälten **Inspelningens namn** och **Inspelningens beskrivning**. När dessa fält är komprimerade visas fler steg i Uppgiftsinspelarens redigeringsfönster. 

[![tg4](./media/tg4-300x252.png)](./media/tg4.png)  

<a name="see-also"></a>Se även
--------

[Skapa dokumentation eller utbildning med uppgiftsregistreringar](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

[Snabbreferens för Uppgiftsinspelare](/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)


