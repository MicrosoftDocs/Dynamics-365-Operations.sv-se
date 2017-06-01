---
title: "Bokföringsdefinitioner"
description: "Det här avsnittet innehåller information om bokföringsdefinitioner och hur du definierar och länkar dem. För bokföringstyper och dokument som stöds kan du använda bokföringsdefinitioner i stället för bokföringsprofiler för att klassificera huvudkontona och ekonomiska dimensioner på redovisningsposter."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: e1865a695a89ed0501f97189b542b3915a96bf08
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="posting-definitions"></a>Bokföringsdefinitioner

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om bokföringsdefinitioner och hur du definierar och länkar dem. För bokföringstyper och dokument som stöds kan du använda bokföringsdefinitioner i stället för bokföringsprofiler för att klassificera huvudkontona och ekonomiska dimensioner på redovisningsposter.

För bokföringstyper och dokument som stöds kan du använda bokföringsdefinitioner i stället för bokföringsprofiler för att klassificera huvudkontona och ekonomiska dimensioner på redovisningsposter. Du kan visa dokumenten och bokföringstyperna på sidan **Bokföringsdefinitioner för transaktioner**. 

Börja använda bokföringsdefinitionerna genom att välja **Använd bokföringsdefinitioner** på sidan **Allmänna huvudboksparametrar**. Även om du använder bokföringsdefinitioner måste du fortfarande definiera bokföringsprofiler för de ursprungliga posterna och bokföringstyper och dokument som inte stöds. 

Du måste använda bokföringsdefinitioner för att kunna aktivera inteckningsredovisning för inköpsorder och förinteckningsredovisning för inköpsrekvisitioner.

## <a name="defining-posting-definitions"></a>Definiera bokföringsdefinitioner
Använd sidan **Bokföringsdefinitioner** för att ange matchningsvillkoren och definiera de poster som ska genereras när en matchning inträffar. Matchningsvillkoren utvärderas för de ursprungliga posterna som redovisningsfördelningar. 

På sidan **Bokföringsdefinitioner** kan du också tilldela prioritetnummer till postrader för att styra ordningen som raderna utvärderas i. Raderna som har lägst prioritet utvärderas först. Exempelvis utvärderas alla rader som har prioriteten 1, sedan raderna med prioriteten 2 osv. När en matchning hittas ignoreras de andra matchvillkoren. Dessutom är det endast kriterierna i gruppen som matchar den ursprungliga transaktionen som resulterar i genererade poster. 

Du kan validera dina bokföringsdefinitioner med guiden **Testbokföringsdefinition**. När du har definierat ett prov från posten för en bokföringsdefinition visas de genererade posterna. 

Du kan använda bokföringsdefinitionsversioner tillsammans med giltighetsdatum. Du kan till exempel skapa en kommande version av en bokföringsdefinition när du vill bokföra på ett annat redovisningskonto i ett nytt räkenskapsår. 

Använd sidan **Bokföringsdefinitioner för transaktioner** för att koppla bokföringsdefinitioner till transaktionstyper.

## <a name="linking-posting-definitions"></a>Länka bokföringsdefinitioner
Du kan länka från en bokföringsdefinition till en annan när du skapar bokföringsdefinitioner. Villkoren för definitionen som du länkar till beaktas sedan tillsammans med villkoren för den aktuella bokföringsdefinitionen. Den här funktionen gör att du kan du spara tid, eftersom du inte behöver ange kriterier igen på snabbfliken **Poster** på sidan **Bokföringsdefinitioner** för den aktuella bokföringsdefinitionen, om du redan har angett raderna för en annan definition. 

Inkludera eventuella länkar som du kan använda i diagrammen eller registren. Undvik konflikter med den aktuella bokföringsdefinitionen genom att se till att raderna i alla bokföringsdefinitioner som du länkar är unika. 

Följande restriktioner gäller när du skapar länkar i bokföringsdefinitioner:

-   En bokföringsdefinition kan antingen länka till en annan bokföringsdefinition eller länkas till från en annan bokföringsdefinition, men inte båda. Du kan dock länka en bokföringsdefinition till flera bokföringsdefinitioner.
-   Du kan bara ställa in länkar mellan bokföringsdefinitioner som finns i samma modulen.
-   Du kan koppla en bokföringsdefinition till en valfri transaktionstyp, men transaktionstypen måste finnas i samma modul som bokföringsdefinitionen. Använd sidan **Bokföringsdefinitioner för transaktioner** för att se vilken modul en transaktionstyp finns i.


Mer information finns i [Exempel på bokföringsdefinitioner](example-posting-definitions.md). 



