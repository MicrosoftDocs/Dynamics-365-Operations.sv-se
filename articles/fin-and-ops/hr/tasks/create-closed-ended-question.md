---
title: Skapa en stängd avslutad fråga
description: Med stängda frågor kan du ange alternativ som den svarande kan välja mellan.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92e4f9697fc00798d917db6f7f50d7e3b8739233
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "858662"
---
# <a name="create-a-closed-ended-question"></a>Skapa en stängd avslutad fråga

[!include [task guide banner](../../includes/task-guide-banner.md)]

Med stängda frågor kan du ange alternativ som den svarande kan välja mellan. Först måste du skapa svarsgruppen med svaren och sedan skapa frågan som använder svarsgruppen. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-an-answer-group"></a>Skapa en svarsgrupp
1. Gå till Enkät > Design > Svarsgrupper.
2. Klicka på Ny.
3. Skriv ett värde i fältet Svarsgrupp.
4. Ange ett värde i fältet Beskrivning.
    * Använd slumpfunktionen för att slumpmässigt placera svaren i en annan ordning varje gång svarsgruppen används för en fråga.  
5. Klicka på Svar.
6. Klicka på Ny.
    * Sekvensnummerkontrollerar ordern svaren som visas i, om inte Slumpmässigt har valts för svarsgruppen.  
    * Poäng kan tilldelas svar för att användas vid poängsättning av enkäten.  
7. Välj ett nummer i fältet Poäng.
    * Det korrekta svaret kan markeras för att visa att det valda svaret är korrekt. Detta kan användas för att poängsätta enkäten.  
8. Skriv ett värde i fältet Svar.
    * Fortsätt att skapa svarsurvalsalternativ för svarsgruppen.  
9. Klicka på Ny.
10. Välj ett nummer i fältet Poäng.
11. Skriv ett värde i fältet Svar.
12. Klicka på Ny.
13. Välj ett nummer i fältet Poäng.
14. Skriv ett värde i fältet Svar.
15. Klicka på Ny.
16. Välj ett nummer i fältet Poäng.
17. Skriv ett värde i fältet Svar.
18. Klicka på Ny.
19. Välj ett nummer i fältet Poäng.
20. Skriv ett värde i fältet Svar.
21. Stäng sidan.
22. Stäng sidan.

## <a name="create-the-question"></a>Skapa frågan
1. Gå till Enkät > Design > Frågor.
2. Klicka på Ny.
3. Använd fältet Typ för att gruppera relaterade frågor tillsammans.
    * Du kan använda ange indatatyper för kryssrutan, alternativsknappen eller kombinationsrutan för stängda frågor.  
4. Välj ett alternativ i fältet Indatatyp.
5. Ange eller välj ett värde i fältet Svarsgrupper.
6. Skriv ett värde i fältet Text.

