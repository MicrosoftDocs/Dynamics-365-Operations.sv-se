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
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 08a806514a92a99a9f0b18b36817f49a09516ab8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964855"
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
    * Välj betalsättet kontant för den här proceduren.  
15. Stäng sidan.
16. Ange belopp.
    * För den här proceduren, ange ett belopp lika med ordersaldot som kan visas på sammanfattningssidan för försäljningsorder till vänster om beloppsfältet. Denna åtgärd gör att du slutför ordern som helt betald.  
17. Välj **OK**.
18. Välj **skicka**.

## <a name="additional-resources"></a>Ytterligare resurser

[Anpassa transaktionsmeddelanden via e-post efter leveranssätt](../customize-email-delivery-mode.md)

[Ändra leveranssätt i POS](../pos-change-delivery-mode.md)

