--- 
title: "Underhåll streckkodstyper"
description: "I den här proceduren visas hur du ställer in en ny streckkoddefinition som sedan kan användas som en del av plocklistarapporten."
author: perlynne
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 57ad3f2cb4f4a246af4d58001c6ef56c440b5431
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="maintain-bar-code-types"></a>Underhåll streckkodstyper

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du ställer in en ny streckkoddefinition som sedan kan användas som en del av plocklistarapporten. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data. Om du använder USMF, kan du använda exempelvärdena som visas. Dessa uppgifter utförs vanligtvis av en lagerchef.

1. Gå till Streckkoder.
2. Klicka på Ny.
3. Ange ett värde i fältet Streckkodsinställningar.
4. Ange ett värde i fältet Beskrivning.
5. Välj ett alternativ i fältet Streckkodstyp.
    * Om du använder USMF kan du välja Code 39.  
6. Ange ett värde i fältet Storlek.
7. Ange ett värde i fältet Maximal längd.
8. Klicka på Spara.
9. Stäng sidan.
10. Gå till parametrarna för hantering av lager och lagerstyrning.
11. Ange eller välj ett värde i fältet Streckkodsinställningar.
    * Välj den streckkodskonfiguration du skapade tidigare, men tänk på att streckkodformatet måste matcha formatet för den unika identifieraren för posttypen som används i processen. För exempelvis plockflöden ska streckkodformatet matcha formatet för plockflödereferensen, som vanligtvis är en nummerserie.  
12. Klicka på Spara.
13. Stäng sidan.


