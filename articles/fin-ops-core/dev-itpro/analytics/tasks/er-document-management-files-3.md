---
title: ER Använd dokumenthanteringsfiler i formatutmatningar (Del 3 - Skapa format)
description: I det här avsnittet beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat för användning av dokumenthanteringsfiler i ER-utdata. (Del 3)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0cb052e2895cd0eb7f5c3bea9f33d988ef54dfb11e2e31c4212706b7fdaada79
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766395"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a>ER Använd dokumenthanteringsfiler i formatutmatningar (Del 3 - Skapa format)

[!include [banner](../../includes/banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar. Dessa steg kan utföras på valfritt företag.

För att slutföra dessa steg måste du först avsluta stegen i proceduren "ER Use Document Management files in format outputs (Part 2: Extend data model".

Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="create-a-format-to-process-invoices"></a>Skapa ett format för att bearbeta fakturor
1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Klicka på Reporting configurations.
3. Expandera "Customer invoice model" i trädet.
4. Välj "Customer invoice model\Customer invoice model (custom)" i trädet.
    * Du kan skapa ett format för att skapa elektroniska meddelanden med information om de filer som har kopplats till en försäljningsorder och som gäller en faktura för elektronisk bearbetning.  
5. Klicka på Skapa konfiguration om du vill öppna dialogrutan.
6. Ange "Format based on data model Customer invoice model (custom)" i fältet New.
7. Ange "Electronic invoice sample message" i namnfältet.
    * Provmeddelande för elektronisk faktura  
8. Ange eller välj ett värde i fältet Data model definition.
    * InvoiceCustomer  
9. Klicka på Skapa konfiguration.

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a>Utforma ett format för att fylla i bilagor så att dessa skapar meddelanden i MIME-format
1. Klicka på Designer.
2. Klicka på Lägg till rot för att öppna dialogrutan.
3. Välj "XML\Element" i trädet.
4. Ange "Invoice" i namnfältet.
    * Faktura  
5. Klicka på OK.
6. Klicka på Lägg till för att öppna dialogrutan.
7. Välj "XML\Attribut" i trädet.
8. Ange "SalesOrder" i namnfältet.
    * SalesOrder  
9. Klicka på OK.
10. Klicka på Add Attribute.
11. Ange "InvoiceNumber" i namnfältet.
    * InvoiceNumber  
12. Klicka på OK.
13. Klicka på Add Attribute.
14. Ange "InvoiceAmount" i namnfältet.
    * InvoiceAmount  
15. Klicka på OK.
16. Klicka på Lägg till för att öppna dialogrutan.
17. Välj "XML\Element" i trädet.
18. Ange "EnclosedDocs" i namnfältet.
    * EnclosedDocs  
19. Klicka på OK.
20. Välj "Invoice\EnclosedDocs" i trädet.
21. Klicka på Add Element.
22. Ange "Document" i namnfältet.
    * Dokument  
23. Klicka på OK.
24. Välj "Invoice\EnclosedDocs\Document" i trädet.
25. Klicka på Lägg till för att öppna dialogrutan.
26. Välj "XML\Attribut" i trädet.
27. Ange "FileName" i namnfältet.
    * FileName  
28. Klicka på OK.
29. Klicka på Lägg till för att öppna dialogrutan.
30. Välj "XML\Element" i trädet.
31. Ange "FileContent" i namnfältet.
    * FileContent  
32. Klicka på OK.
33. Välj "Invoice\EnclosedDocs\Document\FileContent" i trädet.
34. Klicka på Lägg till för att öppna dialogrutan.
35. Välj "Text\Base64" i trädet.
36. Klicka på OK.

## <a name="map-format-elements-to-data-model-as-data-source"></a>Mappa formatelement till datamodeller som datakällor
1. Välj "Invoice\SalesOrder" i trädet.
2. Klicka på fliken Mappning.
3. Expandera "modell" i trädet.
4. Välj "model\Sales order number(SalesId)" i trädet.
5. Klicka på Bind.
6. Välj "Invoice\InvoiceNumber" i trädet.
7. Expandera "model\Base invoice(InvoiceBase)" i trädet.
8. Välj "model\Base invoice(InvoiceBase)\Invoice number(Id)" i trädet.
9. Klicka på Bind.
10. Välj "Invoice\InvoiceAmount" i trädet.
11. Välj "model\Base invoice(InvoiceBase)\Invoice amount(Amount)" i trädet.
12. Klicka på Bind.
13. Expandera "model\Invoice attachments" i trädet.
14. Välj "model\Invoice attachments\File content" i trädet.
15. Välj "Invoice\EnclosedDocs\Document\FileContent\Base64" i trädet.
16. Klicka på Bind.
17. Välj "model\Invoice attachments\File name" i trädet.
18. Välj "Invoice\EnclosedDocs\Document\FileName" i trädet.
19. Klicka på Bind.
20. Välj "model\Invoice attachments" i trädet.
21. Välj "Invoice\EnclosedDocs\Document" i trädet.
22. Klicka på Bind.
23. Klicka på Spara.
24. Stäng sidan.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]