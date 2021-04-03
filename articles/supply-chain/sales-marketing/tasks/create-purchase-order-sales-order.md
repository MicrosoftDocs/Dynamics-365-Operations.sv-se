---
title: Skapa en inköpsorder från en försäljningsorder
description: Proceduren visar hur du kan skapa en inköpsorder som baseras på en försäljningsorder.
author: omulvad
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2cb1829c6ed8b5ea6dbbf7fe465b270e264b78db
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5266041"
---
# <a name="create-a-purchase-order-from-a-sales-order"></a>Skapa en inköpsorder från en försäljningsorder

[!include [banner](../../includes/banner.md)]

Proceduren visar hur du kan skapa en inköpsorder som baseras på en försäljningsorder. Produktens kvantiteter på inköpsordern är angivna för att uppfylla kravet från den ursprungliga försäljningsordern. Att uppfylla säljkravet så här är ett alternativ till den mer omfattande och optimerade planeringsmetoden för fördelningsbehov. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.


## <a name="create-a-purchase-order-from-a-sales-order"></a>Skapa en inköpsorder från en försäljningsorder
1. Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Försäljningsorder > Alla försäljningsorder**.
2. Klicka på **Ny**.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kundkonto**.
4. Hitta och markera önskad post i listan.
5. Klicka på **OK**.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelnummer**.
7. Hitta och markera önskad post i listan. Om du använder USMF kan du välja D0001.  
8. Ange ett nummer i fältet **Kvantitet**.
9. Klicka på **Lägg till rad**.
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelnummer**.
11. Hitta och markera önskad post i listan. Om du använder USMF kan du välja T0020.  
12. Klicka på länken på den valda raden i listan.
13. Ange ett nummer i fältet **Kvantitet**.
14. Klicka på **Spara**.
15. I **åtgärdsrutan**, klicka på **Försäljningsorder**.
16. Klicka på **inköpsordern**. Sidan **Skapa inköpsorder** visar alla öppna försäljningsorderrader som har kopierats från försäljningsorder. Du kan granska orderinformation och om det behövs, även ändra valda detaljer som inköpkvantitet och prissättningsvillkor innan du skapar inköpen. 
17. Välj **Inkludera alla alternativ**.
    - Om du vill skapa inköpsorder för bara en delmängd av försäljningsorderraderna väljer du dessa separat.  
    - Fältet **Leverantörskonto** är eller är inte ifyllt med leverantörsnumret. Om standardleverantören har ställts in för produkten (i den associerade artikeltäckningen) kopieras leverantören till raden. Annars måste du ange en leverantör manuellt.  I den här handboken, oavsett om **säljarkonto** redan innehåller ett värde eller inte, instruerar följande steg dig att välja en ny leverantör som är olika för varje rad.  
18. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Leverantörskonto**.
19. Hitta och markera önskad post i listan.
20. Klicka på länken på den valda raden i listan.
21. Välj den andra orderraden.
22. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Leverantörskonto**.
23. Hitta och markera önskad post i listan.
24. Klicka på länken på den valda raden i listan.
25. Klicka på **Validera.**
26. Klicka på **OK**. Meddelandet informerar dig om att en eller flera inköpsorder har skapats. Systemet genererar en separat inköpsorder för varje leverantör som du angett för försäljning av orderrader. Det innebär att om flera försäljningsorderrader ska levereras av samma leverantör, skapas en inköpsorder med flera rader.  

## <a name="review-purchase-orders-created-from-sales-orders"></a>Granska inköpsorder som har skapats av försäljningsorder
1. I **åtgärdsrutan** klickar du på **Allmänt**.
2. Klicka på **relaterade order**. Sidan **Relaterade order** listar alla de order som har skapats från försäljningsorder. I det här exemplet finns det två inköpsorder som har skapats för två olika leverantörer. 
3. Klicka för att följa länk i fältet **Inköpsorder**. Varje inköpsorderrad har kopplats till försäljningsorderraden som ledde till köpet. Relationen till försäljningsorder anges på **Produktflik** på snabbfliken **Raddetaljer** i fälten **referenstyp**, **referensnummer** och **referensparti**.  
4. Expandera eller dölj avsnittet **Raddetaljer**.
5. Klicka på fliken **Produkter**.
    - **Referensparti** garanterar att kostnaden för det aktuella inköpet debiteras den kopplade försäljningsordern.  
    - Du kan navigera till den ursprungliga försäljningsordern genom att öppna länken i fältet **Referensnummer**.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]