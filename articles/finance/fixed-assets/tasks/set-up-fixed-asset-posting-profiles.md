---
title: Ställ in bokföringsprofiler för anläggningstillgångar
description: I den här proceduren visas hur du ställer in bokföringsprofiler för anläggningstillgångar.
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2964be0b02d6a5553bad9a1b3788a5f1efb208ee
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725273"
---
# <a name="set-up-fixed-asset-posting-profiles"></a>Ställ in bokföringsprofiler för anläggningstillgångar

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du ställer in bokföringsprofiler för anläggningstillgångar. Exempel som angetts i ämnen, gäller en grundläggande bokföringsprofil, fast bokföringsprofiler måste skapas för dina specifika krav för kontoplanen och om den ekonomiska rapporteringen.

1. I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Inställningar > Bokföringsprofiler för anläggningstillgångar**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Bokföringsprofil**.
4. I fältet **Beskrivning** anger du ett värde. Du måste skapa en bokföringsprofil för varje en transaktionstyp som ska användas, när du arbetar med anläggningstillgångar. Den här uppgifthandboken inleds med anskaffningstransaktionstypen.  
5. Klicka på **Lägg till** i verktygsfältet.
6. Ange eller välj ett värde i fältet **Bok**. I fältet **gruppering** kan du definiera bokföringsprofilen nedåt till registret (en kontoinställning för varje anläggningstillgång) eller Grupp (en kontoinställning för varje anläggningstillgångsgrupp). För den här uppgiftsguiden lämnas värdet inställt på "Alla" för att gälla för alla anläggningstillgångar med den angivna boken.  
7. Ange önskade värden i fältet **Huvudkonto**. För anskaffningar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.    
8. I den nedrullningsbara menyn under snabbfliken **redovisningskonto** väljer du "Anskaffningsjustering". För anskaffningsjusteringstransaktioner ska du använda samma konton som använda för anskaffningstransaktioner.  
9. Klicka på **Lägg till**.
10. Ange eller välj ett värde i fältet **Bok**.
11. Ange önskade värden i fältet **Huvudkonto**. För anskaffningsjusteringar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.    
12. I den nedrullningsbara menyn under snabbfliken **redovisningskonto** väljer du "Avskrivning".
13. Klicka på **Lägg till**.
14. Ange eller välj ett värde i fältet **Bok**.
15. Ange önskade värden i fältet **Huvudkonto**.
16. Ange önskade värden i fältet **Motkonto**.
17. I den nedrullningsbara menyn under snabbfliken **redovisningskonto** väljer du "Avskrivningsjustering". För avskrivningsjusteringstransaktioner ska du använda samma konton som använda för avskrivningstransaktioner.  
18. Klicka på **Lägg till**.
19. Ange eller välj ett värde i fältet **Bok**.
20. Ange önskade värden i fältet **Huvudkonto**.
21. Ange önskade värden i fältet **Motkonto**.
22. I den nedrullningsbara menyn under snabbfliken **redovisningskonto** väljer du "Avyttrande försäljning".
23. Klicka på **Lägg till**.
24. Ange eller välj ett värde i fältet **Bok**.
25. Ange önskade värden i fältet **Huvudkonto**. För avyttringar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.  
26. I den nedrullningsbara menyn under snabbfliken **redovisningskonto** väljer du "Avyttrande kassation". Använd samma konton för Avyttrande försäljning och Avyttrande kassation.  
27. Klicka på **Lägg till**.
28. Ange eller välj ett värde i fältet **Bok**.
29. Ange önskade värden i fältet **Huvudkonto**. För avyttringar kan du ange ett motkonto eller lämna tomt om du vill åsidosätta för att fyllas i för den aktuella transaktionen.  
30. Expandera snabbfliken **Avyttra**. Du måste ställa in förfogandebokföringsprofiler för både försäljning och kassation.  Vi inleder med avyttringsförsäljningtransaktioner.  
31. Klicka på **Lägg till**.
32. Ange eller välj ett värde i fältet **Bok**.
33. Välj ”Anskaffningsvärde " i fältet **Bokför värde**.
    * Anskaffningsvärdet används för anskaffnings- och anskaffningsjusteringsvärden för alla år. Du kan också definiera konton för de transaktionstyperna separat.  
    * Du kan ange avyttringsprocessen om du vill använda andra konton, beroende på om avyttringen leder till en vinst eller en förlust. Jag ska ange försäljningvärdetypen till ”Alla” för användning av samma konton för alla typer av avyttringar.  
