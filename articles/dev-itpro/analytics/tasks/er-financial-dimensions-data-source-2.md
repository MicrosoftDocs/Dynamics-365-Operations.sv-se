---
title: "\"ER Använd ekonomiska dimensioner som en datakälla (Del 2 - Modellmappning)\""
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92efd6a0b36471286c292a80542b81cd14a8eff3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "319602"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2-model-mapping"></a>ER Använd ekonomiska dimensioner som en datakälla (Del 2: Modellmappning)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter. Dessa steg kan utföras på valfritt företag.

För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 1: Design data model”.


## <a name="add-required-data-sources-to-model-mapping"></a>Lägg till erforderliga datakällor till modellmappningen
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Välj "Financial dimensions sample model" i trädet.
3. Klicka på Designer.
4. Klicka på Mappa modell till datakälla.
5. Klicka på Ny.
6. Välj Entry i fältet Definition.
7. Ange "Dimensions data mapping" i namnfältet.
8. Ange "Dimensions data mapping" i beskrivningsfältet.
9. Klicka på Spara.
10. Klicka på Designer.
11. Välj "Dynamics 365 for Operations\Table" i trädet.
12. Klicka på Lägg till rot.
13. Skriv "Företag" i fältet Namn.
14. Skriv "CompanyInfo" i fältet Tabell.
15. Klicka på OK.
16. Välj "Functions\Financial dimensions details" i trädet.
17. Klicka på Lägg till rot.
    * Datakällan anger hur omfånget av ekonomiska dimensioner ska definieras för alla rapporter som ska använda den här modellen som en datakälla.  
18. Skriv ett värde i fältet Namn.
19. Välj Yes i fältet Ask for dimensions.
    * Välj Yes om du vill tillåta användaren att välja dimensioner vid körning på användardialogformuläret. Om inställt på No kommer ekonomiska dimensioner för den aktuella instansen att användas som standard.  
20. Välj "Legal entity" i fältet för ekonomisk dimension.
    * Markera All om du vill tillåta användaren att välja önskedimensioner för den aktuella instansen i fältet Lookup.  Markera Legal entity om du vill tillåta användaren att välja dimensioner för företaget i fältet Lookup.  Välj Dimension för att tillåta användaren att välja dimensioner med hjälp av en enda dimensionsuppsättning.  
21. Välj Yes i fältet Ask for main account.
    * Ange "Ask for main account" som Yes om du vill låta användare välja huvudkontot som en del i listan över dimensioner.   Om No kommer huvudkontot inte att inkluderas i listan över dimensioner, och alternativet "Is main account mandatory" aktiveras. Om ”Is main account mandatory" anges som Yes, inkludera då huvudkontot i dimensionslistan oavsett användarens urval.  
22. Klicka på OK.
23. Välj "Dynamics 365 for Operations\Table records" i trädet.
24. Klicka på Lägg till rot.
25. Välj "LedgerJournal" i namnfältet.
26. Välj Ja i fältet Fråga efter fråga.
27. Ange "LedgerJournalTable" i tabellfältet.
28. Klicka på OK.

## <a name="map-data-model-elements-to-added-data-sources"></a>Mappa datamodellelement till tillagda datakällor
1. Expandera "Journal" i trädet.
2. Expandera "Journal\Transaction" i trädet.
3. Expandera "Journal\Transaction\Dimensions data" i trädet.
4. Expandera "Dimensions setting" i trädet.
5. Expandera "LedgerJournal" i trädet.
6. Expandera "LedgerJournal\<Relations" i trädet.
7. Expandera "LedgerJournal\<Relations\LedgerJournalTrans" i trädet.
8. Välj "LedgerJournal\<Relations\LedgerJournalTrans\Voucher" i trädet.
9. Välj "Journal\Transaction\Voucher" i trädet.
10. Klicka på Bind.
11. Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)" i trädet.
    * Notera att för alla referenser till ekonomiska dimensioner, inställda till exempelvis LedgerDimension, finns en motsvarande datakällartikel (LedgerDimension.Dimension). Denna datakällaartikel erbjuder de ekonomiska dimensionerna för denna dimensionsuppsättning som postens lista.  
12. Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)" i trädet.
13. Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions" i trädet.
14. Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value" i trädet.
15. Expandera "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition" i trädet.
16. Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name" i trädet.
17. Välj "Journal\Transaction\Dimensions data\Name" i trädet.
18. Klicka på Bind.
19. Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description" i trädet.
20. Välj "Journal\Transaction\Dimensions data\Description" i trädet.
21. Klicka på Bind.
22. Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code" i trädet.
23. Välj "Journal\Transaction\Dimensions data\Code" i trädet.
24. Klicka på Bind.
25. Välj "LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions" i trädet.
26. Välj "Journal\Transaction\Dimensions data" i trädet.
27. Klicka på Bind.
28. Välj "LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)" i trädet.
29. Välj "Journal\Transaction\Debit" i trädet.
30. Klicka på Bind.
31. Välj "LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)" i trädet.
32. Välj "Journal\Transaction\Date" i trädet.
33. Klicka på Bind.
34. Välj "LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)" i trädet.
35. Välj "Journal\Transaction\Currency" i trädet.
36. Klicka på Bind.
37. Välj "LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)" i trädet.
38. Välj "Journal\Transaction\Credit" i trädet.
39. Klicka på Bind.
40. Välj "LedgerJournal\<Relations\LedgerJournalTrans" i trädet.
41. Välj "Journal\Transaction" i trädet.
42. Klicka på Bind.
43. Välj "LedgerJournal\Journal batch number(JournalNum)" i trädet.
44. Välj "Journal\Batch" i trädet.
45. Klicka på Bind.
46. Välj "LedgerJournal" i trädet.
47. Välj "Journal" i trädet.
48. Klicka på Bind.
49. Expandera "Dimensions" i trädet.
50. Expandera "Dimensions\Main account and dimensions" i trädet.
51. Expandera "Dimensions\Main account and dimensions\Definition" i trädet.
52. Välj "Dimensions\Main account and dimensions\Definition\Name" i trädet.
53. Välj "Dimensions setting\Code".
54. Klicka på Bind.
55. Välj "Dimensions\Main account and dimensions\Definition\Report column name" i trädet.
56. Välj "Dimensions setting\Name" i trädet.
57. Klicka på Bind.
58. Välj "Dimensions\Main account and dimensions" i trädet.
59. Välj "Dimensions setting" i trädet.
60. Klicka på Bind.
61. Välj "Company" i trädet.
62. Klicka på Redigera.
63. I fältet expressionAsStringText anger du "Company.'find()'.'name()''.
    * Company.'find()'.'name()'  
64. Klicka på Spara.
65. Stäng sidan.
66. Klicka på Spara.
67. Stäng sidan.

## <a name="complete-this-draft-models-version"></a>Slutför denna utkastmodellversion
1. Stäng sidan.
2. Stäng sidan.
3. Klicka på Ändra status.
4. Klicka på Slutför.
5. Klicka på OK.

