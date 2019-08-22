---
title: Huvudfakturadata i AP-system med hjälp av godkännandejournal
description: Den här uppgifthandboken visas hur du använder fakturaregister om du vill skapa fakturor och sedan använda godkännandejournalen för att uppdatera utgiftskontona.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0faece510cc85fd86113d8b62d54b71f3014b1db
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837059"
---
# <a name="key-invoice-data-into-ap-system-using-approval-journal"></a>Huvudfakturadata i AP-system med hjälp av godkännandejournal

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgifthandboken visas hur du använder fakturaregister om du vill skapa fakturor och sedan använda godkännandejournalen för att uppdatera utgiftskontona.


## <a name="create-and-post-and-invoice"></a>Skapa och bokför och fakturera
1. Gå till Leverantörsreskontra > Fakturor > Fakturaregister.
2. Klicka på Ny.
3. Välj namnet på det fakturaregister som du vill använda.
4. Klicka på länken på den valda raden i listan.
5. Klicka på på Rader om du vill öppna registret och ange utgiftsrader.
6. Välj en leverantör. Ange eller välj US-104, till exempel
7. Ange ett värde i fältet Faktura.
8. Skriv ett värde i fältet Beskrivning.
9. Välj ett tal i fältet Kredit.
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Godkänt av.
11. Välj en godkännare och klicka sedan på Välj om du vill välja den godkännaren.
12. Klicka på Bokför.
13. Stäng sidan.
14. Stäng sidan.

## <a name="approve-an-invoice"></a>Godkänn en faktura
1. Gå till Leverantörsreskontra > Fakturor > Fakturagodkännande.
2. Klicka på Ny.
3. Välj namnet på fakturagodkännandejournalen som du vill använda.
4. Klicka på länken på den valda raden i listan.
5. Klicka på Rader om du vill visa en sida där du kommer att vara i stånd till att välja fakturorna, som du vill godkänna.
6. Välj Sök efter verifikationer om du vill visa alla fakturor som är klara för godkännande.
7. Välj den faktura som du själv har skapat.
8. Klicka på Välj.
    * Verifikationerna, som du valde ovan, flyttas till listan när du har markerat dem.  
9. Klicka på OK.
10. Klicka på kontonummerfältet om du vill lägga till ett utgiftskonto i fakturan.
11. Ange ett kontonummer och gå till nästa fält. Ange exempelvis 600120.
12. Klicka på Bokför.
13. Klicka på verifikationen om du vill visa poster som bokfördes.
    * Kontot för godkännande av pågående fakturor motbokas och ersätts med det verkliga utgiftskontot.  

