--- 
title: "Leverera försäljningsorder utan lagerstyrning"
description: "I den här handboken visas hur du uppdaterar en försäljningsorder när produkter skickas till kunden."
author: omulvad
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8e7d2198b4976a6f60f05690d7b6f11f3da55e28
ms.openlocfilehash: a98e58b26432ee01e62d60f81a768f14568e34e4
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---
# <a name="ship-sales-orders-without-warehousing"></a>Leverera försäljningsorder utan lagerstyrning

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här handboken visas hur du uppdaterar en försäljningsorder när produkter skickas till kunden. Guiden gäller uppfyllelseflödet som inte ställs in för lagerstyrning (varken grundläggande eller avancerad lagerstyrning) och därför inte kräver att produktplockningen ska registreras före leverans. Du kan köra den här proceduren med dina egna uppgifter i demonstrationsföretaget USMF. I båda fallen innan du startar den här uppgiften, skapa en försäljningsorder för inventerad produkt med samma mängd större än 1. För att undvika bokföringsfelt måste du kontrollera att produktens lagerbehållning på plats och lagerställe som du har valt på ordern omfattar orderkvantiteten.


## <a name="post-packing-slip-for-an-order"></a>Bokför följesedel för en order
1. Gå till försäljning och marknadsföring > beställningar > Alla beställningar.
2. I listan söker du och väljer den order som du har skapat för uppgiften.
3. Klicka på länken på den valda raden i listan.
4. Klicka på Plocka och packa i åtgärdsfönstret.
5. Klicka på Bokför följesedel.
6. Utöka eller komprimera avsnittet Parametrar.
7. Välj Alla i fältet Kvantitet.
    * Andra alternativ inkluderar Leverera nu och Plockat. Om orderraden ska levereras delvis och fältet Leverera nu på orderraden innehållen en kvantitet ska du välja Leverera nu. Om organisationens uppfyllelseflöde inkluderar plockning som en separat process som administreras av och registreras med en plocklista, ska du välja Plockat.  
    * Kontrollera att alternativet Bokför har värdet Ja.  
8. Ställ in alternativet Skriv ut följesedel på Ja.
    * Fliken Översikt innehåller en lista med följesedlar som ska genereras i den här bokföringen. Om du skickar en enskild order, finns det vanligtvis en följesedel. Men om orderns rader ska levereras från olika platser, delas bokföringen automatiskt upp i flera dokument. Detta är ett obligatoriskt och det går inte att ändra. På liknande sätt kommer bokföringen också att delas upp i flera dokument om orderns rader ska skickas till olika leveransadresser, och leveransregeln är inställd på att kräva en delning.  
9. Markera raden för att orderraden ska skickas på fliken Rader.
10. Ange ett värde som är lägre än den ursprungliga kvantiteten i fältet Uppdatera.
11. Klicka på OK.
12. Klicka på Ja.
13. Stäng sidan.
14. Klicka på Alternativ i åtgärdsfönstret.
15. Klicka på Ändra vy.
16. Klicka på Huvudvy.
    * Om alla rader på ordern har skickats ändras orderstatusen från Öppen till Levererat.  
    * I det här exemplet har orderraden skickats delvis. Därför är orderstatusen fortfarande Öppen.     
    * Dokumentstatusfältet har värdet Följesedel eftersom minst en orderrad har skickats.  
17. Klicka på Allmänt i åtgärdsfönstret.
18. Klicka på Radkvantitet.
19. Stäng sidan.
20. Klicka på Plocka och packa i åtgärdsfönstret.
21. Klicka på Följesedel.
    * Sidan Följesedelsjournal innehåller alla följesedlar som har skapats för ordern. Du kan granska informationen i varje dokument och skriva ut dem vid behov.  


