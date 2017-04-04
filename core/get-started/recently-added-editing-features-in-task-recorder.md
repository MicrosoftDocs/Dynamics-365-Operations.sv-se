---
title: Nyligen tillagt redigeringsfunktioner i Uppgiftsinspelaren
description: "Om du använder Uppgiftsinspelning skapa stödlinjer uppgift redigerar du filerna mer effektivt med hjälp av den funktion som beskrivs i wikin."
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

# <a name="recently-added-editing-features-in-task-recorder"></a>Nyligen tillagt redigeringsfunktioner i Uppgiftsinspelaren

Om du använder Uppgiftsinspelning skapa stödlinjer uppgift redigerar du filerna mer effektivt med hjälp av den funktion som beskrivs i wikin.

Dessa funktioner är tillgängliga i den **inställningar &gt;Uppgiftsinspelning &gt;redigera inspelningen** meny.

-   Infoga steg utan att hela filen inspelningen.
-   Flytta steg under en underaktivitet utan att hela filen inspelningen.
-   Dölj registrera namn och beskrivning.

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Infoga steg utan att hela filen rerecording
Du kan nu lägga till ett steg var som helst i en guide för aktiviteten utan att spela upp inspelningen hela filen.

1.  Välj det steg som du vill att nytt steg som ska läggas till. Kontrollera steget har markerats.

Du måste ha rätt sida öppnas efter Uppgiftsinspelning om du vill infoga ett steg. Rätt sida är den sida som nytt steg inträffar. Uppgiftsinspelning har en mekanism som avgör vad som den aktiva sidan och inaktiverar funktionen om inte rätt sida är öppen. 

[![tg1](./media/tg1.png)](./media/tg1.png) 


När du är ansluten till rätt sida **Infoga steg** blir tillgänglig.

[![tg2](./media/tg2-231x300.png)](./media/tg2.png)

2. Klicka på **Infoga steg**.

När du klickar på **Infoga steg**, Uppgiftsinspelning växlar till läget för posten. Alla åtgärder som anges i Användargränssnittet spelas nu och sammanräknad steg på plats.

3. Klicka på **stoppa**.

Du kan upprepa processen att lägga till så många steg eller flytta så många underordnade aktiviteter (se nedan om underaktiviteter).

4. När du är klar redigeringen aktivitet guide du **har gjort redigeringen**, och sedan väljer något av alternativen för att spara eller publicera aktivitet guide.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Flytta steg under en underaktivitet utan att hela filen rerecording
Du kan flytta steg under en underaktivitet utan att spela upp inspelningen hela filen. Du kan också flytta underaktivitet steg eller slutet underaktivitet steg om du vill gruppera ett befintligt block med steg.

1.  Välj det steg eller de steg underaktivitet som du vill flytta. Kontrollera att steget har markerats.
2.  Ellips klickar du **flytta steg efter**.

[![tg3](./media/tg3.png)](./media/tg3.png)

3. Välj det steg eller de steg underaktivitet som du vill flytta det steg eller underaktivitet efter. Uppgiftsinspelning flyttas ett steg.

4. Avsluta underaktivitet steg, markerar du den, klickar du på ellips, klickar **flytta steg efter**, och välj sedan det steget då du vill att slutet underaktivitet steg ska.

Om du vill att det första steget i guiden uppgift som ligger inom en underaktivitet en underaktivitet steget i det andra steget Skapa och flytta sedan det första steget i den. Du kan lägga till eller flytta så många steg eller underordnade aktiviteter efter behov.

5. När du är klar redigeringen aktivitet guide du **har gjort redigeringen**, och sedan väljer något av alternativen för att spara eller publicera aktivitet guide.

## <a name="collapse-recording-name-and-description"></a>Dölj inspelningen namn och beskrivning
Du kan expandera och komprimera den **registrera namn** och **registrerar beskrivning** fält. Fler steg kommer att visas i fönstret Redigera Uppgiftsinspelning när dessa fält är dolda. 

[![tg4](./media/tg4-300x252.png)](./media/tg4.png)  

<a name="see-also"></a>Se även
--------

[Skapa dokumentation eller utbildning med uppgiftsregistreringar](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

[Snabbreferens för uppgiften inspelning](/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)


