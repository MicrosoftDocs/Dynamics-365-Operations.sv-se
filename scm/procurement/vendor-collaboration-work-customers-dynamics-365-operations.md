---
title: "Leverantörssamarbete med kunder"
description: "I det här avsnittet beskrivs hur du kan använda leverantörssamarbeten för att arbeta med inköpsorder och övervaka försändelselager i Microsoft Dynamics 365 for Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 11cd2242b5a575ae87b0dbcf6f8ce268fcea5377
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-collaboration-with-customers"></a>Leverantörssamarbete med kunder

I det här avsnittet beskrivs hur du kan använda leverantörssamarbeten för att arbeta med inköpsorder och övervaka försändelselager i Microsoft Dynamics 365 for Operations.

I det här avsnittet beskrivs hur du kan använda leverantörssamarbete när du arbetar med kunder i Microsoft Dynamics 365 for Operations. Den innehåller information om hur du övervakar och svara på inköpsorder och hur du övervakar försändelse lager. Det går också att använda leverantör samarbete för att arbeta med fakturor. Mer information finns i [leverantör samarbete fakturering arbetsytan](/dynamics365/operations/financials/accounts-payable/vendor-portal-invoicing-workspace).

## <a name="working-with-purchase-orders"></a>Arbeta med inköpsorder
Arbetsyten **Inköpsorderbekräftelse** låter dig besvara de insköpsorder som har skickats till dig för granskning. Den låter dig också visa information om inköpsorder som inväntar åtgärd från kunden, samt inköpsorder som har bekräftats men som fortfarande är öppna.. Det finns tre listor i arbetsytan **Inköpsorderbekräftelse**:

-   **Inköpsorder för granskning** -visar listan POs som har skickats till dig och väntar på ett svar från dig. När du har svarat Inköpsordern tas bort från listan. Om kunden skickar dig en ny version av inköpsordern innan du har svarat på föregående, visas bara den senaste versionen.
-   **Inväntar kundåtgärd -** - Den här listan låter dig se inköpsorder som du har svarat på, men som ännu inte har bekräftats av kunden. Om du godkände inköpsordern kan du övervaka den i den här listan, tills dess att statusen ändras till **Confirmed**. Om du avvisade inköpsordern eller godkände den med ändringar, kan du övervaka inköpsordern här tills kunden skickar en ny version.
-   **Open confirmed purchase orders** - Denna innehåller alla inköpsorder för kontot som har statusen **Confirmed**. När produkter eller tjänster har inlevererats helt mot inköpsordern, försvinner inköpsordern från listan.

Följande lista visar de fyra sidor som du kan använda när du arbetar med inköpsorder, varav två innehåller samma information som listorna i arbetsytan:

-   **Purchase orders for review** (se ovan)
-   **Purchase order vendor confirmation history** - Denna sida innehåller alla inköpsorder och samtliga versioner av inköpsorder som har skickats till leverantören, samt alla svar som har returnerats från leverantören.
-   **Open confirmed purchase orders** (se ovan)
-   **All confirmed purchase orders** - Denna sida innehåller alla inköpsorder som har bekräftats, inklusive de där produkter eller tjänster har mottagits. Via denna lista kan du övervaka inköpsorder som du kan skicka fakturor för.

### <a name="responding-to-purchase-orders"></a>Besvara inköpsorder.

Inköpsorder som kunden har skickat dig att granska syns i den **inköpsorderbekräftelsen** arbetsytan och på den **inköpsorder för granskning** sida. När du har öppnat en inköpsorder kan du godkänna, avvisa eller accepterar ändringarna. Det kan finnas bilagor inköpsorderhuvudet eller på enskilda rader. Du kan även bifoga information för ditt svar på inköpsorderhuvudet eller på enskilda rader. Du kan till exempel föreslå en reservartikel för en av raderna. Du kan granska och skriva ut inköpsordern som en PDF-fil genom att använda alternativet **Preview/Print**. Du kan dölja eller visa följande dimensionskolumner med hjälp av åtgärden **Display dimensions**: Site, Warehouse, Color, Size, Style, Configuration. Om du använder den **acceptera ändringar** alternativ, Godkänn eller avvisa för enskilda rader. Du kan också göra följande ändringar i rader:

-   Ändra datum eller kvantiteter. Om du vill uppdatera det bekräftade leveransdatumet på alla rader, använd alternativet **Update delivery date** i inköpsorderhuvudet.
-   Dela rader för andra leveransdatum eller kvantiteter
-   Byt ut en artikel. För att gör detta, ange en artikelbeskrivning samt ditt artikelnummer i avsnittet **External** field in the **Line details**.

Du kan inte ändra prissättningsinformation eller avgifter, men du kan göra ändringar i förslag för dessa genom anteckningar. Om din kund skickar dig en ny version av en inköpsorder, kommer denna att bära ett versionstillägg som visar att den är en modifierad version av en inköpsorder som tidigare meddelats. Sidan **Purchase order vendor confirmation history** låter dig spåra historiken för respektive order.

## <a name="monitoring-consignment-inventory"></a>Övervaka försändelselager
Om du använder försändelselager kan du använda gränssnittet för leverantörssamarbete för att visa information på följande sidor:

-   **Inköpsorder som förbrukar försändelse lagret** -inköpsorder för försändelse lager skapas när kunden ägarskapet till lagret. Dessa försändelseinköpsorder visas bara på sidan **Purchase orders consuming consignment inventory**. Alla inkluderas in på sidan **All confirmed purchase orders**.
-   **Products received from consignment inventory** - Den här sidan visar alla transaktioner där ägarskapet för produkter har överförts till det företag som har förbrukat lagret. Du kan använda den här informationen för att fakturera kunden.
-   **On-hand consignment inventory** - Den här sidan visar det tillgängliga försändelselager som ägs av ditt företag och som är tillgängligt i kundens lager.


<a name="see-also"></a>Se även
--------

[Hantera leverantörssamarbetesanvändare](manage-vendor-collaboration-users.md)

