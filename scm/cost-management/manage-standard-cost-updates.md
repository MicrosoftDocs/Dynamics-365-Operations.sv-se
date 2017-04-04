---
title: Hantera uppdateringar av standardkostnad
description: "Uppdateringar av standardkostnader data kan hanteras med hjälp av två olika sätt – Enversionssättet- och två versioner."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 7e0f0817ff37c82ed98a51f10bcdde7e785a19a3
ms.lasthandoff: 03/31/2017


---

# <a name="manage-standard-cost-updates"></a>Hantera uppdateringar av standardkostnad

Uppdateringar av standardkostnader data kan hanteras med hjälp av två olika sätt – Enversionssättet- och två versioner. 

I enversionssättet används en enda kostnadsversion som innehåller alla kostnadsposter. Dessa poster inkluderar de ursprungliga kostnaderna och alla kostnadsuppdateringar.
I tvåversionssättet används en version som innehåller uppgifter om de ursprungliga kostnaderna och en andra version, som innehåller registreringar av alla kostnadsuppdateringar. En viktig fördel med tvåversionssättet är den tydliga avbildningen och spårningen av kostnadsuppdateringar i en separat kostnadsversion, utan att den ursprungliga kostnadsversionen påverkas. Använd tvåversionssättet när du vill identifiera flera stegvisa uppdateringar, där varje stegvis uppdatering har en separat kostnadsversion som innehåller de stegvisa kostnadsposterna. **Exempel** Följande exempel visas hur enversionssättet och tvåversionssättet kan användas för att uppdatera standardkostnader i en tillverkningsmiljö. Till exempel uppdateringar som återspeglar nya artiklar eller felkorrigeringar. Anta att en enda kostnadsversion representerar standardkostnaderna för innevarande år. ID för den här versionen är 2016-STD. Versionen 2016-STD innehåller de aktuella aktiva kostnaderna för alla artiklar. Dessutom innehåller alla flödesrelaterade kostnadskategorier och beräkningsformler av tillverkningsomkostnader som är kända vid ingången av år 2016. 2016 STD är den ursprungliga kostnadsversionen.
-   **Enversionssättet för uppdatering av kostnadsdata** − Enversionssättet innebär att den ursprungliga kostnadsversionen 2016-STD innehåller alla kostnadsposter. Kostnad uppdateringar registreras i 2016 STD och ställs till statusen "Väntande". Väntande kostnader kan anges manuellt för nya inköpta artiklar eller ska beräknas för en tillverkad artikel att återspegla korrigeringar. När Enversionssättet används kräver strukturlisteberäkningarna inte en reservprincip datakälla eftersom alla aktiva kostnader finns i kostnadsversionen. När de väntande kostnaderna har aktiverats kommer den ursprungliga kostnadsversionen 2016-STD återigen att innehålla alla aktuella aktiva kostnader.
-   **Tvåversionssättet på kostnadsuppdateringar** − Ttvåversionssättet kräver ytterligare en kostnadsversion, som bara innehåller de uppdateringarna kostnadsredovisning. ID för den här versionen är 2016-STD-CHANGES. Kostnaduppdateringar registreras i 2016-STD-CHANGES och anges till statusen "väntande". Med tvåversionssättet kräver strukturlisteberäkningarna av väntande kostnader för tillverkade artiklar en reservutvägdatakälla. Detta beror på att den ytterligare kostnadsversionen 2016-STD-CHANGES innehåller endast en delmängd av kostnadsdata. Reservutvägen kan uttryckas som de aktiva kostnaderna, eller som kostnadsversionen 2016-STD, eftersom båda identifierar källan för kostnadsdata när den inte inkluderas i 2016-STD-CHANGES. När de väntande kostnaderna har blivit aktiva ska 2016-STD-CHANGES-kostnadsversionen innehåller de aktuella aktiva kostnader som återspeglar uppdateringar, medan den ursprungliga kostnadsversionen 2016-STD ska vara orörd. När tvåversionssättet används, ska du spärra policyerna för den ursprungliga kostnadsversionen för att hindra uppdateringar. Identiska spärrningsprinciper ska ställas in för den ytterligare kostnadsversionen, med undantag för det angivna från-datumet och den selektiva användningen av spärrningsprinciper som tillåter uppdateringar. Angivet fråndatum ska uppdateras med varje grupp med ändringar för att återspegla det schemalagda aktiveringsdatumet.

I det här exemplet används en extra kostnadsversion för hantering av uppdateringar under hela året 2016. Fler än en extra kostnadsversion kan använda, till exempel en separat version för varje grupp med uppdateringar. När fler än en ytterligare kostnadsredovisning används, måste reserven uttryckas som de aktiva kostnaderna, eftersom de aktiva kostnaderna fördelas över flera kostnadsversioner.




