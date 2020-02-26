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
ms.openlocfilehash: d1675d21f1e4176839feace76359afdbdc336c99
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3024066"
---
# <a name="create-call-center-orders"></a> Skapa kundtjänstorder

[!include[task guide banner](../includes/task-guide-banner.md)]

Den här proceduren går igenom hur du söker efter en kund, skapar en ny order, söker efter en produkt och tar emot betalningen från kunden. I den här proceduren används demonstrationsdataföretaget USRT och är avsedd för Försäljningsorderansvarig. Förutsättningar: Användaren som utför proceduren ställs in som kundtjänstanvändare och halvårsutgåvan av Fabrikam-katalogen publiceras med minst en källkod på den.

1. Gå till Butik och handel > Kunder > Kundtjänst.
2. I fältet Söktext, ange sökkriterierna för att hitta kunden.
    * För den här exempelproceduren, skriv ”karen” och tryck på fliken.  
3. Klicka på Sök.
    * Eftersom det bara finns en kund med namnet Karen i demodata, kommer de automatiskt markeras.  
4. Klicka på Ny försäljningsorder.
5. Expandera eller komprimera avsnittet Försäljningsorderhuvud.
6. Välj källkoden för katalogen.
    * Om det inte finns några aktiva källkoder kan du stänga källfältet och hoppa över det här steget.  
7. Klicka på Lägg till rad.
8. Ange artikelsöktermen i fältet Artikelnummer.
    * För den här exempelproceduren, ange ett delvis artikelnummer 8111 och tryck på fliken. Då poppar artikelsökningsfönstret upp.  
9. Välj produkten att lägga till försäljningsordern
10. Ange försäljningskvantiteten.
11. Klicka på Skapa.
12. Klicka på Slutför för att registrera kundbetalningen.
13. Klicka på Lägg till.
    * Lägg till länk finns på betalningsfliken. Expandera fliken Betalning om den är komprimerad.  
14. Välj betalningsmetod.
    * Välj betalningsmetoden kontant för den här proceduren.  
15. Stäng sidan.
16. Ange belopp.
    * För den här proceduren, ange ett belopp lika med ordersaldot som kan visas på sammanfattningssidan för försäljningsorder till vänster om beloppsfältet. Detta gör att du slutför ordern som helt betald.  
17. Klicka på OK.
18. Klicka på Skicka.

