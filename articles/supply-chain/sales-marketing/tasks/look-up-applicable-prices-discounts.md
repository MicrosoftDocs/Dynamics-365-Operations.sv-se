---
title: Slå upp tillämpliga priser och rabatter
description: I den här proceduren visas hur du hittar pris och/eller rabatt för en produkt som för närvarande är giltig för en viss kund, utan att skapa en försäljningsorder.
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: debf66029d6efa42fe6d85eadb3866aadb312a97
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025838"
---
# <a name="look-up-applicable-prices-and-discounts"></a>Slå upp tillämpliga priser och rabatter

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du hittar pris och/eller rabatt för en produkt som för närvarande är giltig för en viss kund, utan att skapa en försäljningsorder. I proceduren går vi igenom ett visst exempel och du måste följa exemplet med hjälp av USMF-demonstrationsföretaget för att välja de nödvändiga värdena.


## <a name="find-the-applicable-price"></a>Sök efter det tillämpliga priset
1. Gå till försäljning och marknadsföring > Priser och rabatter > Sök priser.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.
3. Hitta och markera kunden US-001 i listan.
4. Klicka på länken på den valda raden i listan.
5. Skriv "T0004" i fältet Artikelnummer.
    * Som standard är fältet Kvantitet inställt på värdet 1. Men om du vet storleken av den order som kunden avser att placera för produkten i fråga och ange sedan värdet i stället. Den här informationen är bara relevant om handelsavtal med kunden ha kvantitet avbrott, dvs. produktens pris beror på den minsta kvantitet som kunden köpt.  
6. Ange ett datum för när kunden beräknar att göra en beställning i fältet Datum. 
    * Datumet kan vara dagens datum eller vilket datum som helst i framtiden.  
    * Systemet returnerar nu priset som gäller för den valda produkten när den köps av det valda kunden på det valda datumet med en angiven kvantitet. I detta exempel, om kunden oss-001 köpte 1 enhet av produkten T0004 idag, de skulle debiteras 350 CAD per enhet. Detta pris kommer från en befintlig och aktiv handel avtalet med kunden.      Andra fält på sidan innehåller mer information om produktpriset och produktkostnaden (om det har ställts in på produktmallen) och uppskattad vinst.  
    * Om alternativet Visa relaterade produktvarianter har valts innebär det att det finns ytterligare handelsavtal för produktvarianterna.  
7. Klicka på kryssrutan Visa relaterade produktvarianter.
    * En lista med produktvarianterna visas, med information om dimensionerna för dessa.  
8. Markera raden som representerar färgen Vit i listan.
    * Observera att produktpriset nu skiljer sig från det som tidigare visades när det inte har registrerats per dimension.  
9. Klicka på Visa försäljningspriser.
    * På sidan Pris (försäljning) visas alla handelsavtal som gäller för produkten, inklusive varianterna för denna.  
10. Stäng sidan.

## <a name="find-the-applicable-discount"></a>Sök efter den tillämpliga rabatten
Kontrollera att kundens konto innehåller kundnummer US-001    
1. Skriv "T0012" i fältet Artikelnummer.
    * Kontrollera att fältet Kvantitet har värdet 1.  
    * Följande prissättningsdetaljer som visas för produkten T0012, kommer från ett eller flera handelsavtal: Enhetspriset är 10,00 SEK och rabattprocenten är 5.  
2. Ställ in kvantiteten på 20.
    * Det ökade orderkvantiteten gör att radrabatten som ska erbjudas kunden ändras från 5 till 7 procent.  
    * Det totala nettobeloppet beräknas baserat på enhetspriset, rabatten och den totala kvantiteten.  
3. Klicka på Visa radrabatt.
    * Det finns två radrabattavtal för produkten T0012 som anger en rabatt på 5 procent för en orderradskvantitet från mellan 1 till 10 och 7 procents rabatt för orderkvantiteter över 10. Observera att rabatter gäller för en grupp produkter, i det här exemplet gruppkod 01, som produkten T0012 tillhör.  
4. Stäng sidan.

