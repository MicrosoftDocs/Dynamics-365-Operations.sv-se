---
title: ER Använd dokumenthanteringsfiler i formatutmatningar (Del 5 - ändra och kör format)
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 23e91b6aee62157da9141cc7b6c4fae39c19ce32
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544689"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5-modify-and-run-format"></a>ER Använd dokumenthanteringsfiler i formatutmatningar (Del 5: ändra och kör format)

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar. Dessa steg kan utföras i DEMF-företaget.

För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use Document Management files in format outputs (Part 4): Run format".

Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a>Ändra formatet för att fylla i bilagor så att dessa skapar meddelanden i binärt format
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Expandera "Customer invoice model" i trädet.
3. Expandera "Customer invoice model\Customer invoice model (custom)" i trädet.
4. I trädet väljer du "Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message".
5. Klicka på Designer.
    * Du fyller i fakturameddelandet i skapad utmatning som en XML-fil med hjälp av UNICODE-kodning.  
6. Klicka på Lägg till rot för att öppna dialogrutan.
7. Välj "Allmänt\Fil" i trädet.
8. Ange "Xml message" i namnfältet.
    * Xml-meddelande  
9. Skriv "UTF 8" i fältet Kodning.
    * UTF-8  
10. Klicka på OK.
    * Konfigurera de skapade utmatningen som en zippad fil.  
11. Klicka på Lägg till rot för att öppna dialogrutan.
12. Välj "Common\Folder" i trädet.
13. Ange "Zip output" i namnfältet.
    * Zip-utleverans  
14. Klicka på OK.
15. Välj "Zip output" i trädet.
    * Lägg till bilagor till den skapade, zippade filen som filer med ursprungliga namn och filtillägg.  
16. Klicka på Lägg till för att öppna dialogrutan.
17. Välj "Allmänt\Fil" i trädet.
18. Ange "Attached file" i namnfältet.
    * Bifogad fil  
19. Klicka på OK.
20. Välj "Zip output\Attached file" i trädet.
21. Klicka på Lägg till för att öppna dialogrutan.
22. Välj "Text\Base64" i trädet.
23. Klicka på OK.

## <a name="map-new-format-elements-to-data-model"></a>Mappa nya formatelement till datamodell
1. Klicka på fliken Mappning.
2. Expandera "modell" i trädet.
3. Expandera "model\Invoice attachments" i trädet.
4. Välj "Zip output\Attached file\Base64" i trädet.
5. Välj "model\Invoice attachments\File content" i trädet.
6. Klicka på Bind.
7. Välj "Zip output\Attached file" i trädet.
8. Klick på Edit filename.
9. Expandera "modell" i trädet.
10. Expandera "model\Invoice attachments" i trädet.
11. Välj "model\Invoice attachments\File name" i trädet.
12. Klicka på Lägg till datakälla.
13. Klicka på Spara.
14. Stäng sidan.
15. Välj "model\Invoice attachments" i trädet.
16. Klicka på Bind.
17. Klicka på Spara.
18. Stäng sidan.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>Kör den tidsplanerade rapporten för den valda fakturan
1. Klicka på Kör.
2. Expandera avsnittet Records to include ().
3. Klicka på Filter.
4. Markera raden för kundfakturajournalen och fältet Sales order.
5. Ange ordernummer "000148" i fältet Criteria, i kriteriefältet "Sales order".
    * 000148  
6. Klicka på OK.
7. Klicka på OK.
    * Granska den genererade utleveransen. Notera att: Utöver fakturameddelandet i XML-format har en enda fil skapats för respektive bilaga. Bilagefilerna fylls i med den zippade utmatningen i binärt format.  

