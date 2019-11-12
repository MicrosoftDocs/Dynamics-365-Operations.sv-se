---
title: ER Använd ekonomiska dimensioner som en datakälla (Del 3 - Designa rapporten)
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77f1f2d6390a1d99b22d6eab9f0cae30f9760cc8
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550589"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a>ER Använd ekonomiska dimensioner som en datakälla (Del 3 - Designa rapporten)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter. Dessa steg kan utföras på valfritt företag.

För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 2: Model mapping”.


## <a name="design-a-report-to-present-financial-dimensions"></a>Designa en rapport för att presentera ekonomiska dimensioner
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Välj "Financial dimensions sample model" i trädet.
3. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
4. Ange "Format based on data model Financial dimensions sample model" i fältet New.
    * Använd den modell som skapades i förväg som datakälla för den nya rapporten.  
5. Ange "Ledger journal report" i namnfältet.
6. Välj Entry i fältet Data model definition.
7. Klicka på Skapa konfiguration.
8. Klicka på Designer.
9. Klicka på Lägg till rot för att öppna dialogrutan.
10. Välj "XML\Element" i trädet.
11. Ange "Root" i namnfältet.
12. Klicka på OK.
13. Klicka på Lägg till för att öppna dialogrutan.
14. Välj "XML\Attribut" i trädet.
15. Skriv "Företag" i fältet Namn.
16. Klicka på OK.
17. Klicka på Lägg till för att öppna dialogrutan.
18. Välj "XML\Element" i trädet.
19. Ange "Journal" i namnfältet.
20. Klicka på OK.
21. I trädet väljer du "Root: XML Element\Journal: XML Element".
22. Klicka på Lägg till för att öppna dialogrutan.
23. Välj "XML\Attribut" i trädet.
24. Ange "Batch" i namnfältet.
25. Klicka på OK.
26. Klicka på Lägg till för att öppna dialogrutan.
27. Välj "XML\Element" i trädet.
28. Ange "Transaction" i namnfältet.
29. Klicka på OK.
30. I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element".
31. Klicka på Lägg till för att öppna dialogrutan.
32. Välj "XML\Attribut" i trädet.
33. Ange "Voucher" i namnfältet.
34. Klicka på OK.
35. Klicka på Add Attribute.
36. Ange "Date" i namnfältet.
37. Klicka på OK.
38. Klicka på Add Attribute.
39. Skriv "Valuta" i fältet Namn.
40. Klicka på OK.
41. Klicka på Add Attribute.
42. Ange "Dt" i namnfältet.
43. Klicka på OK.
44. Klicka på Add Attribute.
45. Ange "Ct" i namnfältet.
46. Klicka på OK.
47. Klicka på Lägg till för att öppna dialogrutan.
48. Välj "XML\Element" i trädet.
49. Ange "Dimensions" i namnfältet.
50. Klicka på OK.
51. I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element".
52. Klicka på Lägg till för att öppna dialogrutan.
53. Välj "XML\Attribut" i trädet.
54. Ange "Code" i namnfältet.
55. Klicka på OK.
56. Klicka på Add Attribute.
57. Ange "Value" i namnfältet.
58. Klicka på OK.
59. Klicka på Add Attribute.
60. Ange "Desc" i namnfältet.
61. Klicka på OK.

## <a name="map-report-elements-to-data-sources"></a>Mappa rapportelement till datakällor
1. Klicka på fliken Mappning.
2. Expandera "model: Data model Financial dimensions sample model" i trädet.
3. Expandera "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.
4. Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.
5. Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.
6. Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute" i trädet.
7. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String" i trädet.
8. Klicka på Bind.
9. Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute" i trädet.
10. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String" i trädet.
11. Klicka på Bind.
12. Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute" i trädet.
13. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String" i trädet.
14. Klicka på Bind.
15. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.
16. I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element".
17. Klicka på Bind.
18. Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute" i trädet.
19. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real" i trädet.
20. Klicka på Bind.
21. Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute" i trädet.
22. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real" i trädet.
23. Klicka på Bind.
24. Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute" i trädet.
25. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String" i trädet.
26. Klicka på Bind.
27. Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute" i trädet.
28. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date" i trädet.
29. Klicka på Bind.
30. Välj "Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute" i trädet.
31. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String" i trädet.
32. Klicka på Bind.
33. I trädet väljer du "Root: XML Element\Journal: XML Element\Transaction: XML Element".
34. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.
35. Klicka på Bind.
36. Välj "Root: XML Element\Journal: XML Element\Batch: XML Attribute" i trädet.
37. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Batch: String" i trädet.
38. Klicka på Bind.
39. I trädet väljer du "Root: XML Element\Journal: XML Element".
40. Välj "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.
41. Klicka på Bind.
42. Välj "Root: XML Element\Company: XML Attribute" i trädet.
43. Välj "model: Data model Financial dimensions sample model\Company: String" i trädet.
44. Klicka på Bind.
45. Klicka på Spara.
46. Stäng sidan.

