--- 
title: "Utforma ett format som använder horisontellt expanderbara intervall för att lägga till kolumner dynamiskt i Excel-rapporter för elektronisk rapportering (ER)"
description: "Följande steg beskriver hur en användare som är tilldelad rollen som systemadministratör eller elektronisk rapporteringutvecklare kan konfigurera ett elektroniskt rapporteringsformat (ER) för att generera rapporter som OPENXML-kalkylblad (Excel), där erforderliga kolumner kan skapas dynamiskt som horisontellt expanderbara intervall."
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1ccf3b2d81066fce80fe14428fab24020ab85496
ms.openlocfilehash: b921b5ff51f951112031fe8b1bc2faa90cf29a28
ms.contentlocale: sv-se
ms.lasthandoff: 11/07/2017

---
# <a name="design-a-format-to-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-for-electronic-reporting-er"></a>Utforma ett format som använder horisontellt expanderbara intervall för att lägga till kolumner dynamiskt i Excel-rapporter för elektronisk rapportering (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Följande steg beskriver hur en användare som är tilldelad rollen som systemadministratör eller elektronisk rapporteringutvecklare kan konfigurera ett elektroniskt rapporteringsformat (ER) för att generera rapporter som OPENXML-kalkylblad (Excel), där erforderliga kolumner kan skapas dynamiskt som horisontellt expanderbara intervall. Dessa steg kan utföras på valfritt företag.

För att slutföra dessa steg måste du först avsluta dessa tre uppgiftsguider: 

"ER Skapa en konfigurationsleverantör och välj den som aktiv"

"ER Använd ekonomiska dimensioner som en datakälla (Del 1: Designa datamodell)"

"ER Använd ekonomiska dimensioner som en datakälla (Del 2: Modellmappning)"

Du måste också hämta och spara en lokal kopia av mallen med en exempelrapport som finns här [https://go.microsoft.com/fwlink/?linkid=862266](https://go.microsoft.com/fwlink/?linkid=862266). 


Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="create-a-new-report-configuration"></a>Skapa en ny rapportkonfiguration
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Välj "Financial dimensions sample model" i trädet.
3. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
4. Ange "Format based on data model Financial dimensions sample model" i fältet New.
    * Använd den modell som skapades i förväg som datakälla för den nya rapporten.  
5. Ange "Sample report with horizontally expandable ranges" i namnfältet.
    * Provrapport med horisontellt expanderbara intervall  
6. Ange "To make Excel output with dynamically adding columns" i fältet Description.
    * Skapa Excel-utmatningar med dynamiskt tillagda kolumner  
7. Välj Entry i fältet Data model definition.
8. Klicka på Skapa konfiguration.

## <a name="design-the-report-format"></a>Designa rapportformatet
1. Klicka på Designer.
2. Aktivera knappen "Show details".
3. Klicka på Importera i åtgärdsfönstret.
4. Klicka på Importera från Excel.
5. Klicka på Bilagor.
    * Importera rapportens mall. Använd den Excel-fil du hämtade för detta.  
6. Klicka på Ny.
7. Klicka på Arkiv.
8. Stäng sidan.
9. Ange eller välj ett värde i fältet Template.
    * Välj den hämtade mallen.  
10. Klicka på OK.
    * Lägg till ett nytt intervall för att dynamiskt skapa Excel-utmatning med det antal kolumner du valde (i användardialogformuläret) för ekonomiska dimensioner. Varje cell för respektive kolumn representerar namnet på en enskild ekonomisk dimension.  
11. Klicka på Lägg till för att öppna dialogrutan.
12. Välj "Excel\Range" i trädet.
13. Ange "DimNames" i Excel-intervallsfältet.
    * DimNames  
14. Ange "Horizontal" i fältet Replication direction.
15. Klicka på OK.
16. Välj "Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal" i trädet
17. Klicka på Flytta upp.
18. Välj "Excel = "SampleFinDimWsReport"\Cell<DimNames>" i trädet.
19. Klicka på Cut.
20. Välj "Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal" i trädet
21. Klicka på Paste.
22. Visa "Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal" i trädet
23. Visa "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical" i trädet
24. Expandera "Excel = "SampleFinDimWsReport"\Range<JournalLine>Vertical\Range<TransactionLine>: Vertical" i trädet.
25. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>Vertical\Range<TransactionLine>: Vertical" i trädet.
    * Lägg till ett nytt intervall för att dynamiskt skapa Excel-utmatning med det antal kolumner du valde (i användardialogformuläret) för ekonomiska dimensioner. Varje cell för respektive kolumn representerar värdet för respektive rapporterande transaktion i en enskild ekonomisk dimension.  
26. Klicka på Add Range.
27. Ange "DimValues" i fältet för Excel-intervall.
    * DimValues  
28. Ange "Horizontal" i fältet Replication direction.
29. Klicka på OK.
30. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues>" i trädet.
31. Klicka på Cut.
32. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal" i trädet.
33. Klicka på Paste.
34. Visa "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal" i trädet.

## <a name="map-format-elements-to-data-sources"></a>Mappa formatelement till datakällor
1. Klicka på fliken Mappning.
2. Expandera "model: Data model Financial dimensions sample model" i trädet.
3. Expandera "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.
4. Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.
5. Expandera "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.
6. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>" i trädet.
7. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String" i trädet.
8. Klicka på Bind.
9. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal" i trädet.
10. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list" i trädet.
11. Klicka på Bind.
12. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit>" i trädet.
13. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real" i trädet.
14. Klicka på Bind.
15. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit>" i trädet.
16. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real" i trädet.
17. Klicka på Bind.
18. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency>" i trädet.
19. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String" i trädet.
20. Klicka på Bind.
21. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate>" i trädet.
22. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date" i trädet.
23. Klicka på Bind.
24. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher>" i trädet.
25. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String" i trädet.
26. Klicka på Bind.
27. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch>" i trädet.
28. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Batch: String" i trädet.
29. Klicka på Bind.
30. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>Vertical\Range<TransactionLine>: Vertical" i trädet.
31. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list" i trädet.
32. Klicka på Bind.
33. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>" i trädet.
34. Välj "model: Data model Financial dimensions sample model\Journal: Record list\Batch: String" i trädet.
35. Klicka på Bind.
36. Välj "Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical" i trädet.
37. Välj "model: Data model Financial dimensions sample model\Journal: Record list" i trädet.
38. Klicka på Bind.
39. Expandera "model: Data model Financial dimensions sample model\Dimensions setting: Record list" i trädet.
40. Välj "model: Data model Financial dimensions sample model\Dimensions setting: Record list\Code: String" i trädet.
41. Välj "Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>" i trädet.
42. Klicka på Bind.
43. Välj "model: Data model Financial dimensions sample model\Dimensions setting: Record list" i trädet.
44. Välj "Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal" i trädet
45. Klicka på Bind.
46. Välj "Excel = "SampleFinDimWsReport"\Cell<CompanyName>" i trädet.
47. Välj "model: Data model Financial dimensions sample model\Company: String" i trädet.
48. Klicka på Bind.
49. Klicka på Spara.
50. Stäng sidan.


