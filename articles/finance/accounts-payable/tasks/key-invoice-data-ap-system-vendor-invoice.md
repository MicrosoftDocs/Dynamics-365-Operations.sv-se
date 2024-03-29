---
title: Huvudfakturadata i AP med hjälp av leverantörsfakturan
description: Med den här guiden blir det enklare att skapa en leverantörsfaktura från en inköpsorder och visa resultaten för att matcha inköpsordern, inleverans och fakturan (trevägsmatchning).
author: abruer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4c441d197957674d68c4c92b454a9dca91d76ea0
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775200"
---
# <a name="key-invoice-data-in-ap-using-a-vendor-invoice"></a>Huvudfakturadata i AP med hjälp av leverantörsfakturan

[!include [banner](../../includes/banner.md)]

Med den här guiden blir det enklare att skapa en leverantörsfaktura från en inköpsorder och visa resultaten för att matcha inköpsordern, inleverans och fakturan (trevägsmatchning).


## <a name="create-a-purchase-order"></a>Skapa en inköpsorder
1. I navigeringsfönstret går du till **moduler > leverantörsreskontra > inköpsorder > alla inköpsorder**.
2. Klicka på **Ny**.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Leverantörskonto**.
4. Sök efter en leverantör att välja. Rulla nedåt till US-104, till exempel.
5. Välj leverantör US-104.
6. Klicka på **OK**.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelnummer**.
8. Välj en lagerartikel. I det här exemplet väljer du artikelnummer 1000.
9. Visa snabbfliken **Radinformation**.
10. Klicka på fliken **Inställningar** Du kan åsidosätta matchningspolicyn om du vill använda ingen matchning, tvåvägsmatchning eller trevägsmatchning.  
11. I åtgärdsrutan, klicka på **Köp**.
12. Klicka på **Bekräfta**.

## <a name="receive-the-products"></a>Ta emot produkterna
1. I åtgärdsrutan, klicka på **Ta emot**.
2. Klicka på **Produktinleverans**.
3. Ange produktinleveransnumret i fältet **Produktinleverans**. Ange exempelvis PR123.
4. Klicka på **OK** när du vill bokföra produktinleveransen.
5. Stäng sidan.

## <a name="create-a-vendor-invoice"></a>Skapa en leverantörsfaktura
1. I navigeringsfönstret går du till **moduler > leverantörsreskontra > inköpsorder > inköpsorder har inlevererats men inte fakturerats**.
2. Välj inköpsordern som du skapat.
3. I åtgärdsrutan, klicka på **Faktura**.
4. Klicka på **faktura**.
5. Ange fakturanumret i fältet **Nummer**.
6. Ange ett värde i fältet **Fakturabeskrivning**.
7. Ange ett datum i fältet **Fakturadatum**.
8. Ange 1200 i fältet **Enhetspris**.
9. Klicka på **Lägg till rad**.
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Artikelnummer**.
11. Sök efter artikelnumret med installationavgiften i listan. Till exempel S0001
12. Välj artikelnumret med installationavgiften. Notera att matchning inte har utförts sedan du utförde ändringarna.  
13. Klicka på **Uppdatera matchningsstatus**.
14. Klicka på **Granska** i åtgärdsrutan.
15. Klicka på **Matcha detaljer**. Den nya raden med tjänster behöver inte matchas, så statusen är fortfarande ”Inte utförd”.  
16. Välj produktinleveransen för lagerartikeln som du har fått. Raden med produktinleveransen matchades, men det fanns en felmatchning av kvantiteten eller priset, så den misslyckades.  
17. Ange ett tal i fältet **Enhetspris**. När nu priset per enhet matchar, uppdateras statusvärdet till Godkänt. Om din policy tillåter avvikelser, eller om matchningen bara är en varning, kan du fortfarande bokföra fakturan.  
18. Stäng sidan.
19. Klicka på **Bokför**.
20. Stäng sidan. 

>[!Note] 
>Inköpsordern inte längre registreras som mottagen men inte fakturerad.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
