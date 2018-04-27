---
title: Hantera standardkostnadsuppdateringar
description: "Uppdateringar för standardkostnadsdata kan hanteras genom att använda två olika sätt - med en version eller två versioner."
author: AndersGirke
manager: AnnBe
ms.date: 10/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b64d9e53736fd3b81ee997ed28ccfa62ed7e9ce6
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="manage-standard-cost-updates"></a>Hantera standardkostnadsuppdateringar

[!INCLUDE [banner](../includes/banner.md)]

Uppdateringar för standardkostnadsdata kan hanteras genom att använda två olika sätt - med en version eller två versioner. 

I enversionssättet används en enda kostnadsversion som innehåller alla kostnadsposter. Dessa poster inkluderar de ursprungliga kostnaderna och alla kostnadsuppdateringar.

I tvåversionssättet används en version som innehåller uppgifter om de ursprungliga kostnaderna och en andra version, som innehåller registreringar av alla kostnadsuppdateringar. En viktig fördel med tvåversionssättet är den tydliga avbildningen och spårningen av kostnadsuppdateringar i en separat kostnadsversion, utan att den ursprungliga kostnadsversionen påverkas. Använd tvåversionssättet när du vill identifiera flera stegvisa uppdateringar, där varje stegvis uppdatering har en separat kostnadsversion som innehåller de stegvisa kostnadsposterna. 

**Exempel** 

Följande exempel visas hur enversionssättet och tvåversionssättet kan användas för att uppdatera standardkostnader i en tillverkningsmiljö. Till exempel uppdateringar som återspeglar nya artiklar eller felkorrigeringar. Anta att en enda kostnadsversion representerar standardkostnaderna för innevarande år. ID för den här versionen är 2016-STD. Versionen 2016-STD innehåller de aktuella aktiva kostnaderna för alla artiklar. Den innehåller dessutom alla flödesrelaterade kostnadskategorier och formler för omkostnadsberäkningar kända vid ingången av år 2016. 2016-STD är den ursprungliga kostnadsversionen.

-   **Enversionssättet för uppdatering av kostnadsdata** − Enversionssättet innebär att den ursprungliga kostnadsversionen 2016-STD innehåller alla kostnadsposter. Kostnadsuppdateringar registreras i 2016-STD och ställs in till statusen "Väntande". Väntande kostnader kan anges manuellt för nya inköpta artiklar, eller så kan de beräknas för en tillverkad artikel för att återspegla korrigeringar. Strukturlisteberäkningarna med enversionssättet behöver inte ha någon reservdatakälla, eftersom alla aktiva kostnader finns inom samma kostnadsversion. När de väntande kostnaderna har aktiverats kommer den ursprungliga kostnadsversionen 2016-STD återigen att innehålla alla aktuella aktiva kostnader.
-   **Tvåversionssättet på kostnadsuppdateringar** − Ttvåversionssättet kräver ytterligare en kostnadsversion, som bara innehåller de uppdateringarna kostnadsredovisning. ID för den här versionen är 2016-STD-CHANGES. Kostnadsuppdateringar registreras i 2016-STD-CHANGES och ställs in till statusen "Väntande". Med tvåversionssättet kräver strukturlisteberäkningar av väntande kostnader för tillverkade artiklar en reservdatakälla. Detta beror på att den ytterligare kostnadsversionen 2016-STD-CHANGES innehåller endast en delmängd av kostnadsdata. Reservutvägen kan uttryckas som de aktiva kostnaderna, eller som kostnadsversionen 2016-STD, eftersom båda identifierar källan för kostnadsdata när den inte inkluderas i 2016-STD-CHANGES. När de väntande kostnaderna har blivit aktiva, ska kostnadsversionen 2016-STD-CHANGES innehåller den aktuella aktiva kostnader som återspeglar uppdateringar, medan den ursprungliga kostnadsversionen 2016-STD ska vara orörd. När tvåversionssättet används kommer spärrningsprinciper för den ursprungliga kostnadsversionen ställas in för att förhindra uppdateringar. Identiska spärrningsprinciper ska ställas in för den ytterligare kostnadsversionen, med undantag för det angivna från-datumet och den selektiva användningen av spärrningsprinciper som tillåter uppdateringar. Angivet fråndatum ska uppdateras med varje grupp med ändringar för att återspegla det schemalagda aktiveringsdatumet.

Detta exempel använde en extra kostnadsversion för hantering av uppdateringar under hela år 2016. Mer än en extra kostnadsversion kan användas, till exempel en separat version för varje uppdateringsbatch. När fler än en ytterligare kostnadsredovisning används, måste reserven uttryckas som de aktiva kostnaderna, eftersom de aktiva kostnaderna fördelas över flera kostnadsversioner.






