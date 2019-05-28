---
title: Kör format som ska använda dokumenthanteringsfiler i ER-utdata
description: I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering för att använda dokumenthanteringsfiler i ER-utmatningar.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e87dbb0fa890f4d554c3e2ff09566fb2b1f3206b
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544824"
---
# <a name="run-formats-to-use-document-management-files-in-er-output"></a>Kör format som ska använda dokumenthanteringsfiler i ER-utdata

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera ett format för elektronisk rapportering (ER) för att använda dokumenthanteringsfiler (bilagor) i ER-utmatningar. Dessa steg kan utföras i DEMF-företaget.

För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use Document Management files in format outputs (Part 3: Create format)".

Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a>Lägg till nödvändiga bilagor för en försäljningsorder för en enstaka faktura
1. Gå till Kundreskontra > Fakturor > Öppna kundfakturor.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel fältet Invoice med värdet "CIV-000148".
    * CIV-000148  
3. Klicka för att följa vald fakturalänk.
    * CIV-000148  
4. Klicka för att följa länken i fältet Sales order.
    * 000148  
5. Välj alternativet Header i fältet Lines or header.
    * Markera Header om du vill ange att detta ska vara målet för att lägga till bilagor.  
6. Klicka på Koppla.
    * Lägga till några filer som bilagor för den här försäljningsordern. Använd filer av de dokumenttyper stöds av dokumenthanteringen (med filtilläggen DOCX, DPF, XML, JPG osv.). Bläddra och välj de filer som ska bifogas och bearbetas vidare med den relaterade fakturan i det elektroniska meddelandet ER.  
7. Klicka på Ny.
8. Klicka på Arkiv.
9. Klicka på Ny.
10. Klicka på Arkiv.
11. Stäng sidan.
12. Stäng sidan.
13. Stäng sidan.
14. Stäng sidan.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>Kör den tidsplanerade rapporten för den valda fakturan
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Expandera "Customer invoice model" i trädet.
3. Expandera "Customer invoice model\Customer invoice model (custom)" i trädet.
4. I trädet väljer du "Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message".
5. Klicka på Kör.
6. Expandera avsnittet Records to include ().
7. Klicka på Filter.
8. Markera raden för kundfakturajournalen och fältet Sales order.
9. Ange "000148" i fältet Criteria.
    * Ange ordernumret 000148 i kriteriefältet "Sales order".  
10. Klicka på OK.
11. Klicka på OK.
    * Granska den skapade utleveransen. Notera att en enda XML-nod skapas för respektive bilaga. Bilagans innehåll fylls i textformatet för XML-utleverans i MIME (base64).  

