--- 
title: "Ange en fraktadress för en inomeuropeisk transaktion"
description: "I den här proceduren visas hur du anger en fraktadress för en transaktion för inomeuropeisk handel."
author: v-oloski
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: d2225f54af0d9f900cadda6b418221a5592fe2e6
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="specify-a-lading-address-for-an-intra-community-transaction"></a>Ange en fraktadress för en inomeuropeisk transaktion

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du anger en fraktadress för en transaktion för inomeuropeisk handel. Till exempel: Ett företag i Tyskland beställer artiklar från en leverantör med tysk företagsadress. Denna leverantör har ett lager i Italien och skickar artiklarna därifrån. Denna leverans måste visas i Intrastat. Samma förfarande gäller för kundreturer.
Den här proceduren gäller för alla europeiska länder/regioner. Uppgiften skapades med hjälp av demonstrationsdataföretaget DEMF, med primär adress i Tyskland. Innan du kan slutföra proceduren måste du konfigurera Intrastat-rapporteringen. Proceduren är avsedd för kamrerer. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.

1. Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.
2. Klicka på Ny.
3. Ange eller välj ett värde
    * Välj till exempel DE-001. Denna leverantör har en tysk företagsadress.  
4. Klicka på OK.
5. Markera vald rad i listan.
6. Ange eller välj värdet D0001 i fältet Item number.
7. Klicka på Spara.
8. Klicka på Ta emot i åtgärdsfönstret.
9. Klicka på Transportation details.
10. I fältet Loading date and time anger du datum och tid.
11. Klicka på Add address.
12. Klicka på New och skapa den nya adressen med syftet Lading.
13. Ange "Italian" i fältet Name or description.
14. Välj Lading som värde.
    * Observera att adress-syftet måste vara Lading.  
15. Ange eller välj värdet ITA i fältet Country/region.
16. Klicka på Spara.
17. Stäng sidan.
18. Klicka på Spara.
    * Kontrollera att fraktadressen är korrekt.  
19. Stäng sidan.
20. Klicka på Inköp i åtgärdsfönstret.
21. Klicka på Bekräfta.
22. Klicka på Faktura i åtgärdsfönstret.
23. Klicka på Faktura.
24. Ange ett värde i fältet Antal.
25. Ange ett datum i fältet Fakturadatum.
26. Klicka på Default from: Product receipt quantity för att öppna dialogrutan.
27. I fältet Default quantity for lines väljer du "Ordered quantity".
28. Klicka på OK.
29. Klicka på Transportation details.
    * Kontrollera att varorna skeppades från Italien. Vid behov kan du redigera fraktformationen.  
30. Stäng sidan.
31. Klicka på Bokför.
32. Stäng sidan.
33. Gå till Moms > Deklarationer > Utländsk handel > Intrastat.
34. Klicka på Överför.
35. Välj Yes i fältet Vendor invoice.
36. Klicka på OK.
37. Klicka på fliken Allmänt.
    * Sök efter en nyligen skapad rad och kontrollera att avsändaren skickade varorna från Italien.  


