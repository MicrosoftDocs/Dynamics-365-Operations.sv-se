--- 
title: "Tilldela en mall för fritextfaktura till en kund"
description: Denna uppgift visar hur du tilldelar en fritextfakturamall till en kund.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3bcb59c6edd04877dc2a052002be513205ae840a
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>Tilldela en mall för fritextfaktura till en kund

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Denna uppgift visar hur du tilldelar en fritextfakturamall till en kund. I denna uppgift används USMF-demonstrationsföretaget och är avsett för den användare som ansvarar för hantering och bearbetning av kundreskontrafakturor.

1. Gå till Leverantörsreskontra > Kunder > Alla kunder.
2. Hitta och markera önskad post i listan.
3. Klicka på Faktura i åtgärdsfönstret.
4. Klicka på återkommande fakturor.
    * Använd den här sidan för att tilldela fritextfakturamallar till kunder och ange hur ofta fakturor ska skickas till kunden.  
5. Klicka på Nytt för att tilldela en ny mall till kunden.
6. Välj den fritextfakturamall som du vill tilldela till kunden.
7. Hitta och markera önskad post i listan.
8. Klicka på länken på den valda raden i listan.
9. Ange datumet när den första fakturan ska skapas.
    * Ange ett återkommande slutdatum.  
    * Välj något av följande: Inget slutdatum – Fakturor skapas utan tidsgräns tills mallen tas bort från kundkontot.  Faktureringsslutdatum – Välj det här alternativet för att ange för att ange det senaste datum då fakturan kan genereras.  
    * Maximalt ackumulerat belopp vid vilket skapandet av fakturor kommer att upphöra.  
    * Ange det maximala ackumulerade belopp som kan uppnås med den valda mallen. Om du till exempel anger 1 000,00 och genererar månatliga fakturor för 100,00 styck, kommer fakturor att upphöra att skapas efter att den tionde fakturan har genererats.  
    * Generera återkommande fakturor genom att använda förvalda värden antingen från sidan fritextfakturamall eller kundkontot.  
    * Välj om du vill använda fritextfakturamallen eller kundkontot för att bestämma standardvärdena för språk, bokföringsprofil, momsgrupp, artikelmomsgrupp, listkod, land/region för leveransen, valuta, betalningsvillkor, betalningsmetod, betalningsspecifikationer, betalningsplan, kassarabatt, ekonomiska dimensioner och gireringsblankett när fakturor skapas.  
10. Välj upprepningsmönstret.
    * Dagligen – Ange det här alternativet och ange antalet dagar i fältet Per. Om du till exempel anger 15, kommer en faktura skapas var 15:e dag för den här kunden.  Varje vecka - Välj det här alternativet och ange antalet veckor i fältet Per. Om du till exempel anger 2, kommer en faktura skapas varannan vecka för den här kunden.  Varje månad - Välj det här alternativet och ange antalet månader i fältet Per. Om du till exempel anger 6, kommer en faktura skapas var sjätte månad för den här kunden.  Årligen - Välj det här alternativet och ange antalet år i fältet Per. Om du till exempel anger 2, kommer en faktura skapas vartannat år för den här kunden.  
11. Ange ett tal i fältet Per.


