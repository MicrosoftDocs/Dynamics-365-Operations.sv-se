---
title: ER Använd dokumenthanteringsfiler i formatutmatningar (Del 2 - Utöka datamodellen)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat (ER) för användning av dokumenthanteringsfiler (bilagor) i ER-utdata. (Del 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b47c35790ce04a494b6c58f6e04fa9b829d2ab93
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559783"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a>ER Använd dokumenthanteringsfiler i formatutmatningar (Del 2 - Utöka datamodellen)

[!include [banner](../../includes/banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar. Dessa steg kan utföras på valfritt företag.

För att slutföra dessa steg måste du först avsluta stegen i uppgiftsguiden "ER Use Document Management files in format outputs (Part 1: Prepare data model)".

Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a>Utöka datamodellen för att presentera dokumenthanteringsfilerna i den
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Klicka på Reporting configurations.
3. Expandera "Customer invoice model" i trädet.
4. Välj "Customer invoice model\Customer invoice model (custom)" i trädet.
5. Klicka på Designer.
6. Välj "Customer invoice(InvoiceCustomer)" i trädet.
    * Vi vill utöka den här datamodell till blottan i den vissa filer som har kopplats till en försäljningsorder, som gäller bearbeta en faktura elektroniskt.  
7. Klicka på Nytt om du vill öppna dialogrutan.
8. Ange "Invoice attachments" i namnfältet.
    * Fakturabilagor  
9. Välj "Postlista" i fältet Artikeltyp.
10. Klicka på Lägg till.
11. Klicka på Nytt om du vill öppna dialogrutan.
12. Ange "File content" i namnfältet.
    * Filinnehåll  
13. Välj "Container" i fältet Item type.
14. Klicka på Lägg till.
15. Klicka på Nytt om du vill öppna dialogrutan.
16. Ange "File name" i namnfältet.
    * Filnamn  
17. Välj "Sträng" i fältet Artikeltyp.
18. Klicka på Lägg till.

## <a name="map-new-data-model-elements-to-data-sources"></a>Mappa nya datamodellelement till datakällor
1. Klicka på Mappa modell till datakälla.
2. Använd snabbfiltret (Quick Filter) för att filtrera fältet Definition med värdet "InvoiceCustomer".
    * InvoiceCustomer  
    * Vi skapar nya modellelement till lämpliga datakällor.  
3. Klicka på Designer.
4. Välj "Invoice attachments" i trädet.
5. Expandera "Invoice attachments" i trädet.
6. Välj "Invoice attachments\File name" i trädet.
7. Klicka på Redigera.
8. Ange "CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()" i fromelfältet.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'  
9. Klicka på Spara.
10. Stäng sidan.
11. Välj "Invoice attachments\File content" i trädet.
12. Klicka på Redigera.
13. Ange 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'' i formelfältet.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'  
14. Klicka på Spara.
15. Stäng sidan.
16. Välj "Invoice attachments" i trädet.
17. Klicka på Redigera.
18. Ange 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'' i formelfältet.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'  
19. Klicka på Spara.
20. Stäng sidan.
21. Klicka på Spara.
22. Stäng sidan.
23. Stäng sidan.
24. Stäng sidan.
25. Klicka på Ändra status.
26. Klicka på Slutför.
27. Klicka på OK.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]