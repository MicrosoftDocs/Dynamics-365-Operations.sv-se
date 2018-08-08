--- 
title: "Mata in fakturadata i leverantörsreskontra genom att använda en leverantörsfaktura"
description: "Med den här guiden blir det enklare att skapa en leverantörsfaktura från en inköpsorder och visa resultaten för att matcha inköpsordern, inleverans och fakturan (trevägsmatchning)."
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 48535a283cbdfdc7343a20105b139c527cac85f4
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="key-invoice-data-into-accounts-payable-using-a-vendor-invoice"></a>Mata in fakturadata i leverantörsreskontra genom att använda en leverantörsfaktura

[!include [task guide banner](../../includes/task-guide-banner.md)]

Med den här guiden blir det enklare att skapa en leverantörsfaktura från en inköpsorder och visa resultaten för att matcha inköpsordern, inleverans och fakturan (trevägsmatchning).


## <a name="create-a-purchase-order"></a>Skapa en inköpsorder
1. Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.
4. Sök efter en leverantör att välja. Rulla nedåt till US-104, till exempel.
5. Välj leverantör US-104.
6. Klicka på OK.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
8. Välj en lagerartikel. I det här exemplet väljer du artikelnummer 1000.
9. Expandera eller dölj avsnittet Raddetaljer.
10. Klicka på fliken Inställningar.
    * Du kan åsidosätta matchningspolicyn om du vill använda ingen matchning, tvåvägsmatchning eller trevägsmatchning.  
11. Expandera eller dölj avsnittet Raddetaljer.
12. Klicka på Inköp i åtgärdsfönstret.
13. Klicka på Bekräfta.

## <a name="receive-the-products"></a>Ta emot produkterna
1. Klicka på Ta emot i åtgärdsfönstret.
2. Klicka på Produktinleverans.
3. Ange produktinleveransnumret i fältet Produktinleverans. Ange exempelvis PR123.
4. Klicka på OK när du vill bokföra produktinleveransen.
5. Stäng sidan.

## <a name="create-a-vendor-invoice"></a>Skapa en leverantörsfaktura
1. Gå till Leverantörsreskontra > Inköpsorder > Inköpsorder som tagits emot men inte fakturerats.
2. Välj inköpsordern som du skapat.
3. Klicka på Faktura i åtgärdsfönstret.
4. Klicka på faktura.
5. Ange fakturanumret i fältet Nummer.
6. Ange ett värde i fältet Fakturabeskrivning.
7. Ange ett datum i fältet Fakturadatum.
8. Ange 1200 i fältet Enhetspris.
9. Klicka på Lägg till rad.
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
11. Sök efter artikelnumret med installationavgiften i listan. Till exempel S0001
12. Välj artikelnumret med installationavgiften.
    * Notera att matchning inte har utförts sedan du utförde ändringarna.  
13. Klicka på Uppdatera matchningsstatus.
14. Klicka på Granska i åtgärdsfönstret.
15. Klicka på Matcha detaljer.
    * Den nya raden med tjänster behöver inte matchas, så statusen är fortfarande ”Inte utförd”.  
16. Välj produktinleveransen för lagerartikeln som du har fått.
    * Raden med produktinleveransen matchades, men det fanns en felmatchning av kvantiteten eller priset, så den misslyckades.  
17. Ange ett tal i fältet Enhetspris.
    * När nu priset per enhet matchar, uppdateras statusvärdet till Godkänt. Om din policy tillåter avvikelser, eller om matchningen bara är en varning, kan du fortfarande bokföra fakturan.  
18. Stäng sidan.
19. Klicka på Bokför.
20. Stäng formuläret.
    * Observera att inköpsordern inte längre registreras som mottagen men inte fakturerad.  


