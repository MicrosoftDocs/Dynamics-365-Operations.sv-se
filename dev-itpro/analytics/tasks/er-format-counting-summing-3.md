--- 
title: "Använd beräkningar för att skapa utdata för inventering och summering för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d6f9fc973ae9b36f6d78228d2e8ed4a2684c4875
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="use-computations-to-make-the-output-for-counting-and-summing-for-electronic-reporting-er"></a>Använd beräkningar för att skapa utdata för inventering och summering för elektronisk rapportering (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan genererad textutmatning. Dessa steg kan utföras på valfritt företag.

För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Configure format to do counting and summing (Part 2: Configure computations)"

Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="configure-this-report-to-use-counting-and-summing-info"></a>Konfigurera den här rapporten om du vill använda inventerings- och summeringsinformation
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Klicka på Reporting configurations.
3. Expandera "Intrastat model" i trädet.
4. Expandera "Intrastat model\Intrastat (DE)" i trädet.
5. Välj "Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing" i trädet.
6. Klicka på Designer.
7. Klicka på fliken Mappning.
8. Klicka på Lägg till rot för att öppna dialogrutan.
    * Lägg till en ny datakälla för att få listan över memorerade block.  
9. Välj Funktioner/Beräknat fält i trädet.
10. Ange "$BlocksList" i namnfältet.
    * $BlocksList  
11. Klicka på Redigera formel.
12. Välj "Data collection functions\COLLECTEDLIST" i trädet.
13. Klicka på funktionen Lägg till.
14. Klicka på Lägg till datakälla.
15. Ange "COLLECTEDLIST('$BlockName', " i formelfältet.
    * COLLECTEDLIST('$BlockName',  
16. Ange "COLLECTEDLIST('$BlockName', "*")" i formelfältet.
    * COLLECTEDLIST('$BlockName', "*")  
17. Klicka på Spara.
    * Mönstret ”*” innebär att alla block kommer att inkluderas i listan för denna post.  
18. Stäng sidan.
19. Klicka på OK.
20. Klicka på fliken Format.
21. Välj "Intrastat\Data" i trädet.
22. Klicka på Lägg till för att öppna dialogrutan.
23. Välj "Text\Sequence" i trädet.
24. Ange "Totals by blocks" i namnfältet.
    * Summor per block  
25. Välj "New line - Windows (CR LF)" i fältet för specialtecken.
26. Klicka på OK.
27. Välj "Intrastat\Data\Totals by blocks" i trädet.
28. Klicka på Lägg till för att öppna dialogrutan.
29. Välj "Text\Sträng" i trädet.
30. Ange "Block code" i namnfältet.
    * Blockkod  
31. Klicka på OK.
32. Klicka på Add string.
33. Ange "Lines counting" i namnfältet.
    * Radinventering  
34. Klicka på OK.
35. Klicka på Add string.
36. Ange "Total amount" i namnfältet.
    * Totalt antal timmar  
37. Klicka på OK.
38. Klicka på fliken Mappning.
39. Välj "$BlocksList" i trädet.
40. Klicka på Bind.
    * Skapa en summeringsrad för varje memorerat block.  
41. Klicka på fliken Format.
42. Välj "Intrastat\Data\Totals by blocks\Block code" i trädet.
43. Klicka på fliken Mappning.
44. Klicka på Redigera formel.
45. Ange ""Block id: " & "  " i formelfältet.
    * "Block id: " &  
46. Expandera "$BlocksList" i trädet.
47. Välj "$BlocksList\Value" i trädet.
48. Klicka på Lägg till datakälla.
49. Klicka på Spara.
50. Stäng sidan.
51. Klicka på fliken Format.
52. Välj "Intrastat\Data\Totals by blocks\Lines counting" i trädet.
53. Klicka på fliken Mappning.
54. Klicka på Redigera formel.
    * Skapa utleverans för det antal rader i varje block som presenteras i den här rapporten.  
55. I formelfältet anger du ""Number of lines in this block: " & ".
    * "Antal rader i detta block:  " &   
56. I formelfältet anger du ""Number of lines in this block: " & TEXT(".
    * "Antal rader i detta block: " & TEXT(  
57. Välj "Data collection functions\COUNTIFS".
58. Klicka på funktionen Lägg till.
59. Klicka på Lägg till datakälla.
60. I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', ".
    * "Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName',  
61. Expandera "$BlocksList" i trädet.
62. Välj "$BlocksList\Value" i trädet.
63. Klicka på Lägg till datakälla.
64. I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, ".
    * "Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,  
65. Välj "$RecName" i trädet.
66. Klicka på Lägg till datakälla.
67. I formelfältet anger du ""Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))".
    * "Antal rader i detta block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
68. Klicka på Spara.
69. Stäng sidan.
70. Klicka på fliken Format.
71. I trädet väljer du "Intrastat\Data\Totals by blocks\Total amount".
72. Klicka på fliken Mappning.
73. Klicka på Redigera formel.
    * Skapa utleverans som ska vara summan av det fakturerade beloppet för varje textblock som visas i den här rapporten.  
74. I formelfältet anger du ""Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))".
    * ”Summan av det fakturerade beloppet: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
75. Klicka på Spara.
76. Stäng sidan.
77. Klicka på Spara.
78. Stäng sidan.


