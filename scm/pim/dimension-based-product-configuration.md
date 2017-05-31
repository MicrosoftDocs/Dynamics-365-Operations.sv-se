---
title: Dimensionsbaserad produktkonfiguration
description: "Dimensionsbaserad produktkonfigurering motsvarar en enda lösning för att skapa många produktvarianter från en enda produktmall och dess strukturlista."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d13fc55342030d96d38f264f6bff9586832b4ab5
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="dimension-based-product-configuration"></a>Dimensionsbaserad produktkonfiguration

[!include[banner](../includes/banner.md)]


Dimensionsbaserad produktkonfigurering motsvarar en enda lösning för att skapa många produktvarianter från en enda produktmall och dess strukturlista.

Dimensionsbaserad produktkonfiguration är en av de tre inbyggda teknikerna för produktkonfigurationer. De två andra teknikerna är fördefinierade varianter och begränsningsbaserad konfiguration. Alla tre teknikerna använder en produktmall som startpunkt och gör att användaren kan skapa många produktvarianter av en produktmall.

## <a name="key-concepts"></a>Viktiga begrepp
Dimensionsbaserad produktkonfiguration baseras på följande viktiga begrepp:

-   Produktmallar
-   Konfigurationsproduktdimension
-   Konfigurationsgrupper
-   Strukturlista
-   Konfigurationsflöde
-   Konfigurationsregler

### <a name="product-masters"></a>Produktmallar

En produktmall är startpunkten för alla produktkonfigurationer. Till den dimensionsbaserade produktkonfigurationen behöver du en produktmall med denna specifika konfigurationsteknik och en produktdimensionsgrupp som omfattar konfigurationsproduktdimensionen.

### <a name="configuration-product-dimension"></a>Konfigurationsproduktdimension

Konfigurationsproduktdimensionen används för att identifiera produktvarianter för en produktmall med den dimensionsbaserade konfigurationstekniken. Konfigurationsdimensionsvärdet anges av användaren och kan identifiera enskilda produktvarianter.

### <a name="configuration-groups"></a>Konfigurationsgrupper

Konfigurationsgrupper definieras i en central databas och kan användas för alla dimensionsbaserade produktkonfigurationsmodeller. Konfigurationsgrupper associeras till enskilda strukturlisterader och innehåller tillsammans en grupp med rader som är ömsesidigt uteslutande. Det innebär att det bara är en rad i en grupp som kan väljas för en enskild produktvariant.

### <a name="bill-of-materials-bom"></a>Strukturlista

Strukturlistan visar byggstenarna för en dimensionsbaserad produktkonfiguration. Den måste inkludera alla olika produkter som kan användas i en produktvariant. Varje rad i strukturlistan kan referera till en konfigurationsgrupp. Om en rad inte refererar till en konfigurationsgrupp, inkluderas den i alla produktvarianter.

### <a name="configuration-route"></a>Konfigurationsflöde

Konfigurationsflödet bestämmer ordningen på konfigurationsgrupperna som de visas för användaren under produktkonfigureringen.

### <a name="configuration-rules"></a>Konfigurationsregler

Konfigurationsreglerna representerar en mekanism för säkerställande av att en produkt som ingår i en konfigurationsgrupp i en strukturlista använder antingen ett inkludering eller ett uteslutande en produkt i en annan konfigurationsgrupp i samma strukturlista.

## <a name="product-modeling-process"></a>Produktmodellering
Den naturliga sekvensen för uppbyggnad av en produktmodell för en dimensionsbaserad produkt börjar med att definiera de relevanta konfigurationsgrupperna. Det är viktigt att se till att alla produkter som ska användas i strukturlistan har släppts till det företag som produktmodellen skapas för. Med de här byggblocken på plats kan användaren skapa strukturen och tilldela konfigurationsgrupper till alla relevanta strukturlisterader. Ett konfigurationsflöde kan definieras för att beställa konfigurationsgrupperna i rätt ordning när strukturlistan är klar. \[caption id="attachment\_282671" align="alignnone" width="1187"\][![Dimensionsbaserad process för produktmodellering](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Dimensionsbaserad process för produktmodellering\[/caption\] Om det finns vissa produkter från olika konfigurationsgrupper som antingen måste eller inte får användas tillsammans, så kan du skapa konfigureringsregler som framtvingar dessa produktförhållanden. När strukturlistan har bundits tillsammans med en dimensionsbaserad produktmall via en strukturlisteversion, och båda har godkänts och aktiverats, kan du skapa produktkonfigurationer och ett namn för varje konfiguration. Konfigurationerna kan definieras innan några transaktioner skapas, eller utföras när behovet av en viss konfiguration uppstår.

### <a name="suggested-use"></a>Möjliga användningsområden

Dimensionsbaserad konfigurationsteknik används främst till produkter med begränsade varianter och där kombinationer av produktdimensionerna storlek, färg, utförande och konfiguration inte passar till att identifiera en viss produktvariant. Ett exempel kan vara en cykel med ramhöjd, hjulstorlek, bromstyper och olika växlar.




