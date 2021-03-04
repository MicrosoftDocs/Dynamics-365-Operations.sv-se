---
title: " Skapa kundtjänstorder"
description: Den här proceduren går igenom hur du söker efter en kund, skapar en ny order, söker efter en produkt och tar emot betalningen från kunden.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRCustomerService, SalesTable, MCRSourceIdTargetLookup, MCRSalesQuickQuote, MCRSalesOrderRecap, MCRCustPaymDialog, MCRCustPaymLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c875eaa85d9da997b75b296ad9ace99ae1e91798
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594246"
---
# <a name="create-call-center-orders"></a> Skapa kundtjänstorder

[!include [banner](../includes/banner.md)]

Den här proceduren går igenom hur du söker efter en kund, skapar en ny order, söker efter en produkt och tar emot betalningen från kunden. I den här proceduren används demonstrationsdataföretaget USRT och är avsedd för Försäljningsorderansvarig. Förutsättningar: Användaren som utför proceduren ställs in som kundtjänstanvändare och halvårsutgåvan av Fabrikam-katalogen publiceras med minst en källkod på den.

1. Gå till **Butik och handel \> Kunder \> Kundtjänst**.
2. För **Söktext**, ange sökkriterierna för att hitta kunden.
    * För den här exempelproceduren, skriv ”karen” och tryck på **flik**.  
3. Välj Sök.
    * Eftersom det bara finns en kund med namnet Karen i demodata, kommer resultatet automatiskt markeras.  
4. Välj **Ny försäljningsorder**.
5. Expandera eller komprimera avsnittet **Försäljningsorderhuvud**.
6. Välj källkoden för katalogen.
    * Om det inte finns några aktiva källkoder kan du hoppa över det här steget.  
7. Välj **Markera rad**.
8. För **Artikelnummer** ange artikelsöktermen.
    * För den här exempelproceduren, ange ett delvis artikelnummer 8111 och tryck på fliken. Denna åtgärd öppnar artikelsökningsfönstret.  
9. Välj produkten att lägga till försäljningsordern.
10. Ange försäljningskvantiteten.
11. Markera **Skapa**.
12. Klicka på **Slutför** för att registrera kundbetalningen.
13. Markera **Lägg till**.
    * Lägg till länk finns på betalningsfliken. Expandera fliken Betalning om den är komprimerad.  
14. Välj betalningsmetod.
    * Välj betalningsmetoden kontant för den här proceduren.  
15. Stäng sidan.
16. Ange belopp.
    * För den här proceduren, ange ett belopp lika med ordersaldot som kan visas på sammanfattningssidan för försäljningsorder till vänster om beloppsfältet. Denna åtgärd gör att du slutför ordern som helt betald.  
17. Välj **OK**.
18. Välj **skicka**.

## <a name="additional-resources"></a>Ytterligare resurser

[Anpassa transaktionsmeddelanden via e-post efter leveranssätt](../customize-email-delivery-mode.md)

[Ändra leveranssätt i kassan](../pos-change-delivery-mode.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]