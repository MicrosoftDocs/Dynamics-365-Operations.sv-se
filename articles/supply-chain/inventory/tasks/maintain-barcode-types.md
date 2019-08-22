---
title: Underhålla streckkodstyper
description: I den här proceduren visas hur du ställer in en ny streckkoddefinition som sedan kan användas som en del av plocklistarapporten.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0551784ff55f5dc05fbe92ee354316eb04d755cb
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845476"
---
# <a name="maintain-barcode-types"></a>Underhålla streckkodstyper

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

