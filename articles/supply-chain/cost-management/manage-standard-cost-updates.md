---
title: Hantera standardkostnadsuppdateringar
description: Uppdateringar för standardkostnadsdata kan hanteras genom att använda två olika sätt - med en version eller två versioner.
author: AndersGirke
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: fc4ae40e9740ce76e79b76c2bff2c690568abff2
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500608"
---
# <a name="manage-standard-cost-updates"></a>Hantera standardkostnadsuppdateringar

[!include [banner](../includes/banner.md)]

Uppdateringar för standardkostnadsdata kan hanteras genom att använda två olika sätt - med en version eller två versioner.

I enversionssättet används en enda kostnadsversion som innehåller alla kostnadsposter. Dessa poster inkluderar de ursprungliga kostnaderna och alla kostnadsuppdateringar.

I tvåversionssättet används en version som innehåller uppgifter om de ursprungliga kostnaderna och en andra version, som innehåller registreringar av alla kostnadsuppdateringar. En viktig fördel med tvåversionssättet är den tydliga avbildningen och spårningen av kostnadsuppdateringar i en separat kostnadsversion, utan att den ursprungliga kostnadsversionen påverkas. Använd tvåversionssättet när du vill identifiera flera stegvisa uppdateringar, där varje stegvis uppdatering har en separat kostnadsversion som innehåller de stegvisa kostnadsposterna.

## <a name="example"></a>Exempel

Följande exempel visas hur enversionssättet och tvåversionssättet kan användas för att uppdatera standardkostnader i en tillverkningsmiljö. Till exempel uppdateringar som återspeglar nya artiklar eller felkorrigeringar. Anta att en enda kostnadsversion representerar standardkostnaderna för innevarande år. ID för den här versionen är 2020-STD. Versionen 2020-STD innehåller de aktuella aktiva kostnaderna för alla artiklar. Den innehåller dessutom alla flödesrelaterade kostnadskategorier och formler för omkostnadsberäkningar kända vid ingången av år 2020. 2020-STD är den ursprungliga kostnadsversionen.

- **Enversionssättet för uppdatering av kostnadsdata** − Enversionssättet innebär att den ursprungliga kostnadsversionen 2020-STD innehåller alla kostnadsposter. Kostnadsuppdateringar registreras i 2020-STD och ställs in till statusen "Väntande". Väntande kostnader kan anges manuellt för nya inköpta artiklar, eller så kan de beräknas för en tillverkad artikel för att återspegla korrigeringar. Strukturlisteberäkningarna med enversionssättet behöver inte ha någon reservdatakälla, eftersom alla aktiva kostnader finns inom samma kostnadsversion. När de väntande kostnaderna har aktiverats kommer den ursprungliga kostnadsversionen 2020-STD återigen att innehålla alla aktuella aktiva kostnader.
- **Tvåversionssättet på kostnadsuppdateringar** − Ttvåversionssättet kräver ytterligare en kostnadsversion, som bara innehåller de uppdateringarna kostnadsredovisning. ID för den här versionen är 2020-STD-CHANGES. Kostnadsuppdateringar registreras i 2020-STD-CHANGES och ställs in till statusen "Väntande". Med tvåversionssättet kräver strukturlisteberäkningar av väntande kostnader för tillverkade artiklar en reservdatakälla. Detta beror på att den ytterligare kostnadsversionen 2020-STD-CHANGES innehåller endast en delmängd av kostnadsdata. Reservutvägen kan uttryckas som de aktiva kostnaderna, eller som kostnadsversionen 2020-STD, eftersom båda identifierar källan för kostnadsdata när den inte inkluderas i 2020-STD-CHANGES. När de väntande kostnaderna har blivit aktiva, ska kostnadsversionen 2020-STD-CHANGES innehåller den aktuella aktiva kostnader som återspeglar uppdateringar, medan den ursprungliga kostnadsversionen 2020-STD ska vara orörd. När tvåversionssättet används kommer spärrningsprinciper för den ursprungliga kostnadsversionen ställas in för att förhindra uppdateringar. Identiska spärrningsprinciper ska ställas in för den ytterligare kostnadsversionen, med undantag för det angivna från-datumet och den selektiva användningen av spärrningsprinciper som tillåter uppdateringar. Angivet fråndatum ska uppdateras med varje grupp med ändringar för att återspegla det schemalagda aktiveringsdatumet.

Detta exempel använde en extra kostnadsversion för hantering av uppdateringar under hela år 2020. Mer än en extra kostnadsversion kan användas, till exempel en separat version för varje uppdateringsbatch. När fler än en ytterligare kostnadsredovisning används, måste reserven uttryckas som de aktiva kostnaderna, eftersom de aktiva kostnaderna fördelas över flera kostnadsversioner.

## <a name="financial-dimensions-for-the-standard-cost-revaluation"></a>Ekonomiska dimensioner för omvärdering av standardkostnad

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

Att aktivera ett nytt standardpris omvärderar vanligtvis det aktuella lagervärdet genom transaktioner för omvärdering av standardkostnad. Vanligtvis bokförs de ekonomiska dimensionerna för artikeln sedan på transaktionerna. Om du däremot skulle vilja styra om och hur de ekonomiska dimensionerna bokförs använder du [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera funktionen med namnet *Alternativ som används som standard i ekonomiska dimensioner för omvärdering av standardkostnad för lager*. När du har aktiverat den här funktionen går du till **Kostnadshantering > Policyinställningar för lagerredovisning > Parametrar** och anger den nya listrutan **Ursprunget till den ekonomiska dimensionen** till ett av följande värden:

- **Inga** – inga ekonomiska dimensioner bokförs för transaktioner för omräkning. Om in kontostruktur omfattar en obligatorisk ekonomisk dimension i din kontostruktur, körs omvärderingsprocessen fortfarande men kommer att skapa redovisningsposter som saknar ekonomiska dimensioner. I så fall får användarna ett varningsmeddelande först, så att de kan avbryta omvärderingen om det behövs.
- **Tabell**  – De ekonomiska dimensionerna för artikeln sedan på transaktionerna för omräkning. Detta är standardinställningen och överensstämmer med det ursprungliga systembeteendet utan att funktionen *Alternativ som används som standard i ekonomiska dimensioner för omvärdering av standardkostnad för lager*.
- **Bokföring** – De ekonomiska dimensionerna för transaktionen som omvärderas bokförs i transaktioner för omräkning. Som standard kommer de ekonomiska dimensionerna från den ursprungliga transaktionens lagerkonto att användas för både lagerkontot och omvärderingskontot.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]