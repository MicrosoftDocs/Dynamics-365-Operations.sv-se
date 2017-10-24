---
title: Hantera standardkostnadsuppdateringar
description: "Uppdateringar för standardkostnadsdata kan hanteras genom att använda två olika sätt: med en version eller två versioner."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4a87a12b914fd16e0478cc898c4d53dba0ba0ebe
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="manage-standard-cost-updates"></a>Hantera standardkostnadsuppdateringar

[!include[banner](../includes/banner.md)]


Uppdateringar för standardkostnadsdata kan hanteras genom att använda två olika sätt: med en version eller två versioner. 

I enversionssättet används en enda kostnadsversion som innehåller alla kostnadsposter. Dessa poster inkluderar de ursprungliga kostnaderna och alla kostnadsuppdateringar.
I tvåversionssättet används en version som innehåller uppgifter om de ursprungliga kostnaderna och en andra version, som innehåller registreringar av alla kostnadsuppdateringar. En viktig fördel med tvåversionssättet är den tydliga avbildningen och spårningen av kostnadsuppdateringar i en separat kostnadsversion, utan att den ursprungliga kostnadsversionen påverkas. Använd tvåversionssättet när du vill identifiera flera stegvisa uppdateringar, där varje stegvis uppdatering har en separat kostnadsversion som innehåller de stegvisa kostnadsposterna. **Exempel** Följande exempel visas hur enversionssättet och tvåversionssättet kan användas för att uppdatera standardkostnader i en tillverkningsmiljö. Till exempel uppdateringar som återspeglar nya artiklar eller felkorrigeringar. Anta att en enda kostnadsversion representerar standardkostnaderna för innevarande år. ID för den här versionen är 2016-STD. Versionen 2016-STD innehåller de aktuella aktiva kostnaderna för alla artiklar. Den innehåller dessutom alla flödesrelaterade kostnadskategorier och formler för omkostnadsberäkningar kända vid ingången av år 2016. 2016-STD är den ursprungliga kostnadsversionen.
-   **Enversionssättet för uppdatering av kostnadsdata** − Enversionssättet innebär att den ursprungliga kostnadsversionen 2016-STD innehåller alla kostnadsposter. Kostnadsuppdateringar registreras i 2016-STD och ställs in till statusen "Väntande". De väntande kostnaderna kan anges manuellt för nya inköpta artiklar, men de kan också beräknas för en tillverkad artikel för att återspegla korrigeringar. När enversionssättet används kräver inte strukturlisteberäkningarna någon reservutvägsdatakälla, detta eftersom alla aktiva kostnader finns i kostnadsversionen. När de väntande kostnaderna har aktiverats kommer den ursprungliga kostnadsversionen 2016-STD återigen att innehålla alla aktuella aktiva kostnader.
-   **Tvåversionssättet på kostnadsuppdateringar** − Ttvåversionssättet kräver ytterligare en kostnadsversion, som bara innehåller de uppdateringarna kostnadsredovisning. ID för den här versionen är 2016-STD-CHANGES. Kostnaduppdateringar registreras i 2016-STD-CHANGES och anges till statusen "väntande". Med tvåversionssättet kräver strukturlisteberäkningarna av väntande kostnader för tillverkade artiklar en reservutvägdatakälla. Detta beror på att den ytterligare kostnadsversionen 2016-STD-CHANGES innehåller endast en delmängd av kostnadsdata. Reservutvägen kan uttryckas som de aktiva kostnaderna, eller som kostnadsversionen 2016-STD, eftersom båda identifierar källan för kostnadsdata när den inte inkluderas i 2016-STD-CHANGES. När de väntande kostnaderna har blivit aktiva ska 2016-STD-CHANGES-kostnadsversionen innehåller de aktuella aktiva kostnader som återspeglar uppdateringar, medan den ursprungliga kostnadsversionen 2016-STD ska vara orörd. När tvåversionssättet används, ska du spärra policyerna för den ursprungliga kostnadsversionen för att hindra uppdateringar. Identiska spärrningsprinciper ska ställas in för den ytterligare kostnadsversionen, med undantag för det angivna från-datumet och den selektiva användningen av spärrningsprinciper som tillåter uppdateringar. Angivet fråndatum ska uppdateras med varje grupp med ändringar för att återspegla det schemalagda aktiveringsdatumet.

Detta exempel använde en extra kostnadsversion för hantering av uppdateringar under hela år 2016. Mer än en extra kostnadsversion kan användas, till exempel en separat version för varje uppdateringsbatch. När fler än en ytterligare kostnadsredovisning används, måste reserven uttryckas som de aktiva kostnaderna, eftersom de aktiva kostnaderna fördelas över flera kostnadsversioner.






