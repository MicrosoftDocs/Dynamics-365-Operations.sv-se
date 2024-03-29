---
title: ER Konfigurera format för att utföra inventering och summering (Del 2 - Konfigurera beräkningar)
description: I den här artikeln beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat för inventering och summering baserat på data i det redan genererade textutdata. (Del 2)
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula
ms.openlocfilehash: f7cdfff15ac157d69f0b60de8b36acc870a9cf49
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290677"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-2---configure-computations"></a>ER Konfigurera format för att utföra inventering och summering (Del 2 - Konfigurera beräkningar)

[!include [banner](../../includes/banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) att utföra inventering och summering baserat på data tillhörande redan skapad textutmatning. Dessa steg kan utföras på valfritt företag.

För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Configure format to do counting and summing (Part 1: Create format).

Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a>Skapa en formatkonfiguration för att lägga till att informationsinventering och -summering
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Klicka på Reporting configurations.
3. Expandera "Intrastat model" i trädet.
4. Välj "Intrastat modell\Intrastat (DE)" i trädet.
    * Låt oss anta att du behöver anpassa det format som tillhandahålls av Microsoft genom att lägga till rader med sammanfattningsinformation i slutet av Intrastatrapporten. Du gör detta genom att härleda din egen instans av Intrastatkonfigurationen från Microsoft-instansen för att genomföra ändringar.  
5. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
6. I fältet New anger du "Derive from Name: Intrastat (DE), Microsoft".
7. I namnfältet anger du "Intrastat (DE) with counting & summing".
8. Klicka på Skapa konfiguration.

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a>Konfigurera denna rapport att utföra inventering och summering baserat på utleveransinformation
1. Klicka på Designer.
2. Välj Yes fältet Collect output details.
    * Denna flagga aktiverar (vid körning) den process som samlar in utmatningsinformation för generering av Intrastat-filen.  
    * Du måste genomföra inventering för olika Instrastat-riktningar. Se därför till att lägga till en särskilt avsedd modelluppräkning i datakällans lista för denna formatkonfiguration.  
3. Klicka på fliken Mappning.
4. Klicka på Lägg till rot för att öppna dialogrutan.
5. Välj "Data model\Enumeration" i trädet.
6. Ange "Direction" i namnfältet.
7. Ange eller välj ett värde i fältet Model enumeration.
    * Välj värdet Direction.  
8. Klicka på OK.
9. Klicka på Lägg till rot för att öppna dialogrutan.
10. Välj Funktioner/Beräknat fält i trädet.
11. Ange "$BlockName" i namnfältet.
12. Klicka på Redigera formel.
13. Ange "block" i formelfältet.
14. Klicka på Spara.
15. Stäng sidan.
16. Klicka på OK.
17. Klicka på Lägg till rot för att öppna dialogrutan.
18. Välj Funktioner/Beräknat fält i trädet.
19. Ange "$RecName" i namnfältet.
20. Klicka på Redigera formel.
21. Ange "record" i formelfältet.
22. Klicka på Spara.
23. Stäng sidan.
24. Klicka på OK.
25. Klicka på Lägg till rot för att öppna dialogrutan.
26. Välj Funktioner/Beräknat fält i trädet.
27. Ange "$InvName" i namnfältet.
28. Klicka på Redigera formel.
29. Ange "InvoicedAmountEUR" i formelfältet.
30. Klicka på Spara.
31. Stäng sidan.
32. Klicka på OK.
33. Välj "Intrastat\Data" i trädet.
34. Klicka på knappen Edit för fältet "Collected data key name"
35. Klicka på Lägg till datakälla.
    * $BlockName  
36. Klicka på Spara.
37. Stäng sidan.
38. Klicka på knappen Edit för fältet Collected data key value.
39. Ange "IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")" i formelfältet.
    * IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")  
