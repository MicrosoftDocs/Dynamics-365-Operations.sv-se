--- 
title: Granska fakturor och nyckeldata i LR-system
description: "När du får en faktura från en leverantör för varor eller tjänster på en inköpsorder kanske affärsprocesserna kräver att varorna eller tjänsterna inlevereras innan fakturan godkänns för betalning."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 70a7a1f7d7a8221a72addfbee1d21f813df4eb46
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="audit-invoices-and-key-data-in-ap-system"></a>Granska fakturor och nyckeldata i LR-system

[!include [task guide banner](../../includes/task-guide-banner.md)]

När du får en faktura från en leverantör för varor eller tjänster på en inköpsorder kanske affärsprocesserna kräver att varorna eller tjänsterna inlevereras innan fakturan godkänns för betalning. Innan du börjar kontrollerar du att konfigurationsnyckeln för fakturamatchning har valts. 

På sidan med leverantörsreskontraparametrarna kontrollerar du att alternativet Aktivera fakturamatchningsvalidering har valts, fältet Bokför faktura med avvikelser har ställts in som Begär godkännande och fältet Radmatchningspolicy har ställts in som Trevägsmatchning.

I den här proceduren används demonstrationsföretaget USMF. Leverantörsreskontrachefsrollen eller redovisningschefsrollen ska utföra stegen nedan.


## <a name="create-a-purchase-order"></a>Skapa en inköpsorder
1. Gå till Alla inköpsorder.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.
4. Ange ett värde i fältet Leverantörskonto.
5. Klicka på OK.
6. Klicka på Lägg till rad.
7. Skriv ett värde i fältet Artikelnummer.
8. Klicka på Inköp i åtgärdsfönstret.
9. Klicka på Bekräfta.

## <a name="post-a-product-receipt"></a>Bokför en produktinleverans
1. Klicka på Ta emot i åtgärdsfönstret.
2. Klicka på Produktinleverans.
3. Markera vald rad i listan.
4. Skriv ett värde i fältet Produktinleverans.
5. Klicka på OK.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Registrera och matcha en leverantörsfaktura mot en produktinleverans
1. Klicka på Faktura i åtgärdsfönstret.
2. Klicka på Faktura.
3. Ange ett värde i fältet Antal.
4. Klicka på Standard från: Beställd kvantitet för att öppna dialogrutan.
5. I fältet Standardkvantitet för rader, välj ett alternativ.
6. Klicka på OK.
7. Klicka på Ja.
8. Klicka på Matcha produktinleveranser.
9. Klicka på OK.
10. Klicka på Granska i åtgärdsfönstret.
11. Klicka på Matcha detaljer.


