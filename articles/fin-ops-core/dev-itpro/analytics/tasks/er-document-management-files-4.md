---
title: ER Använd dokumenthanteringsfiler i formatutmatningar (Del 4 - Kör format)
description: I den här artikeln beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat för användning av dokumenthanteringsfiler i ER-utdata. (Del 4)
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
ms.openlocfilehash: 3d4e26d15ea287c99cac85bf383e09c15729d37a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290977"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a>ER Använd dokumenthanteringsfiler i formatutmatningar (Del 4 - Kör format)

[!include [banner](../../includes/banner.md)]

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
    * Granska den genererade utleveransen. Notera att en enda XML-nod skapas för respektive bilaga. Bilagans innehåll fylls i textformatet för XML-utleverans i MIME (base64).  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
