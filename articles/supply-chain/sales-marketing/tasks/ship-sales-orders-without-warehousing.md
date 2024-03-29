---
title: Leverera försäljningsorder utan lagerhållning
description: I denna artikel visas hur du uppdaterar en försäljningsorder när produkter levereras till kunden.
author: Henrikan
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, SalesTableLineQuantity, CustPackingSlipJournal
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2bb4115a486fbfe7287c9b183224699de4dfd456
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335538"
---
# <a name="ship-sales-orders-without-warehousing"></a>Leverera försäljningsorder utan lagerhållning

[!include [banner](../../includes/banner.md)]

I denna artikel visas hur du uppdaterar en försäljningsorder när produkter levereras till kunden. Guiden gäller uppfyllelseflödet som inte konfigurerats för lagerstyrning (varken grundläggande eller lagerstyrningsprocesser (WMS)) och kräver därför inte att produktplockningen ska registreras före leverans. Du kan köra den här proceduren med dina egna uppgifter i demonstrationsföretaget USMF. I båda fallen innan du startar den här uppgiften, skapa en försäljningsorder för inventerad produkt med samma mängd större än 1. För att undvika bokföringsfelt måste du kontrollera att produktens lagerbehållning på plats och lagerställe som du har valt på ordern omfattar orderkvantiteten.

## <a name="post-packing-slip-for-an-order"></a>Bokför följesedel för en order
1. I navigeringsfönstret, gå till **Moduler > Försäljning och marknadsföring > Försäljningsorder > Alla försäljningsorder**.
2. I listan söker du och väljer den order som du har skapat för uppgiften.
3. I åtgärdsfönstret, klicka **Plocka och packa.**
4. Välj **Bokför följesedel**.
5. Expandera eller komprimera avsnittet **Parametrar.**
6. I fältet **Kvantitet**, välj **Alla**.
    - Andra alternativ inkluderar **Leverera nu** och **Plockat**. Om orderraden ska levereras delvis och fältet **Leverera nu** på orderraden innehåller en kvantitet ska du välja **Leverera nu**. Om organisationens uppfyllelseflöde inkluderar plockning som en separat process som administreras av och registreras med en plocklista, ska du välja **Plockat**.  
    - Kontrollera att alternativet **Bokför** har värdet **Ja**.  
7. Ställ in alternativet **Skriv ut följesedel** på **Ja**. Fliken **Översikt** innehåller en lista med följesedlar som ska genereras i den här bokföringen. Om du skickar en enskild order, finns det vanligtvis en följesedel. Men om orderns rader ska levereras från olika platser, delas bokföringen automatiskt upp i flera dokument. Detta är ett obligatoriskt och det går inte att ändra. På liknande sätt kommer bokföringen också att delas upp i flera dokument om orderns rader ska skickas till olika leveransadresser, och leveransregeln är inställd på att kräva en delning.  
8. Markera raden för att orderraden ska skickas på fliken **Rader**.
9. Ange ett värde som är lägre än den ursprungliga kvantiteten i fältet **Uppdatera**.
10. Välj **OK**.
11. Välj **Ja**.
12. Stäng sidan.
13. Välj **Alternativ** i åtgärdsfönstret.
14. Välj **Byt visning**.
15. Välj **Huvudvy**.
    - Om alla rader på ordern har skickats ändras orderstatusen från Öppen till Levererat.  
    - I det här exemplet har orderraden skickats delvis. Därför är orderstatusen fortfarande Öppen.     
    - Fältet **Dokumentstatus** har värdet Följesedel eftersom minst en orderrad har skickats.  
16. Välj **Allmänt** i åtgärdsfönstret.
17. Välj **Radkvantitet**.
18. Stäng sidan.
19. I åtgärdsfönstret, klicka **Plocka och packa.**
20. Välj **Följesedel**. Sidan **Följesedelsjournal** innehåller alla följesedlar som har skapats för ordern. Du kan granska informationen i varje dokument och skriva ut dem om du vill.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]