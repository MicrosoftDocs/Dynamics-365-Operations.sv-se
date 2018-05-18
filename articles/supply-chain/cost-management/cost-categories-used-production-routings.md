---
title: "Kostnadskategorier som används i produktionsflöden"
description: "Den här artikeln innehåller information om kostnadskategorier som används i de tillverkningsmiljöer som använder flöden."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjCategory, RouteCostCategoryPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 78153
ms.assetid: a3fdc76c-0a27-4723-b1c7-4322f707d89e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 53e038183a10b8732a9a5e0f25aac440c224400e
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="cost-categories-used-in-production-routing"></a>Kostnadskategorier som används i produktionsflöden

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller information om kostnadskategorier som används i de tillverkningsmiljöer som använder flöden.

Kostnadskategorier används i de tillverkningsmiljöer där flöden används. De tilldelas verksamhetsresurser och flödesoperationer för definiering av timkostnader och segmenteringskostnadsbidrag i en tillverkad artikels beräknade kostnader. De kostnadsgrupper som tilldelas kostnadskategorier klassificerar tillverkningskostnadsbidrag baserat på verksamhetsresurserna och typ av aktivitet, till exempel ställ- och körtid. Nivån av kostnadsgruppstilldelningar utgör grunden för beräkning av tillverkningsomkostnader som baseras på flödesinformation. 

**Obs!** Kostnadskategorier har flera andra namn i tillverkningsmiljöer, till exempel arbetstariffkoder och maskintariffkoder. 

Varje kostnadskategori har associerade kostnadsposter och en tilldelad kostnadsgrupp. Olika kostnadskategorier krävs för olika tillverkningssyften.

-   Tilldela olika timkostnader, beroende på verksamhetsresursen. Kostnaderna kan till exempel skilja sig mellan olika typer av färdigheter, maskiner eller tillverkningsceller.
-   Tilldela olika timkostnader för den ställtid eller körtid som associeras med en flödesoperation.
-   Tilldela verksamhetsresurskostnader baserat på utleveranskvantitet i stället för timkostnader, till exempel ackord för betalning av arbete.
-   Tillhandahåll kostnadsgruppssegmentering för kostnadsbidrag för en tillverkad artikels beräknade kostnad. Du kan till exempel segmentera arbets- och maskinkostnader.
-   Ange kostnadsgruppsunderlaget för beräkningsformler för omkostnader, till exempel formler för arbetsrelaterade eller maskinrelaterade omkostnader som relateras till ställ- och körtid.

En kostnadskategori kan tilldelas ställtiden, processtiden och kvantiteten för en flödesoperation. När till exempel kostnader eller kostnadsgruppssegmenteringen är olika för ställtid och processtid, ska olika kostnadskategorier definieras och tilldelas ställtiden och processtiden. Den selektiva användningen av kostnadskategorier för ställtid, processtid och kvantitet fastställs av flödesgruppen som tilldelas en operation. Tilldelningen av kostnadskategorier till tid och kvantitet kan bestämmas utifrån företagsomfattande principer som definieras på sidan **Produktionskontrollparametrar**. 

Varje kostnadskategori har associerade kostnader som baseras på definitionen av kostnadsposter i en kostnadsversion. Använd **Kostnadskategoripris**-sidan för att definiera kostnadsposter för en angiven kostnadsredovisningsversion och plats. När kostnadsposten för en kostnadskategori först anges får den statusen **Väntande** och ett tänkt giltighetsdatum. När kostnadsposten aktiveras uppdateras statusvärdet till **För tillfället aktiva** och giltighetsdatumet uppdateras till aktiveringsdatumet. Olika artikelkostnadsposter kan återspegla olika platser, giltighetsdatum eller statusar. Strukturlisteberäkningar för ett framtida eller historiskt datum använder kostnadsposter som har det relevanta giltighetsdatumet. Den aktuella aktiva kostnadsposten används för uppskattning av tillverkningsorderkostnader och värdering av rapporterad tid jämfört med en tillverkningsorder. 

Kostnadsposten för en kostnadskategori kan vara platsspecifik eller gälla för hela företaget. Kostnadsposten blir platsspecifik om du tilldelar en plats till den. Ett tomt värde indikerar annars att kostnadsposten används på alla platser i företaget. Eftersom kostnaderna kan skilja sig mellan olika platser måste till exempel kostnadsposterna definieras som platsspecifika. 

En flödesoperation ärver generellt sett kostnadskategorierna som tilldelas verksamhetsresursen eller huvudoperationen. När du skapar en tillverkningsorder återspeglar flödesoperationerna i produktionsflödet den valda flödesversionen. Du kan åsidosätta kostnadskategorierna som tilldelas operationerna i produktionsflödet. 

Vissa typer av produktionsarbete kan gälla för projekttidsuppskattningar och rapportering. I det här fallet krävs en kostnadskategori för produktions- och projektandamål. Du måste definiera ytterligare projektrelaterad information när en kostnadskategori flaggas för användning i projekt.




