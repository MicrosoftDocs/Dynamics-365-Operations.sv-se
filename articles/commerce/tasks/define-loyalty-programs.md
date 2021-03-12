---
title: " Definiera bonusprogram"
description: Den här proceduren visar hur du ställer in ett bonusprogram med två lojalitetnivåer.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a853287c0795057b09c429ea1c9ad5231e39a33
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972315"
---
# <a name="define-loyalty-programs"></a> Definiera bonusprogram

[!include [banner](../includes/banner.md)]

Den här proceduren visar hur du ställer in ett bonusprogram med två lojalitetnivåer. I proceduren används demonstrationsföretaget USRT.

1. Gå till Butik och handel > .. > Bonusprogram.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Ange ett värde i fältet Beskrivning.
5. Klicka på Lägg till rad.
6. Välj ett tal i fältet Nivå.
7. Ange ett namn för bonusnivån i fältet nivå.
8. Skriv ett värde i fältet Beskrivning.
9. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Datumintervall.
    * Detta datumintervall bör utvidgas i framtiden. Om till exempel det tidsintervall som valts för gold-nivån är en ettårsperiod, någon kund som kvalificerar sig för gold-nivån kan få belöningar som tilldelats gold-nivån för ett år. Om kunden kvalificerar sig igen för Guld-nivån medan de är på den nivån, utökas utgångsdatumet för denna status med ett år med start från det datum när de kvalificerar sig igen.  
10. Klicka på länken på den valda raden i listan.
11. Klicka på Lägg till rad.
12. Välj ett tal i fältet Nivå.
13. Ange ett namn för bonusnivån i fältet nivå.
14. Skriv ett värde i fältet Beskrivning.
15. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Datumintervall.
16. Klicka på länken på den valda raden i listan.
17. Klicka på Spara.
18. Hitta och markera önskad post i listan.
    * Nivåregler definierar minsta antalet belöningspoäng som måste tjänas in under en tidsperiod när du vill kvalificera dig för nivån.  
19. Växla expanderingen av avsnittet Skiktregler.
20. Klicka på Ny.
    * Du kan använda flera nivåregler för varje nivå. Du vill kanske ha tre olika kriterier för att tjäna in en nivå – genom att spendera 500 USD under en månad, genom att spendera 1 000 USD under ett år och genom att göra 20 transaktioner under ett år. Om du vill kunna genomföra detta måste du skapa tre nivåregler.  
21. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Belöningspoäng.
    * Det ska vara en ej inlösbar förmånsbelöningspoäng.  
22. Klicka på länken på den valda raden i listan.
23. Ange ett värde i fältet Lägsta antal utfärdade poäng.
    * Om du vill att alla kunder ska kunna bli medlemmar på den lägsta nivån anger du 0 (noll).  
24. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Intervall för bedömningsdatum.
    * Detta datumintervall bör utvidgas till det förgångna. Endast poäng som erhållits under detta datumintervall ska göra det möjligt att tillgodoräkna sig lägsta möjliga utlevererade poängvärde.  
25. Klicka på länken på den valda raden i listan.
26. Klicka på Spara.
27. Hitta och markera önskad post i listan.
28. Klicka på Ny.
29. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Belöningspoäng.
30. Klicka på länken på den valda raden i listan.
31. Ange ett värde i fältet Lägsta antal utfärdade poäng.
32. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Intervall för bedömningsdatum.
    * Det här datumintervallet bör utökas bakåt i tiden.  
33. Klicka på länken på den valda raden i listan.
34. Klicka på Spara.
35. Klicka på prisgrupper.
    * Om du vill ge förmånskunder rabatter. måste du tilldela en eller flera prisgrupper till bonusprogrammet och tilldela prisgrupperna till rabatter. Det är bästa praxis att inte blanda prisgrupper på olika typer av diskontering av enheter.  Använd till exempel inte samma prisgrupp för en lojalitetsrabatt och en kanalrabatt.  
36. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Prisgrupp.
    * Prisgrupperna länk överst på sidan är för lojalitetsprogram. Länken Prisgrupper på programnivåernas snabbflikar används endast för en specifik lojalitetsnivå.  
37. Klicka på länken på den valda raden i listan.
38. Klicka på Spara.
39. Stäng sidan.
40. Klicka på Spara.

