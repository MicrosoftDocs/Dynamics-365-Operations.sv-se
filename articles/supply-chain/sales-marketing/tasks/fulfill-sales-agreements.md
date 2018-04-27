--- 
title: "Uppfyll försäljningsavtal"
description: "I den här proceduren visas hur du uppfyller ett försäljningsavtal genom att koppla försäljningsorder med det."
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
ms.openlocfilehash: f0894bf962c139c2e9e4c9f8d1589fd933afcedb
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="fulfill-sales-agreements"></a>Uppfyll försäljningsavtal

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du uppfyller ett försäljningsavtal genom att koppla försäljningsorder med det. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data. Innan du startar guiden ser du till att du har ett gällande försäljningsavtal av typen Utfästelse för produktvärde. Alternativt kan du köra den guiden som heter ”Skapa försäljningsavtal".  




## <a name="release-a-sales-order-from-the-agreement"></a>Frisläppa en försäljningsorder som avtalet
1. Gå till försäljning och marknadsföring > Försäljning avtal > försäljningsavtal.
2. I listan öppnar du avtalet som du vill släppa ordern mot.
3. Klicka på Försäljningsavtal i åtgärdsfönstret.
4. Klicka på Frisläpp order.
    * Som texten överst på sidan Skapa frisläppningsorder anger, skiljer sig uppgifterna som behövs på försäljningsorderraderna åt, beroende på om avtalet är baserat på kvantitet eller värde.  
    * Avtalet i den här guiden är av typen Utfästelse för produktvärde. Det är därför radavsnittet på den här sidan är tom. Om utfästelsen hade varit baserad på kvantitet, skulle radinformationen ha kopierats från avtalet.  
5. Klicka på Skapa.
    * Meddelandet informerar dig om att en försäljningsorder har skapats. Eftersom ordern inte innehåller några rader, måste du lägga till orderraddetaljer för att slutföra leveransprocessen.   
6. Stäng sidan.
7. Stäng sidan.
8. Gå till försäljning och marknadsföring > beställningar > Alla beställningar.
9. I listan letar du reda på ordern som har skapats som resultatet av orderfrisläppandet i föregående uppgift. Öppna ordern.
10. Klicka på Lägg till rad.
11. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
12. Ange eller välj artikeln som anges på det associerade försäljningsavtalet i fältet Artikelnummer.
13. Ange ett tal i fältet Kvantitet.
    * Se till att du anger en kvantitet som gör att nettovärdet är lägre än värdet i det associerade försäljningsavtalet.  
    * Observera att eftersom försäljningsordern är länkad till avtalet, gäller den förhandlade rabattprocenten orderraden.  
14. Klicka på Uppdatera rad.
15. Klicka på Kopplat.
    * På sidan Bifogat avtal visas id:t och villkoren för avtalet som raden har släppts från.  
16. Stäng sidan.
17. Klicka på Allmänt i åtgärdsfönstret.
18. Klicka på Bifogat försäljningsavtal.
19. Expandera avsnittet Radinformation.
20. Klicka på fliken Uppfyllelse.
    * Uppfyllelsefliken visar en sammanfattning av alla försäljningsorderrader som är kopplade till den här åtagandet och dess läge samt beloppet och kvantiteten som ännu inte har frisläppts.   
21. Stäng sidan.
22. Stäng sidan.
23. Stäng sidan.

## <a name="apply-sales-agreement-in-the-order-process"></a>Använda försäljningsavtal i orderprocessen
1. Gå till försäljning och marknadsföring > beställningar > Alla beställningar.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.
4. I listan väljer du den kund som anges i försäljningsavtalet.
5. Klicka på länken på den valda raden i listan.
6. Expandera avsnittet Allmänt.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Försäljningsavtals-ID.
8. Klicka på länken på den valda raden i listan.
9. Klicka på Ja.
10. Klicka på OK.
11. Markera vald rad i listan.
12. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
13. Ange eller välj artikeln som anges på det associerade försäljningsavtalet i fältet Artikelnummer.
14. Klicka på länken på den valda raden i listan.
15. Klicka på Spara.
16. Klicka på Plocka och packa i åtgärdsfönstret.
17. Klicka på Bokför följesedel.
18. Expandera avsnittet Parametrar.
19. Välj Ja i fältet Bokför.
20. Klicka på OK.
21. Klicka på OK.
22. Klicka på Allmänt i åtgärdsfönstret.
23. Klicka på Bifogat försäljningsavtal.
24. Klicka på fliken Uppfyllelse.


