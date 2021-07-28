---
title: ER Använd ekonomiska dimensioner som en datakälla (Del 1 - Designa datamodell)
description: I det här avsnittet beskrivs hur du konfigurerar en elektronisk rapporteringsmodell (ER) för användning av ekonomiska dimensioner som datakälla för ER-rapporter. (Del 1)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ce7b1ad5472a6e276d356ff4e814defcc5af1f9d
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359397"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a>ER Använd ekonomiska dimensioner som en datakälla (Del 1 - Designa datamodell)

[!include [banner](../../includes/banner.md)]

I följande steg beskrivs hur antingen en systemadministratör eller en utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) att använda ekonomiska dimensioner som datakällor för ER-rapporter. Dessa steg kan utföras på valfritt företag.

För att slutföra dessa steg måste du först slutföra stegen i proceduren "Create a configuration provider and mark it as active”.


## <a name="create-a-new-data-model"></a>Skapa en ny datamodell
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
    * Kontrollera att ”Litware Inc."-leverantören är tillgänglig och markerats som aktiv.  
2. Klicka på Reporting configurations.
3. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
4. Ange "Financial dimensions sample model" i namnfältet.
5. Klicka på Skapa konfiguration.
6. Klicka på Designer.
7. Klicka på Nytt om du vill öppna dialogrutan.
8. Ange "Entry" i namnfältet.
9. Klicka på Lägg till.
10. Klicka på Nytt om du vill öppna dialogrutan.
11. Skriv "Företag" i fältet Namn.
12. Klicka på Lägg till.
    * Vi ska lägga till en ny postlista till vår modell. Den här listan kommer att visa inställningarna för valda ekonomiska dimensioner (för alla ER-rapporter som använder denna modell som en datakälla). Varje ekonomisk dimension visas i listan som en post med passande fält som representerar dimensionens inställning.  
13. Klicka på Nytt om du vill öppna dialogrutan.
14. Ange "Dimensions setting" i namnfältet.
15. Välj "Postlista" i fältet Artikeltyp.
16. Klicka på Lägg till.
17. Klicka på Nytt om du vill öppna dialogrutan.
18. Ange "Code" i namnfältet.
19. Välj "Sträng" i fältet Artikeltyp.
20. Klicka på Lägg till.
21. Klicka på Nytt om du vill öppna dialogrutan.
22. Skriv "Namn" i fältet Namn.
23. Klicka på Lägg till.
24. Välj "Entry" i trädet.
25. Klicka på Nytt om du vill öppna dialogrutan.
26. Ange "Journal" i namnfältet.
27. Välj "Postlista" i fältet Artikeltyp.
28. Klicka på Lägg till.
29. Klicka på Nytt om du vill öppna dialogrutan.
30. Ange "Batch" i namnfältet.
31. Välj "Sträng" i fältet Artikeltyp.
32. Klicka på Lägg till.
33. Klicka på Nytt om du vill öppna dialogrutan.
34. Ange "Transaction" i namnfältet.
35. Välj "Postlista" i fältet Artikeltyp.
36. Klicka på Lägg till.
37. Klicka på Nytt om du vill öppna dialogrutan.
38. Ange "Date" i namnfältet.
39. Välj "Datum" i fältet Artikeltyp.
40. Klicka på Lägg till.
41. Klicka på Nytt om du vill öppna dialogrutan.
42. Ange "Debit" i namnfältet.
43. Välj "Realtal" i fältet Artikeltyp.
44. Klicka på Lägg till.
45. Klicka på Nytt om du vill öppna dialogrutan.
46. Ange "Credit" i namnfältet.
47. Klicka på Lägg till.
48. Klicka på Nytt om du vill öppna dialogrutan.
49. Skriv "Valuta" i fältet Namn.
50. Välj "Sträng" i fältet Artikeltyp.
51. Klicka på Lägg till.
52. Klicka på Nytt om du vill öppna dialogrutan.
53. Ange "Voucher" i namnfältet.
54. Klicka på Lägg till.
55. Klicka på Nytt om du vill öppna dialogrutan.
56. Ange "Dimensions data" i namnfältet.
57. Välj "Postlista" i fältet Artikeltyp.
58. Klicka på Lägg till.
    * Vi har lagt till en ny postlisa i vår modell. Den här listan kommer att visa värdena för valda ekonomiska dimensioner (för alla ER-rapporter som använder denna modell som en datakälla). Varje ekonomisk dimension visas i listan som en post med passande fält som representerar dimensionens värden. Dimensionsnamn visas även i denna post som ett fält som vid behov ska användas för urval.  
59. Klicka på Nytt om du vill öppna dialogrutan.
60. Ange "Code" i namnfältet.
61. Välj "Sträng" i fältet Artikeltyp.
62. Klicka på Lägg till.
63. Klicka på Nytt om du vill öppna dialogrutan.
64. Skriv "Beskrivning" i fältet Namn.
65. Klicka på Lägg till.
66. Klicka på Nytt om du vill öppna dialogrutan.
67. Skriv "Namn" i fältet Namn.
68. Klicka på Lägg till.
69. Klicka på Spara.
70. Stäng sidan.

![Sidan ER-datamodelldesigner.](../media/er-financial-dimensions-guides-data-model.png)



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]