---
title: Underhåll streckkodstyper
description: I den här proceduren visas hur du ställer in en ny streckkodsdefinition som sedan kan användas som en del av plocklistarapporten.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b689d1fc85d59ac87efa1903fd7122ae5ff011da
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571123"
---
# <a name="maintain-bar-code-types"></a>Underhåll streckkodstyper

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du ställer in en ny streckkodsdefinition som sedan kan användas som en del av plocklistarapporten. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data. Om du använder USMF, kan du använda exempelvärdena som visas. Dessa uppgifter utförs vanligtvis av en lagerchef.

1. Gå till **Streckkoder**.
1. Välj **Ny**.
1. I fältet **Streckkodsinställningar** anger du ett värde.
1. I fältet **Beskrivning** anger du ett värde.
1. Välj ett alternativ i fältet **Streckkodstyp**.
    * Om du använder USMF kan du välja Code 39.
1. I fältet **Mask-ID** anger du streckkodsmaskens ID. Streckkodsmasker används för att skapa streckkoder och snabbt identifiera streckkoder som skannas till kassasystemet. Mer information finns [i Ställa in streckkodsmasker](../../../commerce/set-up-bar-code-masks.md).
1. Ange ett nummer i fältet **Storlek**.
1. Ange ett värde i fältet **Maximal längd**.
1. Välj **Spara**.
1. Stäng sidan.
1. Gå till **Parametrar oför lager- och lagerstyrning**.
1. I fältet **Streckkodsinställningar** anger du eller väljer ett värde.
    * Välj den streckkodskonfiguration du skapade tidigare, men tänk på att streckkodformatet måste matcha formatet för den unika identifieraren för posttypen som används i processen. För exempelvis plockflöden ska streckkodformatet matcha formatet för plockflödereferensen, som vanligtvis är en nummerserie.  
1. Välj **Spara**.
1. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
