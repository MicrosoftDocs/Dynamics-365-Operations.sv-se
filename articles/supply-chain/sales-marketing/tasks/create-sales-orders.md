---
title: Skapa försäljningsorder
description: Den här proceduren visar hur du skapar en försäljningsorder.
author: Henrikan
ms.date: 04/06/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, InventDimParmFixed, InventProductDimensionLookup, SalesTotals
audience: Application User, SalesTableDelete, SalesTableListPagePreviewPage, SalesUpdateRemain
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 462f47ab5d85665ed8132e5bfb6dd945c537c1ef
ms.sourcegitcommit: 4861ec2d3ae24cc9dd4ad3ac748fd05be3d80c70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2022
ms.locfileid: "8551736"
---
# <a name="create-sales-orders"></a>Skapa försäljningsorder

[!include [banner](../../includes/banner.md)]

Den här proceduren visar hur du skapar en försäljningsorder. Du kan köra den här proceduren i demonstrationsdataföretaget USMF. Försäljningsorder skapas vanligtvis av en försäljningsorderprocessor. 

## <a name="enter-sales-order-header-details"></a>Ange huvuddetaljer för försäljningsorder
1. Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Försäljningsorder > Alla försäljningsorder**.
2. Välj **Ny**.
3. På fältet **Kundkonto** klicka på knappen för att öppna sökning.
4. Hitta och markera kundposten i listan.
    - I det här exemplet väljer du kundknummer US-004.  
5. Välj **OK**.

## <a name="enter-sales-order-line-details"></a>Ange raddetaljer för försäljningsorder
    
Produkterna som säljs av din organisation kan levereras i varianter beroende på dimension, till exempel konfiguration, färg, storlek och utföranden. Produkter som kan ställas in för användning lagring dimensioner, såsom site, lager och pall och lagringsplatsen dimensioner, som parti- och serienummer. När dessa dimensioner har tilldelats måste du välja värden för dessa dimensioner på orderraden. Om du vill förbättra orderregistreringseffektivitet kan du lägga till respektive dimensionsfält i orderrutnätet.
    
1. Under avsnittet **Försäljningsorderrader**, välj **Försäljningsorderrader**.
2. Välj **dimensioner**
    
    Välj dimensionerna Färg, Plats och Lagerställe i det här exemplet. De dimensioner som du väljer här kommer att visas i försäljningen för raster. Om du vill behålla dina val, ange alternativet **Spara inställningarna** som Ja.
    
3. Välj **OK**.
4. På fält **Artikelnummer** klicka på nedrullningsbara knappen för att öppna sökningen.
5. I det här exemplet väljer du artikelnummer T0004.
    - Om artikeln är en del av en försäljningkategori visas artikelnamnet automatiskt i försäljningskategorifältet.  
    - Om produktdimensionsfältet redan innehåller ett värde är detta eftersom värdet har kopierats från produktposten där den har definierats som en standardproduktdimension. Du kan ändra standardvärdet när som helst.   
6. På fältet **Färg** klicka på nedrullningsbara knappen för att öppna sökning.
7. Hitta och markera önskad post i listan.
8. Ange ett nummer i fältet **Kvantitet**.
    - Om objektet säljs i olika enheter än när det är köpt, produceras och lagras, och en försäljningsenheter är inställd på produkten anteckna värdet visas i fältet **Enhet**. Du kan ändra värdet när som helst.   
    - Om fältet **Plats** redan innehåller ett värde värde kopierades från orderhuvudet eller från inställningar som är förknippade med produkten. Du kan ändra värdet när som helst. Välj ett värde om fältet är tomt.   
    - Om fältet **Enhetspris** redan innehåller ett värde, värdet har kopierats från en giltig handelsavtal, eller från produkten. (Enhetspriset kan också komma från ett försäljningsavtal, men processen för att skapa försäljningsorder från försäljningsavtal skiljer sig från den som visas här.) Om fältet är tomt, anger du ett värde.   
    - Fältet **Rabatt** innehåller ett rabattbelopp per producerad enhet. För att beräkna det totala radbeloppet rabattbelopp, rabatten värdet multipliceras med antal på raden. Om fältetb **Rabatt** redan finns ett värde i fältet värde har kopierats från en giltig handelsavtal. Om fältet är tomt och du vill ge kunden en radrabatt, ange ett värde.  
    - Fältet **Rabattprocent** innehåller ett procentvärde med vilket radens totala bruttobelopp minskas.  Om fältet **Rabattprocent** innehåller redan ett värde, det var kopierat från ett giltigt handelsavtal. Om fältet är tomt och du vill ge kunden en radrabatt, ange ett värde. 
    - I fältet **Nettobelopp** innehåller ett värde som beräknas baserat på linjens kvantitet och enhet pris justeras genom rabatter.  Du kan åsidosätta det beräknade värdet till ett annat.  

## <a name="review-the-order-totals"></a>Granska ordersummor
1. Klicka på **Försäljningsorder** i **åtgärdsfönstret**.
2. Välj **Summor**.
    
    Sidan med **summor** visar detaljer om hela ordern. Detta inkluderar delsummabeloppet som är summan av alla radnettobelopp justerat med eventuella radrabatter, det totala fakturabeloppet som är ett delsummabelopp justerat med eventuella ordernivårabatter, tillägg och moms, kundkreditgränsen med mera. Fakturabeloppet är det belopp som ska visas på kundens fakturadokument.  
    
3. Välj **OK**.

## <a name="sales-order-creation-performance-enhancement"></a>Prestandaförbättringar när försäljningsorder skapas
Den nya funktionen som introduceras i programversion 10.0.26 minskar det extra skapandet av poster för tabellerna **SourceDocumentHeader** och **SourceDocumentLine**. Prestandan förbättras och lagringsstorleken minskas eftersom dessa poster inte skapas. Dessa underliggande ramverksregister för källdokument används inte för försäljningsorder i produkten vid denna tidpunkt, och det finns inga planerade planer på att använda dem. Att aktivera den här funktionen betraktas som en säker ändring för att förbättra prestandan. 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
