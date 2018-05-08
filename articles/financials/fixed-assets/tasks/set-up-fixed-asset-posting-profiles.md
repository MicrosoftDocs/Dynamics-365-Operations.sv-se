--- 
title: "Ställ in bokföringsprofiler för anläggningstillgångar"
description: "I den här uppgiftsguiden ställer vi in bokföringsprofiler för anläggningstillgångar."
author: saraschi2
manager: AnnBe
ms.date: 02/24/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b9766d96d16429d0ce0864695a3157f54cad4054
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-fixed-asset-posting-profiles"></a>Ställ in bokföringsprofiler för anläggningstillgångar

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här uppgiftsguiden ställer vi in bokföringsprofiler för anläggningstillgångar.  Här används revisorrollen och demonstrationdata för den juridiska personen USMF.  Exempel som angetts i uppgifthandboken, gäller en grundläggande bokföringsprofil, fast bokföringsprofiler måste skapas för dina specifika krav för kontoplanen och om den ekonomiska rapporteringen.

1. Gå till Anläggningstillgångar > Inställning > Bokföringsprofiler för anläggningstillgångar.
2. Klicka på Ny.
3. Skriv ett värde i fältet Bokföringsprofil.
4. Ange ett värde i fältet Beskrivning.
    * Du måste skapa en bokföringsprofil för varje en transaktionstyp som ska användas, när du arbetar med anläggningstillgångar.  Den här uppgifthandboken inleds med anskaffningstransaktionstypen.  
5. Klicka på Lägg till.
6. Ange eller välj ett värde i fältet Book.
    * I grupperingfältet kan du definiera bokföringsprofilen nedåt till registret (en kontoinställning för varje anläggningstillgång) eller Grupp (en kontoinställning för varje anläggningstillgångsgrupp).  För den här uppgiftsguiden lämnas värdet inställt på "Alla" för att gälla för alla anläggningstillgångar med den angivna boken.  
7. Ange önskade värden i fältet Huvudkonto.
    * För anskaffningar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.    
8. Välj Anskaffningsjustering i fältet Transaktionstyp.
    * För anskaffningsjusteringstransaktioner ska du använda samma konton som använda för anskaffningstransaktioner.  
9. Klicka på Lägg till.
10. Ange eller välj ett värde i fältet Book.
11. Ange önskade värden i fältet Huvudkonto.
    * För anskaffningsjusteringar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.    
12. Välj Avskrivning i fältet Transaktionstyp.
13. Klicka på Lägg till.
14. Ange eller välj ett värde i fältet Book.
15. Ange önskade värden i fältet Huvudkonto.
16. Ange önskade värden i fältet Motkonto.
17. Välj Avskrivningsjustering i fältet Transaktionstyp.
    * För avskrivningsjusteringstransaktioner ska du använda samma konton som använda för avskrivningstransaktioner.  
18. Klicka på Lägg till.
19. Ange eller välj ett värde i fältet Book.
20. Ange önskade värden i fältet Huvudkonto.
21. Ange önskade värden i fältet Motkonto.
22. Välj Avyttrande försäljning i fältet Transaktionstyp.
23. Klicka på Lägg till.
24. Ange eller välj ett värde i fältet Book.
25. Ange önskade värden i fältet Huvudkonto.
    * För avyttringar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.  
26. Välj Avyttrande kassation i fältet Transaktionstyp.
    * Vi använder samma konton för Avyttrande försäljning och Avyttrande kassation.  
27. Klicka på Lägg till.
28. Ange eller välj ett värde i fältet Book.
29. Ange önskade värden i fältet Huvudkonto.
    * För avyttringar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.  
30. Expandera valet Avyttra.
    * Du måste ställa in förfogandebokföringsprofiler för både försäljning och kassation.  Vi inleder med avyttringsförsäljningtransaktioner.  
31. Klicka på Lägg till.
32. Ange eller välj ett värde i fältet Book.
33. Välj ”Anskaffningsvärde " i fältet Bokför värde.
    * Anskaffningsvärdet används för anskaffnings- och anskaffningsjusteringsvärden för alla år.  Du kan också definiera konton för de transaktionstyperna separat.  
    * Du kan ange avyttringsprocessen om du vill använda andra konton, beroende på om avyttringen leder till en vinst eller en förlust.  Jag ska ange försäljningvärdetypen till ”Alla” för användning av samma konton för alla typer av avyttringar.  
34. Ange önskade värden i fältet Huvudkonto.
35. Ange önskade värden i fältet Motkonto.
36. Klicka på Lägg till.
37. Ange eller välj ett värde i fältet Book.
    * Välj ”Avskrivning (tidigare år)” i fältet Bokför värde.  
38. Ange önskade värden i fältet Huvudkonto.
39. Ange önskade värden i fältet Motkonto.
40. Klicka på Lägg till.
41. Ange eller välj ett värde i fältet Book.
42. Välj ”Avskrivning (detta år)” i fältet Bokför värde.
43. Ange önskade värden i fältet Huvudkonto.
44. Ange önskade värden i fältet Motkonto.
45. Klicka på Lägg till.
46. Ange eller välj ett värde i fältet Book.
47. Välj ”Avskrivningsjusteringar (tidigare år)” i fältet Bokför värde.
48. Ange önskade värden i fältet Huvudkonto.
49. Ange önskade värden i fältet Motkonto.
50. Klicka på Lägg till.
51. Ange eller välj ett värde i fältet Book.
52. Välj ”Avskrivningsjusteringar (detta år)” i fältet Bokför värde.
53. Ange önskade värden i fältet Huvudkonto.
54. Ange önskade värden i fältet Motkonto.
55. Klicka på Lägg till.
56. Ange eller välj ett värde i fältet Book.
57. Välj ”Bokfört nettovärde " i fältet Bokför värde.
58. Ange önskade värden i fältet Huvudkonto.
59. Ange önskade värden i fältet Motkonto.
60. Välj ”Kassation” i fältet Försäljning eller kassation.
61. Klicka på Lägg till.
62. Ange eller välj ett värde i fältet Book.
63. Välj ”Anskaffningsvärde " i fältet Bokför värde.
64. Ange önskade värden i fältet Huvudkonto.
65. Ange önskade värden i fältet Motkonto.
66. Klicka på Lägg till.
67. Ange eller välj ett värde i fältet Book.
    * Välj ”Avskrivning (tidigare år)” i fältet Bokför värde.  
68. Ange önskade värden i fältet Huvudkonto.
69. Ange önskade värden i fältet Motkonto.
70. Klicka på Lägg till.
71. Ange eller välj ett värde i fältet Book.
72. Välj ”Avskrivning (detta år)” i fältet Bokför värde.
73. Ange önskade värden i fältet Huvudkonto.
74. Ange önskade värden i fältet Motkonto.
75. Klicka på Lägg till.
76. Ange eller välj ett värde i fältet Book.
77. Välj ”Avskrivningsjusteringar (tidigare år)” i fältet Bokför värde.
78. Ange önskade värden i fältet Huvudkonto.
79. Ange önskade värden i fältet Motkonto.
80. Klicka på Lägg till.
81. Ange eller välj ett värde i fältet Book.
82. Välj ”Avskrivningsjusteringar (detta år)” i fältet Bokför värde.
83. Ange önskade värden i fältet Huvudkonto.
84. Ange önskade värden i fältet Motkonto.
85. Klicka på Lägg till.
86. Ange eller välj ett värde i fältet Book.
87. Välj ”Bokfört nettovärde " i fältet Bokför värde.
88. Ange önskade värden i fältet Huvudkonto.
89. Ange önskade värden i fältet Motkonto.


