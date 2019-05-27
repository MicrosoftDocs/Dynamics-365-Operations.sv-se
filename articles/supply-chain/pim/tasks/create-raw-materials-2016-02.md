---
title: Skapa råmaterial (februari 2016)
description: Den här uppgiften fokuserar på att skapa komponenterna för färdiga och halvfärdiga produkter.
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
ms.openlocfilehash: 091b6edaf43e86e6e3665bf79871648473e284c7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552680"
---
# <a name="create-raw-materials-february-2016"></a>Skapa råmaterial (februari 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiften fokuserar på att skapa komponenterna för färdiga och halvfärdiga produkter. Detta är den tredje uppgiften i beräkningsserien för strukturlista. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.


## <a name="create-the-first-material"></a>Skapa det första materialet
1. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
2. Klicka på Ny.
3. Skriv ett värde i fältet Produktnummer.
    * Ange ITEM_A i det här exemplet.  
4. Ange eller välj ett värde i fältet Artikelmodellgrupp.
    * Välj STD. STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.  
5. Ange eller välj ett värde i fältet Artikelgrupp.
    * Välj till exempel "Ljud". Detta påverkar inte kostnadsberäkningarna.  
6. Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.
    * Välj SiteWH. Endast plats och lagerställe används för demonstrationen.  
7. Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.
    * Spårningsdimensioner kommer inte att användas i det här exemplet. Välj Ingen.  
8. Klicka på OK.
9. Klicka på Hantera inventering i åtgärdsfönstret.
10. Visa standardorderinställningar.
11. Ange eller välj ett värde i fältet Inköpsplats.
    * Välj Plats 1 i det här exemplet.  
12. Ange eller välj ett värde i fältet Lagerplats.
    * Välj Plats 1 i det här exemplet.  
13. Ange eller välj ett värde i fältet Försäljningsplats.
    * Välj Plats 1 i det här exemplet.  
14. Stäng sidan.
15. Stäng sidan.
16. Klicka på länken på den valda raden i listan.
    * Klicka på ITEM_A.  
17. Expandera avsnittet Hantera kostnader.
18. Ange ett värde i fältet för kostnadsgrupp.
    * Ange M2 i det här exemplet.  
19. Klicka på Hantera kostnader i åtgärdsfönstret.
20. Klicka på Artikelpris.
21. Klicka på Ny.
22. Ange eller välj ett värde i fältet Version.
    * I det här exemplet väljer du 10, som är kostnadsredovisningstypen för standardkostnad.  
23. Ange eller välj ett värde i fältet Plats.
    * Välj Plats 1 i det här exemplet.  
24. Ange ett tal i fältet Pris.
    * Ange 10 i det här exemplet.  
25. Klicka på Spara.
26. Klicka på Aktivera väntande pris(er).
27. Stäng sidan.
28. Stäng sidan.

## <a name="create-the-second-material"></a>Skapa det andra materialet
1. Klicka på Ny.
2. Skriv ett värde i fältet Produktnummer.
    * Välj ITEM_B i det här exemplet.  
3. Ange eller välj ett värde i fältet Artikelmodellgrupp.
    * Välj STD. STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.  
4. Ange eller välj ett värde i fältet Artikelgrupp.
    * Välj till exempel "Ljud". Detta påverkar inte kostnadsberäkningarna.  
5. Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.
    * Välj SiteWH. Endast plats och lagerställe används för detta exempel.  
6. Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.
    * Spårningsdimensioner kommer inte att användas i det här exemplet. Välj Ingen.  
7. Klicka på OK.
8. Klicka på Hantera inventering i åtgärdsfönstret.
9. Visa standardorderinställningar.
10. Ange eller välj ett värde i fältet Inköpsplats.
    * Välj Plats 1 i det här exemplet.  
11. Ange eller välj ett värde i fältet Lagerplats.
    * Välj Plats 1 i det här exemplet.  
12. Ange eller välj ett värde i fältet Försäljningsplats.
    * Välj Plats 1 i det här exemplet.  
13. Stäng sidan.
14. Stäng sidan.
15. Klicka på länken på den valda raden i listan.
    * Klicka på ITEM_B.  
16. Expandera avsnittet Hantera kostnader.
17. Ange ett värde i fältet för kostnadsgrupp.
    * Ange M2 i det här exemplet.  
18. Klicka på Hantera kostnader i åtgärdsfönstret.
19. Klicka på Artikelpris.
20. Klicka på Ny.
21. Ange eller välj ett värde i fältet Version.
    * Välj 10 i det här exemplet. Detta är kostnadsredovisningstypen för standardkostnad.  
22. Ange eller välj ett värde i fältet Plats.
    * Välj Plats 1 i det här exemplet.  
23. Ange ett tal i fältet Pris.
    * Ange 10 för demonstrationen.  
24. Klicka på Spara.
25. Klicka på Aktivera väntande pris(er).
26. Stäng sidan.
27. Stäng sidan.

## <a name="create-the-third-material"></a>Skapa det tredje materialet
1. Klicka på Ny.
2. Skriv ett värde i fältet Produktnummer.
    * Ange ITEM_C för demonstrationen.  
3. Ange eller välj ett värde i fältet Artikelmodellgrupp.
    * Välj STD. STD innebär "standardkostnad" och är den vanligaste modellen när du arbetar med kostnadsberäkningar.  
4. Ange eller välj ett värde i fältet Artikelgrupp.
    * Välj till exempel "Ljud". Detta påverkar inte kostnadsberäkningarna.  
5. Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.
    * Välj SiteWH. Endast plats och lagerställe används för demonstrationen.  
6. Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.
    * Spårningsdimensioner kommer inte att användas i det här exemplet. Välj Ingen.  
7. Klicka på OK.
8. Klicka på Hantera inventering i åtgärdsfönstret.
9. Visa standardorderinställningar.
10. Ange eller välj ett värde i fältet Inköpsplats.
    * Välj Plats 1 i det här exemplet.  
11. Ange eller välj ett värde i fältet Lagerplats.
    * Välj Plats 1 i det här exemplet.  
12. Ange eller välj ett värde i fältet Försäljningsplats.
    * Välj Plats 1 i det här exemplet.  
13. Stäng sidan.
14. Stäng sidan.
15. Klicka på länken på den valda raden i listan.
    * Klicka på ITEM_C.  
16. Expandera avsnittet Hantera kostnader.
17. Ange ett värde i fältet för kostnadsgrupp.
    * Ange M1 i det här exemplet.  
18. Klicka på Hantera kostnader i åtgärdsfönstret.
19. Klicka på Artikelpris.
20. Klicka på Ny.
21. Ange eller välj ett värde i fältet Version.
    * Välj 10 i det här exemplet. Detta är kostnadsredovisningstypen för standardkostnad.  
22. Ange eller välj ett värde i fältet Plats.
    * Välj Plats 1 i det här exemplet.  
23. Ange ett tal i fältet Pris.
    * Ange 10 i det här exemplet.  
24. Klicka på Spara.
25. Klicka på Aktivera väntande pris(er).
26. Stäng sidan.
27. Stäng sidan.

