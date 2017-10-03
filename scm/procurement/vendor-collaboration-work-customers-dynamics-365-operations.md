---
title: "Leverantörssamarbete med kunder"
description: "I det här avsnittet beskrivs hur du kan använda leverantörssamarbete i Finance and Operations för att arbeta med inköpsorder och övervaka försändelselager."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ConsignmentProductReceiptLines, ConsignmentVendorPortalOnHand, PurchVendorPortalConfirmedOrders, PurchVendorPortalOriginalOrder, PurchVendorPortalResponsesHistoryList, PurchVendorPortalResponsesPart
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221234
ms.assetid: 6e69fb8b-6d3a-46ef-88cf-6d01212aa7c3
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 41436dab710a5fee0fe0800dff1ebefefa841afc
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="vendor-collaboration-with-customers"></a>Leverantörssamarbete med kunder

[!include[banner](../includes/banner.md)]


I det här avsnittet beskrivs hur du kan använda leverantörssamarbete i Finance and Operations för att arbeta med inköpsorder och övervaka försändelselager.

I det här avsnittet beskrivs hur du kan använda leverantörssamarbete när du arbetar med kunder i Microsoft Finance and Operations. Det innehåller information om hur du övervakar och svarar på inköpsorder och hur du övervakar försändelselager. Det går också att använda leverantörsamarbete för att arbeta med fakturor. Mer information finns i [Arbetsyta för leverantörssamarbetesfakturering](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace).

## <a name="working-with-purchase-orders"></a>Arbeta med inköpsorder
Arbetsyten **Inköpsorderbekräftelse** låter dig besvara de insköpsorder som har skickats till dig för granskning. Den låter dig också visa information om inköpsorder som inväntar åtgärd från kunden, samt inköpsorder som har bekräftats men som fortfarande är öppna.. Det finns tre listor i arbetsytan **Inköpsorderbekräftelse**:

-   **Inköpsorder för granskning** - Denna lista visas inköpsorder som har skickats till dig och som inväntar ett svar från dig. När du har svarat tas inköpsordern bort från listan. Om kunden skickar dig en ny version av inköpsordern innan du har svarat på föregående, visas bara den senaste versionen.
-   **Inväntar kundåtgärd -** - Den här listan låter dig se inköpsorder som du har svarat på, men som ännu inte har bekräftats av kunden. Om du godkände inköpsordern kan du övervaka den i den här listan, tills dess att statusen ändras till **Bekräftat**. Om du avvisade inköpsordern eller godkände den med ändringar, kan du övervaka inköpsordern här tills kunden skickar en ny version.
-   **Öppna bekräftade inköpsorder** - Denna innehåller alla inköpsorder för kontot som har statusen **Bekräftat**. När produkter eller tjänster har inlevererats helt mot inköpsordern, försvinner inköpsordern från listan.

Följande lista visar de fyra sidor som du kan använda när du arbetar med inköpsorder, varav två innehåller samma information som listorna i arbetsytan:

-   **Inköpsorder för granskning** (se ovan)
-   **Bekräftelsehistorik för inköpsorderleverantör** - Denna sida innehåller alla inköpsorder och samtliga versioner av inköpsorder som har skickats till leverantören, samt alla svar som har returnerats från leverantören.
-   **Öppna bekräftade inköpsorder** (se ovan)
-   **Alla bekräftade inköpsorder** - Denna sida innehåller alla inköpsorder som har bekräftats, inklusive de där produkter eller tjänster har mottagits. Via denna lista kan du övervaka inköpsorder som du kan skicka fakturor för.

### <a name="responding-to-purchase-orders"></a>Besvara inköpsorder.

Inköpsordern som kunden har skickat dig att granska visas på arbetsytan **Inköpsorderbekräftelse** och på sidan **Inköpsorder för granskning**. När du har öppnat en inköpsorder kan du godkänna, avvisa eller acceptera ändringarna. Det kan finnas bilagor inköpsorderhuvudet eller på enskilda rader. Du kan även bifoga information för ditt svar på inköpsorderhuvudet eller på enskilda rader. Du kan till exempel föreslå en reservartikel för en av raderna. Du kan granska och skriva ut inköpsordern som en PDF-fil genom att använda alternativet **Förhandsgranska/Skriv ut**. Du kan dölja eller visa följande dimensionskolumner med hjälp av åtgärden **Visa dimensioner**: Plats, Lagerställe, Färg, Storlek, Stil, Konfiguration. Om du använder alternativet **Acceptera ändringar** kan du godkänna eller avvisa enskilda rader. Du kan även göra följande ändringar på rader:

-   Ändra datum eller kvantiteter. Om du vill uppdatera det bekräftade leveransdatumet på alla rader, använd alternativet **Uppdatera leveransdatum** i inköpsorderhuvudet.
-   Dela rader för andra leveransdatum eller kvantiteter
-   Byt ut en artikel. För att gör detta, ange en artikelbeskrivning samt ditt artikelnummer i avsnittet **Extern** field in the **Radinformation**.

Du kan inte ändra prissättningsinformation eller avgifter, men du kan göra ändringar i förslag för dessa genom anteckningar. Om din kund skickar dig en ny version av en inköpsorder, kommer denna att bära ett versionstillägg som visar att den är en modifierad version av en inköpsorder som tidigare meddelats. Sidan **Bekräftelsehistorik för inköpsorderleverantör** låter dig spåra historiken för respektive order.

## <a name="monitoring-consignment-inventory"></a>Övervaka försändelselager
Om du använder försändelselager kan du använda gränssnittet för leverantörssamarbete för att visa information på följande sidor:

-   **Inköpsorder som förbrukar försändelselager** - Inköpsorder för försändelselager skapas när kunden tar över ägarskapet för lagret. Dessa försändelseinköpsorder visas bara på sidan **Inköpsorder som förbrukar försändelselager**. Alla inkluderas in på sidan **Alla bekräftade inköpsorder**.
-   **Mottagna produkter från försändelselager** - Den här sidan visar alla transaktioner där ägarskapet för produkter har överförts till det företag som har förbrukat lagret. Du kan använda den här informationen för att fakturera kunden.
-   **Behållning i försändelselager** - Den här sidan visar det tillgängliga försändelselager som ägs av ditt företag och som är tillgängligt i kundens lager.


<a name="see-also"></a>Se även
--------

[Hantera leverantörssamarbetesanvändare](manage-vendor-collaboration-users.md)




