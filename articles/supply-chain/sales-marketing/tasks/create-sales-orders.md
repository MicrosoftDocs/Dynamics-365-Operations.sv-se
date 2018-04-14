--- 
title: "Skapa försäljningsorder"
description: "Den här proceduren visar hur du skapar en försäljningsorder."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4ccd2c4ace41f07dce14498031e3cc29ecb61b1c
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-sales-orders"></a>Skapa försäljningsorder

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du skapar en försäljningsorder. Du kan köra den här proceduren i demonstrationsdataföretaget USMF. Försäljningsorder skapas vanligtvis av en försäljningsorderprocessor. 




## <a name="enter-sales-order-header-details"></a>Ange huvuddetaljer för försäljningsorder
1. Gå till försäljning och marknadsföring > beställningar > Alla beställningar.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.
4. Hitta och markera kundposten i listan.
    * I det här exemplet väljer du kundknummer US-004.  
5. Klicka på länken på den valda raden i listan.
6. Klicka på OK.

## <a name="enter-sales-order-line-details"></a>Ange raddetaljer för försäljningsorder
    * Produkterna som säljs av din organisation kan levereras i varianter beroende på dimension, till exempel konfiguration, färg, storlek och utföranden. Produkter som kan ställas in för användning lagring dimensioner, såsom site, lager och pall och lagringsplatsen dimensioner, som parti- och serienummer. När dessa dimensioner har tilldelats måste du välja värden för dessa dimensioner på orderraden. Om du vill förbättra orderregistreringseffektivitet kan du lägga till respektive dimensionsfält i orderrutnätet.  
1. Klicka på Försäljningsorderrad.
2. Klicka på Dimensioner.
    * Välj dimensionerna Färg, Plats och Lagerställe i det här exemplet. De dimensioner som du väljer här kommer att visas i försäljningen för raster. Om du vill behålla dina val, ange alternativet Spara inställningarna som Ja.   
3. Klicka på OK.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
5. I det här exemplet väljer du artikelnummer T0004.
6. Klicka på länken på den valda raden i listan.
    * Om artikeln är en del av en försäljningkategori visas artikelnamnet automatiskt i försäljningskategorifältet.  
    * Om produktdimensionsfältet redan innehåller ett värde är detta eftersom värdet har kopierats från produktposten där den har definierats som en standardproduktdimension. Du kan ändra standardvärdet när som helst.   
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Färg.
8. Hitta och markera önskad post i listan.
9. Klicka på länken på den valda raden i listan.
10. Ange ett tal i fältet Kvantitet.
    * Om artikeln säljs i olika enheter än när den köptes, producerades och lagrades, och en försäljningsenhet anges för produktposten, kommer detta värde att visas i fältet Enhet. Du kan ändra värdet när som helst.   
    * Om fältet Plats redan innehåller ett värde har värdet kopierats från orderrubriken eller från orderinställningarna som är kopplade till produkten. Du kan ändra värdet när som helst. Välj ett värde om fältet är tomt.   
    * Om enhetsprisfältet redan innehåller ett värde, har värdet kopierats från ett giltigt handelsavtal eller från produktposten. (Enhetspriset kan också komma från ett försäljningsavtal, men processen för att skapa försäljningsorder från försäljningsavtal skiljer sig från den som visas här.) Om fältet är tomt, anger du ett värde.   
    * Rabattfältet innehåller ett rabattbelopp per produktenhet. För att beräkna det totala radbeloppet rabattbelopp, rabatten värdet multipliceras med antal på raden.    Om rabatten redan finns ett värde i fältet värde har kopierats från en giltig handelsavtal. Om fältet är tomt och du vill ge kunden en radrabatt, ange ett värde.  
    * Rabattprocentfältet innehåller ett procentsats som det totala radbruttobeloppet ska minskas med.  Om fältet Rabattprocent innehåller redan ett värde, det var kopierat från ett giltigt handelsavtal. Om fältet är tomt och du vill ge kunden en radrabatt, ange ett värde.  
    * Nettobeloppsfältet innehåller ett värde som beräknas utifrån radens kvantitet och enhetspris som justeras med rabatter.  Du kan åsidosätta det beräknade värdet till ett annat.  

## <a name="review-the-order-totals"></a>Granska ordersummor
1. Klicka på Försäljningsorder i åtgärdsfönstret.
2. Klicka på Summor.
    * Summasidan visar information om hela ordern. Detta inkluderar delsummabeloppet som är summan av alla radnettobelopp justerat med eventuella radrabatter, det totala fakturabeloppet som är ett delsummabelopp justerat med eventuella ordernivårabatter, tillägg och moms, kundkreditgränsen med mera.  Fakturabeloppet är det belopp som ska visas på kundens fakturadokument.  
3. Klicka på OK.


