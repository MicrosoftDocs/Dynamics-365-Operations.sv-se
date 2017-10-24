--- 
title: "Utforma en datamodell som använder ekonomiska dimensioner som datakälla för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur antingen en systemadministratör eller en utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) att använda ekonomiska dimensioner som datakällor för ER-rapporter."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: d8a03c4b85666975a7b42d46f3afdd35019e9b93
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="design-data-model-to-use-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a>Utforma en datamodell som använder ekonomiska dimensioner som datakälla för elektronisk rapportering (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


