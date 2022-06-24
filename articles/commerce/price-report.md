---
title: Prisrapporter för butik
description: Denna artikel innehåller en översikt över prisrapportfunktionen som kan användas för att visa kommande prisändringarna för de utvalda produkterna.
author: shajain
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 84025cf148e1b5a92b78593fc093c629a3af4764
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899051"
---
# <a name="retail-price-reports"></a>Prisrapporter för Retail

[!include [banner](includes/banner.md)]


För att kunna förse kunderna med konkurrenskraftiga priser ändrar återförsäljare ofta priserna på produkter. Butikschefer vill ha möjlighet att enkelt komma åt tidigare eller kommande prisändringar så att de kan planera för resurserna som krävs för att uppdatera prisetiketterna som visas på butikshyllorna. Med versionen 10.0 av Commerce kan butikschefen öppna rapporten **Pris** genom att gå till **Alla butiker \> Butik \> Prisrapport** och visa de uppdaterade priserna för produkter som är kopplade till butiken. 

För att aktivera prisrapporten måste parametern **Aktivera prisrapport för butik** vara aktiverad. Denna parameter finns på fliken **Handelsparametrar \> Rabatter \> Ddiverse**. När du öppnar sidan **Prisrapport** visas en dialogruta med olika konfigurationer. Nedan finns tillgängliga konfigurationer.

| Inställningar | beskrivning |
|---|---|
| Datum från/datum till| Datumintervallet som prisrapporten ska genereras för. Varaktigheten är för närvarande begränsad till 7 dagar. |
| Kanal| Butiken som prisrapporten ska genereras för. |
| Visa produkter med tillgängligt lager| Om detta anges till **Ja** visas priserna för produkter som för närvarande har fysiskt lager tillgängligt i butiken. |
| Visa priser för varianter | Om detta anges till **Ja** visas priser för varianterna tillsammans med produktmallarna. Detta bör endast aktiveras till **På** om du har variantspecifika priser eftersom antalet rader blir mycket stort. I framtida versioner kan vi aktivera dimensionsbaserade priser så att butikschefen kan välja dimensioner som priserna ska visas för. |
| Visa produkter med prisändringar | Om du anger detta till **Ja** visas priserna endast för de datum då priset har ändrats. Priset för *en dag före* det valda **från datumet** kommer alltid att visas, så att butikschefen enkelt kan identifiera de produkter som inte har ändrade priser under hela valda varaktigheten och kan också visa det aktuella priset. |

När rapporten har skapats kan Excel-filen hämtas för eventuella ytterligare filtreringsbehov. Prisrapporten kan också användas för att kontrollera historiska priser för produkter för tidigare datum.


[!INCLUDE[footer-include](../includes/footer-banner.md)]