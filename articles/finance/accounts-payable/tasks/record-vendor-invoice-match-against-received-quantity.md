---
title: Registrera leverantörsfakturan och matcha mot mottagen kvantitet
description: När du får en faktura från en leverantör för varor eller tjänster på en inköpsorder kanske affärsprocesserna kräver att varorna eller tjänsterna inlevereras innan fakturan godkänns för betalning.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: debf8ca47666252633e67e2592acd5a4e4122403
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778696"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a>Registrera leverantörsfakturan och matcha mot mottagen kvantitet

[!include [banner](../../includes/banner.md)]

När du får en faktura från en leverantör för varor eller tjänster på en inköpsorder kanske affärsprocesserna kräver att varorna eller tjänsterna inlevereras innan fakturan godkänns för betalning. Innan du börjar kontrollerar du att konfigurationsnyckeln för fakturamatchning har valts. 

På sidan med **leverantörsreskontraparametrarna** kontrollerar du att alternativet **Aktivera fakturamatchningsvalidering** har valts, fältet **Bokför faktura med avvikelser** har ställts in som **Begär godkännande** och fältet **Radmatchningspolicy** har ställts in som **Trevägsmatchning**.

I den här proceduren används demonstrationsföretaget USMF. Leverantörsreskontrachefsrollen eller redovisningschefsrollen ska utföra stegen nedan.


## <a name="create-a-purchase-order"></a>Skapa en inköpsorder
1. Gå till **Alla inköpsorder**.
2. Klicka på **Ny**.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Leverantörskonto**.
4. I fältet **Leverantörskonto**, skriv ett värde.
5. Klicka på **OK**.
6. Klicka på **Lägg till rad**.
7. I fältet **Artikelnummer**, skriv ett värde.
8. I åtgärdsrutan, klicka på **Köp**.
9. Klicka på **Bekräfta**.

## <a name="post-a-product-receipt"></a>Bokför en produktinleverans
1. I åtgärdsrutan, klicka på **Ta emot**.
2. Klicka på **Produktinleverans**.
3. Markera vald rad i listan.
4. I fältet **Produktinleverans**, skriv ett värde.
5. Klicka på **OK**.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Registrera och matcha en leverantörsfaktura mot en produktinleverans
1. I åtgärdsrutan, klicka på **Faktura**.
2. Klicka på **faktura**.
3. I fältet **Antal**, skriv ett värde.
4. Klicka på **Standard från: Beställd kvantitet** för att öppna dialogrutan.
5. I fältet **Standardkvantitet för rader**, välj ett alternativ.
6. Klicka på **OK**.
7. Klicka på **Ja**.
8. Klicka på **Matcha produktinleveranser**.
9. Klicka på **OK**.
10. Klicka på **Granska** i åtgärdsrutan.
11. Klicka på **Matcha detaljer**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
