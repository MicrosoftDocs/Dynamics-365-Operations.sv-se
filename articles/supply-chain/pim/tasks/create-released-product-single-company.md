--- 
title: "Skapa en frisläppt produkt för ett enskilt företag"
description: "I den här proceduren beskrivs hur du skapar en enskild frisläppt produkt i sammanhanget för en enskild juridisk enhet."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 042eafc29e377e0ad6fb8dc1499daf8eb105b7ed
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-released-product-for-a-single-company"></a>Skapa en frisläppt produkt för ett enskilt företag

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren beskrivs hur du skapar en enskild frisläppt produkt i sammanhanget för en enskild juridisk enhet. När en frisläppt den produkten har skapats, är den endast direkt tillgänglig i den här enheten. Du kan gå igenom den här proceduren i demonstrationsföretaget USMF. Denna uppgift utförs vanligtvis av en produktdesigner.


## <a name="create-a-released-product"></a>Skapa en frisläppt produkt
1. Gå till Frisläppta produkter.
2. Klicka på Ny.
3. Skriv ett värde i fältet Produktnummer.
    * Om ett produktnummer inte anges automatiskt i fältet Produktnummer skriver du ett unikt produktnummer. Det här steget krävs endast om ingen nummerserie har ställts in för produktnummer.  
4. Skriv ett värde i fältet Produktnamn.
    * Produktnamn anges som standard till söknamnet. Du kan välja att ändra söknamnet om det behövs.  
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmodellgrupp.
    * Artikelmodellgrupper innehåller inställningar som bestämmer hur artiklar kontrolleras och hanteras för artikelinleveranser och artikelutleveranser. Inställningarna bestämmer även hur förbrukningen av artiklar beräknas.  
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelgrupp.
    * Artikelgrupper används för att hantera lager genom att dela upp lagerartiklar i grupper efter artikelegenskaper. Om du till exempel vill hantera hur information bokförs på huvudkontona, kan du skapa en serie olika artikelgrupper som är associerade med specifika huvudkonton. På så sätt kan du följa lagervärdet för artiklar vid olika faser.  
9. Hitta och markera önskad post i listan.
10. Klicka på länken på den valda raden i listan.
11. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagringsdimensionsgrupp.
    * Lagringsdimensioner bestämmer hur artiklar lagras och tas från lagret. Till exempel kan en lagringsdimension vara webbplats och lagerställe.  
12. Hitta och markera önskad post i listan.
13. Klicka på länken på den valda raden i listan.
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Spårningsdimensionsgrupp.
    * Spårningsdimensionsgruppen avgör vilka spårningsdimensioner du kan lägga till för en produkt. Batchnummer och serienummer används till exempel för att spåra lagerartiklar.  
15. Hitta och markera önskad post i listan.
16. Klicka på länken på den valda raden i listan.
17. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerenhet.
    * Lagerenheten bestämmer hur produkten kvantifieras när den sparas i lagret.  
18. Hitta och markera önskad post i listan.
19. Klicka på länken på den valda raden i listan.
20. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Inköpsenhet.
    * Inköpsenheten bestämmer hur produkten kvantifieras när den har köpts från en leverantör.  
21. Hitta och markera önskad post i listan.
22. Klicka på länken på den valda raden i listan.
23. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Försäljningsenhet.
    * Försäljningsenheten bestämmer hur produkten kvantifieras när den säljs till en kund.  
24. Hitta och markera önskad post i listan.
25. Klicka på länken på den valda raden i listan.
26. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Strukturlisteenhet.
    * Strukturlisteenheten bestämmer hur produkten kvantifieras när du inkluderar den i en strukturlista (BOM).  
27. Hitta och markera önskad post i listan.
28. Klicka på länken på den valda raden i listan.
29. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.
    * Artikelmomsgruppen i momsbeskattningsgruppen bestämmer hur moms beräknas för varje artikel.  
30. Hitta och markera önskad post i listan.
31. Klicka på länken på den valda raden i listan.
32. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.
    * Artikelmomsgruppen i inköpsbeskattningsgruppen bestämmer hur ingående moms beräknas för varje artikel.  
33. Hitta och markera önskad post i listan.
34. Klicka på länken på den valda raden i listan.
35. Klicka på OK.

## <a name="add-product-characteristics"></a>Lägga till produktegenskaper
1. Visa eller dölj avsnittet Hantera lager.
2. Ange ett nummer i fältet Nettovikt.
3. Ange ett nummer i fältet Taravikt.
4. Välj ett nummer i fältet Bruttodjup.
5. Välj ett nummer i fältet Bruttobredd.
6. Välj ett nummer i fältet Bruttohöjd.
7. Välj ett nummer i fältet Volym.

## <a name="add-financial-dimensions"></a>Lägga till ekonomiska dimensioner
1. Expandera eller komprimera avsnittet Ekonomiska dimensioner.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet BusinessUnit.
3. Hitta och markera önskad post i listan.
4. Klicka på länken på den valda raden i listan.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet CostCenter.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Avdelning.
9. Hitta och markera önskad post i listan.
10. Klicka på länken på den valda raden i listan.
11. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet ItemGroup.
12. Hitta och markera önskad post i listan.
13. Klicka på länken på den valda raden i listan.


