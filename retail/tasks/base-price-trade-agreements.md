--- 
title: " Baspris och handelsavtal"
description: "Den här proceduren går igenom hur du skapar kanalspecifika handelsavtal för försäljningspriset."
author: josaw1
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 6fe49a5c871a175612223e0354e7880f17108044
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="base-price-and-trade-agreements"></a> Baspris och handelsavtal

[!include[task guide banner](../includes/task-guide-banner.md)]

Den här proceduren går igenom hur du skapar kanalspecifika handelsavtal för försäljningspriset. I proceduren används demonstrationsföretaget USRT.

1. Gå till butik och handel > prissättning och rabatter > prisgrupper > alla prisgrupper.
    * Prisgrupper hur handelsavtal tilldelas specifika kanaler. Användningen av prisgrupperna för att tilldela handelsavtal till en kanal aktiverar kanalspecifik prissättning.  
2. Klicka på Ny.
3. Ange ett värde i fältet Prisgrupper.
4. Skriv ett värde i fältet Namn.
5. Klicka på Spara.
6. Stäng sidan.
7. Gå till butik och handel > Kanaler > butiker > Alla butiker.
8. Välj New York i listan.
9. Klicka på Butik i åtgärdsfönstret.
10. Klicka på Prisgrupper.
11. Klicka på Ny.
12. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Prisgrupper.
13. Hitta och markera önskad post i listan.
14. Klicka på Spara.
15. Stäng sidan.
16. Stäng sidan.
17. Gå till butik och handel > Produkter och kategorier > Frisläppta produkter per kategori.
18. Klicka på länken på den valda raden i listan.
19. Klicka på Redigera.
20. Växla utökningen av avsnittet Sälj.
21. Ange ett tal i fältet Pris.
    * Detta pris används om inget tillämpligt handelsavtal hittas.  
22. Klicka på Spara.
23. Klicka på Sälj i åtgärdsfönstret.
24. Klicka på Skapa handelsavtal.
25. Klicka på Ny.
26. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
27. I listan väljer du Butik .
    * I demonstrationsdata har journalnamnet Butik standardrelationen Pris (Försäljning). Det innebär att alla skapade nya rader får standardinställningen handelsavtal för försäljningspriset.  
28. Klicka på Rader.
29. Välj Grupp i fältet Konto.
30. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kontomarkering.
31. Hitta och markera önskad post i listan.
    * Detta slutför länken från Kanal till Prisgrupp till Handelsavtal.  
32. Skriv ett värde i fältet Artikelrelation.
33. Ange ett nummer i fältet Belopp i valuta.
34. Markera eller avmarkera kryssrutan Sök nästa.
    * När Sök nästa sedan anges till Ja, prissättningsmotorn ska fortsätta att söka efter tillämpliga handelsavtal med ett lägre försäljningspris. När Sök nästa anges till Nej slutar prismotorn söka och använder handelsavtalet.  
35. Klicka på Bokför.
36. Klicka på OK.
37. Stäng sidan.
38. Klicka på Sälj i åtgärdsfönstret.
39. Klicka på Försäljningspris.


