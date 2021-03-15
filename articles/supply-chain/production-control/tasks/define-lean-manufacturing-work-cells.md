---
title: Definiera arbetsgrupper för lean manufacturing
description: En arbetsgrupp är en viss form av resursgrupp som går att använda i lean manufacturing-aktiviteter.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, InventLocationIdLookup, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 96c65690b7d67bffc2cf09c4ea34c84755f8530a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001559"
---
# <a name="define-lean-manufacturing-work-cells"></a>Definiera arbetsgrupper för lean manufacturing

[!include [banner](../../includes/banner.md)]

En arbetsgrupp är en viss form av resursgrupp som går att använda i lean manufacturing-aktiviteter. Arbetsgrupper har platser för inleverans och utleverans och en kapacitetsdefinition som baseras på en produktionsflödesmodell. Mer grundläggande information om arbetsgrupper och kapacitetsberäkningar i lean manufacturing finns i dokumentationen om lean manufacturing. I proceduren används demonstrationsföretag USMF.


## <a name="create-a-work-cell"></a>Skapa en arbetsgrupp. 
1. Gå till Organisationsadministration > Resurser > Resursgrupper.
2. Klicka på Ny.
3. Skriv ett värde i fältet Resursgrupp.
    * Arbetsgrupps-id:t är vanligtvis en systematisk kod och måste vara unik för juridiska personen.  
4. Ange ett värde i fältet Beskrivning.
    * Beskrivningen innehåller namnet på arbetsgruppen.  
5. Öppna sökningen genom att klicka på listruteknappen i fältet Plats.
    * En arbetsgrupp finns på en viss plats. Både inleverans- och utleveranslagerstället och lagerplatsen måste finnas på platsen.  
6. Klicka på länken på den valda raden i listan.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Produktionsenhet.
8. Klicka på länken på den valda raden i listan.
    * Välj en produktionsenhet som arbetsgruppen tillhör.  
9. Markera kryssrutan Arbetsgrupp.
    * Om en resursgrupp ska kunna användas som en lean-arbetsgrupp måste kryssrutan Arbetsgrupp markeras.  Observera att egenskapen kan inte ändras när resursgruppen har skapats.  
10. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Inleveranslagerställe.
11. Klicka på länken på den valda raden i listan.
    * För redovisning och materialkontroll, fördelas materialet som mellanlagras på tillverkningsstället vanligtvis till ett visst virtuell lagerställe. Om du vill fylla på platserna med hjälp av lagerställearbete, måste de dock vara en del av det mottagande råvarulagerstället.  
12. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plats för inleverans.
13. Klicka på länken på den valda raden i listan.
    * Observera att för en processaktivitet, kan inleveransplatsen ersättas i allmänhet eller för en viss produkt eller produktvariant genom att plockningsaktiviteter definieras som matar in till processaktiviteten. Det går inte att id-nummerstyra inleveransplatserna för en arbetsgrupp.  
14. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Utleveranslagerställe.
15. Hitta och markera önskad post i listan.
    * I flera aktivitetsproduktionsflöden eller produktionsrader, är detta ofta inleveranslagerstället för nästa resursgrupp eller försäljnings- eller transitlager dit en produkt vanligen överförs efter produktionsprocessen. Kom ihåg att transport och även transportrapporteringen vanligen är slöseri när modeller för lean manufacturing-processer skapas.  
16. Klicka på länken på den valda raden i listan.
17. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Utleveransplats.
    * I ett produktionsflöde med flera processaktiviteter är detta ofta inleveransplatsen för nästa arbetsgrupp.  
18. Hitta och markera önskad post i listan.
19. Klicka på länken på den valda raden i listan.
20. Utöka eller komprimera avsnittet Åtgärd.
    * En körtidskategori måste anges om du vill aktivera kostnadsberäkning och kostnadsbearbetning i lean-kanban-jobb.  
21. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kategori för körtid.
22. Hitta och markera önskad post i listan.
    * Körtidskostnadskategorin används i standardkostnadsberäkningar och på kostnadskalkylering med automatisk lageravräkning.  
23. Klicka på länken på den valda raden i listan.
24. Utöka eller komprimera avsnittet Kalendrar.
25. Klicka på Lägg till.
26. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kalender.
27. Hitta och markera önskad post i listan.
    * Normalt använder arbetsgrupper på en viss plats samma arbetstidskalender. Om arbetsgrupper ska han separata arbetstider, kan du behöva skapa specifika arbetstidskalendrar för grupperna. Observera att kalendern ska ha en definierad standardarbetstid när den används till en lean-arbetsgrupp, eftersom kapacitetdefinitionen oftast är relaterad till standardarbetstiden för en arbetsdag.  
28. Klicka på länken på den valda raden i listan.
29. Expandera eller komprimera avsnittet Kapacitet för arbetsgrupp.
30. Klicka på Lägg till.
31. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Produktionsflödesmodell.
32. Hitta och markera önskad post i listan.
    * Detta kräver produktionsflödesmodelltypen Genomflöde för att visa definitionen av genomflödekapaciteten.  
33. Klicka på länken på den valda raden i listan.
34. Markera ett alternativ i fältet Kapacitetsperiod.
    * Alternativen omfattar: Standardarbetsdag – kapaciteten uttrycks i längden på standardarbetsdagen i arbetstidskalendern för arbetsgruppen. För varje dag bestäms den verkliga arbetstiden i kalendern och den gällande tillgängliga kapaciteten beräknas baserat på det.   Vecka – tillåter en veckokapacitet. Ingen justering görs av den verkliga arbetstiden.   Månad – tillåter en månadskapacitet. Ingen justering görs av den verkliga kapaciteten.   Vanligtvis används standardarbetsdagen för dagliga perioder, och veckokapaciteten används för veckokapacitetsperioder.  
35. Ange ett värde i fältet Genomsnittlig genomflödeskvantitet.
    * Observera att en lean-operation aldrig ställs in för den högsta möjliga kapaciteten i en ideal miljö. Istället ska kapaciteten alltid definieras för operationer som körs under normala omständigheter.  
36. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Enhet.
37. Klicka på länken på den valda raden i listan.
38. ResolveChanges enheten.

## <a name="add-a-financial-dimension"></a>Lägga till en ekonomisk dimension
1. Expandera eller komprimera avsnittet Ekonomiska dimensioner.
    * Observera att de ekonomiska dimensioner som anges i produktionsflödet ersätter den ekonomiska dimensionen i en viss arbetsgrupp.    Vilka ekonomiska dimensionerna som går att välja beror på de ekonomiska dimensionernas konfiguration i systemet. Nedanstående steg motsvarar datauppsättningen i demoföretaget USMF. Om du använder andra uppgifter kanske inte stegen stämmer.  
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet CostCenter.
3. Hitta och markera önskad post i listan.
    * Dimensionerna som måste markeras i lean-arbetsgrupper, beror på implementeringen av ekonomiska dimensioner i redovisningsmodellen för en viss juridisk person.  
4. Klicka på länken på den valda raden i listan.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet ItemGroup.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.

## <a name="save"></a>Spara
1. Klicka på Spara.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]