--- 
title: "Masskapa försäljningsofferter"
description: "I den här proceduren visas hur du skapar offerter med en uppsättning produkter eller tjänster som ska skickas till flera kunder."
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: bb32fbf14e7a96481dd78059e0299e33e754c0d7
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="mass-create-sales-quotations"></a>Masskapa försäljningsofferter

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar offerter med en uppsättning produkter eller tjänster som ska skickas till flera kunder. Den här genereringen av massofferter baseras på offertmallar. Du kan köra den här proceduren med dina egna uppgifter i demonstrationsföretaget USMF.


## <a name="create-a-quotation-template"></a>Skapa en offertmall
1. Gå till försäljning och marknadsföring > Installation > offerter > Template Groups.
2. Klicka på Ny.
3. Ange ett id i fältet Grupp-ID.
4. Ange ett värde i fältet Beskrivning.
5. Klicka på Spara.
6. Stäng sidan.
7. Gå till försäljning och marknadsföring > offerter > Alla offerter.
8. Klicka på Ny.
9. I fältet Kontotyp väljer du "Kund".
10. I fältet Kundkonto, ange eller välj ett värde.
11. Klicka på OK.
    * För att en offert ska kunna bli en mall, måste du utföra inställningssteg i offerthuvudet. Detta måste göras innan du lägger till rader i offerten.   
12. Klicka på Alternativ i åtgärdsfönstret.
13. Klicka på Ändra vy.
14. Klicka på Huvudvy.
15. Expandera avsnittet Inställningar.
16. Ange eller välj ett värde i fältet Grupp-ID.
17. I fältet Mallnamn, skriv ett värde.
18. Välj Ja i fältet Aktivt.
    * Endast aktiva mallar kan användas när du använder en mall till en ny försäljningsoffert.  
19. Klicka på Alternativ i åtgärdsfönstret.
20. Klicka på Ändra vy.
21. Klicka på Radvy.
22. Ange eller välj ett värde i fältet Artikel.
23. Ange ett värde i fältet Artikel.
24. Stäng sidan.
25. Ange ett värde i fältet Rabatt i procent.
26. Klicka på Lägg till rad.
27. Ange eller välj ett värde i fältet Artikel.
28. Ange ett värde i fältet Artikel.
29. Stäng sidan.
30. Ange ett nytt pris eller ändra det aktuella i fältet Enhetspris.
31. Klicka på Lägg till rad.
32. Ange eller välj ett värde i fältet Artikel.
33. Ange ett värde i fältet Artikel.
34. Stäng sidan.
35. Ange ett tal i fältet Kvantitet.
36. Ange ett värde i fältet Rabatt.
37. Klicka på Spara.

## <a name="apply-the-template-to-create-a-single-quotation"></a>Använd mallen för att skapa en offert
1. Gå till försäljning och marknadsföring > offerter > Alla offerter.
    * Observera att offerten som du nyss skapade markeras som mall.  
2. Klicka på Ny.
3. I fältet Kontotyp väljer du "Kund".
4. I fältet Kundkonto, ange eller välj ett värde.
5. Expandera alternativet Mall.
6. Ange eller välj ett värde i fältet Grupp-ID.
7. Ange eller välj ett värde i fältet Mallnamn.
8. Välj Baserat på mallvärden i fältet Beräkningsmetod.
9. Klicka på OK.
    * Den nya offerten har nu skapats, baserat på data och villkoren i mallen.  
10. Stäng sidan.
11. Stäng sidan.

## <a name="apply-the-template-to-mass-create-quotations"></a>Använd mallen för att skapa flera offerter
1. Gå till försäljning och marknadsföring > offerter > Offert update > massa skapa offerter.
2. I fältet Kontotyp väljer du "Kund".
3. Ange eller välj ett värde i fältet Grupp-ID.
4. Ange eller välj ett värde i fältet Mallnamn.
5. Välj Baserat på mallvärden i fältet Beräkningsmetod.
6. Expandera avsnittet Poster som ska ingå.
7. Klicka på Filter.
8. Gå till fältet Kriterier och ställ in ett filter som omfattar kunder du vill ta med i massofferten. Använd format Kund1..KundN.
    * Du kan till exempel ställa in filtret på US-001..US-004  
9. Klicka på OK.
10. Klicka på OK.
11. Gå till försäljning och marknadsföring > offerter > Alla offerter.
    * Kontrollera att offerter har skapats för alla angivna kunder i massuppdateringrutinen som baserat på den valda mallen.  

