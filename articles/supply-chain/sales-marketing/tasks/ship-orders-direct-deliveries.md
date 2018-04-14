--- 
title: Leverera order som direktleveranser
description: "Den här proceduren visar hur du kan skapa en direktleverans för en försäljningsorder."
author: omulvad
manager: AnnBe
ms.date: 02/12/2016
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
ms.openlocfilehash: f674de4877dd2d6e6f1ff02f16a68cb4805d9864
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="ship-orders-as-direct-deliveries"></a>Leverera order som direktleveranser

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du kan skapa en direktleverans för en försäljningsorder. Du använder direktleverans när du vill leverera varor direkt till kunden från leverantören, i stället för att skicka dem till ditt lagerställe först. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Om du vill slutföra den andra deluppgiften ”Skapa direktleveranser från arbetsbänken” ska du se till att artikeln du väljer på försäljningsordern har en standardleverantör angiven på inköpsnabbfliken för den frisläppta produktmallen.


## <a name="set-an-individual-order-for-direct-delivery"></a>Ange en enskild order för direktleverans
1. Gå till Alla försäljningsorder.
2. Klicka på Ny.
3. I fältet Kundkonto, ange eller välj ett värde.
    * Om du använder USMF kan du välja kontot US-001.  
4. Klicka på OK.
5. Ange eller välj ett värde i fältet Artikelnummer.
    * Om du använder USMF kan du välja artikeln T0020.  
6. Klicka på Spara.
7. Klicka på Försäljningsorder i åtgärdsfönstret.
8. Klicka på Direktleverans.
    * På sidan för leveransgenerering visas alla öppna försäljningsorderrader som kopierade från försäljningsordern. Du kan granska orderinformation och om det behövs, även ändra detaljer som inköpkvantitet och prissättningsvillkor innan du skapar direktleveransen.  
9. Välj Ja i fältet Inkludera allt.
    * Om du vill skapa en direktleverans för bara en delmängd av försäljningsorderraderna väljer du dessa separat.  
    * Fältet Leverantörskonto har eller har inte redan fyllts i med ett leverantörsnummer. Om säljaren är inställd för produkten (på den associerade artikeltäckning) då säljaren kommer att kopieras till kundorderraden. Annars måste du ange en leverantör manuellt. I det här exemplet kommer vi att välja en ny leverantör i nästa steg, även om det redan ifylld.   
10. Ange eller välj ett värde i fältet Leverantörskonto.
    * Om du använder USMF kan du välja kontot 1001.  
11. Klicka på OK.
    * Meddelandet informerar dig om att inköpsordern har skapats.   
12. Expandera avsnittet Radinformation.
13. Klicka på fliken Leverans.
    * Direktleveransfältet är inställt på Ja.  
    * Status för direktleverans visar den skapade inköpsordern.   
14. Klicka på Allmänt i åtgärdsfönstret.
15. Klicka på Relaterade order.
16. Klicka för att följa länken i fältet Inköpsorder.
17. Expandera avsnittet Radinformation.
18. Klicka på fliken Adress.
    * Observera att leveransadressen för den här inköpsorderraden är kundens leveransadress och inte företagsadressen.  
    * Om du ändrar leveransadressen på antingen inköpsorderraden eller den ursprungliga försäljningsorderraden, kommer adressen på motsvarande orderrad att uppdateras automatiskt.  
19. Klicka på fliken Leverans.
    * Precis som försäljningsorderraden, har den associerade radtypen för inköpsordern ställts in på direktleverans.  
    * Inköpsorderradens leveransdatum och datumet för bekräftad leverans har ställts in på begärt inleveransdatum respektive bekräftat inleveransdatum för den ursprungliga försäljningsorderraden.   
    * Om du uppdaterar någon av dessa datum på antingen inköpsraden eller försäljningsraden, kommer data på motsvarande order att uppdateras automatiskt.     
    * Inköpsordern som har ställts in på att leverera varor direkt till kunden, är kopplad till den ursprungliga försäljningsordern med hjälp av en speciell associering. Denna association medför regeln att följesedeln uppdatering av försäljningsorder kan inte göras från försäljningen för sig själv och måste göras med hjälp av inköpsordern. Kundfakturering måste dock göras från försäljningsordern.  
20. Klicka på Inköp i åtgärdsfönstret.
21. Klicka på Bekräftelse.
22. Klicka på OK.
23. Klicka på Ta emot i åtgärdsfönstret.
24. Klicka på Produktinleverans.
25. Skriv ett värde i fältet Produktinleverans.
26. Klicka på OK.
27. Klicka på Allmänt i åtgärdsfönstret.
28. Klicka på Relaterade order.
29. Markera vald rad i listan.
    * När inköpsordern har uppdaterats som inkommen, med andra ord efter att leverantören har skickat varor till kundens adress, uppdateras status för den ursprungliga försäljningsordern automatiskt till Levererat.  
    * Försäljningsordern går nu att fakturera.    
30. Klicka på OK.
31. Stäng sidan.
32. Klicka på OK.

## <a name="create-direct-deliveries-from-the-workbench"></a>Skapa direktleveranser från arbetsytan.
1. Stäng sidan.
2. Stäng sidan.
3. Gå till Alla försäljningsorder.
4. Klicka på Ny.
5. I fältet Kundkonto, ange eller välj ett värde.
6. Klicka på OK.
7. Ange eller välj ett värde i fältet Artikelnummer.
8. Expandera avsnittet Radinformation.
9. Klicka på fliken Leverans.
    * Istället för att skapa en direktleverans som en del av bearbetningen av försäljningsordern som i föregående procedur, kan du överlämna uppgiften till en inköpare. Om du vill inkludera försäljningsorderraden i hanteringsprocessen för direktleveransen måste du markera raden för direktleverans.  
10. Välj Ja i fältet Direktleverans.
    *   Om artikeln redan har ställts in för direktleverans som standard, kommer fältet automatiskt att ställas in på Ja i orderradposten. Du kan ställa in en artikel för direktleverans i en frisläppts produkts mall genom att ställa in alternativet Direktleverans på Ja och markera ett standardlagerställe för direktleveransen.  
    * Eftersom inköpsordern ännu inte har skapats, ställs statusen för direktleveransen in på För direktleverans.   
11. Stäng sidan.
12. Stäng sidan.
13. Gå till Direktleverans.
    * Direktleveranssidan fungerar som en arbetsyta som ger inköparen en översikt över alla försäljningsorderrader som ska direktlevereras, och det gör att det går att skapa respektive inköpsorder. Dessutom kan de visa öppna direktleveransorder och bekräftade order på flikarna Bekräftelse och Leverans.   
14. Klicka på Skapa direktleverans.
15. Klicka på fliken Bekräftelse.
    * När du har skapat en direktleverans skapas flyttas denna automatiskt till fliken Bekräftelse. Du kan välja att bekräfta ordern direkt från den här sidan. När inköpet har bekräftats flyttas det automatiskt till fliken Leverans där du kan registrera inleveransen.  


