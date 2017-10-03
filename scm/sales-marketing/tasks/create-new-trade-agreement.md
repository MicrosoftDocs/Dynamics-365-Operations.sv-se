--- 
title: Skapa ett nytt handelsavtal
description: "I den här proceduren visas hur du skapar ett handelsavtal där du registrerar ett nytt produktförsäljningspris som du har avtalat med en viss kund."
author: omulvad
manager: AnnBe
ms.date: 11/11/2016
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 1178c7a5db129801f83afa8b4caf9357ccf76b71
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-new-trade-agreement"></a>Skapa ett nytt handelsavtal

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar ett handelsavtal där du registrerar ett nytt produktförsäljningspris som du har avtalat med en viss kund. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Om du använder dina egna data måste du se till att det finns ett namn på handelsavtalsjournalen där standardrelationen har angetts till "Pris (försäljning)" innan du startar den här guiden.


## <a name="create-and-post-a-new-trade-agreement-journal"></a>Skapa och bokför en ny handelsavtalsjournal.
1. Gå till försäljning och marknadsföring > Priser och rabatter > Handel journaler.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Klicka på Rader.
7. Välj "Tabell" i fältet Kontokod.
    * I det här exemplet uppdaterar du priset för en viss kund, vilket innebär att du måste välja Tabell. Om du har uppdaterat produktens listpris, du vill markera alla, så att det nya priset är giltigt för alla kunder. Om du differentiera priser mellan olika kundsegment, då skulle du välja grupp. Du måste ha ställt in Kundprisgrupper för att välja Grupp.  
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kontomarkering.
9. Hitta och markera önskad post i listan.
10. Välj "Tabell" i fältet Artikelkod.
    * När du anger ett handelsavtal av typen "Pris (försäljning)" behöver du bara välja "Tabell" i fältet Artikelkod. Detta beror på att ett pris är ett absolut värde och kan inte vara samma för alla produkter eller en grupp av produkter.  
11. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelrelation.
12. I listan väljer du vilken produkt som du vill inkludera i avtalet.
    * Gör en notering för vilken produkt du har valt.  
13. Klicka på länken på den valda raden i listan.
14. Ange en minsta kvantitet i fältet Från.
    * Om kunden måste beställa en minimikvantitet innan de är berättigade till det nya priset, så måste du ange den kvantiteten här.  
    * Ange ett värde i fältet Till för att ange den högsta kvantitet över vilken avtalets pris inte kommer att gälla. Om du erbjuder priser och rabatter baserat på flera kvantitetsavbrott anger du sedan varje kvantitetshakparentes som ett par av minsta och högsta kvantitet i fälten "Från" respektive "Till".  
15. Ange ett pris i fältet Belopp i valuta.
16. Ange ett datum från vilket det här avtalet kommer att gälla i fältet Från.
17. Klicka på Spara.
18. Klicka på Validera.
19. Klicka på Validera markerade rader.
20. Klicka på OK.
21. Klicka på Bokför.
22. Klicka på OK.

## <a name="view-trade-agreements-for-a-product"></a>Visa handelsavtal för en produkt.
1. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
2. Hitta och markera den produkt vars pris du precis har uppdaterat.
3. Klicka på Sälj i åtgärdsfönstret.
4. Klicka på Visa handelsavtal.
    * Granska informationen i prishandelsavtalet som du precis har skapat.    
5. Stäng sidan.


