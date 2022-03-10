---
title: " Baspris och handelsavtal"
description: Den här proceduren går igenom hur du skapar kanalspecifika handelsavtal för försäljningspriset.
author: josaw1
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 282cbe0cb115d6204137613f4754068b8a9a321400d24808eb67266a83d7bcc6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730741"
---
# <a name="base-price-and-trade-agreements"></a> Baspris och handelsavtal

[!include [banner](../includes/banner.md)]

Den här proceduren går igenom hur du skapar kanalspecifika handelsavtal för försäljningspriset. I proceduren används demonstrationsföretaget USRT.

1. I **Navigeringsfönstret** går du till **Moduler > Butik och handel > Hantering av priser och rabatter > Prisgrupper > Alla prisgrupper**. Prisgrupper hur handelsavtal tilldelas specifika kanaler. Användningen av prisgrupperna för att tilldela handelsavtal till en kanal aktiverar kanalspecifik prissättning.  
2. Klicka på **Ny**.
3. Ange ett värde i fältet **Prisgrupper**.
4. Skriv ett värde i fältet **Namn**.
5. Klicka på **Spara**.
6. Stäng sidan.
7. I **Navigeringsfönstret**, gå till **Moduler > Butik och handel > Kanaler > Butiker > Alla butiker**.
8. Välj New York i listan.
9. Klicka på **Butik** i åtgärdsfönstret.
10. Klicka på **Prisgrupper**.
11. Klicka på **Ny**.
12. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Prisgrupper**.
13. Hitta och markera önskad post i listan.
14. Klicka på **Spara**.
15. Stäng sidan.
16. Stäng sidan.
17. I **Navigeringsfönstret**, gå till **Moduler > Butik och handel > Produkter och kategorier > Frisläppta produkter per kategori**.
18. Klicka på länken på den valda raden i listan.
19. Klicka på **Redigera**.
20. Expandera snabbfliken **Sälj**.
21. Ange ett tal i fältet **Pris**. Detta pris används om inget tillämpligt handelsavtal hittas.  
22. Klicka på **Spara**.
23. Klicka på **Sälj** i **åtgärdsfönstret**.
24. Klicka på **Skapa handelsavtal**.
25. Klicka på **Ny**.
26. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Namn**.
27. I listan välj raden **Commerce**. I demonstrationsdata har journalnamnet **Commerce** standardrelationen **Pris (Försäljning)**. Det innebär att alla skapade nya rader får standardinställningen handelsavtal för försäljningspriset.  
28. Klicka på **Rader** i **åtgärdsfönstret**.
29. I fältet **Partkodtyp** välj Grupp.
30. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Kontomarkering**.
31. Hitta och markera önskad post i listan. Detta slutför länken från Kanal till Prisgrupp till Commercesavtal.  
32. Skriv ett värde i fältet **Artikelrelation**.
33. Ange ett nummer i fältet **Belopp i valuta**.
34. På snabbfliken **Detaljer**, markera eller avmarkera kryssrutan **Sök nästa**. När **Sök nästa** sedan anges till Ja, prissättningsmotorn ska fortsätta att söka efter tillämpliga handelsavtal med ett lägre försäljningspris. När **Sök nästa** anges till Nej slutar prismotorn söka och använder handelsavtalet.  
35. Klicka på **Bokför**.
36. Klicka på **OK**.
37. Stäng sidan.
38. Klicka på Sälj i **åtgärdsfönstret**.
39. Klicka på **Försäljningspris**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]