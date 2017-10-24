--- 
title: "Skapa en inköpsorder från en försäljningsorder"
description: "Proceduren visar hur du kan skapa en inköpsorder som baseras på en försäljningsorder."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 412a8c7acca06fc1be073019f91144e2a3f1c94b
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-order-from-a-sales-order"></a>Skapa en inköpsorder från en försäljningsorder

[!include[task guide banner](../../includes/task-guide-banner.md)]

Proceduren visar hur du kan skapa en inköpsorder som baseras på en försäljningsorder. Produktens kvantiteter på inköpsordern är angivna för att uppfylla kravet från den ursprungliga försäljningsordern. Att uppfylla säljkravet så här är ett alternativ till den mer omfattande och optimerade planeringsmetoden för fördelningsbehov. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.


## <a name="create-a-purchase-order-from-a-sales-order"></a>Skapa en inköpsorder från en försäljningsorder
1. Gå till försäljning och marknadsföring > beställningar > Alla beställningar.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.
4. Hitta och markera önskad post i listan.
5. Klicka på OK.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
7. Hitta och markera önskad post i listan.
    * Om du använder USMF kan du välja D0001.  
8. Ange ett tal i fältet Kvantitet.
9. Klicka på Lägg till rad.
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
11. Hitta och markera önskad post i listan.
    * Om du använder USMF kan du välja T0020.  
12. Klicka på länken på den valda raden i listan.
13. Ange ett tal i fältet Kvantitet.
14. Klicka på Spara.
15. Klicka på Försäljningsorder i åtgärdsfönstret.
16. Klicka på Inköpsorder.
    * På sidan Skapa inköpsorder visas alla öppna försäljningsorderrader som har kopierats från försäljningsordern. Du kan granska orderinformation och om det behövs, även ändra valda detaljer som inköpkvantitet och prissättningsvillkor innan du skapar inköpen.  
17. Välj alternativet Inkludera allt.
    * Om du vill skapa inköpsorder för bara en delmängd av försäljningsorderraderna väljer du dessa separat.  
    * Fältet Leverantörskonto har eller har inte redan fyllts i med ett leverantörsnummer. Om standardleverantören har ställts in för produkten (i den associerade artikeltäckningen) kopieras leverantören till raden. Annars måste du ange en leverantör manuellt.  I den här handboken, oavsett om fältet Leverantörskonto redan innehåller ett värde, visar följande steg att du ska välja en ny leverantör som är olika för varje rad.  
18. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.
19. Hitta och markera önskad post i listan.
20. Klicka på länken på den valda raden i listan.
21. Välj den andra orderraden.
22. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.
23. Hitta och markera önskad post i listan.
24. Klicka på länken på den valda raden i listan.
25. Klicka på Validera.
26. Klicka på OK.
    * Meddelandet informerar dig om att en eller flera inköpsorder har skapats. Systemet genererar en separat inköpsorder för varje leverantör som du angett för försäljning av orderrader. Det innebär att om flera försäljningsorderrader ska levereras av samma leverantör, skapas en inköpsorder med flera rader.  

## <a name="review-purchase-orders-created-from-sales-orders"></a>Granska inköpsorder som har skapats av försäljningsorder
1. Klicka på Allmänt i åtgärdsfönstret.
2. Klicka på Relaterade order.
    * Sidan Relaterade order visar alla order som har skapats av försäljningsordern. I det här exemplet finns det två inköpsorder som har skapats för två olika leverantörer.  
3. Klicka för att följa länken i fältet Inköpsorder.
    * Varje inköpsorderrad har kopplats till försäljningsorderraden som ledde till köpet. Relationen på försäljningsordern visas på fliken Produkt på snabbfliken Radinformation i fälten Referenstyp, Referensnummer och Referensparti.  
4. Expandera eller dölj avsnittet Raddetaljer.
5. Klicka på fliken Produkt.
    * Referensparti garanterar att kostnaden för det aktuella inköpet debiteras den kopplade försäljningsordern.  
    * Du kan navigera till den ursprungliga försäljningsordern genom att öppna länken i fältet Referensnummer.  