40. Klicka på Spara.
41. Stäng sidan.
    * Räkna raderna i denna sekvens. Resultaten kommer att användas med namnet "block" separat för olika riktningar. Värdet ”Import” kommer att användas för eventuella Intrastat-transaktioner. Värdet ”Export” kommer att användas för eventuella Intrastat-transaktioner för utförslar. Betrakta detta som ett virtuellt Excel-kalkylblad. För varje transaktion fylls en rad i, där den första kolumnen ”block” fylls i med värdena ”Import ”respektive ”Export”.  
42. Expandera "Intrastat\Data: Sequence" i trädet.
43. Välj "Intrastat\Data: Sequence\Arrivals?" i trädet.
44. Klicka på knappen Edit för fältet "Insamlat datanyckelnamn".
    * Räkna raderna i denna sekvens. Klicka på knappen Edit för fältet "Insamlat datanyckelvärde".  
45. Välj "$RecName" i trädet.
46. Klicka på Lägg till datakälla.
47. Klicka på Spara.
48. Stäng sidan.
49. Klicka på knappen Redigera för fältet Insamlat datanyckelvärde.
50. Ange "Intrastat.CommodityRecord.CommodityCode" i formelfältet.
51. Klicka på Spara.
52. Stäng sidan.
    * Räkna raderna i denna sekvens. Resultaten kommer att användas med namnet "post" separat för olika varukoder. Betrakta detta som ett virtuellt Excel-kalkylblad. För varje transaktion kommer en rad att fyllas i på följande sätt: Det första kolumn-"blocket" fylls i med värdena ”Import" respektive "Export”, och den andra block-"posten" med varans kodvärde.  
53. Välj "Intrastat\Data: Sequence\Dispatches?" i trädet.
54. Klicka på knappen Edit för fältet "Collected data key name"
55. Välj "$RecName" i trädet.
56. Klicka på Lägg till datakälla.
57. Klicka på Spara.
58. Stäng sidan.
59. Klicka på knappen Edit för fältet "Insamlat datanyckelvärde".
60. Ange "Intrastat.CommodityRecord.CommodityCode" i formelfältet.
61. Klicka på Spara.
62. Stäng sidan.
63. Expandera "Intrastat\Data: Sequence\Dispatches: Sequence?" i trädet.
64. Expandera "Intrastat\Data: Sequence\Dispatches: Sequence?\Record =  Intrastat.CommodityRecord" i trädet.
65. Klicka på fliken Format.
66. Välj "Intrastat\Data\Dispatches\Record\Invoice amount EUR" i trädet.
67. Klicka på fliken Mappning.
68. Klicka på knappen Edit för fältet "Insamlat datanyckelnamn".
69. Välj "$InvName" i trädet.
70. Klicka på Lägg till datakälla.
71. Klicka på Spara.
72. Stäng sidan.
    * Sammanfatta de fakturerade beloppvärdena för rader i denna sekvens. Resultaten kommer att användas med namnet "InvoicedAmountEUR" separat för olika Intrastat-riktningar och varukoder. Betrakta detta som en virtuell skapelse i ett Excel-kalkylblad. För varje transaktion fylls en rad i, där den första kolumnen ”block” fylls i med värdena ”Import ”respektive ”Export”. Det andra blocket ”post” fylls i med varans kodvärde, och den tredje kolumnen "InvoicedAmountEUR" fylls i med fakturabeloppets värde.  
73. Expandera "Intrastat\Data\Arrivals?" i trädet.
74. Expandera "Intrastat\Data\Arrivals?\Record =  Intrastat.CommodityRecord" i trädet.
75. Klicka på fliken Format.
76. Välj "Intrastat\Data\Arrivals\Record\Invoice amount EUR" i trädet.
77. Klicka på fliken Mappning.
78. Klicka på knappen Edit för fältet "Insamlat datanyckelnamn".
79. Välj "$InvName" i trädet.
80. Klicka på Lägg till datakälla.
81. Klicka på Spara.
82. Stäng sidan.
83. Klicka på Spara.
84. Stäng sidan.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