34. Ange önskade värden i fältet **Huvudkonto**.
35. Ange önskade värden i fältet **Motkonto**.
36. Klicka på **Lägg till**.
37. Ange eller välj ett värde i fältet **Bok**.
38. Välj ”Avskrivning (tidigare år)” i fältet **Bokför värde**.  
38. Ange önskade värden i fältet **Huvudkonto**.
39. Ange önskade värden i fältet **Motkonto**.
40. Klicka på **Lägg till**.
41. Ange eller välj ett värde i fältet **Bok**.
42. Välj ”Avskrivning (detta år)” i fältet **Bokför värde**.
43. Ange önskade värden i fältet **Huvudkonto**.
44. Ange önskade värden i fältet **Motkonto**.
45. Klicka på **Lägg till**.
46. Ange eller välj ett värde i fältet **Bok**.
47. Välj ”Avskrivningsjusteringar (tidigare år)” i fältet **Bokför värde**.
48. Ange önskade värden i fältet **Huvudkonto**.
49. Ange önskade värden i fältet **Motkonto**.
50. Klicka på **Lägg till**.
51. Ange eller välj ett värde i fältet **Bok**.
52. Välj ”Avskrivningsjusteringar (detta år)” i fältet **Bokför värde**.
53. Ange önskade värden i fältet **Huvudkonto**.
54. Ange önskade värden i fältet **Motkonto**.
55. Klicka på **Lägg till**.
56. Ange eller välj ett värde i fältet **Bok**.
57. Välj ”Bokfört nettovärde " i fältet **Bokför värde**.
58. Ange önskade värden i fältet **Huvudkonto**.
59. Ange önskade värden i fältet **Motkonto**.
60. Välj ”Kassation” i fältet **Försäljning eller kassation**.
61. Klicka på **Lägg till**.
62. Ange eller välj ett värde i fältet **Bok**.
63. Välj ”Anskaffningsvärde " i fältet **Bokför värde**.
64. Ange önskade värden i fältet **Huvudkonto**.
65. Ange önskade värden i fältet **Motkonto**.
66. Klicka på **Lägg till**.
67. Ange eller välj ett värde i fältet **Bok**.
67. Välj ”Avskrivning (tidigare år)” i fältet **Bokför värde**.  
68. Ange önskade värden i fältet **Huvudkonto**.
69. Ange önskade värden i fältet **Motkonto**.
70. Klicka på **Lägg till**.
71. Ange eller välj ett värde i fältet **Bok**.
72. Välj ”Avskrivning (detta år)” i fältet **Bokför värde**.
73. Ange önskade värden i fältet **Huvudkonto**.
74. Ange önskade värden i fältet **Motkonto**.
75. Klicka på **Lägg till**.
76. Ange eller välj ett värde i fältet **Bok**.
77. Välj ”Avskrivningsjusteringar (tidigare år)” i fältet **Bokför värde**.
78. Ange önskade värden i fältet **Huvudkonto**.
79. Ange önskade värden i fältet **Motkonto**.
80. Klicka på **Lägg till**.
81. Ange eller välj ett värde i fältet **Bok**.
82. Välj ”Avskrivningsjusteringar (detta år)” i fältet **Bokför värde**.
83. Ange önskade värden i fältet **Huvudkonto**.
84. Ange önskade värden i fältet **Motkonto**.
85. Klicka på **Lägg till**.
86. Ange eller välj ett värde i fältet **Bok**.
87. Välj ”Bokfört nettovärde " i fältet **Bokför värde**.
88. Ange önskade värden i fältet **Huvudkonto**.
89. Ange önskade värden i fältet **Motkonto**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
