--- 
title: "Skapa flöden (enbart februari 2016)"
description: "Den här uppgiften fokuserar på att skapa produktionsrutter för en färdig produkt och en halvfärdig produkt."
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a1c4b7623f3409d4474adcd04fb1331b944b9fbb
ms.openlocfilehash: a1da6a38e9e70efdbbd04e85318f208c82ab39ed
ms.contentlocale: sv-se
ms.lasthandoff: 02/13/2018

---
# <a name="create-routes-february-2016-only"></a>Skapa flöden (enbart februari 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiften fokuserar på att skapa produktionsrutter för en färdig produkt och en halvfärdig produkt. Detta är den femte uppgiften i beräkningsserien för strukturlista. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.


## <a name="create-a-route-for-a-semi-finished-product"></a>Skapa en rutt för en halvfärdig produkt
1. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
2. Klicka på länken på den valda raden i listan.
    * Välj artikelnummer BOM_2.  
3. Klicka på Konstruera i åtgärdsfönstret.
4. Klicka på Flöde.
5. Klicka på Ny.
6. Klicka på Rutt och ruttversion.
7. Ange ett värde i fältet Beskrivning.
    * Ange till exempel ROUTE_2.  
8. Ange eller välj ett värde i fältet Plats.
    * Ange eller välj Plats 1 i det här exemplet.  
9. Klicka på OK.
10. Klicka på Ny.
11. Ange eller välj ett värde i fältet Operation.
    * Välj Montage i det här exemplet.  
12. Ange ett värde i fältet Körtid.
    * Ange till exempel 1. Körtider ingår ofta i det pris som beräknas för en artikel.  
13. Ange eller välj ett värde i fältet Flödesgrupp.
    * Välj Std i det här exemplet.  
14. Klicka på fliken Inställningar.
15. I fältet Inställningskategori, ange eller välj ett värde.
    * Välj Montage i det här exemplet.  
16. Klicka på fliken Tider.
17. Ange ett värde i fältet Ställtid.
    * Ange 1 i det här exemplet. Ställtider ingår ofta i det pris som beräknas för en artikel.  
18. Klicka på Ruttversion i åtgärdsfönstret.
19. Klicka på Godkänn.
20. Välj Ja under Vill du även godkänna rutten? .
21. Klicka på OK.
22. Klicka på Ruttversion i åtgärdsfönstret.
23. Klicka på Aktivera.
24. Stäng sidan.
25. Stäng sidan.

## <a name="create-a-route-for-a-finished-product"></a>Skapa en rutt för en färdig produkt
1. Klicka på länken på den valda raden i listan.
    * Markera artikelnummer BOM_1.  
2. Klicka på Konstruera i åtgärdsfönstret.
3. Klicka på Flöde.
4. Klicka på Ny.
5. Klicka på Rutt och ruttversion.
6. Ange ett värde i fältet Beskrivning.
    * Ange ROUTE_1 i detta exempel.  
7. Ange eller välj ett värde i fältet Plats.
    * Ange eller välj Plats 1 i det här exemplet.  
8. Klicka på OK.
9. Klicka på Ny.
10. Ange eller välj ett värde i fältet Operation.
    * Välj Förpackning i det här exemplet.  
11. Ange ett värde i fältet Körtid.
    * Ange 1 i det här exemplet.  
12. Ange eller välj ett värde i fältet Flödesgrupp.
    * Välj Std i det här exemplet.  
13. Klicka på fliken Inställningar.
14. I fältet Inställningskategori, ange eller välj ett värde.
    * Välj Förpackning i det här exemplet.  
15. Klicka på fliken Tider.
16. Ange ett värde i fältet Ställtid.
    * Ange 1 i det här exemplet.  
17. Klicka på Ruttversion i åtgärdsfönstret.
18. Klicka på Godkänn.
19. Klicka på OK.
20. Klicka på Ruttversion i åtgärdsfönstret.
21. Klicka på Aktivera.
22. Stäng sidan.
23. Stäng sidan.

## <a name="enable-automatic-consumption-of-setup-time"></a>Aktivera automatisk förbrukning av ställtid
1. Gå till Produktionskontroll > Inställningar > Rutter > Ruttgrupper.
2. Hitta och markera önskad post i listan.
    * Ange Std i listan .  
3. Klicka på Redigera.
4. Välj Ja i fältet Ställtid.
    * Ställtider ingår ofta i det pris som beräknas för en artikel.  
5. Klicka på Spara.
6. Stäng sidan.


