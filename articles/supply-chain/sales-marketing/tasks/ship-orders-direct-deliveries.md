---
title: Leverera order som direktleveranser
description: Det här avsnittet visar hur du kan skapa en direktleverans för en försäljningsorder.
author: omulvad
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, PurchCreateFromSalesOrder, VendAccountItemLookup, SalesTableReferences, PurchTable, PurchEditLines, PurchTableReferences, MCRDropShipWorkbench
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 81ebd845d9900d891b17618b3719d45060a1968f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148439"
---
# <a name="ship-orders-as-direct-deliveries"></a>Leverera order som direktleveranser

[!include [banner](../../includes/banner.md)]

Det här avsnittet visar hur du kan skapa en direktleverans för en försäljningsorder. Du använder direktleverans när du vill leverera varor direkt till kunden från leverantören, i stället för att skicka dem till ditt lagerställe först. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Om du vill slutföra den andra deluppgiften ”Skapa direktleveranser från arbetsbänken” ska du se till att artikeln du väljer på försäljningsordern har en standardleverantör angiven på inköpsnabbfliken för den frisläppta produktmallen.

## <a name="set-an-individual-order-for-direct-delivery"></a>Ange en enskild order för direktleverans
1. Gå till **Navigeringsfönstret > Moduler > Kundreskontra > Order > Alla försäljningsorder**.
2. Välj **Ny**.
3. Ange eller välj ett värde i fältet **Kundkonto** och välj sedan **OK**
4. Ange eller välj värden i fälten **artikelnummer** och **plats** och välj sedan **spara**.
5. I åtgärdsfönstret, välj **Försäljningsorder**, välj sedan **Direktleverans**. På sidan för leveransgenerering visas alla öppna försäljningsorderrader som kopierade från försäljningsordern. Du kan granska orderinformation och om det behövs, även ändra detaljer som inköpkvantitet och prissättningsvillkor innan du skapar direktleveransen.  
6. Välj **Ja** i fältet **inkludera alla**.
    - Om du vill skapa en direktleverans för bara en delmängd av försäljningsorderraderna väljer du dessa separat.  
    - Fältet **Leverantörskonto** är eller är inte ifyllt med leverantörsnumret. Om säljaren är inställd för produkten (på den associerade artikeltäckning) då säljaren kommer att kopieras till kundorderraden. Annars måste du ange en leverantör manuellt. I det här exemplet kommer vi att välja en ny leverantör i nästa steg, även om det redan ifylld.   
7. Ange eller välj ett värde i fältet **Leverantörskonto** och välj sedan **OK** Meddelandet informerar dig om att inköpsordern har skapats.   
8. Visa avsnittet **Raddetaljer**.
9. Välj fliken **leverans** och kontrollera att fältet **direktleverans** är inställt på **ja**.
10. Välj **Allmänt** i åtgärdsfönstret.
11. Välj **Relaterade order**.
12. Klicka på länken i fältet **Inköpsorder**.
13. Visa avsnittet **Radinformation** och välj fliken **adress**.
    - Leveransadressen för den här inköpsorderraden är kundens leveransadress och inte företagsadressen.  
    - Om du ändrar leveransadressen på antingen inköpsorderraden eller den ursprungliga försäljningsorderraden, kommer adressen på motsvarande orderrad att uppdateras automatiskt.  
14. Välj fliken **Leverans**.
    - Precis som försäljningsorderraden, har den associerade radtypen för inköpsordern ställts in på direktleverans.  
    - Inköpsorderradens leveransdatum och bekräftat leveransdatum är satt till begärt inleveransdatum och bekräftat inleveransdatum för respektive ursprunglig försäljningsorderrad.   
    - Om du uppdaterar någon av dessa datum på antingen inköpsraden eller försäljningsraden, kommer data på motsvarande order att uppdateras automatiskt.     
    - Inköpsordern som har ställts in på att leverera varor direkt till kunden, är kopplad till den ursprungliga försäljningsordern med hjälp av en speciell associering. Denna association medför regeln att följesedeln uppdatering av försäljningsorder kan inte göras från försäljningen för sig själv och måste göras med hjälp av inköpsordern. Kundfakturering måste dock göras från försäljningsordern.  
15. I åtgärdsfönstret, välj **Inköp**.
16. VäljSelect **Bekräftelse**.
17. Välj **OK**.
18. Välj **Ta emot** i åtgärdsfönstret.
19. Välj **produktinleverans**
20. I fältet **Produktinleverans**, skriv ett värde.
21. Välj **OK**.
22. Välj **Allmänt** i åtgärdsfönstret.
23. Välj **relaterade order** och markera önskad post.
    - När inköpsordern har uppdaterats som inkommen, med andra ord efter att leverantören har skickat varor till kundens adress, uppdateras status för den ursprungliga försäljningsordern automatiskt till Levererat.  
    - Försäljningsordern går nu att fakturera.    
24. Välj **OK**.
25. Stäng sidan.
26. Välj **OK**. Stäng sidorna och gå tillbaka till startsidan.

## <a name="create-direct-deliveries-from-the-workbench"></a>Skapa direktleveranser från arbetsytan.
1. Gå till **Navigering > Moduler > Kundreskontra > Order > Alla försäljningsorder**.
2. Välj **Ny**.
3. Ange eller välj ett värde i fältet **Kundkonto** och välj sedan **OK**
4. Ange eller välj ett värde i fälten **Artikelnummer** och **site**.
5. Visa avsnittet **Raddetaljer** och välj sedan fliken **Leverans**. Istället för att skapa en direktleverans som en del av bearbetningen av försäljningsordern som i föregående procedur, kan du överlämna uppgiften till en inköpare. Om du vill inkludera försäljningsorderraden i hanteringsprocessen för direktleveransen måste du markera raden för direktleverans.  
6. Välj **Ja** i fältet **Direkt leverans**.
    - Om artikeln redan har ställts in för direktleverans som standard, kommer fältet automatiskt att ställas in på Ja i orderradposten. Du kan ställa in en artikel för direktleverans i en frisläppts produkts mall genom att ställa in alternativet Direktleverans på Ja och markera ett standardlagerställe för direktleveransen.  
    - Eftersom inköpsordern ännu inte har skapats, ställs statusen för direktleveransen in på För direktleverans.   
7. Välj **Spara**.
8. Stäng sidorna tills du går tillbaka till startsidan.
9. Ange `Direct delivery` i sökfältet.
    - Direktleveranssidan fungerar som en arbetsyta som ger inköparen en översikt över alla försäljningsorderrader som ska direktlevereras, och det gör att det går att skapa respektive inköpsorder. Dessutom kan de visa öppna direktleveransorder och bekräftade order på flikarna Bekräftelse och Leverans.  
    - När du har skapat en direktleverans skapas flyttas denna automatiskt till fliken Bekräftelse. Du kan välja att bekräfta ordern direkt från den här sidan. När inköpet har bekräftats flyttas det automatiskt till fliken Leverans där du kan registrera inleveransen.  

