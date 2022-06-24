---
title: Granska fakturor och nyckeldata i leverantörsreskontra
description: Den här artikeln visar hur du granskar fakturor och nyckeldata på leverantörskonton.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 76c45133091a86da773d7f63addd460abd92aae7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868370"
---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>Granska fakturor och nyckeldata i leverantörsreskontra

[!include [banner](../../includes/banner.md)]

När du får en faktura från en leverantör för varor eller tjänster på en inköpsorder kanske affärsprocesserna kräver att varorna eller tjänsterna inlevereras innan fakturan godkänns för betalning. Innan du börjar kontrollerar du att konfigurationsnyckeln för fakturamatchning har valts. 

På sidan med **leverantörsreskontraparametrarna** kontrollerar du att alternativet Aktivera fakturamatchningsvalidering har valts, fältet **Bokför faktura med avvikelser** har ställts in som **Begär godkännande** och fältet **Radmatchningspolicy** har ställts in som **Trevägsmatchning**.

I den här proceduren används demonstrationsföretaget USMF. Leverantörsreskontrachefsrollen eller redovisningschefsrollen ska utföra stegen nedan.


## <a name="create-a-purchase-order"></a>Skapa en inköpsorder
1. Gå till **Alla inköpsorder**.
2. Klicka på **Ny**.
3. I fältet **Leverantörskonto**, skriv ett värde.
4. Klicka på **OK**.
5. Klicka på **Lägg till rad**.
6. I fältet **Artikelnummer**, skriv ett värde.
7. I åtgärdsrutan, klicka på **Köp**.
8. Klicka på **Bekräfta**.

## <a name="post-a-product-receipt"></a>Bokför en produktinleverans
1. I åtgärdsrutan, klicka på **Ta emot**.
2. Klicka på **Produktinleverans**.
3. I fältet **Produktinleverans**, skriv ett värde.
4. Klicka på **OK**.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Registrera och matcha en leverantörsfaktura mot en produktinleverans
1. I åtgärdsrutan, klicka på **Faktura > Faktura**.
2. I fältet **Antal**, skriv ett värde.
3. Klicka på **Standard från: Beställd kvantitet** för att öppna dialogrutan.
4. I fältet **Standardkvantitet för rader**, välj ett alternativ.
5. Klicka på **OK**.
6. Klicka på **Ja**.
7. Klicka på **Matcha produktinleveranser**.
8. Klicka på **OK**.
9. Klicka på **Granska** i åtgärdsrutan.
10. Klicka på **Matcha detaljer**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
