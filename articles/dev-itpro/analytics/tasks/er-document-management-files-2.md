--- 
title: "Utöka en datamodell som ska använda dokumenthanteringsfiler i formatutdata för elektronisk rapportering (ER)"
description: "I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar."
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
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: ebbd442c9f69290dc995c05462ca70b554f7d9f2
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---
# <a name="extend-data-model-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a>Utöka en datamodell som ska använda dokumenthanteringsfiler i formatutdata för elektronisk rapportering (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

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

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-data-sources"></a>Mappa nya datamodellelement till datakällor i Dynamics 365 for Finance and Operations.
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


