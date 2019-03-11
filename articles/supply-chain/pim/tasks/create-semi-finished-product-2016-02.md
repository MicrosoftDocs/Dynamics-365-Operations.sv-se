---
title: Skapa en halvfärdig produkt (februari 2016)
description: Den här uppgiften fokuserar på att skapa en halvfärdig produkt.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9caeae552471eed1cb1d8630f387ca31107fcece
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "362865"
---
# <a name="create-a-semi-finished-product-february-2016"></a>Skapa en halvfärdig produkt (februari 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiften fokuserar på att skapa en halvfärdig produkt. Detta är den andra uppgiften i beräkningsserien för strukturlista. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.

1. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
2. Klicka på Ny.
3. Skriv ett värde i fältet Produktnummer.
    * Ange BOM_2 i det här exemplet.  
4. Ange eller välj ett värde i fältet Artikelmodellgrupp.
    * Välj STD. STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.  
5. Ange eller välj ett värde i fältet Artikelgrupp.
    * Välj till exempel "Ljud". Detta påverkar inte kostnadsberäkningarna.  
6. Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.
    * Välj SiteWH. Endast plats och lagerställe används för detta exempel.  
7. Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.
    * Spårningsdimensioner kommer inte att användas i det här exemplet; välj Ingen.  
8. Klicka på OK.
9. Klicka på Hantera inventering i åtgärdsfönstret.
10. Visa standardorderinställningar.
11. Välj "Produktion" i fältet för förvald ordertyp.
    * Eftersom detta är en halvfärdig produkt som ska tillverkas, välj Produktion.  
12. Ange eller välj ett värde i fältet Inköpsplats.
    * Välj Plats 1 i det här exemplet.  
13. Ange eller välj ett värde i fältet Lagerplats.
    * Välj Plats 1 i det här exemplet.  
14. Ange eller välj ett värde i fältet Försäljningsplats.
    * Välj Plats 1 i det här exemplet.  
15. Stäng sidan.
16. Klicka på Hantera kostnader i åtgärdsfönstret.
17. Klicka på Artikelpris.
18. Klicka på Ny.
19. Markera vald rad i listan.
20. Ange eller välj ett värde i fältet Version.
    * Välj Version 10 för det här exemplet.  
21. Ange eller välj ett värde i fältet Plats.
    * Välj Plats 1 i det här exemplet.  
22. Ange Pris som "10".
    * Ange ett självkostnadspris på 10 i det här exemplet.  
23. Klicka på Spara.
24. Klicka på Aktivera väntande pris(er).
25. Stäng sidan.
26. Stäng sidan.
27. Klicka på BOM_2 för att öppna.
28. Expandera avsnittet Hantera kostnader.
29. Ange eller välj ett värde i fältet Kostnadsgrupp.
    * Välj Kostnadsgrupp M1 i det här exemplet.  
30. Använd genvägen för att spara en post.
31. Stäng sidan.

